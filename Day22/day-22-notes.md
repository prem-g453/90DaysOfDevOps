#### Day 22 – Git Basics Notes





##### 1\. Difference between git add and git commit



git add moves changes from the working directory to the staging area.

git commit saves the staged changes permanently in the Git repository.



---



##### 2\. What does the staging area do?



The staging area allows us to prepare changes before committing them.

It helps select which changes should be included in the next commit instead of committing everything at once.



---



##### 3\. What information does git log show?



git log shows:

\- Commit ID (hash)

\- Author name

\- Date of commit

\- Commit message



---



##### 4\. What is the .git folder?



The .git folder stores all Git data such as:

\- commit history

\- branches

\- configuration

\- repository metadata



If the .git folder is deleted, the project is no longer a Git repository and all version history is lost.



---



##### 5\. Difference between working directory, staging area, and repository



Working Directory:

Where we edit project files.



Staging Area:

A temporary area where changes are prepared before committing.



Repository:

The database where Git stores the full commit history.

