# YouTube KDAB Channel

- [KDAB Channel](https://youtube.com/@KDABtv)
ee
# Introduction to Qt Widgets

> Jesper Pederson from KDAB

* Part 01 - Compiling Hello World
    * Hello World
    * QtApplication could have been named QtWidgetApplication
* Part 02 - Compiling Hello World
    * QMake vs. CMake
* Part 03 - The Qt Help Text
    * Qt Creator Qt Assistant
        * CLI: "/c/Qt/6.8.3/mingw_64/bin/assistant.exe
            * Add this to the NUC2 arlis user environment variables Path
        * Hover on Class name and press "F1"
            * Press "F1" a second time for full-screen documentation
        * When finished, press "Escape" to dismiss the documentation
        * "Build with CMake"
            * If using Qt Creator Help: "CMake 3.30.5 Documentation"
    * Qt Creator Preferences Help Documentation Add cppreference.com
        * TODO download the qch file ... still looking for the C++ Reference qch file
        * [cppreference.com - Archives for offline viewing](https://cppreference.com/w/Cppreference%253AArchives.html)
        * I gave up because cannot find the qchelpgenerator utility on NUC1 Ubuntu 24.04 LTS
    * Separate YouTube video: "Adding CPPReference to Qt Creator"                   
        * [YouTube - KDAB - Adding CPPreference to Qt Creator](https://www.youtube.com/watch?v=5ELbrOdRM2c)
            * [cppreference.com - Archives for offline viewing](https://en.cppreference.com/w/Cppreference%253AArchives.html)
                * Qt help book
                * no longer available
            * "https://en.cppreference.com/w/Cppreference:Archives"
                * download Qt help book (qch)
        * I am not seeing "C++ Reference Guide" in my display
            * "cppreference.com"
            * "learncpp.com"
* Part 04 - Qt's Object Model
   * see below
* [Part 05 - Qt Object Model and QWidgets Basics](https://www.youtube.com/watch?v=EqHtuVnoITw&t=246s)
   * [see below 1](#part05)
   * [see below 2](#part-05-blah)

## Part 04 - Qt's Object Model

> about 9 minutes into the video


### On Heap - QObject with parent

> It is forbidden to copy QObject instances

```
QLabel *label = new QLabel("Some Text", parent);
```

### On Stack - QObject without parent

```
QFile, usually local to a function

QGuiApplication, local to main()

Top level QWidgets QMainWindow
```

### On Stack - "value" type

```
QString name;
QStringList list;
QColor color;
```

> Implicitly shared - Cheap to copy

> "Value" types are not QObject subclasses

> Do not use "new"

## Part 05 Blah

> Part 05 - Qt Object Model and QWidgets Basics

## Part05

> Part 05 - Qt Object Model and QWidgets Basics


# GitHub PeterFeicht cppreference-doc

> NUC1 Ubuntu 24.04 LTS

```
$ sudo apt-get install python3-venv python3-all
$ sudo apt-get install qttools5-dev-tools

... provides qhelpgenerator ...

```

```
$ python3 -m venv cppreference_env
$ source cppreference_env/bin/activate
(cppreference_env)$
```

```
(cppreference_env)$ pip install cssutils
(cppreference_env)$ pip install lxml
(cppreference_env)$ pip install premailer
(cppreference_env)$
```

```
(cppreference_env)$ cd ~/projects/github/PeterFeicht/cppreference-doc
(cppreference_env)$ mkdir -p output/reference_cssless
(cppreference_env)$ make doc_ach

generates output/cppreference-doc-en-cpp.qch
```

> Add this to Qt Creator Help files

After adding the file (Preferences - Help - Documentation - Add)

```
cppreference.com.cppreference-doc-en-cpp
```

Now Qt Creator Help displays a new Contents reference "C++ Standard Library reference"


