# Git for ProPresenter

This project aims to simplify and guide the process of using git and github with Pro Presenter 7.

#### This guide intensly uses the command line (Bash shell to be exact), If you don't feel comftorable using a terminal, checkout [my command line guide](command-line-basics.md)

If you want a quick cheat sheet with all the important commands, then checkout the ones by [github](https://education.github.com/git-cheat-sheet-education.pdf) and [ATLASSIAN](https://www.atlassian.com/git/tutorials/atlassian-git-cheatsheet), they each have some differences so make sure to go over both to find exactly what you want. Alternatively use the [manual pages](https://linux.die.net/man/) to better understand the arguments that you can parse into a command and when you should do it (Note: the man pages include documentation for many terminal tools other than git so you can use them for those tools aswell)

# Setting up git

#### If you don't have git on your machine, install it:
-[Windows](https://gitforwindows.org/)

-MacOS through [Homebrew](https://brew.sh/)	
```
$ brew install git
```

## Configuring git

#### On Windows run all of these commands in a 'git bash' terminal where as on MacOS you can run them in a normal terminal instance

Add your email and name

```
git config --global user.name "Your name"
```
```
git config --global user.email "youremail@example.com"
```

#### (Optional) Use the main naming scheme


As the world is moving away from the master naming scheme, it might be more conveniet for you to switch away aswell to avoid any confusion.

To switch to main naming scheme run:
```
git config --global init.defaultBranch main
```

## Connecting git to github

#### If you don't already have one, create a [github](https://github.com) account.

Using the terminal run the following command to check if you have an ssh key
```
ls ~/.ssh/id_ed25519.pub
```

If you get a message saying that no such file exists, that means you don't have an ssh-key, that is perfectly fine and expected as you are going to create one in the next step and connect it to your github account.

Create an ssh-key (If you have an ssh key in skip this step)
```
ssh-keygen -t ed25519 -C <youremail>
```

##### Note the'<>' is supposed to be removed and replaced with your email.

When it prompts you for a location to save the generated key, just push Enter.

Next, it will ask you for a password; enter one if you wish, but it's not required.

Next Run
```
cat ~/.ssh/id_ed25519.pub
```
and copy the output

## Link your ssh-key to your github

On Github, click on your profile picture then Settings > SSH and GPG keys then click 'New SSH key' Then paste the output you previously copied into the Key section and add a title (preferably something that lets you know what this key will be used for and/or which computer) Then click 'Add SSH key'

# Using Git

Before we implement git's workflow into our usual Pro Presenter workflow, we first have to learn how to use git, this is what this section aims to achieve.

For now, we will use the current repository you are reading this on as a "learning" repository to give you a better idea of how to use git, later on you will learn how to apply the skills you learned in your Pro Presenter workflow.

<img align="right" width="300" src="./assets/fork.png" alt="fork this repository">

## Fork this repository

Fork this repository by clicking on the fork button on the top of this page.
This will create a copy of this repository in your account.

## Clone the forked repository

<img align="right" width="300" src="./assets/clone.png" alt="clone your fork of this repository">

Now clone the forked repository to your machine. Go to your GitHub account, open the forked repository, click on the code button and then click 'SSH' the _copy to clipboard_ icon.

Open a terminal and run the following git command:

```
git clone "url you just copied"
```

where "url you just copied" (without the quotation marks) is the to this repository (your fork of this project). See the previous steps to obtain the url.

<img align="right" width="300" src="./assets/copy-to-clipboard.png" alt="copy SSH URL to clipboard">

For example:

```
git clone git@github.com:your-name/git-for-propresenter.git
```

where 'your-name' is your GitHub username. Here you're copying the contents of the git-for-propresenter repository from github into your computer.

## Creating a branch

Creating multiple branches lets us mess around within these branches without actually making changes inside of our main local branch, if we like the changes made we can later on merge them into our main branch or push the branch into a remote repository (Github repository in this case).

To create a branch change to the repository directory on your computer (if you are not already there):

```
cd git-for-propresenter
```

Now create a branch and automatically switch to that branch using the `git switch` comand:

```
git switch -c your-new-branch name
```

For example:

```
git switch -c test-branch
```
## Make necessary changes and commit those changes

Now open `favourite-foods.md` file in a text editor (`nano` in this case), add your name and favourite food to it. Don't add it at the beginning of the file. 

To open the file type:
```
nano favourite-foods.md
```
<img align="right" width="450" src="./assets/git-status.png" alt="git status" >

If you go to the project directory and execute the command `git status`, you'll see there are changes.

Add those changes to the branch you just created using the `git add` command:

```
git add favourite-foods.md
```

Now commit those changes using the `git commit` command:

```
git commit -m "Add your favourite-food to the favourite-foods.md list"
```
replacing 'favourite-food' with your favourite food.

#### In a proffesional enviornment, it is necessary to have good commit messages as it is the only thing a person will be looking for when looking at the commit history. Checkout this well written [CBEAMS](https://cbea.ms/git-commit/) article for more information on how to write a good git commit message.

## Push changes to GitHub

Push your changes using the command `git push`:

```
git push origin -u your-branch-name
```

replacing `your-branch-name` with the name of the branch you created earlier.

## Sumbit your changes to be merged in.

If you go to your repository on GitHub, you'll see a `Copmare & pull request` button. Click on that button.

<img style="float: right;" src="./assets/compare-and-pull.png" alt="create a pull request" />

Now leave a message about what you changed and pull request.

<img style="float: right;" src="./assets/submit-pull-request.png" alt="submit pull request" />

I will try to merge your changes as soon as possible so you can see your changes being displayed in this repository, You will get a notification email once the changes have been merged.
