# python_venv

In Raspbian 12 **Bookworm**, user are not longer allowed to install packages system-wide using pip. Below is an example of the error

```
pi@raspberrypi:~$ sudo pip3 install gpiozero
error: externally-managed-environment

× This environment is externally managed
╰─> To install Python packages system-wide, try apt install
    python3-xyz, where xyz is the package you are trying to
    install.
    
    If you wish to install a non-Debian-packaged Python package,
    create a virtual environment using python3 -m venv path/to/venv.
    Then use path/to/venv/bin/python and path/to/venv/bin/pip. Make
    sure you have python3-full installed.
    
    If you wish to install a non-Debian packaged Python application,
    it may be easiest to use pipx install xyz, which will manage a
    virtual environment for you. Make sure you have pipx installed.
    
    See /usr/share/doc/python3.11/README.venv for more information.

note: If you believe this is a mistake, please contact your Python installation or OS distribution provider. You can override this, at the risk of breaking your Python installation or OS, by passing --break-system-packages.
hint: See PEP 668 for the detailed specification.
```

## Installing a virtual environment

1. To install **Python Virtualenv**

```
sudo apt install virtualenv python3-virtualenv -y
```

2. To create a new virtual environment

```
python3 -m venv --system-site-packages <enviroment_name>
```
**Note** - the virtual environment will be a folder

3. To activate virtual environment

```
source <environment_folder>/bin/activate
```

4. To install a package

```
pip3 install python-osc
```

5. To deactivate environment

```
deactivate
```

## To copy virtual environment

1. Generate dependencies file

```
pip3 freeze > requirements.txt
```

This will generate a requirement file at the current working directory.

2. To install dependencies in new enviroment

```
source <environment_folder>/bin/activate
```

```
pip3 install -r ~/<directory>/requirements.txt
```

## References
1. Using virtual environment - Click [here](https://blog.piwheels.org/debian-bookworm-and-raspberry-pi-5/#:~:text=If%20you%20wish%20to%20install,you%20have%20python3%2Dfull%20installed.)
2. Copy environment - Click [here](https://stackoverflow.com/questions/7438681/how-to-duplicate-virtualenv)