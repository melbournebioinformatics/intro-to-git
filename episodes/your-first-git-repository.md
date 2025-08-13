---
title: 'Your first Git repository'
teaching: 20
exercises: 1
---

:::::::::::::::::::::::::::::::::::::: questions 

- How do we create a Git repository?
- What are some of the basic Git commands?

::::::::::::::::::::::::::::::::::::::::::::::::

::::::::::::::::::::::::::::::::::::: objectives

- Create our first Git repository on GitHub.
- Learn basic Git commands such as `init`,`status`, `add`, `log`, and `diff`.

::::::::::::::::::::::::::::::::::::::::::::::::

Now that we've learned the basics of version control, and reasons to use it, let's get some hands-on experience on how to create our first Git repository.

Let's start navigating to the Desktop folder and creating a new directory there.

```bash
cd
cd Desktop
mkdir gitgood
cd gitgood
```

Now that you're in the new `gitgood` directory, we can start a new repository with the following command:

```bash
git init
```

You should see a message like this:

```output
Initialized empty Git repository in /home/username/Desktop/gitgood/.git/
```

If we try to list the files in the repository, we can't see anything. Try again with the `-a` option:

```bash
# This doesn't show anything
ls

# This shows the following
ls -a
```

```output
. .. .git
```

We can see that we have created the `.git` directory. This hidden directory (hidden files and directories start with `.` character) will contain the Git repository, with all of the data that will be read and written by Git. If we delete this directory, we will lose all of the version control data stored by Git.

::::::::::::::::::::::::::::::::::::: challenge

**Hidden Files**

Based on your previous knowledge of UNIX command line, try answering the following:  
1. Why did the first `ls` command did not show anything?  
2. What does the `-a` mean when we run `ls`?  
3. If we don't know what the `-a`, or any other command flags mean, how can we find out?  
4. What do the `.` and `..` files mean?

::::::::::::::::::::::::::::::::::::: solution

1. By default, `ls` does not display hidden files (starting with a `.` character). The `.git` directory hidden by default when we create it.  
2. `-a` shows **all** of the files and directories, including hidden ones.  
3. If we don't know what a command-line flag means, we can try looking for the command in the man pages, for example by typing `man ls`.  
4. The `.` and `..` files respectively refer to the current directory and the directory one level above (the `Desktop`, in this case).

:::::::::::::::::::::::::::::::::::::

:::::::::::::::::::::::::::::::::::::

We can now try one of the most important Git commands, which tells us the current state of our repository:

```bash
git status
```

```output
On branch main

No commits yet

nothing to commit (create/copy files and use "git add" to track)
```

We can use `git status` as much as we want to check the state of the repository. In this case, there isn't anything very interesting, but once we start accumulating changes, it will become very useful.

::::::::::::::::::::::::::::::::::::: caution 

**Nested Directories**

Once we have run `git init` on a directory, there is no need to run it again in subdirectories of the original directory.
That's why we should run the command on the **parent directory** of the project and we can include additional subdirectories as needed.

:::::::::::::::::::::::::::::::::::::

::::::::::::::::::::::::::::::::::::: keypoints 

- `git init` initializes a repository.
- Git stores all of its repository data in the `.git` directory.

::::::::::::::::::::::::::::::::::::::::::::::::

