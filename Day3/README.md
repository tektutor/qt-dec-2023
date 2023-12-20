## Lab - QML State Machine

Your .pro file looks as shown below
![image](https://github.com/tektutor/qt-dec-2023/assets/12674043/35b44281-41f9-499f-b146-564da0072eca)

Your main.cpp looks as shown below
```
#include <QGuiApplication>
#include <QQmlApplicationEngine>

int main(int argc, char *argv[])
{
    QGuiApplication a(argc, argv);

    QQmlApplicationEngine engine;
    engine.load( QUrl(QStringLiteral("qrc:/main.qml")));

    return a.exec();
}
```

Create a main.qml with below code
<pre>
import QtQuick 2.15


Window {
    id: mainWindow

    width: 1000; height: 1000
    visible: true

    FirstScreen {}
}  
</pre>
![image](https://github.com/tektutor/qt-dec-2023/assets/12674043/c5791d60-e751-43a9-9ae5-ecda8e40e78c)

Create file name FirstScreen.qml with below code
<pre>
import QtQuick 2.15
import QtQml.StateMachine as SM

Rectangle {
    id: firstScreen

    width: 200; height: 200

    signal batteryCharging()
    signal batteryCharged()

    SM.StateMachine {
        id: stateMachine

        initialState: batteryLow

        SM.State {
            id: batteryLow

            SM.SignalTransition {
                targetState: batteryCharging
                signal: firstScreen.batteryCharging
            }

            onEntered:
                console.log("In Battery low state ...")

            onExited:
                console.log("Leaving Battery low state ...")
        }

        SM.State {
            id: batteryCharging

            SM.SignalTransition {
                targetState: batteryCharged
                signal: firstScreen.batteryCharged
            }

            onEntered:
                console.log("In Battery Charging state ...")

            onExited:
                console.log("Leaving Battery charging state ...")
        }

        SM.FinalState {
           id: batteryCharged

           onEntered:
               console.log("In Battery Charged state ...")

           onExited:
               console.log("All done!")

        }
    } //State Machine end



    Row {


        Button {
            caption: "Set Battery Low"

            onButtonClicked: {
                console.log ( "State Machine started ...")
                stateMachine.running = true
            }

        } // Button end

        Button { caption: "Set Battery Charging"

            onButtonClicked: {
                console.log( "entered " + stateMachine.toString() )
                firstScreen.batteryCharging()
            }
        }

        Button { caption: "Set Battery Charged"
            onButtonClicked: {
                console.log( "entered " + stateMachine.toString() )
                firstScreen.batteryCharged()
            }
        }
    } //Row end
}  
</pre>
