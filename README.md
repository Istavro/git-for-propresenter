# Git for ProPresenter

This project aims to simplify and guide the process of using git and github with Pro Presenter 7.

## Setting up git

#### If you don't have git on your machine, install it:
-[Windows](https://gitforwindows.org/)

-MacOS through [Homebrew](https://brew.sh/)	
```
$ brew install git
```

### Configuring git

#### (On Windows run all of these commands in a 'git bash' terminal where as on MacOS you can run them in a normal terminal instance)

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

### Connecting git to github

#### If you don't already have one, create a [github] (https://github.com) account.

Using the terminal run the following command to check if you have an ssh key
```
ls ~/.ssh/id_ed25519.pub
```

If you get a message saying that no such file exists, that means you don't have an ssh-key, that is perfectly fine and expected as you are going to create one in the next step and connect it to your github account.

Create an ssh-key (If you have an ssh key in skip this step)
```
ssh-keygen -t ed25519 -C <youremail>
```

##### Note the <youremail> is supposed to be removed and replaced with your email.

When it prompts you for a location to save the generated key, just push Enter.

Next, it will ask you for a password; enter one if you wish, but it's not required.

Next Run
```
cat ~/.ssh/id_ed25519.pub
```
and copy the output

#### Link your ssh-key to your github

On Github, click on your profile picture then Settings > SSH and GPG keys then click 'New SSH key' Then paste the output you previously copied into the Key section and add a title (preferably something that lets you know what this key will be used for and/or which computer) Then click 'Add SSH key'
