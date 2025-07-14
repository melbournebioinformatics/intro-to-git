---
title: "Fundamental concepts"
teaching: 20
exercises: 0
---

:::::::::::::::::::::::::::::::::::::: questions 

- What are the fundamental concepts of version control?

::::::::::::::::::::::::::::::::::::::::::::::::

::::::::::::::::::::::::::::::::::::: objectives

- Understand the fundamental concepts of Git, such as commits, remotes, and the staging area.

::::::::::::::::::::::::::::::::::::::::::::::::

Before we get started with hands-on work, let's understand some basic concepts about Git. We've already learned that Git tracks different versions of a project by using **commits**, which are like **snapshots of a project**. But let's take a closer look on how this works in practice, by learning about [remotes](../learners/reference.md#glossary) and [the staging area:](../learners/reference.md#glossary)

### Remotes
Think of remotes as "cloud copies" of your Git repository. While you have your project on your local computer, a remote is a version stored on platforms like GitHub or GitLab. Remotes allow multiple people to work on the same project, sharing updates by pushing changes to the remote and pulling others' changes from it. For example, you can push your work to a remote to back it up or collaborate with teammates by pulling their changes into your local project.

### Staging area
The staging area in Git is like a "waiting room" for changes you want to commit. When you modify files, those changes don’t go directly into a commit. Instead, you first add them to the staging area, where you can review and decide what will be included in your next commit. It gives you control to commit only specific changes rather than everything at once. Think of it as preparing ingredients on the counter before putting them into a recipe—you only add what you need.

![](fig/git-staging-area.svg)


:::::::::::::::::::::::::::::::::::::: keypoints

- **Commits** are snapshots of a repository.
- We can have a copy of our repository in a different location, called a **remote**. We can send ("push") and receive ("pull") changes from the remote to interact with others' work, and also to back up or update our local copy.
- The **staging area** is where we keep track of the changes that we are going to commit, that is, which are going to be written in the repository history.

::::::::::::::::::::::::::::::::::::::
