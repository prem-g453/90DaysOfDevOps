#### Day 24 – Advanced Git: Merge, Rebase, Stash \& Cherry Pick



##### 

##### Task 1: Git Merge



\### What is a fast-forward merge?

A fast-forward merge happens when there are no new commits in the main branch after branching. Git simply moves the main pointer forward to the latest commit of the feature branch without creating a merge commit.



\### When does Git create a merge commit instead?

Git creates a merge commit when both branches have new commits. This combines histories and preserves branch structure.



\### What is a merge conflict?

A merge conflict occurs when the same line of code is modified in two branches. Git cannot automatically decide which change to keep.



---



##### Task 2: Git Rebase



\### What does rebase actually do to your commits?

Rebase rewrites commit history by placing your feature branch commits on top of the latest commits from the main branch.



\### How is the history different from a merge?

Rebase creates a linear history (clean), while merge keeps branch history (non-linear).



\### Why should you never rebase pushed commits?

Rebasing shared commits rewrites history, causing conflicts and confusion for other collaborators.



\### When would you use rebase vs merge?

\- Use rebase: for clean history (before pushing)

\- Use merge: for shared/public branches



---



##### Task 3: Squash Commit vs Merge Commit



\### What does squash merging do?

Squash merge combines all commits from a branch into a single commit before merging.



\### When would you use squash merge vs regular merge?

\- Squash: small fixes, clean history

\- Merge: preserve commit history



\### What is the trade-off of squashing?

You lose detailed commit history.



---



##### Task 4: Git Stash



\### What is the difference between git stash pop and git stash apply?

\- `git stash pop`: applies and removes stash

\- `git stash apply`: applies but keeps stash



\### When would you use stash in a real workflow?

When you need to switch branches quickly without committing incomplete work.



---



##### Task 5: Cherry Pick



\### What does cherry-pick do?

Cherry-pick applies a specific commit from one branch to another.



\### When would you use cherry-pick?

When you need only a specific fix instead of merging the whole branch.



\### What can go wrong with cherry-picking?

It can cause duplicate commits and conflicts if dependencies are missing.

