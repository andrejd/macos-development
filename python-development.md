## Python development on macOS High Sierra


> macOS High Sierra already comes with Python 2.7 pre-installed and can be used as it is. If you need to use latest version of Python3, you need to install it.

###  _Homebrew_ installation

While macOS comes with a large number of UNIX utilities, those familiar with Linux systems will notice one key component missing, a package manager. `Homebrew` fills this void.

To install Homebrew, open Terminal and run 

```bash
$ ruby -e "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/master/install)"
```

The script will explain what changes it will make and prompt you before the installation begins. Once you’ve installed Homebrew, insert the Homebrew directory at the top of your PATH environment variable. You can do this by adding the following line at the bottom of your ~/.profile file
```bash
export PATH=/usr/local/bin:/usr/local/sbin:$PATH
```

#### Homebrew cheatsheet

Homebrew help is accessible trough `brew -h`, here are some most usefull commands

| Commands                  | Output |
| -----------               | ----------- |
| brew list --versions 	    | List installed packages|
| brew search _package_     | Search for a package|
| brew install _package_    | Install a package |
| brew upgrade _package_	| Upgrade a package|
| brew info _package_	    | List versions, caveats, etc|
| brew home _package_	    | Open homepage|
| brew cleanup _package_	| Remove old versions|
| brew update	            | Update brew |
| brew outdated	            | What’s due for upgrades?|
| brew doctor               | check brew health|

### Xcode Command Line Tools Installation

Xcode and Xcode Command Line Tools needs to be installed to use Python packages. The Command Line Tools Package is a small self-contained package available for download 
separately from Xcode and that allows you to do command line development in macOS. It consists of the macOS SDK and command-line tools such as Clang (C compiler), which are installed in the /Library/Developer/CommandLineTools directory.

First of all, install Xcode if you don’t have it already. You can find it in the Apple Store. Next, install the Command Line Tools of Xcode. Open a Terminal and type:
```
$ xcode-select --install
```
This should trigger a pop-up window that will ask you to install the Command Line Tools.

### Virtual environments

Python virtual environments, managed by `venv`, are set up for installing packages and running programs in a way that isolates them from other packages installed on the rest of the system. Because each environment has its own interpreter executable and directory for installing packages, it is easy to create environments configured with various combinations of Python and package versions all on the same computer.

#### Creating Environments

The primary command line interface to venv relies on Python’s ability to run a “main” function in a module using the -m option.
```bash
$ python3 -m venv /tmp/demoenv
```
Contents of a Virtual Environment

Each virtual environment contains a bin directory, where the local interpreter and any executable scripts are installed, an include directory for files related to building C extensions, and a lib directory, with a separate site-packages location for installing packages.

The default `bin` directory contains “activation” scripts for several Unix shell variants. These can be used to install the virtual environment on the shell’s search path to ensure the shell picks up programs installed in the environment. It’s not necessary to activate an environment to use programs installed into it, but it can be more convenient.

On platforms that support them, symbolic links are used rather than copying the executables like the Python interpreter. In this environment, `pip` is installed as a local copy but the interpreter is a symlink.

2. Using Virtual Environments

Once a virtual environment has been created, it can be “activated” using a script in the virtual environment’s binary directory. The invocation of the script is platform-specific:


```bash
$ source <venv>/bin/activate
```
 
You don’t specifically need to activate an environment; activation just prepends the virtual environment’s binary directory to your path, so that “python” invokes the virtual environment’s Python interpreter and you can run installed scripts without having to use their full path. However, all scripts installed in a virtual environment should be runnable without activating it, and run with the virtual environment’s Python automatically.

You can deactivate a virtual environment by typing `deactivate` in your shell. The exact mechanism is platform-specific: for example, the Bash activation script defines a “deactivate” function.

3. Save installed packages for later use

Save current environment for later setup, do this after installanig new python package

```bash
# save project requrements to file fol later use
$ env1/bin/pip freeze > requirements.txt
# install project requirements in new virtual env
$ env2/bin/pip install -r requirements.txt
```

### Python instalation

Now, we can install Python 3:

```bash
$ brew install python3
```
This will take a minute or two. After that you are ready to go.




