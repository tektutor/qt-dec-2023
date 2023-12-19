## Lab1 - Creating your first QML 3D application using QtCreator IDE

Following the instructions described in Day1, Lab1 create a Qt QML application.  
May be you could name the project as Hello3D.

### Step 1 - Update your .pro file as shown below
![image](https://github.com/tektutor/qt-dec-2023/assets/12674043/a7496a30-6dd0-4450-ae77-3594fc1cca48)

### Step 2 - main.cpp as shown below
```
#include <QGuiApplication>
#include <QQmlApplicationEngine>

int main(int argc, char *argv[])
{
    QGuiApplication a(argc, argv);

    QQmlApplicationEngine engine;
    engine.load( QUrl (QStringLiteral ("qrc:/main.qml")));

    return a.exec();
}
```
![image](https://github.com/tektutor/qt-dec-2023/assets/12674043/486c2f50-18b9-4dea-94e0-96c0184d793d)

### Step 3 - Update your main.qml as shown below
<pre>
import QtQuick 2.15
import QtQuick3D

Window {
    width: 1000; height: 1000
    visible: true

    Row {
        View3D {
            width: 500; height: 500

            id: scene1
            camera: perspectiveCamera

            Model {
                id: myCube1
                source: "#Cube"

                eulerRotation.z: 45 //Rotates in z axis
                eulerRotation.x: 30 //Rotates in x axis
                eulerRotation.y: 20 //Rotates in y axis

                materials: [
                    DefaultMaterial {
                        diffuseColor: "red"
                    }
                ]
            }

            PerspectiveCamera {
                id: perspectiveCamera

              position: Qt.vector3d(0,0,600)
            }

            DirectionalLight {
                id: sunLight1
            }
        }
        View3D {
            width: 500; height: 500

            id: scene2
            camera: directionalCamera

            Model {
                id: myCube2
                source: "#Cube"

                eulerRotation.z: 45 //Rotates in z axis
                eulerRotation.x: 30 //Rotates in x axis
                eulerRotation.y: 20 //Rotates in y axis

                materials: [
                    DefaultMaterial {
                        diffuseColor: "red"
                    }
                ]
            }

            OrthographicCamera {
                id: directionalCamera
                position: Qt.vector3d(0,0,600)
            }

            DirectionalLight {
                id: sunLight2
            }
        }
    }
}  
</pre>

### Step 4 - Save all files
Make sure you have saved all file changes by pressing [Ctrl + Shift + S]

### Step 5 - Build and Run the project

Build the project by pressing [Ctrl + B]

Run the project by pressing [Ctrl + R]
![image](https://github.com/tektutor/qt-dec-2023/assets/12674043/c9829ef6-c894-4587-9765-5bb678c8abbf)

The left View3D uses a perspective Camera, while the right side View3D uses an OrthographicCamera.
