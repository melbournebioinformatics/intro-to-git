---
title: 'Cloning a repository'
teaching: 20
exercises: 2
---

:::::::::::::::::::::::::::::::::::::: questions 

- How do we collaborate with Git?
- How do we get code from GitHub into our computer?
- How do we revert changes that we do not want?

::::::::::::::::::::::::::::::::::::::::::::::::

::::::::::::::::::::::::::::::::::::: objectives

- *Clone* a repository and the `git clone` command.
- *Pull* changes and the `git pull` command.
- Revert a change that was made and broke the code.

::::::::::::::::::::::::::::::::::::::::::::::::

To start, we have two repositories to choose from, one in **Python** and one in **R**. Both repositories contain the same thing: a script that calculates the GC content of the sequences in a given FASTA file. Pick the language that you're most comfortable with to proceed:

- [**Python repository**](https://github.com/melbournebioinformatics/python_gc_content)
- [**R repository**](https://github.com/melbournebioinformatics/R_gc_content)

Take a note of the contents of each repository:
- A README file
- The script with the code
- An example data file
- A LICENSE file

Clone your chosen repository locally using the `git clone` command.

::::::::::::::::::::::::::::::::::::: checklist

### Cloning a repository

1. Click the `< > Code` button on the top right of the repository's contents.

![](fig/clone_repo_gh.png)

This copies the remote's URL to your clipboard.

2. Navigate to a suitable directory (**not** inside our previous `gitgood` repository), such as the Desktop directory, and run `git clone <URL>`

![](fig/clone_repo_cli.png)

:::::::::::::::::::::::::::::::::::::

Well done! You now have a local copy of the code. Cloning is a powerful feature that allows us to effortlessly create a copy of an existing repository. If you make your code available on GitHub, people can clone it and customise it.

### Undoing changes

Now, let's try running the code in the repository:

::::::::::::::::::::::::::::::::::::: tab

### Python

```bash
python python_gc_content.py example.fasta
```

### R

```bash
Rscript R_gc_content.R example.fasta
```

:::::::::::::::::::::::::::::::::::::

You most likely got an error message like this one:

::::::::::::::::::::::::::::::::::::: tab

### Python

```output
File "/path/to/python_gc_content/python_gc_content.py", line 45
   print(f"Overall GC Content: {gc_content:.2f}%"
         ^
SyntaxError: '(' was never closed
```

### R

```output
Error: unexpected '}' in:
"  cat(sprintf("Overall GC Content: %.2f%%\n", gc_content)
}"
Execution halted
```

:::::::::::::::::::::::::::::::::::::

Let's explore the log on the repository. Run `git log`:

![](fig/git_log_break_code.png)

Apparently, the last commit purposefully breaks the code so that we can fix it ourselves! We wouldn't know that if it weren't for a descriptive commit message.

Now, there are two things we could do:

1. Go back to the previous commit to inspect the working version of the code.  
2. Fix the code ourselves and commit the changes.

There are multiple ways to move between commits in Git. Here, we will use the `git checkout` command:

```bash
git checkout HEAD~1

# # You could also run the following
# git checkout 82c8425
```

This tells Git to “check out” the commit that came just before the current one (`HEAD~1`, or the commit ID `82c8425`).
In other words, we’re temporarily moving our working directory to the previous commit so we can look at what the code was like before it broke. Let’s check the files in our project now — you’ll see that the broken code is gone.

The output message shows that we’re in what Git calls a "detached HEAD" state:

```bash
Note: switching to 'HEAD~1'.

You are in 'detached HEAD' state. You can look around, make experimental
changes and commit them, and you can discard any commits you make in this
state without impacting any branches by switching back to a branch.

If you want to create a new branch to retain commits you create, you may
do so (now or later) by using -c with the switch command. Example:

  git switch -c <new-branch-name>

Or undo this operation with:

  git switch -

Turn off this advice by setting config variable advice.detachedHead to false

HEAD is now at 82c8425 Code is working
```

This simply means we’re no longer “on” a branch — we’re just viewing a past snapshot of the project.
From here, we can examine the code or even copy the fixed version.

If you want to see what changed in the broken commit, you can use:


```bash
git diff main
```

::::::::::::::::::::::::::::::::::::: tab

### Python

```output
diff --git a/python_gc_content.py b/python_gc_content.py
index 81aa457..8ec3fc4 100644
--- a/python_gc_content.py
+++ b/python_gc_content.py
@@ -42,7 +42,7 @@ def main():
   fasta_file = sys.argv[1]
   full_sequence = read_fasta(fasta_file)
   gc_content = calculate_gc_content(full_sequence)
-    print(f"Overall GC Content: {gc_content:.2f}%")
+    print(f"Overall GC Content: {gc_content:.2f}%"

if __name__ == "__main__":
   main()
```

### R

```output
diff --git a/R_gc_content.R b/R_gc_content.R
index abb31f4..e6fe7f0 100644
--- a/R_gc_content.R
+++ b/R_gc_content.R
@@ -26,7 +26,7 @@ main <- function() {
   full_sequence <- read_fasta(fasta_file)
   gc_content <- calculate_gc_content(full_sequence)

-  cat(sprintf("Overall GC Content: %.2f%%\n", gc_content))
+  cat(sprintf("Overall GC Content: %.2f%%\n", gc_content)
}

# Call main function if script is run
```

:::::::::::::::::::::::::::::::::::::

We can see that the code broke because a closing parenthesis was removed in the last commit.

When you’re done inspecting this older version, return to the latest state of the project with:

```bash
git checkout main
```

This brings you back to the most recent commit on your main branch.
You can now fix the broken code yourself, add your changes, and commit them as usual.

<!-- ::::::::::::::::::::::::::::::::::::: callout 

**Git reset alternatives**

Running these two commands, that is, to unstage and restore the changes after `git reset`, would be the equivalent of running:

```bash
git reset --hard HEAD~1
```

In this case, using the `--hard` flag undoes all of the changes from the current state (the `HEAD`) to the specified state (in this case, one commit previous to the `HEAD`). The reason we may want to use `--soft` instead of `--hard` is that sometimes we may not want to lose all of our uncommitted changes, but rather review them on a case-by-base basis.

Another thing we could do is:

```bash
git checkout HEAD~1
```

The `git checkout` command is use to transition between **branches**. We haven't gone into the concept of branches yet so we will leave this one alone for now. But basically, by using `git checkout`, we can navigate between the repository at different points in time (that is, at each commit).

::::::::::::::::::::::::::::::::::::: -->

Now that we have fully restored the breaking changes, let's try running the code again:

::::::::::::::::::::::::::::::::::::: tab

### Python

```bash
python python_gc_content.py example.fasta
```

### R

```bash
Rscript R_gc_content.R example.fasta
```

:::::::::::::::::::::::::::::::::::::

The result should be:

```output
Overall GC Content: 57.98%
```

This was the first way that we could fix what wrong with the code, by reverting to a previous version that we know that worked. Let's try the second approach, of fixing the change ourselves in a new commit. First, let's undo what we did by running `git reset`. By doing that, we moved to a previous commit in time. That means that our local copy is **one commit behind the remote**. So, we can go back to the broken version simply by running:

```bash
git pull
```

This will sync the remote with the local.


::::::::::::::::::::::::::::::::::::: challenge

Now, try perfoming the fix yourself. Once you make sure that the new code works, run `git add`, `git commit`. Raise your hand or put up a green post-it when you are done.

::::::::::::::::::::::::::::::::::::: solution

::::::::::::::::::::::::::::::::::::: tab

### Python

```bash
python python_gc_content.py example.fasta
```

### R

```bash
Rscript R_gc_content.R example.fasta
```

:::::::::::::::::::::::::::::::::::::

:::::::::::::::::::::::::::::::::::::

:::::::::::::::::::::::::::::::::::::

**Well done!** You fixed a broken a script and committed the result using Git. That is no easy feat! It will pave your way to making more contributions in the future.

After making sure that the code works, push your changes using `git push`. What happens then?

Because the repository that we cloned is under Melbourne Bioinformatics, we don't have write access to it. In order to push the code to GitHub, we need our own copy of the code, so we must **fork** the repository. Let's see how to do that.


::::::::::::::::::::::::::::::::::::: keypoints 

- `git clone` copies a remote repository to our local repository.
- `git checkout` allows us to move between commits – back and forth through a repository's timeline.
- `HEAD` indicates the current state of the repository. `HEAD~1`, `HEAD~2` refer to one or two commits before the current
- We cannot push to a remote repository if we do not have access to it.

::::::::::::::::::::::::::::::::::::::::::::::::

