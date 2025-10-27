---
title: Setup
---

Please follow the steps below and install the required software **before** the scheduled workshop.

<!--
FIXME: Setup instructions live in this document. Please specify the tools and
the data sets the Learner needs to have installed.

## Data Sets

FIXME: place any data you want learners to use in `episodes/data` and then use
       a relative link ( [data zip file](data/lesson-data.zip) ) to provide a
       link to it, replacing the example.com link.
Download the [data zip file](https://example.com/FIXME) and unzip it to your Desktop
-->
## Software Setup

We use VS Code for general coding. Make sure to install VS Code for your operating system following the instructions below:

- [Windows](https://code.visualstudio.com/docs/setup/windows)
- [macOS](https://code.visualstudio.com/docs/setup/mac)
- [Linux](https://code.visualstudio.com/docs/setup/linux)


::::::::::::::::: discussion

### Windows users

If you are a Windows user, you may also need WSL, the Windows Subsystem for Linux. WSL will allow you to use the Terminal from within VS Code and to execute UNIX style commands.

Follow the [official instructions here.](https://learn.microsoft.com/en-us/windows/wsl/install)

After installing WSL, you will also need to install [GitBash](https://gitforwindows.org/).

After installing GitBash, change the default Terminal executable on VS Code:

1. Open VS Code.
2. From the `View` menu select `Command Palette --> Terminal: Select Default Profile`.
3. Select `GitBash` as the default profile.

✅ You're all set to use VS Code with GitBash on Windows. 

::::::::::::::::::::::::::::


<!--
READ HERE FOR OS-SPECIFIC INSTRUCTIONS

Setup for different systems can be presented in dropdown menus via a `spoiler`
tag. They will join to this discussion block, so you can give a general overview
of the software used in this lesson here and fill out the individual operating
systems (and potentially add more, e.g. online setup) in the solutions blocks.
-->

<!--
:::::::::::::::: spoiler

### Windows

Use PuTTY

::::::::::::::::::::::::

:::::::::::::::: spoiler

### MacOS

Use Terminal.app

::::::::::::::::::::::::


:::::::::::::::: spoiler

### Linux

Use Terminal

::::::::::::::::::::::::
-->


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

### macOS

Open the Terminal app and run `git --version`. You may be prompted to install git.

Note: You may be prompted to install Xcode which will take some time.

::::::::::::::::::::::::


:::::::::::::::: spoiler

### Linux

Your Linux distribution likely comes with Git. If not, [click here and follow the instructions](https://git-scm.com/install/linux).

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

## Environment management with conda

For certain workshops, you may need to install [conda](https://docs.conda.io/en/latest/), an open-source software and package management system. This is usually necessary when working with Python code.

Our preferred flavour of conda is [miniforge](https://github.com/conda-forge/miniforge), but you could also use [miniconda](https://www.anaconda.com/docs/getting-started/miniconda/main).

[Click here and follow the miniforge installation instructions for your OS.](https://conda-forge.org/download/)
