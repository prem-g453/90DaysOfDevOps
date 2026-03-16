#### Git Commands Cheat Sheet



This file contains Git commands I learned while starting my Git journey.



---



##### 1\. Setup \& Configuration



git --version

Shows the installed Git version.



Example:

git --version



---



git config --global user.name "Your Name"



Sets your Git username.



Example:

git config --global user.name "Prem Goswami"



---



git config --global user.email "your@email.com"

Sets your Git email.



Example:

git config --global user.email "prem@email.com"



---



git config --list

Displays all Git configuration settings.



Example:

git config --list



---



##### 2\. Repository Initialization



git init

Creates a new Git repository in the current directory.



Example:

git init



---



git status

Shows the current state of the working directory and staging area.



Example:

git status



---



##### 3\. Basic Workflow



\### git add

Adds files to the staging area.



Example:

git add git-commands.md



---



git commit

Saves staged changes to the repository.



Example:

git commit -m "Add initial git commands reference"



---



##### 4\. Viewing Changes



git log

Shows the full commit history.



Example:

git log



---



git log --oneline

Shows commit history in compact format.



Example:

git log --oneline



---



git diff

Shows changes between working directory and last commit.



Example:

git diff

