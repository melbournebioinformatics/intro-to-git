---
title: 'Instructor Notes'
---

Additional notes:
- Should we do the whole workshop through the VS Code extension? Just reference the commands but don't actually teach them.
- Add the command "on the side"
- RE-DO section on pull requests and conflicts

Notes about this workshop:

- Make sure that Windows users use Git Bash for their commands.
- Use VS Code – it's better than teaching nano. If possible, avoid nano entirely.
- Present graph model of commits early on - can use this repository as example.
    - Use VS Code Git tab for that.
- Windows users can struggle with cloning the R repository because Windows doesn't find the Rscript executable.
- In "`cloning-a-repository.md`", follow steps carefully and in order to avoid problems.
- Practice more switching between branches/commits (`git checkout` command).
    - **This can be done in the `cloning-a-repository.md` episode.** Instead of using `git reset --soft HEAD~1`, we can use `git checkout`, see if the code works, then check back to HEAD (which is broken), and apply the fix

TO-DO notes from sprint 01/08/2025
- Rearrange "your-first-git-repository.md" to first create on GitHub, and then clone.
- This allows to keep learners "fresh" and not burden them with concepts of remotes.
- "tracking-changes.md": do enough changes that we revert both an individual file and also the whole repository. For the whole repository it would be good to revert to a state where certain files don't exist anymore (easier to visualise)
- Introduce branches in "tracking-changes.md" as well. Switch between branches.
- Engineer conflict in "tracking-changes.md" to make sure that they pull remote changes before pushing.
    - `git pull --no-rebase`
  
