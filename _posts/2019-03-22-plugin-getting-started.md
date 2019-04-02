---
title: "Getting Started Guide with ARGOS-LABS RPA+ plugin"
date: 2019-03-22 08:26:28+0900
categories: 
  - plugin 
toc: true
---

ARGOS-LABS RPA+ have open architecture using Plugin.
This guide is the `Getting Started Guide` with ARGOS-LABS RPA+ plugin.

Once you finish this simple plugin guide you can build your own plugin.
This plugin program is not only for ARGOS-LABS RPA+ but can be used any kind of purpose as general CLI program.

# Running Environments

Plugin can be developed in Windows, Linux or Mac. However this guide is built these environments:

* OS: Windows 10 Pro
* Prerequsite Programs:
	* Python interpreter 3.7.x
	* PyCharm CE IDE

PyCharm and Python interpreter support Linux and Mac also, You can build this environment in Mac or Linux.

> Our plugin manager and SDK is made by Python programming language. So the environments are familiar to most of python programmer.

![00010 clean up windows 10 desktop](https://argos-labs.github.io/images/gst-captures/00010.png)


# Prerequsite Programs

First of all let's install PyCharm IDE.

## PyCharm

> If you already your own IDE then skip to [the next section](https://argos-labs.github.io/plugin/plugin-getting-started/#python-3).

* Open Web browser. (Next example, Chrome browser is used but other browsers are fine.)
* Goto [google search](https://www.google.com)
* Type `pycharm download`
* Select [Download PyCharm: Python IDE for ...](https://www.jetbrains.com/pycharm/download/)
![00020 google search pycharm download](https://argos-labs.github.io/images/gst-captures/00020.png)

* You can see `Download PyCharm` page.
* Click the `Download` button at Community to download PyCharm setup program. (You can use PyCharm Community Edition without payment)
> If you want to get Professional editon with payment, you can get it. However it's enough to develop plugin program with Community Edition.

![00030 download pycharm community edition](https://argos-labs.github.io/images/gst-captures/00030.png)

* After download the PyCharm setup program, run it.
* At welcome page just click `Next>` button.

![00040 PyCharm setup welcome page](https://argos-labs.github.io/images/gst-captures/00040.png)

* There is a setup widzard page, "Choose Install Location".
* Just click the `Next>` button to use default location if you have any special reason.

![00050 PyCharm setup choose location](https://argos-labs.github.io/images/gst-captures/00050.png)

* There is a setup widzard page, "Installation Options".
* Default is nothing checked.
* Just click the `Next>` button to use default options if you have any special reason.
* There is another explanation for PyCharm settings.

![00060 PyCharm setup Installation Options](https://argos-labs.github.io/images/gst-captures/00060.png)

* There is a setup widzard page, "Choose Start Menu Folder".
* Just click the `Next>` button to use default Menu Folder if you have any special reason.

![00070 PyCharm setup Choose Start menu Folder](https://argos-labs.github.io/images/gst-captures/00070.png)

* There is the last setup widzard page, "Completing PyCharm Community Edition Setup".
* Please do not check `Run PyCharm Community Edition` at this time because another Python Interpreter installation is needed.
* Click the `Finish` to complete PyCharm setup program.

![00080 PyCharm setup completing](https://argos-labs.github.io/images/gst-captures/00080.png)


## Python 3

Next is for setting up Python Interpreter.

* Open Web browser.
* Goto [google search](https://www.google.com)
* Type `python 3.7 windows download`
* Select first result, [Download Python | Python.org](https://www.python.org/downloads/)

![00090 google search python 3.7 download](https://argos-labs.github.io/images/gst-captures/00090.png)

* There is a Python Download page.
* Select Windows. (You can choose Mac OS X or Linux platform according to your platform.)
* Click `Python 3.7.3` to download Python Setup program. (The most recent version of March 2019 is 3.7.3. You can download the above version will be fine.)
> We recommand to install Python 3.7 but 3.6 is fine. The minimal required version is 3.6.  
> For Windows there are two kind of Python, 32-bit and 64-bit. We recommand 32-bit Python even though your Windows system is 64-bit.

![00100 python.org download](https://argos-labs.github.io/images/gst-captures/00100.png)

* After download the Python Setup program, run the setup program.
* There is the first widzard page, "Install Python 3.7.3 (32-bit)"
* First check "Add Python 3.7 to PATH".
* Select "Customize installation".

![00110 python setup](https://argos-labs.github.io/images/gst-captures/00110.png)

* There is a widzard page, "Optional Features".
* Uncheck all options except `pip`.
* Click the `Next` button.

![00120 python setup Optional Features](https://argos-labs.github.io/images/gst-captures/00120.png)

* There is a widzard page, "Advanced Options".
* Check "Create shortcuts for installed applications".
* Check "Add Python to environment variables"
* Uncheck the rest options.
* Please type `C:\Python37-32` at "Customize install location" input box.
* Click the `Install` button.

![00130 python setup Advanced Options](https://argos-labs.github.io/images/gst-captures/00130.png)

* There is the last widzard page, "Setup was successful".
* Just click `Close` button.

![00140 python setup finish](https://argos-labs.github.io/images/gst-captures/00140.png)

* Now that we install the python interpreter let us check it is installed well or not.
* Execute `CMD.EXE`. (`WindowsKey+R` and then type `cmd` and then `Enter` key) 

![00150 run cmd.exe](https://argos-labs.github.io/images/gst-captures/00150.png)

* type `python -V` at command prompt. It must say `Python 3.7.3`.
* type `pip list` to list installed modules. Next shows the command and results.
> In example machine, the user name is `Administrator`. So the prompt shows `C:\Users\Administrator>`. If your user name if toor then then prompt will show `C:\Users\toor>`. 

```cmd
C:\Windows\system32>python -VPython 3.7.3C:\Windows\system32>pip listPackage    Version---------- -------pip        19.0.3setuptools 40.8.0
```

![00160 cmd.exe python check](https://argos-labs.github.io/images/gst-captures/00160.png)

You installed `PyCharm IDE` and `Python Interpreter` to develop ARGOS-LABS RPA+. The installation is needed only once.

Next we will have some preparation process.

# Preparation

## VirtualEnv

![00010 clean up windows 10 desktop](https://argos-labs.github.io/images/gst-captures/00170.png)

## Plugin Package Manager

![00010 clean up windows 10 desktop](https://argos-labs.github.io/images/gst-captures/00180.png)
![00010 clean up windows 10 desktop](https://argos-labs.github.io/images/gst-captures/00190.png)

### .argos-rpa.conf
![00010 clean up windows 10 desktop](https://argos-labs.github.io/images/gst-captures/00200.png)
![00010 clean up windows 10 desktop](https://argos-labs.github.io/images/gst-captures/00210.png)

## alabs.ppm
![00010 clean up windows 10 desktop](https://argos-labs.github.io/images/gst-captures/00220.png)
![00010 clean up windows 10 desktop](https://argos-labs.github.io/images/gst-captures/00230.png)

# Preparation of plugin Development

## Copy from template
![00010 clean up windows 10 desktop](https://argos-labs.github.io/images/gst-captures/00240.png)
![00010 clean up windows 10 desktop](https://argos-labs.github.io/images/gst-captures/00250.png)
![00010 clean up windows 10 desktop](https://argos-labs.github.io/images/gst-captures/00260.png)

## Starting PyCharm
![00010 clean up windows 10 desktop](https://argos-labs.github.io/images/gst-captures/00270.png)
![00010 clean up windows 10 desktop](https://argos-labs.github.io/images/gst-captures/00280.png)
![00010 clean up windows 10 desktop](https://argos-labs.github.io/images/gst-captures/00290.png)

## PyCharm Settings
![00010 clean up windows 10 desktop](https://argos-labs.github.io/images/gst-captures/00300.png)
![00010 clean up windows 10 desktop](https://argos-labs.github.io/images/gst-captures/00310.png)
![00010 clean up windows 10 desktop](https://argos-labs.github.io/images/gst-captures/00320.png)
![00010 clean up windows 10 desktop](https://argos-labs.github.io/images/gst-captures/00330.png)
![00010 clean up windows 10 desktop](https://argos-labs.github.io/images/gst-captures/00340.png)
![00010 clean up windows 10 desktop](https://argos-labs.github.io/images/gst-captures/00350.png)
![00010 clean up windows 10 desktop](https://argos-labs.github.io/images/gst-captures/00360.png)

# First Run / Debug

![00010 clean up windows 10 desktop](https://argos-labs.github.io/images/gst-captures/00370.png)
![00010 clean up windows 10 desktop](https://argos-labs.github.io/images/gst-captures/00380.png)
![00010 clean up windows 10 desktop](https://argos-labs.github.io/images/gst-captures/00390.png)

## Making New Plugin

### Copying from HelloWorld
![00010 clean up windows 10 desktop](https://argos-labs.github.io/images/gst-captures/00400.png)
![00010 clean up windows 10 desktop](https://argos-labs.github.io/images/gst-captures/00410.png)
![00010 clean up windows 10 desktop](https://argos-labs.github.io/images/gst-captures/00420.png)
![00010 clean up windows 10 desktop](https://argos-labs.github.io/images/gst-captures/00430.png)
![00010 clean up windows 10 desktop](https://argos-labs.github.io/images/gst-captures/00440.png)
![00010 clean up windows 10 desktop](https://argos-labs.github.io/images/gst-captures/00450.png)
![00010 clean up windows 10 desktop](https://argos-labs.github.io/images/gst-captures/00460.png)
![00010 clean up windows 10 desktop](https://argos-labs.github.io/images/gst-captures/00470.png)
![00010 clean up windows 10 desktop](https://argos-labs.github.io/images/gst-captures/00480.png)
![00010 clean up windows 10 desktop](https://argos-labs.github.io/images/gst-captures/00490.png)

### __init__.py

![00010 clean up windows 10 desktop](https://argos-labs.github.io/images/gst-captures/00500.png)
![00010 clean up windows 10 desktop](https://argos-labs.github.io/images/gst-captures/00510.png)
![00010 clean up windows 10 desktop](https://argos-labs.github.io/images/gst-captures/00520.png)
![00010 clean up windows 10 desktop](https://argos-labs.github.io/images/gst-captures/00530.png)

### change icon

![00010 clean up windows 10 desktop](https://argos-labs.github.io/images/gst-captures/00540.png)
![00010 clean up windows 10 desktop](https://argos-labs.github.io/images/gst-captures/00550.png)

### prerequisite modues

![00010 clean up windows 10 desktop](https://argos-labs.github.io/images/gst-captures/00560.png)
![00010 clean up windows 10 desktop](https://argos-labs.github.io/images/gst-captures/00570.png)

### Completion of __init__.py

![00010 clean up windows 10 desktop](https://argos-labs.github.io/images/gst-captures/00580.png)
![00010 clean up windows 10 desktop](https://argos-labs.github.io/images/gst-captures/00590.png)

### Unittest for plugin

![00010 clean up windows 10 desktop](https://argos-labs.github.io/images/gst-captures/00600.png)
![00010 clean up windows 10 desktop](https://argos-labs.github.io/images/gst-captures/00610.png)
![00010 clean up windows 10 desktop](https://argos-labs.github.io/images/gst-captures/00620.png)
![00010 clean up windows 10 desktop](https://argos-labs.github.io/images/gst-captures/00630.png)
![00010 clean up windows 10 desktop](https://argos-labs.github.io/images/gst-captures/00640.png)

### configuration of plugin

![00010 clean up windows 10 desktop](https://argos-labs.github.io/images/gst-captures/00650.png)

# build and submit
![00010 clean up windows 10 desktop](https://argos-labs.github.io/images/gst-captures/00660.png)
![00010 clean up windows 10 desktop](https://argos-labs.github.io/images/gst-captures/00670.png)
![00010 clean up windows 10 desktop](https://argos-labs.github.io/images/gst-captures/00680.png)

