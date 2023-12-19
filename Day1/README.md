# QML 2D Programming

## ⛹️‍♂️ Lab1 - Creating your first 2D QML Application

Launch your Qt Creator IDE
![image](https://github.com/tektutor/qt-dec-2023/assets/12674043/89acafc7-a441-4af4-8da8-8046dac1fde6)

Click on "Create Project", select "Qt Console Application" and click on "Choose" button
![image](https://github.com/tektutor/qt-dec-2023/assets/12674043/1e3f08ec-58dd-4ea7-b936-56a1ec9ffac8)

Project Location, click on "Next" button
![image](https://github.com/tektutor/qt-dec-2023/assets/12674043/f33c0adc-16b0-4c64-974d-7d3cd754ee82)

Define Build System, click on "Next" button
![image](https://github.com/tektutor/qt-dec-2023/assets/12674043/bcefe689-3877-4550-9ab4-5e2766a5517a)

Translation File, click on "Next" button
![image](https://github.com/tektutor/qt-dec-2023/assets/12674043/9d1f9b18-8a76-452d-978f-e8224cfd52e9)

Kit Selection, click on "Next" button
![image](https://github.com/tektutor/qt-dec-2023/assets/12674043/2042277e-073a-4f9a-b105-8dcff17f9fe6)

Project Management, click on "Finish" button
![image](https://github.com/tektutor/qt-dec-2023/assets/12674043/6ef54b9e-b21a-417e-a9d5-bcaf501ff6f8)

We need to convert the Qt console application project into a QML project, hence we need to customize the HelloQML.pro file

Currently your HelloQML.pro file will look as shown below
![image](https://github.com/tektutor/qt-dec-2023/assets/12674043/62b9baaf-1990-460b-ae16-185362b194e0)

We need to update the line number 1 as shown below and Save all (Ctrl + Shift + S)
![image](https://github.com/tektutor/qt-dec-2023/assets/12674043/f650055f-070f-4b71-a264-78441d90aa5a)

Next, open the main.cpp file which looks as shown below
![image](https://github.com/tektutor/qt-dec-2023/assets/12674043/437fbc61-cf0c-469f-9875-122e6cd05216)

We need to update the main.cpp as shown below
```
#include <QGuiApplication>
#include <QQmlApplicationEngine>

int main(int argc, char *argv[])
{
    QGuiApplication a(argc, argv);

    QQmlApplicationEngine engine;
    engine.load ( QUrl (QStringLiteral( "qrc:/main.qml")));

    return a.exec();
}
```
![image](https://github.com/tektutor/qt-dec-2023/assets/12674043/dc057a8a-cf91-4fe0-bafe-a846c400fa4b)

Next, we need to add a Qt Resource File to the project
![image](https://github.com/tektutor/qt-dec-2023/assets/12674043/c1ef830a-f8f8-4958-ab08-b39d76ab382c)

Location
![image](https://github.com/tektutor/qt-dec-2023/assets/12674043/de325c99-631f-4608-a76b-0f372bb9ecad)

Project Management, click on "Finish" button
![image](https://github.com/tektutor/qt-dec-2023/assets/12674043/284d8d26-3bb1-4dd7-a4b1-c5de2a3878a6)

At this point, your HelloQML project will look as shown below
![image](https://github.com/tektutor/qt-dec-2023/assets/12674043/eb273192-15cf-41cf-8ad6-bd838c64703f)

We need to add a QML File as shown below
![image](https://github.com/tektutor/qt-dec-2023/assets/12674043/98515571-38ee-4b0c-8fcf-b9af60014acd)
    
Location
![image](https://github.com/tektutor/qt-dec-2023/assets/12674043/a86a26ef-2909-48a8-963b-26ef745a210a)

Project Management, click on "Finish" button
![image](https://github.com/tektutor/qt-dec-2023/assets/12674043/b6102cf9-d783-4149-9599-1512061a1861)

File Changed - Qt Creator, select "Yes to All"
![image](https://github.com/tektutor/qt-dec-2023/assets/12674043/e99adf97-69d3-4dd3-8f4c-31334f371d75)

Currently, your main.qml file will look as shown below
![image](https://github.com/tektutor/qt-dec-2023/assets/12674043/103324e6-25d6-46fa-9bf2-f09c7f3de277)

We need to edit the main.qml as shown below
<pre>
import QtQuick 2.15

Window {
    width: 1000; height: 1000
    visible: true

    Rectangle {
        width: 500; height: 500

        color: "blue"

        Text {
            anchors.centerIn: parent
            text: "Hello QML!"
        }
    }
}    
</pre>
![image](https://github.com/tektutor/qt-dec-2023/assets/12674043/70806ff7-059c-4e80-85ad-008f5a61578d)

Now you can build and run the project, Build(Ctrl+B) and Run(Ctrl+R)
![image](https://github.com/tektutor/qt-dec-2023/assets/12674043/3f722475-bebf-468c-978d-3974a4c05cbb)

Build (Ctrl+B)
![image](https://github.com/tektutor/qt-dec-2023/assets/12674043/533b7ae1-31e6-429b-a965-7d72abbee6df)

Run (Ctrl+R)
![image](https://github.com/tektutor/qt-dec-2023/assets/12674043/763d3ac6-7841-4cc6-911d-01d942f7d7e6)

Let's change the font color to White and make the font bold and increate the font size by updating the main.qml as shown below
<pre>
import QtQuick 2.15

Window {
    width: 1000; height: 1000
    visible: true

    Rectangle {
        width: 500; height: 500
        anchors.centerIn: parent
        color: "blue"

        Text {
            anchors.centerIn: parent
            text: "Hello QML!"
            
            color: "white"
            font.bold: true
            font.pointSize: 20
            
        }
    }
}    
</pre>
![image](https://github.com/tektutor/qt-dec-2023/assets/12674043/e2c908d9-74f1-466e-a07b-2d9451fa2e4b)

You need to save all changes (Ctrl+Shif+S)

Build(Ctrl+B)

Run(Ctrl+R)
![image](https://github.com/tektutor/qt-dec-2023/assets/12674043/19e61787-aba3-4bd2-8e98-5c0d100d4d56)

Close the project (File menu --> Close Project)
![image](https://github.com/tektutor/qt-dec-2023/assets/12674043/c669eb70-12f9-4f7c-8105-f7293eeb8858)

## ⛹️‍♀️ Lab2 - Creating your own custom Controls(Components) and reuse them in your QML Project

As you already know how to create a new QML Project, I'm skipping those steps.

Once you have created a new project named ButtonApp

You need to edit your .pro file, line 1 as shown below
![image](https://github.com/tektutor/qt-dec-2023/assets/12674043/1a10a8be-4914-422c-9cba-9eaf1fe5b747)

You need to edit the main.cpp file as shown below
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
![image](https://github.com/tektutor/qt-dec-2023/assets/12674043/2e1db3c6-1d6f-48f4-aa02-e5f24eb4fe12)

Create a Button.qml as shown below
<pre>
import QtQuick 2.15

Rectangle {
    id: button

    width: 150; height: 80

    property string caption: "Button"
    signal buttonClicked()

    color: "darkgray"

    border.width: 5
    border.color: Qt.color("blue")

    radius: 40

    Text {
        anchors.centerIn: parent
        font.bold: true
        font.pointSize: 15
        color: "white"

        text: caption
    }

    MouseArea {
        anchors.fill: parent
        hoverEnabled: true

        onClicked: {
            buttonClicked()
        }

        onEntered: {
            button.scale = 1.1
            button.border.color = Qt.color("red")
        }

        onExited: {
            button.scale = 1.0
            button.border.color = Qt.color("blue")
        }
    }
}
</pre>
![image](https://github.com/tektutor/qt-dec-2023/assets/12674043/a596a96e-aa0d-4428-9d48-ceff0ab32c72)

You need to edit the main.qml file as shown below
<pre>
import QtQuick 2.15

Window {
    width: 1000; height: 1000
    visible: true

    Button {
        anchors.centerIn: parent

        caption: "Button 1"

        onButtonClicked:
            console.log(caption + " clicked")
    }
}    
</pre>
![image](https://github.com/tektutor/qt-dec-2023/assets/12674043/30caae9d-293d-4827-9a8c-c4e3d1c74082)

You may build your project (Ctrl+B)

Run your project (Ctrl+R)
![image](https://github.com/tektutor/qt-dec-2023/assets/12674043/a7776880-1058-4997-a4ef-10383ec85655)

When your mouse cursor enter the button area, it would look as shown below
![image](https://github.com/tektutor/qt-dec-2023/assets/12674043/b773619c-c5a3-47a9-938f-4d17687b3f2a)

When your mouse cursor leaves the button area, it would look as shown below
![image](https://github.com/tektutor/qt-dec-2023/assets/12674043/3ca524de-00a1-4898-a426-21bd789a567b)

## ⛹️‍♂️ Lab3 - Understanding QML Column Positioner

Create a new QML Project following the Lab1 steps.

### Step 1 - Your .pro file shall be updated as shown below
![image](https://github.com/tektutor/qt-dec-2023/assets/12674043/58298366-34fe-48d4-8c8d-da4e925c8fbb)

### Step 2 - Your Button.qml shall be updated as shown below
<pre>
import QtQuick 2.15

Rectangle {
    id: button

    width: 150; height: 80

    property string caption: "Button"
    signal buttonClicked()

    color: "darkgray"

    border.width: 5
    border.color: Qt.color("blue")

    radius: 40

    Text {
        anchors.centerIn: parent
        font.bold: true
        font.pointSize: 15
        color: "white"

        text: caption
    }

    MouseArea {
        anchors.fill: parent
        hoverEnabled: true

        onClicked: {
            buttonClicked()
        }

        onEntered: {
            button.scale = 1.1
            button.border.color = Qt.color("red")
        }

        onExited: {
            button.scale = 1.0
            button.border.color = Qt.color("blue")
        }
    }
}
    
</pre>

### Step 3 - Your main.qml shall be updated as shown below
<pre>
import QtQuick 2.15

Window {
    width: 1000; height: 1000
    visible: true

    Rectangle {
        width: 500; height: 500
        radius: 50

        border.width: 5
        border.color: Qt.color("blue")

        anchors.centerIn: parent

        Text {
            anchors.horizontalCenter: parent.horizontalCenter
            text: "QML Column Positioner"
            y: 10

            font.bold: true
            font.pointSize: 20

        }

        Column {
            anchors.centerIn: parent
            spacing: 20

            Button {
                id: button1
                caption: "Button1"

                onButtonClicked:
                    console.log (caption + " clicked")
            }

            Button {
                id: button2
                caption: "Button2"

                onButtonClicked:
                    console.log (caption + " clicked")
            }

            Button {
                id: button3
                caption: "Button3"

                onButtonClicked:
                    console.log (caption + " clicked")
            }

        } //Column
    } //Rectangle
}    
</pre>

### Step 4 - Save All
Make sure you have saved all your changes [Ctrl + Shift + S]

### Step 5 - Build and Run

Build (Ctrl+B)

Run (Ctrl+R)
![image](https://github.com/tektutor/qt-dec-2023/assets/12674043/87026a09-c7cb-4098-a666-fe850afd8531)

## ⛹️‍♂️ Lab4 - Understanding QML Row Positioner

Create a new QML project following Lab1 Steps and name your project as "RowPositioner"

### Step 1 - Update your .pro file
![image](https://github.com/tektutor/qt-dec-2023/assets/12674043/1c608fa2-9d3c-4217-9fab-77ee711283e3)

### Step 2 - Update your main.cpp as shown below
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

### Step 3 - Update your Button.qml as shown below
<pre>
import QtQuick 2.15

Rectangle {
    id: button

    width: 150; height: 80

    property string caption: "Button"
    signal buttonClicked()

    color: "darkgray"

    border.width: 5
    border.color: Qt.color("blue")

    radius: 40

    Text {
        anchors.centerIn: parent
        font.bold: true
        font.pointSize: 15
        color: "white"

        text: caption
    }

    MouseArea {
        anchors.fill: parent
        hoverEnabled: true

        onClicked: {
            buttonClicked()
        }

        onEntered: {
            button.scale = 1.1
            button.border.color = Qt.color("red")
        }

        onExited: {
            button.scale = 1.0
            button.border.color = Qt.color("blue")
        }
    }
}    
</pre>

### Step 4 - Update your main.qml as shown below
<pre>
import QtQuick 2.15

Window {
    width: 1000; height: 1000
    visible: true

    Rectangle {
        width: 800; height: 800
        radius: 50

        border.width: 5
        border.color: Qt.color("blue")

        anchors.centerIn: parent

        Text {
            anchors.horizontalCenter: parent.horizontalCenter
            text: "QML Row Positioner"
            y: 10

            font.bold: true
            font.pointSize: 20
        }

        Row {
            anchors.centerIn: parent
            spacing: 20

            Button {
                id: button1
                caption: "Button1"

                onButtonClicked:
                    console.log (caption + " clicked")
            }

            Button {
                id: button2
                caption: "Button2"

                onButtonClicked:
                    console.log (caption + " clicked")
            }

            Button {
                id: button3
                caption: "Button3"

                onButtonClicked:
                    console.log (caption + " clicked")
            }

        } //Column
    } //Rectangle
}    
</pre>

### Step 5 - Save all your changes
Make sure all file changes are saved, press [Ctrl + Shift + S]

### Step 6 - Build and Run your project

To build your project, press [Ctrl + B]

To Run your project, press [Ctrl + R]
![image](https://github.com/tektutor/qt-dec-2023/assets/12674043/89a018cc-e181-459a-948f-d950d8b1ae9c)


## ⛹️‍♂️ Lab5 - Combining Row and Grid Positioner to develop a Simple Math Application

Create a new QML project following Lab1 Steps and name your project as "SimpleMathApp"

### Step 1 - Update your .pro file
![image](https://github.com/tektutor/qt-dec-2023/assets/12674043/4f3d2655-c541-4e88-878b-d8afff233eec)

### Step 2 - Update your main.cpp as shown below
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

### Step 3 - Update your Button.qml file shown below
<pre>
import QtQuick 2.15

Rectangle {
    id: button
    width: 100; height: 50

    property string caption: "Button"
    property string borderColor: "black"
    property string textColor: "white"

    signal buttonClicked()

    border.color: borderColor
    border.width: 2
    radius: 25

    color: "darkgray"

    Text {
        anchors.centerIn: parent
        text: caption
        color: textColor
        font.bold: true
    }

    MouseArea {
        anchors.fill: parent
        hoverEnabled: true

        onClicked: {
            console.log(caption + " clicked")
            buttonClicked()
        }
        onEntered: {
            button.borderColor = "blue"
            button.scale = 1.1
            button.textColor = "red"
        }
        onExited: {
            button.borderColor = "black"
            button.scale = 1.0
            button.textColor = "white"
        }
    }
}    
</pre>

### Step 4 - Update your Edit.qml file shown below
<pre>
 import QtQuick 2.15

Rectangle {
    width: 475; height: 80

    property string caption: "Edit"

    border.color: "blue"
    border.width: 2
    radius: 10

    TextInput {
        anchors.centerIn: parent
        text: caption
    }
}   
</pre>

### Step 5 - Update your Label.qml as shown below
<pre>
import QtQuick 2.15

Rectangle {
    width: 150; height: 80

    property string caption: "Label"

    border.color: "black"
    border.width: 2
    radius: 10

    color: "lightgray"

    Text {
        anchors.centerIn: parent
        text: caption
    }
}    
</pre>

### Step 6 - Update your main.qml as shown below
<pre>
import QtQuick 2.15

Window {
    width: 1000; height: 1000
    title: "Simple Math Application"
    visible: true

    Rectangle {
        width: 800; height: 800
        anchors.centerIn: parent

        border.width: 20
        border.color: "blue"
        radius: 40

        color: "lightblue"

        Column {
            anchors.centerIn: parent
            spacing: 30
            Grid {
                rows: 3
                columns: 2

                Label{caption: "First Number"}
                Edit {id: txtFirstNumber}

                Label{caption: "Second Number"}
                Edit {id: txtSecondNumber}

                Label{caption: "Result"}
                Edit {id: txtResult}
            }

            Row {
                spacing: 5
                Button{
                    id: addButton
                    caption: "Add"
                }
                Button{
                    id: subtractButton
                    caption: "Subtract"
                }
                Button{
                    id: multiplyButton
                    caption: "Multiply"
                }
                Button{
                    id: dividemultiplyButton
                    caption: "Divide"
                }
                Button{
                    id: clearButton
                    caption: "Clear"
                }
                Button{
                    id: exitButton
                    caption: "Exit"
                }

            }
        } //Column
    } //Rectangle
}    
</pre>

### Step 7 - Save all your changes
Make sure all file changes are saved, press [Ctrl + Shift + S]

### Step 8 - Build and Run your project

To build your project, press [Ctrl + B]

To Run your project, press [Ctrl + R]
![image](https://github.com/tektutor/qt-dec-2023/assets/12674043/cab802d9-0012-4744-8aab-6bdf50236494)
