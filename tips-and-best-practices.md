---
title: 'Tips and best practices'
teaching: 20
exercises: 0
---

:::::::::::::::::::::::::::::::::::::: questions 

- How do we incorporate Git into our everyday work?
- What are some tips and best practices for working with Git?

::::::::::::::::::::::::::::::::::::::::::::::::

::::::::::::::::::::::::::::::::::::: objectives

- Learn best practices that help make the most out of Git.

::::::::::::::::::::::::::::::::::::::::::::::::

Next up, let's look at some tips and best practices to incorporate Git into your day-to-day work.

### How to incorporate Git in your day-to-day work

Adopting Git for beginners can be daunting at first. There are many commands to learn, it requires constant interaction with the command line, and instead of just pressing "Save", or "Ctrl+S", you have to type in a message everytime you want to record your work. However, there are strategies to mitigate or circumvent these problems.

One of them is to **think of Git as a digital research notebook.** Even if you're not doing full-blown software engineering, but rather just recording a data analysis project, Git is very useful in the sense that you can document your work as you execute it. Every time you commit a change, you are creating a structured record of that change, which is appropriate for data compliance requirements in most scenarios. By using Git to record your work, you are not only guaranteeing that you will have a back up of your code and the possibility of reverting specific changes if something breaks, but also creating a digital notebook of the what you have done. By thinking of Git like this, you can build up a habit of, for example, committing your work at the end of each day, describing what you have done, much like you would don on a laboratory notebook.

The second strategy to **take advantage of existing solutions to use Git**. This could mean plugins for your IDE, the [GitHub Desktop client](https://desktop.github.com/download/), or other services like [GitKraken](https://www.gitkraken.com/). Git is a well-established software with many, many tools that support. Take advantage of that instead of struggling with the Git command-line.

The third strategy is to, at the very least, **to think of Git as a backup tool**. Even though you may create backups of your code in platforms like Dropbox or Google Drive, you would have to sync your backups regularly in other to keep track of an evolving code base. By using Git, you can rest assured that you will have a cloud backup of your code, and you can rely on it in case your local machine stops working.

### Ignoring unnecessary files with `.gitignore`

Another important best practice is to **keep your repository clean by using a `.gitignore` file**.  
This file tells Git which files or folders it should completely ignore — meaning they won’t be tracked or committed.  

For example, you might not want to include:

- temporary files (e.g. `*.log`, `.DS_Store`)  
- large datasets or binary files  
- results or plots that can be regenerated  
- configuration files specific to your computer  

You can create a `.gitignore` file at the root of your repository and list one pattern per line:

```bash
# Example .gitignore
data/
results/
*.log
.DS_Store
```

::::::::::::::::::::::::::::::::::::: callout

### When to commit?

It is common for Git beginners to not know exactly *when* to commit their changes. Since commits can be seen as "checkpoints", a good time to commit changes is **when things are working as intended.** Are you trying to fix a bug, and the error message changed? Even though the code is not fully working, that may be worth a commit to record that you are on the right track. When you fix the code for certain, it is *definitely* worth a commit! Don't wait until things break again, because if you haven't committed your changes when the code was working, you won't be able to revert back to it. If you are making big changes to a file, such as writing large chunks of documentation, you can split your commits into different sections. For example, commit after you have finished drafting the Introduction, and then again after you've finished drafting the Methodology. You can make additional commits later when you are reviewing and editing your text.

When you're first starting with some new code or making fast progress on a project, you don't have to commit every single line of code (although this may be required if you're submitting changes to a large code base!). But it's important to start developing a feeling of "would I want/need to come back to this checkpoint if I had to?"

::::::::::::::::::::::::::::::::::::: 

#### Leveraging the GitHub interface
In regards to the second strategy of using existing solutions, you can do most Git operations very easily through the GitHub web interface. GitHub has advanced tremendously over the years, and not only you can do most basic operations directly through the interface, it also offers a number of features such as the ability to [set up web pages](https://docs.github.com/en/pages); [autolinked references and URLs](https://docs.github.com/en/get-started/writing-on-github/working-with-advanced-formatting/autolinked-references-and-urls) and [linking pull requests to issues](https://docs.github.com/en/issues/tracking-your-work-with-issues/linking-a-pull-request-to-an-issue), which help with project management; automated workflows through [GitHub Actions](https://docs.github.com/en/actions), and many others.


### Do's and Dont's

::::::::::::::::::::::::::::::::::::: checklist
**Do:**

- Write good commit messages
    - Say **why**, not **what** you changed
    - Document as you code
- Make small changes
- Commit often
- Ignore large files (use `.gitignore`)

::::::::::::::::::::::::::::::::::::: 

::::::::::::::::::::::::::::::::::::: caution 
**Dont's:**

- Make vague commit messages
- Accumulate unrelated changes in a single commit
- Let things go stale – delete or "stash" them
- Commit large files to history – they will be there forever.

:::::::::::::::::::::::::::::::::::::

::::::::::::::::::::::::::::::::::::: keypoints 

- There are a number of strategies to incorporate Git into your day-to-day work.
- The learning curve can seem steep at first, but with time you will understand how valuable Git is and it will become easier and easier to use.
- GitHub offers numerous features that make adopting Git easier, and enable you to showcase your projects.
- There are a few best practices which will dramatically improve your efficiency with Git.

::::::::::::::::::::::::::::::::::::::::::::::::

