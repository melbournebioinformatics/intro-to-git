---
title: "Tracking changes"
teaching: 20
exercises: 0
---

:::::::::::::::::::::::::::::::::::::: questions

- How do we create a Git repository?
- What are some of the basic Git commands?

::::::::::::::::::::::::::::::::::::::::::::::::

::::::::::::::::::::::::::::::::::::: objectives

- Create our first Git repository.
- Learn basic Git commands such as `init`,`status`, `add`, `log`, and `diff`.

::::::::::::::::::::::::::::::::::::::::::::::::

We have successfully created a repository (yay!) so let's start making some changes so we understand how version control works. At the moment, our repository is completely empty (with exception of the `.git` directory), so can create a few files to get started.

Any code project should have a **README** file, which, at the very least, should provide a brief overview of the contents of that project directory. Even though our directory is empty, we can get started with a README file:

```bash
touch README.md
```

The `touch` command creates an empty file. We will be formatting our README file in [Markdown](https://www.markdownguide.org/). If you haven't heard of Markdown, basically it's a simple, easy-to-use language [markup language](https://en.wikipedia.org/wiki/Markup_language) which GitHub fully supports.

::::::::::::::::::::::::::::::::::::: prereq

Markdown files are plain text files. Even though Markdown has a range of features (such as acting as an extension of HTML), we can stick to the basics:

- `#` creates Level 1 Headings (usually the page title).
- `##` creates Level 2 Headings (usually the different sections in the page).
- Subsequent Heading levels can be created with `###`, `####`, etc.
- Backticks (\`\`) create `mono-spaced text, useful for formatting code.`
- \*\* **Bold text is written with double-asterisks.** \*\*
- \*\*Italics is written with a single-asterisk.\*\*

:::::::::::::::::::::::::::::::::::::

Now open `README.md` on your favourite text editor, such as VS Code, nano, Vim, or good old Notepad, and let's
add some content (we recommend that you use VS Code):

```bash
nano README.md
```

Add the following content:

```output
# 'gitgood' repository

A repository to learn how to use Git.
```

If you type in `git status` and see what it shows:

```bash
git status
```

```output
On branch main

No commits yet

Untracked files:
  (use "git add <file>..." to include in what will be committed)
        README.md

nothing added to commit but untracked files present (use "git add" to track)
```

It's similar to what we had the first time, but we can see that it showed an **untracked file**. Git has detected that a new file has been created, but it's not performing any version control for it. We must first **commit** this file to our repository. Let's do so by using two fundamental Git commands:

```bash
git add README.md
```

The `git add <FILENAME>` command **adds a file to the staging area.** We learned in the previous section that the **staging area** is where we store the changes that we intend to **commit** to the repository. We can see the effect that this has on the repository by typing `git status` again:

```bash
git status
```

```output
On branch main

No commits yet

Changes to be committed:
  (use "git rm --cached <file>..." to unstage)
        new file:   README.md
```

Depending on the version of Git you have, the output may be slightly different. But the main things is that this change, that is, of creating a new file, has **been staged, and is now ready to be committed**. Therefore, the `git add` command is used to **add files to the staging area**. Now that these changes area ready to be committed, we can move on with the next command:

```bash
git commit -m "Add repository README"
```

```output
[main (root-commit) 62a9ebb] Add repository README
 1 file changed, 4 insertions(+)
 create mode 100644 README.md
```

The `git commit` command effectively records the changes that we made and added to the staging area **into the repository history.** Now, we've created another snapshot of the repository, one that has the changes that we've made, compared to the previous one where the repository was empty.

::::::::::::::::::::::::::::::::::::: callout

**Commit Messages**

The `-m` in the `git commit` command means `--message`, that is, the message associated with that particular commit. **You should always write descriptive messages** of what has been done in a particular commit.

After all, one of the reasons of why Git is so powerful and adopted is that it allows you to document your work as you go, and this is largely done by writing (good) commit messages. This may seem a bit excessive at first, such as having to write something everytime you press "Save" on a Word document, but as your project grows and you add more and more code to it, it's important to be able to see what has been done in each commit. You can also just type `git commit` without the `-m`, in this case a text editor will pop up in the Terminal prompting you to write a commit message.

We will learn **how to write good commit messages** later on in this lesson. But basically we want to describe **what** we changed and **why** we changed it.

:::::::::::::::::::::::::::::::::::::

Now that we have made our first commit, let's check the `git status` again:

```bash
git status
```

```output
On branch main
nothing to commit, working tree clean
```

The message is a bit different than before. Now, we don't see `No commits yet`, but rather, that we don't have anything to commit. That is because we haven't changed anything in the repository since our last commit.

::::::::::::::::::::::::::::::::::::: callout

Now that we have a commit, we can learn a new command:

```bash
git log
```

```output
commit 62a9ebbef3d7a9e0e07f2344a86f10fa58e7479c (HEAD -> main)
Author: Vini Salazar <17276653+vinisalazar@users.noreply.github.com>
Date:   Mon Sep 9 14:58:43 2024 +1000

    Add repository README
```

The `git log` command shows a list of our commits. We can see the commit **checksum** (the long code after the word `commit`), the associated author and email, **which is the same user name and email that we set up with `git config` earlier**, the timestamp of the commit, and the commit message. The `git log` command is useful to get an understanding of recent activity in the repository.

:::::::::::::::::::::::::::::::::::::

Let's modify the `README.md` file again and add some new lines:

````output hl_lines="5 6"
# 'gitgood' repository

A repository to learn how to use Git.

## Section 1
How to git good at version control.

We've added the `## Section 1` which will represent a new section of text in our Markdown document, and added a little bit of normal text underneath it.

Let's see how this affects our repository by running `git status` again:

```bash
git status
````

```output
On branch main
Changes not staged for commit:
  (use "git add <file>..." to update what will be committed)
  (use "git restore <file>..." to discard changes in working directory)
        modified:   README.md

no changes added to commit (use "git add" and/or "git commit -a")
```

Now that Git is keeping track of `README.md`, any changes that we make to the file will be tracked, so Git knows that we modified the file and added some lines to it. The same goes for when we delete lines from a file.

::::::::::::::::::::::::::::::::::::: caution

Git will only detect differences in files which have been previously committed to the history. If the file is **untracked**, like `README.md` was before our first commit, Git will not record any changes. Be mindful of this, because if you make changes to untracked files, you may not be able to revert them to a previous version!

:::::::::::::::::::::::::::::::::::::

he `git status` command shows that `README.md` was modified, but let's have a look at **what specific changes happened**. We can do this by running a new command:

```bash
git diff
```

```output
diff --git a/README.md b/README.md
index 24e122d..e96d76a 100644
--- a/README.md
+++ b/README.md
@@ -2,3 +2,5 @@

 A repository to learn how to use Git.

+## Section 1
+How to git good at version control.
```

The `git diff` command shows the specific lines that have been changed. Lines that were added will have a `+` next to them and will be highlighted in green, and lines that were removed will have a `-` and will be highlighted in red. `git diff` is very useful in combination with `git status`, so we can see the current state of the repository and what has been changed.

Let's add and commit that change, and check out log again:

```bash
git add README.md
git status  # (1)!
git diff  # (2)!
git commit -m "Drafting Section 1 of README"
git log
```

1. Check that `README.md` has been moved to the staging area.
2. `git diff` doesn't show the change anymore. Why do you think that is?

We can see another commit has been added to the history.

```output
commit 7d3487ad746e2cd6e0beaab3271de9e300a267ca (HEAD -> main)
Author: Vini Salazar <17276653+vinisalazar@users.noreply.github.com>
Date:   Mon Sep 9 15:32:45 2024 +1000

    Drafting Section 1 of README

commit 62a9ebbef3d7a9e0e07f2344a86f10fa58e7479c
Author: Vini Salazar <17276653+vinisalazar@users.noreply.github.com>
Date:   Mon Sep 9 14:58:43 2024 +1000

    Add repository README
```

**Well done!** You've learned 6 new commands, and the fundamentals of version control. With this alone, you can start tracking changes in your local repository. Next, we are going to learn how to interact with GitHub, based on what we've done so far.

::::::::::::::::::::::::::::::::::::: keypoints

We learned several new commands. Let's take note of them:

- `git init` initialises a Git repository, which is contained within the hidden `.git` directory.
- `git status` shows the current state of the repository, such as _which files have been changed._
- `git add` adds a file to the **staging area**, where we gather all of the changes that will be committed.
- `git commit` writes the changes to history, permanently recording them to the repository.
- `git log` shows the list of commits in the repository.
- `git diff` shows the changes between the last commit and the current repository, showing _how files have been changed_.

::::::::::::::::::::::::::::::::::::::::::::::::
