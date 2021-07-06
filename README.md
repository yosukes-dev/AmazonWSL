# AmazonWSL
Amazon Linux on WSL (Windows 10 FCU or later)
based on [wsldl](https://github.com/yuk7/wsldl)

![screenshot](https://raw.githubusercontent.com/yosukes-dev/AmazonWSL/master/img/screenshot.png)

[![CircleCI](https://circleci.com/gh/yosukes-dev/AmazonWSL.svg?style=svg)](https://circleci.com/gh/yosukes-dev/AmazonWSL)
[![Github All Releases](https://img.shields.io/github/downloads/yosukes-dev/AmazonWSL/total.svg?style=flat-square)](https://github.com/yosukes-dev/AmazonWSL/releases)
[![PRs Welcome](https://img.shields.io/badge/PRs-welcome-brightgreen.svg?style=flat-square)](http://makeapullrequest.com)
![License](https://img.shields.io/github/license/yosukes-dev/AmazonWSL.svg?style=flat-square)

### [Download](https://github.com/yosukes-dev/AmazonWSL/releases)


## Requirements
* Windows 10 Fall Creators Update x64 or later. 
* Windows Subsystem for Linux feature is enabled.

## Install
#### 1. [Download](https://github.com/yosukes-dev/AmazonWSL/releases) installer zip

#### 2. Extract all files in zip file to same directory

#### 3.Run Amazon2.exe to Extract rootfs and Register to WSL
Exe filename is using to the instance name to register.
If you rename it you can register with a diffrent name and have multiple installs.

## Icon settings for Windows Terminal
![terminal-icon](https://raw.githubusercontent.com/yosukes-dev/AmazonWSL/master/img/terminal-icon.png)

The following is an example of `profiles.json` if you extracted to `C:\`
```
{
    "guid": "{dc13e3b1-2863-5b9b-9749-3a31bc67a12a}",
    "hidden": false,
    "name": "Amazon2",
    "source": "Windows.Terminal.Wsl",
    "icon": "C:\\Amazon2\\assets\\icon.png"
}
```

## How-to-Use(for Installed Instance)
#### exe Usage
```dos
Usage :
    <no args>
      - Open a new shell with your default settings.

    run <command line>
      - Run the given command line in that distro. Inherit current directory.

    runp <command line (includes windows path)>
      - Run the path translated command line in that distro.

    config [setting [value]]
      - `--default-user <user>`: Set the default user for this distro to <user>
      - `--default-uid <uid>`: Set the default user uid for this distro to <uid>
      - `--append-path <on|off>`: Switch of Append Windows PATH to $PATH
      - `--mount-drive <on|off>`: Switch of Mount drives
      - `--default-term <default|wt|flute>`: Set default terminal window

    get [setting]
      - `--default-uid`: Get the default user uid in this distro
      - `--append-path`: Get on/off status of Append Windows PATH to $PATH
      - `--mount-drive`: Get on/off status of Mount drives
      - `--wsl-version`: Get WSL Version 1/2 for this distro
      - `--default-term`: Get Default Terminal for this distro launcher
      - `--lxguid`: Get WSL GUID key for this distro

    backup [contents]
      - `--tgz`: Output backup.tar.gz to the current directory using tar command
      - `--reg`: Output settings registry file to the current directory

    clean
      - Uninstall the distro.

    help
      - Print this usage message.
```

#### Just Run exe
```cmd
>Amazon2.exe
[root@PC-NAME user]#
```

#### Run with command line
```cmd
>Amazon2.exe run uname -r
4.4.0-43-Microsoft
```

#### Run with command line with path translation
```cmd
>Amazon2.exe runp echo C:\Windows\System32\cmd.exe
/mnt/c/Windows/System32/cmd.exe
```

#### Change Default User(id command required)
```cmd
>Amazon2.exe config --default-user user

>Amazon2.exe
[user@PC-NAME dir]$
```

#### Set "Windows Terminal" as default terminal
```cmd
>Amazon2.exe config --default-term wt
```

#### How to uninstall instance
```dos
>Amazon2.exe clean

```
