# QML 2D Programming

## Lab - Creating your first 2D QML Application

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
![image](https://github.com/tektutor/qt-dec-2023/assets/12674043/62c4c37a-d02f-4886-aed3-1d370a932c0b)
