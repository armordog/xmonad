# Getting Started with Xmonad
_I love Xmonad so much, I hope you will too!_

## Basic Tools

### Start and Stop a Terminal
Press `ALT + SHIFT + ENTER`.
Type `exit` to close.
Use `ARROW UP/DOWN` to navigate previously executed commands.
Use `TAB` to autocomplete folder and files.

### Xmonad
Xmonad is the windowing system. No more bloat. It's heavily customized, but the basics work as usual.
Switch between workspaces: `ALT + 0-9`
Kill a Program: `ALT + SHIFT + C`
Key combinations can be found [here](https://wiki.haskell.org/wikiupload/b/b8/Xmbindings.png).

### Xmobar
Xmobar is the status bar at the top. To customize it use
```shell
vi .config/.xmobarrc
```
To update changes you need to recompile & restart xmonad.

### Start Browser
Type `chrome` into the terminal.

### Vi
Vi is the default, minimalistic file editor. Read all about it [here](https://www.washington.edu/computing/unix/vi.html)

### Copy + Paste
Additional Clipboard: Select text to copy and use middle mouse button to paste
Normal Clipboard: `Ctrl C` to copy, `Ctrl V` to paste, `Ctrl X` to cut

## Update and Installation

### OS and Package Related
Do this regularly!
```shell
sudo apt-get update
sudo apt-get upgrade
sudo apt-get dist-upgrade (might not always be necessary)
sudo apt-get autoremove
```

### Shutdown and Restart Computer
```shell
sudo shutdown -h now
sudo reboot -h now
```

### Install a Package
```shell
sudp apt-get install PACKAGE
```

#### Example
Find the apt-get install package online, let’s take [vlc](http://www.videolan.org/vlc/download-ubuntu.html) as an example.
```shell
sudo apt-get install vlc
```
Open .bash_aliases (dot files are hidden) with
```shell
vi .bash_aliases
```
And press i for edit mode
Add a new line
```shell
alias vlc='vlc &> /dev/null &'
```
This will make sure that when we spawn vlc from the terminal it is started as a new process and error messages are not dumped to our terminal.

Press escape to exit edit mode and save and close the file with `:wq`
Now type close and re-open the terminal. Type `vlc` to run vlc on the computer

### Remove a Package completely
```shell
sudo apt-get purge PACKAGE --auto-remove
```

## Misc

### Change Password
```shell
sudo passwd USERNAME
```

### Taking a Screenshot
```shell
import screenshot.png
```
This will allow you to select an area to screenshot and save it as `screenshot.png` in the current terminal working directory.
If you need to take a delayed screenshot you can use 
```shell
sleep 3; import screenshot.png
```

### File and Directory Management
* List Files and Dirs: `ls`
* List Files and Dirs including hidden: `ls -al`
* List Hierarchy (two levels): `tree -L 2`
* Remove File: `rm [FILENAMe]`
* Remove Empty Directory: `rmdir [DIRNAME]`
* Remove Any Directory: `rm -rf [DIRNAME]`

### Unzip a *.tar.gz file
```shell
tar -zxvf FILENAME
```

## Debug

### Startup Script Error
You might have edited some files that prevent you from logging in. In this case you can press `CTRL + ALT + F3`. Nothing will change on the screen, however when you login now the startup scripts are not run.
