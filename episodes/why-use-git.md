---
title: "Why use Git?"
teaching: 10
exercises: 0
---

:::::::::::::::::::::::::::::::::::::: questions 

- Why use version control?

::::::::::::::::::::::::::::::::::::::::::::::::

::::::::::::::::::::::::::::::::::::: objectives

- Understand the benefits of Git in everyday life as a researcher.

::::::::::::::::::::::::::::::::::::::::::::::::

### Why use version control?

Now that we've learned what version control **is**, let's understand why we should use it as researchers.

There are a number of reasons to argue that using version control will make us better researchers. That is because 
version control systems can be used for:

### Backing up your code
The most fundamental idea of version control is that you can use it to safely back up your code. That means not only
having a copy of it, but having a copy of each version as your code evolves throughout time. If you use version control
effectively, it will be very difficult for your code to be permanently lost, deleted or erased.

### Sharing your code
Although Git is already explicitly designed to work in a distributed manner, modern version control platforms
make sharing code with others even easier. If our repository is public, anyone can easily access it, copy, and modify the code as they please.
You can make your GitHub profile a portfolio of your coding and analysis projects, with a user-friendly interface.

**Packaging and distribution**

Platforms such as GitHub provide a number of features that facilitate **packaging** our code. One thing is to have a bunch of scripts in
a repository, but if we want to distribute our code effectively, to make it easier for users to acquire and install our code, we can bundle
it as a **software package** and upload it to platforms such as [PyPI](https://pypi.python.org/) (for Python) or [CRAN](https://cran.r-project.org/) (for R).

### Collaborating
Sharing code with others is one thing, but Git also enables researchers to work *together* on the same project. You can review other users' commits,
and selectively apply or reject changes that they propose. This is further enabled by GitHub, which makes it easy to do it through the web interface.
Moreover, you can create organisations to host multiple projects, give collaborators write and admin access to projects, and give access to private repositories.

:::::::::::::::::::::::::::::::::::::: discussion

**The 'Lingua Franca' of software engineering**
        
Because of the way Git enables collaboration, it has essentially become the way that programmers interact on a technical basis.
If you want to make a contribution to a large code base or project, most likely you will have to submit your changes through Git.
GitHub also allows the creation of **issues**, where you can report problems or create discussions about the code. Knowing Git will
probably be required if you want to work in coding projects with other people (including past and future you!)

::::::::::::::::::::::::::::::::::::::

### Documenting your work**  
Because changes in Git are structured through commits, it is very straightforward to document our work as we go. Whenever we create a commit,
we must write a message that's attached to it (we'll learn more about that), which almost mandates that we document what we are doing. This will
create a [history](../learners/reference.md#glossary) of our work which can effectively be used as a **digital research notebook** if done correctly. The way Git works also allows the creation of [branches](../learners/reference.md#glossary) and [tags](../learners/reference.md#glossary), which can be used to keep track of different parts of the development. This is especially useful for large projects where many people may be working on different things in parallel.

:::::::::::::::::::::::::::::::::::::: keypoints

Why using Git will make you **a better researcher:**

- You know you can always go back to a working version of your code
- You will have a way of showcasing your projects
- You will be able to distribute your code to others
- You will be able to modify other peoples' code and make contributions to it
- You will have a digital lab notebook 

::::::::::::::::::::::::::::::::::::::
