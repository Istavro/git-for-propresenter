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
