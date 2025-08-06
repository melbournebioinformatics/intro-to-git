---
title: Setup
---

This lesson will teach you how to manage software projects with the popular version control system *Git*.

The example project will assume a basic understanding of either Python or R, and learners are expected to be comfortable using simple commands in a Bash shell.

The lesson assumes learners are working with a Linux style shell (i.e. zsh on MacOS or GitBash on Windows) inside the *VS Code* IDE.

It is important that students complete these setup tasks before the workshop.


## Environment Management with Conda

::::::::::::::::::::::::::::::::::::::: discussion

### Details

In this workshop we will use `conda` to manage Python environments and install packages.

Our preferred flavour of `conda` is provided by Miniforge3, but you could also use `Miniconda`.



:::::::::::::::::::::::::::::::::::::::::::::::::::



:::::::::::::::: spoiler

### Windows

After installing miniforge you will use `conda` from within the `GitBash` shell to manage environments and software instalation. See "Installing Git" below.

1. Install the latest version of [Miniforge3](https://conda-forge.org/miniforge/#latest-release)
2. Open the `miniforge prompt` app and run the command `conda init bash`

::::::::::::::::::::::::

:::::::::::::::: spoiler

### MacOS

1. Install the latest version of [Miniforge3](https://conda-forge.org/miniforge/#latest-release)

Note: Select the "x86_64" for Intel processors, or "Arm64" for Apple Silicon chips.  

Check installation:

- Open the `Terminal` app.
- Check for `(base)` prefix in your prompt.
- Run `conda --version`


::::::::::::::::::::::::


## Installing Git


:::::::::::::::: spoiler

### Windows

Windows users will need to install `GitBash` which is a linux-like terminal that comes pre-installed with `Git`.

You will use `conda` from within the `GitBash` shell to manage environments and software instalation.

1. Install [GitBash](https://gitforwindows.org/)

Windows checks:

- Open the `GitBash` terminal app.
- Check for `(base)` prefix in your prompt.
- If `(base)` is not present, open the "miniforge prompt" app and run `conda init bash`
- Open a new `GitBash` terminal session.
- Run `conda --version`
- Run `git --version`

::::::::::::::::::::::::


:::::::::::::::: spoiler

### Mac

Open the Terminal app and run `git --version`. You may be prompted to install git.

Note: You may be prompted to install Xcode which will take some time.

::::::::::::::::::::::::


## Configure Git

If you are setting up Git for the first time, you will need to set your user name and email.

**IMPORTANT:**

- You must use same email as your github account.
- You should use an email address that you will always have access to (not a work or university address).

```bash
git config --global user.name "Alfredo Linguini"
git config --global user.email "a.linguini@gmail.com"
```

Please use your own name and email address instead of Alfredo's. And make sure you use the same email associated with your GitHub account.

We will also set the default editor as `nano`.

```bash
git config --global core.editor "nano -w"
```

## Setup Github

### Create a GitHub account

Create a new account at [GitHub.com](github.com}) if you do not have one.

Again, use an email address that you will always have access to (not a work or university address).

### Configure SSH access

If you do not have ssh set up for git [create a new ssh key](https://docs.github.com/en/authentication/connecting-to-github-with-ssh/generating-a-new-ssh-key-and-adding-it-to-the-ssh-agent) and [add the key](https://docs.github.com/en/authentication/connecting-to-github-with-ssh/adding-a-new-ssh-key-to-your-github-account) to your github account.

Note: On windows you should do this from the GitBash shell.

To confirm that your key is correctly configured run:

```bash
ssh -T git@github.com
```

## VS Code setup

VS Code is a popular Interactive Development Environment (IDE) that we will use to edit our project.

[Follow the VS Code installation instructions here.](https://code.visualstudio.com/Download)

If you are on Windows, also follow the steps below:

:::::::::::::::: spoiler

### Windows

1. Open VS Code and set GitBash as default terminal.
2. From the `View` menu select `Command Palette --> Terminal: Select Default Profile`.
3. Then select `GitBash` as the default profile.

::::::::::::::::::::::::