# Command Line Basics

While the command line might seem like an old relic of the past that is only used by cool movie hacker, the command line is used way more frequently than anyone would think. This simple tutorial aims to help you get started a terminal powered by a unix-like shell.

## Getting started

If you use a mac or a linux system then you already have all you need, simply openup a terminal windows and follow with the rest of the guide.

If you use a windows system, then you might have relised that windows doesn't come with a unix-like shell, but in the modern world that doesn't seem to be a problem as there are many ways to get a unix-like enviornment working on windows.

### Using Windows Subsystem for Linux (WSL)

WSL pretty much aims to emulate a linux enviornment inside of windows, you can learn more about this and how to get it working on the [official Microsoft WSL documentation](https://learn.microsoft.com/en-us/windows/wsl/install).

This method is most useful for those who want to get as close of an experience to a unix-like system without actually install one in a virtual machine or on bare metal.

### Using git bash temrinal (Recommended)

This guide is meant to be used in tandem with my git-for-ProPresenter guide, in that guide you are suggested to install git using [git for windows](https://gitforwindows.org/), the people behind git for windows decided to build the tool on top of MSYS2 which provides a minimal unix-like shell enviornment  for the users to use.

To sum what I just said up, just follow the first step of my git-for-ProPresenter guide or just go to [git for windows](https://gitforwindows.org/) and the version of git you install there should come pre-shipped with a git-bash tool (optained in the right click menu) which imitates a unix-like enviornment for you to use in this tutorial.

## Print the current working directory (pwd)

### To kick off the guide, you will either need to open a terminal window on mac/linux or right click and open 'git bash' on windows.

Now type in the following command to print the directory you are currently located in:
```
pwd
```
You should now get the full path to where you are currently located, this might not seem that useful now but we will need to utilize it in the later steps to help you better navigate in the terminal.

## List (ls)

`ls` is a simple command that just shows all the files in your current working directory, if you pass the `-l` argument it displays it in a way that makes it easier for humans to read, and if you pass in the `-a` argument, it shows all files even the hidden ones whos name starts with a . (dot).
```
ls -la
```

## Change directory (cd)

Now that you know where you are located, type `cd` to navigate to your home directory.

Your home directory (symbolised by the ~ sign) is pretty much where your user account lives, this directory usually contains all your picture, documents, configuration files, etc... if you type `pwd` in here you should see the exact path to your home directory.

By only typing `cd` without any other arguments, your shell just assumes that you want to go to your home directory so it puts you there. But what if you wanted to move to other directories?

Firstly list all the directories that reside within your home directory using `ls -la` as shown above, the pick any random directory within there and type:
```
cd directory-name
```
where you replace 'directory-name' with the directory you chose to go into.

To move into multiple directories at a time simply type:
```
cd path/to/directory
```
Where you replace 'path/to/directory' by the path to the directory you want to navigate to.

## . and .. directory

Those with a keen eye might have relised that when typing `ls -la` into their terminal, there were 2 directories with names '.' and '..', and these two directories seem to follow wherever you navigate on your system, so what are they?

To put is simply, . indicates the current directory and .. indicates the directory that comes before that.

For example if you type `pwd` the run:
```
cd .
```
Then run `pwd` again, you will relise that you haven't changed your directory, why? because the path you parsed to `cd` is where you are currently located, so if you were located in /home/username/coolfolder then `cd .` would pretty much be the same as `cd /home/username/coolfolder`.

Now type `pwd` again and run the following command:
```
cd ..
```
As usual run `pwd` to check your current directory and you might have relised that you have changed directory to the folder that comes before the directory you originally started at, for example using /home/username/coolfolder again, typing `cd ..` would lead us to changing our directory to /home/username.

## Relative and Absolute paths

TBD

## Moving files/folders (mv)

#### If you want to, you can just move, rename, delete, etc... your files through a graphical user interface, these following guides are here just incase you want to use the terminal to achieve these tasks.

To move a file or a folder type the following command:
```
mv file-name path/to/new/directory
```

where 'file-name' is the name of the file or folder you want to move and 'path/to/new/directory' is where you want to move it to.

### Rename a file using mv:

To rename a file type:
```
mv file-name new-file-name
```

Here you are pretty much moving the contents of a file to a new file with a different name.

## Print file content to the terminal (cat)

To print a file's content to the terminal, simply type:
```
cat file-name
```

## Make files (touch)

To create a file type the following in the terminl:
```
touch file-name
```

## Create a directory (mkdir)

To create a directory Type the following command:
```
mkdir directory-name
```

Now what if you wanted to create a folder within the a folder but the parent folder doesn't exist? For example lets say you are located in /home/username and want to create a folder called 'cool-folder' inside your working directory but you also want to create a folder inside of that call 'cooler-folder' you can:
```
mkdir cool-folder
```
```
mkdir cool-folder/cooler-folder
```

Or alternatively just use the `-p` option which checks if the directory you are creating's parent exists and if not it creates it:
```
mkdir -p cool-folder/cooler-folder
```

## Editing a text file (nano)

To edit a text file in the terminal, type:
```
nano file-name
```

When opening nano, you will relise that there is a list of all the shortcuts you will need at the very bottom, while the symbols might look confusing, pretty much any shortcut starting with a '^' means `ctrl + letter-key` and any shortcut starting with a 'M-' means `alt + letter-key`.

`^X` is `ctrl + X` and `M-E` is `alt + E`

When you are done editing a file, press `ctrl + x` and you should be asked if you want to save, if you press Y for yes then you will be prompted to write the file name where you want to write all the changes to, if you want to keep the same file name just press enter.
