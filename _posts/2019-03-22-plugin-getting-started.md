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

> If you have already your own IDE then skip to [the next section](https://argos-labs.github.io/plugin/plugin-getting-started/#python-3).

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
* Type `python 3.7 windows download`.
* Select first result, [Download Python - Python.org](https://www.python.org/downloads/)

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
> In example machine, the user name is `Administrator`. So the prompt shows `C:\Users\Administrator>`. If your user name is toor then then prompt will show `C:\Users\toor>`. 

```Shell
C:\Windows\system32>python -V
Python 3.7.3

C:\Windows\system32>pip list
Package    Version
---------- -------
pip        19.0.3
setuptools 40.8.0
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

```Shell
C:\>cd %USERPROFILE%

C:\Users\Administrator>python -m venv py3

C:\Users\Administrator>py3\Scripts\activate

(py3) C:\Users\Administrator>pip list
Package    Version
---------- -------
pip        19.0.3
setuptools 40.8.0
```

![00170 cmd python venv](https://argos-labs.github.io/images/gst-captures/00170.png)

## Plugin Package Manager

### Enter Virtual Environment

Above `Making Virtual Environment` section shows how to make a new virtual environment named `py3`. Once the `py3` virtual environment is made, next time you just enter the virtual environment.

```Shell
C:\>cd %USERPROFILE%

C:\Users\Administrator>py3\Scripts\activate

(py3) C:\Users\Administrator>
```

Or directly the execute `activate`.

```Shell
C:\Users\Administrator>%USERPROFILE%\py3\scripts\activate

(py3) C:\Users\Administrator>
```

When everything is done, you need to exit the virtual environment. you can do this `deactivate` command.

```Shell
(py3) C:\Users\Administrator>deactivate
C:\Users\Administrator>
```

![00180 enter venv](https://argos-labs.github.io/images/gst-captures/00180.png)

### Install `Plugin Package Manager`

Our plugin SDK include two parts.
* Plugin Package Manager named `alabs.ppm`
* Plugin library module named `alabs.common`

Next explanation is how to install `Plugin Package Manager`.
* You need command prompt which is entered virtual environment. You can refer above `Enter Virtual Environment` section.
* Install with command: `pip install -U alabs.ppm alabs.icon --index https://pypi-official.argos-labs.com/pypi`

```Shell
(py3) C:\Users\Administrator>pip install -U alabs.ppm alabs.icon --index https://pypi-official.argos-labs.com/pypi
Looking in indexes: https://pypi-official.argos-labs.com/pypi
Collecting alabs.ppm
  Downloading https://pypi-official.argos-labs.com/api/package/alabs-ppm/alabs.ppm-1.627.1628-py3-none-any.whl
Collecting alabs.icon
  Downloading https://pypi-official.argos-labs.com/api/package/alabs-icon/alabs.icon-1.711.2351-py3-none-any.whl (136kB)
    100% |████████████████████████████████| 143kB 655kB/s
Collecting alabs.common (from alabs.ppm)
  Downloading https://pypi-official.argos-labs.com/api/package/alabs-common/alabs.common-1.612.1212-py3-none-any.whl
Collecting requests (from alabs.ppm)
  Using cached https://files.pythonhosted.org/packages/51/bd/23c926cd341ea6b7dd0b2a00aba99ae0f828be89d72b2190f27c11d4b7fb/requests-2.22.0-py2.py3-none-any.whl
Collecting requirements-parser (from alabs.ppm)
  Using cached https://files.pythonhosted.org/packages/03/80/eb6ba1dd0429089436e90e556db50884ea21da060b10f2e5668c4cac99da/requirements-parser-0.2.0.tar.gz
Collecting PyYAML (from alabs.ppm)
  Using cached https://files.pythonhosted.org/packages/f5/93/b5ebdabc7e450418c26a1395d995d878a59bc4272d6ac63d2ada922126ad/PyYAML-5.1.1-cp37-cp37m-win_amd64.whl
Collecting beautifulsoup4 (from alabs.ppm)
  Using cached https://files.pythonhosted.org/packages/1d/5d/3260694a59df0ec52f8b4883f5d23b130bc237602a1411fa670eae12351e/beautifulsoup4-4.7.1-py3-none-any.whl
Collecting icon-font-to-png (from alabs.icon)
  Using cached https://files.pythonhosted.org/packages/3d/70/c3b6c5904ae8592cb97c3ddb5de40801837f66922aa140e285d4a2e49a42/icon_font_to_png-0.4.1-py2.py3-none-any.whl
Collecting certifi>=2017.4.17 (from requests->alabs.ppm)
  Using cached https://files.pythonhosted.org/packages/69/1b/b853c7a9d4f6a6d00749e94eb6f3a041e342a885b87340b79c1ef73e3a78/certifi-2019.6.16-py2.py3-none-any.whl
Collecting urllib3!=1.25.0,!=1.25.1,<1.26,>=1.21.1 (from requests->alabs.ppm)
  Using cached https://files.pythonhosted.org/packages/e6/60/247f23a7121ae632d62811ba7f273d0e58972d75e58a94d329d51550a47d/urllib3-1.25.3-py2.py3-none-any.whl
Collecting chardet<3.1.0,>=3.0.2 (from requests->alabs.ppm)
  Using cached https://files.pythonhosted.org/packages/bc/a9/01ffebfb562e4274b6487b4bb1ddec7ca55ec7510b22e4c51f14098443b8/chardet-3.0.4-py2.py3-none-any.whl
Collecting idna<2.9,>=2.5 (from requests->alabs.ppm)
  Using cached https://files.pythonhosted.org/packages/14/2c/cd551d81dbe15200be1cf41cd03869a46fe7226e7450af7a6545bfc474c9/idna-2.8-py2.py3-none-any.whl
Collecting soupsieve>=1.2 (from beautifulsoup4->alabs.ppm)
  Using cached https://files.pythonhosted.org/packages/35/e3/25079e8911085ab76a6f2facae0771078260c930216ab0b0c44dc5c9bf31/soupsieve-1.9.2-py2.py3-none-any.whl
Collecting Pillow>=4.0.0 (from icon-font-to-png->alabs.icon)
  Using cached https://files.pythonhosted.org/packages/ae/96/6f83deebfcd20a5d4ad35e4e989814a16559d8715741457e670aae1a5a09/Pillow-6.1.0-cp37-cp37m-win_amd64.whl
Collecting six>=1.10.0 (from icon-font-to-png->alabs.icon)
  Using cached https://files.pythonhosted.org/packages/73/fb/00a976f728d0d1fecfe898238ce23f502a721c0ac0ecfedb80e0d88c64e9/six-1.12.0-py2.py3-none-any.whl
Collecting tinycss>=0.4 (from icon-font-to-png->alabs.icon)
  Using cached https://files.pythonhosted.org/packages/05/59/af583fff6236c7d2f94f8175c40ce501dcefb8d1b42e4bb7a2622dff689e/tinycss-0.4.tar.gz
Installing collected packages: certifi, urllib3, chardet, idna, requests, PyYAML, alabs.common, requirements-parser, soupsieve, beautifulsoup4, alabs.ppm, Pillow, six, tinycss, icon-font-to-png, alabs.icon
  Running setup.py install for requirements-parser ... done
  Running setup.py install for tinycss ... done
Successfully installed Pillow-6.1.0 PyYAML-5.1.1 alabs.common-1.612.1212 alabs.icon-1.711.2351 alabs.ppm-1.627.1628 beautifulsoup4-4.7.1 certifi-2019.6.16 chardet-3.0.4 icon-font-to-png-0.4.1 idna-2.8 requests-2.22.0 requirements-parser-0.2.0 six-1.12.0 soupsieve-1.9.2 tinycss-0.4 urllib3-1.25.3
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
---
version: "1.1"

repository:
  url: https://pypi-official.argos-labs.com/pypi
  req: https://pypi-req.argos-labs.com
private-repositories:
- name: pypi-demo
  url: https://pypi-demo.argos-labs.com/simple
  username: guest
  password: guestpasswd
```
> The configuration format is [YAML](https://en.wikipedia.org/wiki/YAML).

* repository is the official plugin module by ARGOS-LABS.
	* url is the default address to access the office repository of ARGOS-LABS.
	* Do NOT change the `https://pypi-official.argos-labs.com/pypi`.
	* Once your plugin is doing well in you private repository and then you can submit the plugin as candidate for the  official repository.
	* If your plugin is submitted to the ARGOS-LABS and your candidate is evaluated and checked not to be harmful.
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
---
version: "1.1"

repository:
  url: https://pypi-official.argos-labs.com/pypi
  req: https://pypi-req.argos-labs.com
private-repositories:
```

![00210 notepad .argos-rpa.conf](https://argos-labs.github.io/images/gst-captures/00210.png)

### alabs.ppm
`alabs.ppm` plugin package manager has many command options.

* To begin with `CMD.EXE` enter virtual environment with command, `%USERPROFILE%\py3\Scripts\activate`
* `alabs.ppm` without any parameter says help output.

```Shell
(py3) C:\work\plugin-demo-master\argoslabs\ai\tts>alabs.ppm
c:\users\administrator\py3\lib\site-packages\alabs\ppm\__init__.py:660: YAMLLoadWarning: calling yaml.load() without Loader=... is deprecated, as the default Loader is unsafe. Please read https://msg.pyyaml.org/load for full details.
  dcf = yaml.load(ifp)
Need command for ppm.
usage: alabs.ppm [-h] [--new-py] [--venv] [--clean] [--verbose]
                 {test,build,submit,upload,clear,clear-py,clear-all,get,install,show,uninstall,search,dumpspec,list,list-repository,pip,py,setup}
                 ...

ARGOS-LABS Plugin Package Manager

This manager use private PyPI repository.
set C:\Users\Administrator\.argos-rpa.conf as follows:

---
version: "1.1"

repository:
  url: https://pypi-official.argos-labs.com/pypi
  req: https://pypi-req.argos-labs.com
private-repositories:
- name: pypi-demo
  url: https://pypi-demo.argos-labs.com/simple
  username: guest
  password: guestpasswd


* repository is the main plugin modules's store
  * url is the url of ARGOS RPA+ main pypi module
  NB) ARGOS RPA+ main module is not allowed to upload directly
      but submit first and then ARGOS team to decide
* private-repositories are the list of user's private plugin modules's store
  * name is the name of private repository (for example "internal", "external")
  * url is the url of pypi module
  * username is the user name at pypi repository
  * password is the user password at pypi repository
  NB) username and password is only needed for upload
      upload is only valid for private repositories

positional arguments:
  {test,build,submit,upload,clear,clear-py,clear-all,get,install,show,uninstall,search,dumpspec,list,list-repository,pip,py,setup}
                        ppm command help
    test                test this module
    build               build this module
    submit              submit to upload server
    upload              upload this module to pypi server
    clear               clear all temporary folders
    clear-py            clear py.win32 virtual environment
    clear-all           clear all temporary folders and virtual environment
    get                 get configuration
    install             install module
    show                show module info
    uninstall           uninstall module
    search              search keywords
    dumpspec            dumpspec keywords
    list                list installed module
    list-repository     list all modules at remote
    pip                 pip command
    py                  python command
    setup               setup command with setup.yaml

optional arguments:
  -h, --help            show this help message and exit
  --new-py              making new python venv environment at py.win32
  --venv                if set use package top py.win32 for virtual env. If not set. Use system python instead.
  --clean, -c           clean all temporary folders, etc.
  --verbose, -v         verbose output eg) -v, -vv, -vvv, ...
```

![00220 clean up windows 10 desktop](https://argos-labs.github.io/images/gst-captures/00220.png)

One of commands is searching specific plugin with a name.
The most official plugin modules are started with `argoslabs.` prefix.
You can search all plugin modules:

```Shell
(py3) C:\work\plugin-demo-master\argoslabs\ai\tts>cd \

(py3) C:\>alabs.ppm search argoslabs
c:\users\administrator\py3\lib\site-packages\alabs\ppm\__init__.py:660: YAMLLoadWarning: calling yaml.load() without Loader=... is deprecated, as the default Loader is unsafe. Please read https://msg.pyyaml.org/load for full details.
  dcf = yaml.load(ifp)
start search ...
argoslabs.data.rdb (1.313.1857)    - 1.313.1857
argoslabs.api.rossum (1.327.1355)  - 1.327.1355
argoslabs.api.rest (1.315.1054)    - 1.315.1054
argoslabs.data.excel (1.325.1359)  - 1.325.1359
argoslabs.data.json (1.324.2344)   - 1.324.2344
argoslabs.ai.tts (1.330.1500)      - 1.330.1500

done.
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

This `pluin-demo-master` project has two demo plugin: 

* `argoslabs\demo\helloworld`: The most simple but complete plugin sample.
* `argoslabs\demo\argtest`: The most complex user arguments sample.

Every plugin has it's own unittest.
Let's just debug the unittest for `argoslabs\demo\argtest`.

## Debug unittest

* Left panel show `Project` list.
* Double click `argoslabs\demo\helloworld\tests\test_me.py`.
* Then in editor pane `test_me.py` shows up.

![00370 select test_me.py](https://argos-labs.github.io/images/gst-captures/00370.png)

* Right click `argoslabs\demo\helloworld\tests\test_me.py`.
* Select `Debug 'Unitests in test_me...'`.
* Then `Debug` pane comes up at bottom.

![00380 debug test_me.py](https://argos-labs.github.io/images/gst-captures/00380.png)

* There are four unit tests.
* The result says, `Ran 4 tests in 0.028s. OK`

![00390 unittest](https://argos-labs.github.io/images/gst-captures/00390.png)

> * Unittest must be implemented and file name must be starts with `test_`.
> * `alabs.ppm test` automatically run all test files starts with `test_`.

# Making New Plugin

It's time making a new plugin named `argoslabs.ai.tts`.
This plugin source is located in [https://github.com/argos-labs/plugin-tts](https://github.com/argos-labs/plugin-tts).

## Making proper python package

Let us categorize `argoslabs` / `ai` / `tts` that is to say `argoslabs.ai.tts`. Above `argoslabs.demo.helloworld` plugin has two python package `demo` and `helloworld`.

So next steps makeing `ai` and `tts` python package.

* To create a `ai` python package, right click the `argoslabs` folder at `Project` pane and then select `New>Python Package`.

![00400 new package](https://argos-labs.github.io/images/gst-captures/00400.png)

* Type `ai` at `New Package` window. 
* Click `OK` button.
* And then sub folder named `ai` is created from `argoslabs`.

![00410 ai package](https://argos-labs.github.io/images/gst-captures/00410.png)

* To create a `tts` python package, right click the `ai` folder and then select `New>Python Package`.

![00010 clean up windows 10 desktop](https://argos-labs.github.io/images/gst-captures/00420.png)

* Type `tts` at `New Package` window. 
* Click `OK` button.
* And then sub folder named `tts` is created from `ai`.

![00010 clean up windows 10 desktop](https://argos-labs.github.io/images/gst-captures/00430.png)

## Copying from HelloWorld

Now let us copy all files and sub folder from `helloworld` to `tts`.

* Expand folder `argoslabs\demo\helloworld`.
* Click first `tests` sub folder.
* Press down `Shift` key and click the last file `setup.yaml` and then release `Shift` key. This action select all sub folder and files.

![00440 copy helloworld](https://argos-labs.github.io/images/gst-captures/00440.png)

* In selected status, right click and select `Copy`.

![00450 copy](https://argos-labs.github.io/images/gst-captures/00450.png)

* Right click `argoslabs\ai\tts` and then select `Paste`.

![00460 paste](https://argos-labs.github.io/images/gst-captures/00460.png)

* The `Copy` window shows up.
* Click `OK` button.

![00470 Copy](https://argos-labs.github.io/images/gst-captures/00470.png)

* The `Copy` windows says, "File '__init__.py' already exists in directory 'C:/work/plugin-demo-master/argoslabs/ai/tts'.
* Click `Overwrite` button.

![00480 overwrite](https://argos-labs.github.io/images/gst-captures/00480.png)

## __init__.py

Plugin's main script is located at `__init__.py` that python package so the file is `argoslabs\ai\tts\__init__.py`.

We can see the doc string from line 3 to 13 in `__init__.py` editor window.
And some comments from line 13 to 23. You can change any contents for this.

![00500 comments](https://argos-labs.github.io/images/gst-captures/00500.png)

You can change the main function from `helloworld` into `do_tts`.

* Select by double click `helloworld` at line 33.
* Type `Shift+F6` keys.
* At `Rename` window type `do_tts`.
* Click `Refactor` button.

![00510 refactor](https://argos-labs.github.io/images/gst-captures/00510.png)

* `Refactoring Preview` pane comes up at bottom side.
* Click `Do Refactor` button.

![00520 do refactor](https://argos-labs.github.io/images/gst-captures/00520.png)

* At lines from 53 to 61 there is a instance definition of `ModuleContext` class with `with` clause.
* This `ModuleContext` class defines the plugin itself.
	* `owner` is the plugin owner. Official plugin's owner is `ARGOS-LABS`.
	* `group` is the group name for plugin.
	* `vresion` is the specific version.
	* `platform` defines the list of running platform.
		* `windows` is for Windows.
		* `darwin` is for Mac OS X.
		* `linux` is for Linux.
	* `output_type` is just for result type. Currently this option is not used any more.
	* `display_name` is the displayed name at `Stu`.
	* `icon_path` is the `icon.*` icon file folder. `get_icon_path(__file__)` is the defult with same folder with `__init__.py`.
	* `description` is the description.

![00530 ModuleContext](https://argos-labs.github.io/images/gst-captures/00530.png)

## change icon

The `helloworld` default icon is:

![00540 default icon](https://argos-labs.github.io/images/gst-captures/00540.png)

But we can change it with:

![00550 new icon](https://argos-labs.github.io/images/gst-captures/00550.png)

> * Your plugin will be submitted to ARGOS-LABS plugin submitted repository.
> * The icon can be changed by ARGOS-LABS for consistency with other icons.

## prerequisite modues

We need some other modules already provided offcial [pypi repository](https://pypi.org).

### requirements.txt

In python prerequisite third party modules defined in [requirements.txt](https://pip.pypa.io/en/stable/user_guide/#requirements-files) file.

We add two prerequisite modues.

* `gTTS` module is for google TTS engine.
* `playsound` module is for play `mp3` or `wave` sound file.

![00560 requirements.txt](https://argos-labs.github.io/images/gst-captures/00560.png)

### Install such prerequisite modues

You can install the prerequisite modues:

* Run `CMD.EXE` and enter virtual environment with command `py3\Scripts\activate`.
* Change into the plugin folder with command `cd \work\pluin-demo-master\argoslabs\ai\tts`.
* You can install modules with command `pip install -r requirements.txt`.

![00570 install requirements.txt](https://argos-labs.github.io/images/gst-captures/00570.png)

## Completion of __init__.py

Now you can complete the `__init__.py` script.

> You can get the complete `argoslabs.ai.tts` [source](https://github.com/argos-labs/plugin-tts).

`argoslabs.ai.tts` plugin takes 5 arguments, so we define 5 argument definition.
5 arguments consists three options and two parameters:

* There are three options.
	* `--save-mp3` or `-o` option is for saving result TTS `mp3` file at line 172 ~ 174. This option need filename to save.
	* `--lang` or `-l` option is for select the language used in TTS engine. Default is `en`, english. This argument need language made by two alphabet.
	* `--slow` or `-s` option is flag to say slowly or not. This option need no more argument.
* There are two parameters which means mandatory arguments at line 182 ~ 185.
	* `engine` argument must be defined. At this source only `google` is allowed.
	* `msg` argument must be defined for saying.

> * Above argument definition is the main key to use ARGOS-LABS RPA+ `Stu` program.
> * We explain it in detailed article. 

![00580 argument](https://argos-labs.github.io/images/gst-captures/00580.png)

We complete the `do_tts` function at line 118~151.
> One of the main advantage using python is simple code than any other programming language.

![00590 do_tts](https://argos-labs.github.io/images/gst-captures/00590.png)

## Unittest for plugin

You can edit test_me.py unittest file, `argoslabs\ai\tts\tests\test_me.py`.

### make your own unittest

* Edit top comments or doc string with your own information.

![00600 test_me](https://argos-labs.github.io/images/gst-captures/00600.png)

Then we can define each unittest functions like `testnnnn_...`:

* `test0100_empty_parameter`: empty user argument make error, exception.
* `test0110_unknown_engine`: other than `google` engine make error, exception.
* `test0120_missing_msg `: without `msg` parameter make error, exception.
* `test0200_say_hello`: say "Hello world?" in english.
* `test0210_say_hello_slow`: say "Hello world?" in english more slowly.
* `test0250_say_hello_ko`: say some words in korean.
* `test0260_say_hello_ja`: say some words in japaneese.
* `test0270_say_hello_zh_cn`: say some words in chineese.
* `test0300_say_hello_save_mp3` and `test0310_say_hello_save_mp3`: say some words in english and keep it with `mp3` file.

> The more unittest make the program more robust moreover when you add new feature all previous unittest used as regression test.

![00610 test_me second page](https://argos-labs.github.io/images/gst-captures/00610.png)

### debug unittest

You can debug the `test_me.py` unittest.

* Right click the `test_me.py` file and then select `Debug 'Unittests in test_me...'`.

![00630 debug test_me](https://argos-labs.github.io/images/gst-captures/00630.png)

* `Debug` pane comes up bottom side.
* Left `Test Results` says the reuslt of all unittest.
* Keep debugging the unittest until every unittest is passed.

![00640 debugging test_me](https://argos-labs.github.io/images/gst-captures/00640.png)

## configuration of plugin

`setup.yaml` is the configuration of plugin.
This is related with [setup.py specification](https://packaging.python.org/tutorials/packaging-projects/).
> Note. Be careful with `argoslabs.ai.tts` before `['icon.*']`. Copyed contents is `argoslabs.demo.helloworld`. If this name is not matched the icon will not show.

![00650 ](https://argos-labs.github.io/images/gst-captures/00650.png)

# build and submit

Once you finished the `__init__.py` main script and `test_me.py` unittest. It's time to build and submit.

## Edit build.bat

All of these job can be run by `build.bat` in Windows using `alabs.pps` plugin package manager.

* `alabs.ppm --venv test` will test all test scripts starts with `test`.
	* `--venv` make the new temporary virtual environment at `%USERPROFILE%\py.windows`.
	* Using this venv every dependent modules are installed from the clean environment.
	* If any unittest is not ok, then exit with `test have error` message. 
	
```bat
REM test
alabs.ppm --venv %VB% test
IF NOT %ERRORLEVEL% == 0 (
	echo "test have error"
    goto errorExit
)
```

* `alabs.ppm --venv build` will build release type of `wheel`.
	* If build command failed, then exit with `build have error` message. 

```bat
REM # build
alabs.ppm --venv %VB% build
IF NOT %ERRORLEVEL% == 0 (
	echo "build have error"
    goto errorExit
)
```

* `alabs.ppm --venv submit` will submit zipped plugin to ARGOS-LABS plugin upload server.
	* Your uploaded zipped plugin can be a candidate of official ARGOS-LABS plugin available to all users.
	* Your candidate code will be scanned and checked with any security issue or harmful code.
	* If your candidate passed then your plugin published to official plugin repository, `pypi.argos-labs.com`.
	* You can skip this `submit` process, instead you can upload this plugin to your own private pypi server and the result is noticed to you by email which is described at `setup.yaml`.
	* If submit command failed, then exit with `submit have error` message. 

```bat
REM # submit to repository
alabs.ppm %VB% submit
IF NOT %ERRORLEVEL% == 0 (
	echo "submit have error"
    goto errorExit
)
```

* `alabs.ppm --venv upload` will upload your plugin release to your private pypi server.
	* If there is no parameter after upload then then first item at `private-repositories` list at `.argos-rpa.conf` file.
	* If you want choose one private pypi server then `name` item will be followed after upload command.
	* You can use your own plugin for your site only with at your own risk. 

```bat
REM # upload to private repository
alabs.ppm --venv %VB% upload
IF NOT %ERRORLEVEL% == 0 (
	echo "upload have error"
    goto errorExit
)
```

> * You can edit your build.bat. If you do not know well then just use this `build.bat`.
> * In Mac OS X or Linux platform you can use `build.sh`.

![00660 build.bat](https://argos-labs.github.io/images/gst-captures/00660.png)

## Run the build.bat

You can run the `build.bat`.

* Run `CMD.EXE` and enter `py3` virtual environment.
* Go to the `tts` folder.
* Run the `build.bat`

```Shell
C:\>%USERPROFILE%\py3\Scripts\activate

(py3) C:\>cd \work\plugin-demo-master\argoslabs\ai\tts

(py3) C:\work\plugin-demo-master\argoslabs\ai\tts>build.bat
```

![00010 clean up windows 10 desktop](https://argos-labs.github.io/images/gst-captures/00670.png)

A few minites later you can see `"Build all success!"`. Then all is done for your side.

![00010 clean up windows 10 desktop](https://argos-labs.github.io/images/gst-captures/00680.png)

Good luck!
