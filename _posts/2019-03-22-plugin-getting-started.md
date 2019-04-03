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

There are some needs to do before starting development. It is related to environmental configuration.

## Making Virtual Environment

VirtualEnv is the python's independent running environment. [venv](https://docs.python.org/3/library/venv.html) is one of such virtual environmental implementations.

You can make your own virtual environment as follows:

* Change into home folder using command: `cd %USERPROFILE%` at first.
* Create a new python virtual environment named `py3` using command: `python -m venv py3`
	* You can make venv as much as you want with different name.
	* You can change each venv.
	* `pip` is the python package manager.
	* venv, `py3` has some folders.
		* Scripts: some execuable files including `python.exe` and `pip.exe`.
		* Lib\site-packages:
			* If you install some third-party modules with `pip` then such modules will be located in this folder. (Some other platform use `dist-packages`)
			* If you install our plugin module using alabs.ppm (will explain later) then our plugin modules will be located in this folder.
* Change into this `py3` virtual environment using command: `py3\Scripts\activate`.
	* After changed into venv your prompt will be changed `C:\Users\user>` into `(py3) C:\Users\user>`. The prompt will be prefixed with `(name-of-venv) `.
	* At this virtual environment your installed modules including plugin programs are valid only at this virtual environment. This means each virtual environment has it's own running environment with dependent modules or plugins.
* `pip list` command shows the modules including plugins which are installed by `pip install ...` command.
	* `(py3) C:\Users\user>` prompt means `py3` virtual environment.
	* Every modules or plugins in `py3` venv are only valid on `py3` venv.

```python
C:\>cd %USERPROFILE%C:\Users\Administrator>python -m venv py3C:\Users\Administrator>py3\Scripts\activate(py3) C:\Users\Administrator>pip listPackage    Version---------- -------pip        19.0.3setuptools 40.8.0```

![00170 cmd python venv](https://argos-labs.github.io/images/gst-captures/00170.png)

## Plugin Package Manager

### Enter Virtual Environment

Above `Making Virtual Environment` section shows how to make a new virtual environment named `py3`. Once the `py3` virtual environment is made, next time you just enter the virtual environment.

```cmd
C:\>cd %USERPROFILE%C:\Users\Administrator>py3\Scripts\activate(py3) C:\Users\Administrator>
```

Or directly the execute `activate`.

```cmd
C:\Users\Administrator>%USERPROFILE%\py3\scripts\activate(py3) C:\Users\Administrator>
```

When everything is done, you need to exit the virtual environment. you can do this `deactivate` command.

```cmd
(py3) C:\Users\Administrator>deactivateC:\Users\Administrator>
```

![00180 enter venv](https://argos-labs.github.io/images/gst-captures/00180.png)

### Install `Plugin Package Manager`

Our plugin SDK include two parts.
* Plugin Package Manager named `alabs.ppm`
* Plugin library module named `alabs.common`

Next explanation is how to install `Plugin Package Manager`.
* You need command prompt which is entered virtual environment. You can refer above `Enter Virtual Environment` section.
* Install with command: `pip install -U alabs.ppm alabs.common --index http://pypi.argos-labs.com:8080 --trusted-host pypi.argos-labs.com`

```cmd
(py3) C:\Users\Administrator>pip install -U alabs.ppm alabs.common --index http://pypi.argos-labs.com:8080 --trusted-host pypi.argos-labs.comLooking in indexes: http://pypi.argos-labs.com:8080Collecting alabs.ppm  Downloading http://pypi.argos-labs.com:8080/packages/alabs.ppm-1.327.2123-py3-none-any.whlCollecting alabs.common  Downloading http://pypi.argos-labs.com:8080/packages/alabs.common-1.327.1200-py3-none-any.whlCollecting requests (from alabs.ppm)  Using cached https://files.pythonhosted.org/packages/7d/e3/20f3d364d6c8e5d2353c72a67778eb189176f08e873c9900e10c0287b84b/requests-2.21.0-py2.py3-none-any.whlCollecting PyYAML (from alabs.ppm)  Using cached https://files.pythonhosted.org/packages/a2/50/d42aa0b14fd7b04d287fa739c16e49d9eb79d364a6aa0c5df6ecdeef3dd4/PyYAML-5.1-cp37-cp37m-win32.whlCollecting idna<2.9,>=2.5 (from requests->alabs.ppm)  Using cached https://files.pythonhosted.org/packages/14/2c/cd551d81dbe15200be1cf41cd03869a46fe7226e7450af7a6545bfc474c9/idna-2.8-py2.py3-none-any.whlCollecting certifi>=2017.4.17 (from requests->alabs.ppm)  Using cached https://files.pythonhosted.org/packages/60/75/f692a584e85b7eaba0e03827b3d51f45f571c2e793dd731e598828d380aa/certifi-2019.3.9-py2.py3-none-any.whlCollecting chardet<3.1.0,>=3.0.2 (from requests->alabs.ppm)  Using cached https://files.pythonhosted.org/packages/bc/a9/01ffebfb562e4274b6487b4bb1ddec7ca55ec7510b22e4c51f14098443b8/chardet-3.0.4-py2.py3-none-any.whlCollecting urllib3<1.25,>=1.21.1 (from requests->alabs.ppm)  Using cached https://files.pythonhosted.org/packages/62/00/ee1d7de624db8ba7090d1226aebefab96a2c71cd5cfa7629d6ad3f61b79e/urllib3-1.24.1-py2.py3-none-any.whlInstalling collected packages: idna, certifi, chardet, urllib3, requests, PyYAML, alabs.ppm, alabs.commonSuccessfully installed PyYAML-5.1 alabs.common-1.327.1200 alabs.ppm-1.327.2123 certifi-2019.3.9 chardet-3.0.4 idna-2.8 requests-2.21.0 urllib3-1.24.1
```
> `-U` or `--upgrade` option after `install` can upgrade to latest version.

![00190 install ppm](https://argos-labs.github.io/images/gst-captures/00190.png)

### .argos-rpa.conf
`alabs.ppm` Plugin Package Manager use configuration file `.argos-rpa.conf` located in `C:\Users\Administrator` or `%USERPROFILE%`.

First create this file.
* In `CMD.EXE` prompt goto User folder with command `cd %USERPROFILE%`.
* Make and edit with `notepad .argos-rpa.conf`
> You can use explorer to create `.argos-rpa.conf` file.

![00200 cmd notepad](https://argos-labs.github.io/images/gst-captures/00200.png)

The contents of configuration is:

``` yaml
---repository:  url: http://pypi.argos-labs.com:8080private-repositories:  - name: internal    url: http://10.211.55.2:48080    username: user1    password: pass_01
  - name: internal    url: http://10.211.55.3    username: user2    password: pass_02
```
> The configuration format is [YAML](https://en.wikipedia.org/wiki/YAML).

* repository is the official plugin module by ARGOS-LABS.
	* url is the default address to access the office repository of ARGOS-LABS.
	* Do NOT change the `http://pypi.argos-labs.com:8080` without special reason.
* `private-repositories` can contain the list of private repositories.
	* You can biild your own private [pypiserver](https://github.com/pypiserver/pypiserver).
	* Each list item can have next four key:value pairs.
		* `name` is the unique name to use at `alabs.ppm`
		* `url` is the URL address to access your own private pypi server.
		* `username` and `password` is the user credential to upload to this pypiserver.
			* Currently private pypiserver support `htaccess` credential method.
			* If another credential method must be used then contact us.
> * If `alabs.ppm upload` command to upload plugin to private pypiserver is never used, then private-repositories can be empty.

The simplist form is:
``` yaml
---repository:  url: http://pypi.argos-labs.com:8080private-repositories:```

![00210 notepad .argos-rpa.conf](https://argos-labs.github.io/images/gst-captures/00210.png)

### alabs.ppm
`alabs.ppm` plugin package manager has many command options.

* To begin with `CMD.EXE` enter virtual environment with command, `%USERPROFILE%\py3\Scripts\activate`
* `alabs.ppm` without any parameter says help output.

```cmd
(py3) C:\work\plugin-demo-master\argoslabs\ai\tts>alabs.ppmc:\users\administrator\py3\lib\site-packages\alabs\ppm\__init__.py:660: YAMLLoadWarning: calling yaml.load() without Loader=... is deprecated, as the default Loader is unsafe. Please read https://msg.pyyaml.org/load for full details.  dcf = yaml.load(ifp)Need command for ppm.usage: alabs.ppm [-h] [--new-py] [--venv] [--clean] [--verbose]                 {test,build,submit,upload,clear,clear-py,clear-all,get,install,show,uninstall,search,dumpspec,list,list-repository,pip,py,setup}                 ...ARGOS-LABS Plugin Package ManagerThis manager use private PyPI repository.set C:\Users\Administrator\.argos-rpa.conf as follows:---repository:  url: http://pypi.argos-labs.com:8080private-repositories:  - name: internal    url: http://10.211.55.2:48080    username: user    password: pass  - name: external    url: http://pypi.argos-labs.com:8080    username: user    password: pass* repository is the main plugin modules's store  * url is the url of ARGOS RPA+ main pypi module  NB) ARGOS RPA+ main module is not allowed to upload directly      but submit first and then ARGOS team to decide* private-repositories are the list of user's private plugin modules's store  * name is the name of private repository (for example "internal", "external")  * url is the url of pypi module  * username is the user name at pypi repository  * password is the user password at pypi repository  NB) username and password is only needed for upload      upload is only valid for private repositoriespositional arguments:  {test,build,submit,upload,clear,clear-py,clear-all,get,install,show,uninstall,search,dumpspec,list,list-repository,pip,py,setup}                        ppm command help    test                test this module    build               build this module    submit              submit to upload server    upload              upload this module to pypi server    clear               clear all temporary folders    clear-py            clear py.win32 virtual environment    clear-all           clear all temporary folders and virtual environment    get                 get configuration    install             install module    show                show module info    uninstall           uninstall module    search              search keywords    dumpspec            dumpspec keywords    list                list installed module    list-repository     list all modules at remote    pip                 pip command    py                  python command    setup               setup command with setup.yamloptional arguments:  -h, --help            show this help message and exit  --new-py              making new python venv environment at py.win32  --venv                if set use package top py.win32 for virtual env. If not set. Use system python instead.  --clean, -c           clean all temporary folders, etc.  --verbose, -v         verbose output eg) -v, -vv, -vvv, ...
```

![00220 clean up windows 10 desktop](https://argos-labs.github.io/images/gst-captures/00220.png)

One of commands is searching specific plugin with a name.
The most official plugin modules are started with `argoslabs.` prefix.
You can search all plugin modules:

```cmd
(py3) C:\work\plugin-demo-master\argoslabs\ai\tts>cd \(py3) C:\>alabs.ppm search argoslabsc:\users\administrator\py3\lib\site-packages\alabs\ppm\__init__.py:660: YAMLLoadWarning: calling yaml.load() without Loader=... is deprecated, as the default Loader is unsafe. Please read https://msg.pyyaml.org/load for full details.  dcf = yaml.load(ifp)start search ...argoslabs.data.rdb (1.313.1857)    - 1.313.1857argoslabs.api.rossum (1.327.1355)  - 1.327.1355argoslabs.api.rest (1.315.1054)    - 1.315.1054argoslabs.data.excel (1.325.1359)  - 1.325.1359argoslabs.data.json (1.324.2344)   - 1.324.2344argoslabs.ai.tts (1.330.1500)      - 1.330.1500done.
```

![00230 alabs.ppm search](https://argos-labs.github.io/images/gst-captures/00230.png)

# Development
Now that all kind of preparation is done, it is time to start development.

## Preparation of plugin development

Before starting plugin development there is no need all necessary files from the empty folder. We prepared the basic template `argos.demo.*` sample. This can be a good to use as a template.

### Copy from template

To download `argos.demo.*` template, first visit site `https://github.com/argos-labs/plugin-demo`.

![00240 visit https://github.com/argos-labs/plugin-demo](https://argos-labs.github.io/images/gst-captures/00240.png)

Click the "Clone or download" and then click `Download ZIP` button.

![00250 download demo](https://argos-labs.github.io/images/gst-captures/00250.png)

* If you unzip the downloaded zip then there is a folder named `plugin-demo-master`.
* Make a new folder `C:\work`.
* Move the folder `plugin-demo-master` into `C:\work`.

![00260 make work folder and move unzipped](https://argos-labs.github.io/images/gst-captures/00260.png)

### Starting PyCharm

It is time to run PyCharm IDE.

* Double click the desktop's `JetBrains PyCharm ...` icon.
* After flash window there come up `Welcome to PyCharm` window.
* Select `Open`.

![00270 start pycharm](https://argos-labs.github.io/images/gst-captures/00270.png)

* Select foler `C:\work\plugin-demo-master`.
* Click `OK` button.

![00280 select folder](https://argos-labs.github.io/images/gst-captures/00280.png)

* Next captured image shows the opened status just after starting.

![00290 IDE starting screen](https://argos-labs.github.io/images/gst-captures/00290.png)

### PyCharm Settings

Just after starting this project you have to do some settings.

* Open `File` menu and select `Settings...` or just type short-cut key `Ctrl+Alt+S`.

![00300 select settings](https://argos-labs.github.io/images/gst-captures/00300.png)

Every project must have specific python interpreter.

* In `Settings` window, select `Project: plugin-demo-master` and then `Project Interpreter`.

![00310 settings project interpreter](https://argos-labs.github.io/images/gst-captures/00310.png)

* To add interpreter click right-most icon at `Project Interpreter` row.
* Select `Add...`

![00320 add interpreter](https://argos-labs.github.io/images/gst-captures/00320.png)

* Select `Existing environment`.
* Select `C:\Users\Administrator\py3\Scripts\python.exe`. (please replace `Administrator` with your own user id)
* Click `OK` button.

![00330 select interpreter](https://argos-labs.github.io/images/gst-captures/00330.png)

After select `C:\Users\Administrator\py3\Scripts\python.exe` interpreter, there are `alabs.ppm` and `alabs.ppm` modules in module list.

![00340 project interpreter](https://argos-labs.github.io/images/gst-captures/00340.png)

Next is optional options.

* In `Settings` windows search `right` keyword at secher input.
* In `Editor>Code Style` change `120` into `80` at `Hard wrap at` item.
> Python coding convention [PEP8](https://www.python.org/dev/peps/pep-0008/) guides `80` columns for editing.
 
![00350 80 column](https://argos-labs.github.io/images/gst-captures/00350.png)

* In `Settings` windows search `typo` keyword at secher input.
* In `Editor>Inspections` uncheck `Typo`. If you want only valid dictionary word at script then leave this item checked. 

![00360 uncheck typo](https://argos-labs.github.io/images/gst-captures/00360.png)

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

