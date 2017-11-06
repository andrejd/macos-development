### Python development on macOS High Sierra
---

> macOS High Sierra already comes with Python 2.7 pre-installed and can be used as it is. If you need to use latest version of Python3, you need to install it.

####  Python3 installation

While macOS comes with a large number of UNIX utilities, those familiar with Linux systems will notice one key component missing, a package manager. `Homebrew` fills this void.

To install Homebrew, open Terminal and run 

```bash
$ ruby -e "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/master/install)"
```

The script will explain what changes it will make and prompt you before the installation begins. Once you’ve installed Homebrew, insert the Homebrew directory at the top of your PATH environment variable. You can do this by adding the following line at the bottom of your ~/.profile file
```bash
export PATH=/usr/local/bin:/usr/local/sbin:$PATH
```

Now, we can install Python 3:

```bash
$ brew install python3
```
This will take a minute or two. After that you are read to go.



