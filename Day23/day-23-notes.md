#### Day 23 – Git Branching \& Working with GitHub



##### Task 1: Understanding Branches



\### What is a branch in Git?

A branch in Git is a separate line of development. It allows you to work on features or fixes without affecting the main codebase.



\### Why do we use branches instead of committing everything to main?

Branches help in:

\- Keeping the main branch stable

\- Working on features independently

\- Avoiding conflicts

\- Collaborating with teams efficiently



\### What is HEAD in Git?

HEAD is a pointer that refers to the current branch or commit you are working on.



\### What happens to your files when you switch branches?

When switching branches:

\- Git updates your working directory

\- Files change to match the selected branch

\- Uncommitted changes may be affected or blocked



---



##### Task 2: Branching Commands – Hands-On



\### Commands Used:



\# List branches

git branch



\# Create branch

git branch feature-1



\# Switch to branch

git checkout feature-1



\# Create and switch in one command

git checkout -b feature-2



\# Using modern command

git switch feature-1



\# Switch to main

git switch main



\# Delete branch

git branch -d feature-2



---



\## Difference: git switch vs git checkout



\- git checkout:

&nbsp; - Used for switching branches and restoring files

\- git switch:

&nbsp; - Only used for switching branches

&nbsp; - More clear and safer



---



##### Task 3: Push to GitHub



\### Steps:



\# Add remote

git remote add origin <repo-url>



\# Push main branch

git push -u origin main



\# Push feature branch

git push -u origin feature-1



---



\### Difference: origin vs upstream



\- origin:

&nbsp; - Your fork or your GitHub repo



\- upstream:

&nbsp; - Original repository you forked from



---



##### Task 4: Pull from GitHub



\# Pull changes

git pull origin main



---



\### Difference: git fetch vs git pull



\- git fetch:

&nbsp; - Downloads changes but does not merge



\- git pull:

&nbsp; - Downloads + merges changes



---



##### Task 5: Clone vs Fork



\### Difference:



\- Clone:

&nbsp; - Copy of repository to local machine



\- Fork:

&nbsp; - Copy of repository to your GitHub account



---



\### When to use:



\- Clone:

&nbsp; - When you have direct access to repo



\- Fork:

&nbsp; - When contributing to someone else's repo



---



\### Keeping fork updated:



\# Add upstream

git remote add upstream <original-repo-url>



\# Fetch updates

git fetch upstream



\# Merge updates

git merge upstream/main

