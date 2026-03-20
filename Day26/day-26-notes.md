#### Day 26 – GitHub CLI (gh)





GitHub CLI (gh) is a command-line tool that allows developers to interact with GitHub directly from the terminal. It helps reduce context switching and enables automation of GitHub workflows.





##### Task 1: Installation \& Authentication



Commands



gh --version

gh auth login

gh auth status

Observations



Installed GitHub CLI successfully



Logged in using browser-based authentication



Verified active account using gh auth status



Answer



What authentication methods does gh support?



Browser-based authentication



Personal Access Token (PAT)



SSH authentication



##### Task 2: Working with Repositories



Commands



gh repo create my-test-repo --public --clone

gh repo list

gh repo view my-test-repo

gh repo view --web

gh repo delete my-test-repo --confirm

Observations



Created a repository directly from terminal



Cloned repository automatically



Viewed repository details in terminal



Opened repository in browser using CLI



Deleted repository safely



##### Task 3: Issues



Commands



gh issue create --title "Test Issue" --body "This is a test issue" --label bug

gh issue list

gh issue view 1

gh issue close 1

Observations



Created issue with title, description, and label



Listed all issues in repository



Viewed specific issue by number



Closed issue from terminal



Answer



How could you use gh issue in automation?



Automatically create issues from CI/CD failures



Log errors or bugs from scripts



Integrate with monitoring tools to raise alerts



##### Task 4: Pull Requests



Commands



git checkout -b feature-test

echo "Hello DevOps" >> test.txt

git add .

git commit -m "Added test file"

git push origin feature-test



gh pr create --fill

gh pr list

gh pr view

gh pr merge

Observations



Created branch and pushed changes



Created pull request directly from terminal



Viewed PR details including status and checks



Merged PR without using browser



Answers



What merge methods does gh pr merge support?



Merge commit



Squash merge



Rebase merge



How would you review someone else's PR using gh?



Checkout PR using gh pr checkout <number>



Review changes locally



Add comments or approve using gh pr review



##### Task 5: GitHub Actions (Preview)



Commands



gh run list

gh run view <run-id>

Observations



Listed workflow runs of repository



Viewed detailed status of specific workflow



Answer



How could gh run and gh workflow be useful in CI/CD?



Monitor pipeline executions from terminal



Debug failed workflows quickly



Automate deployment checks and status tracking



##### Task 6: Useful gh Commands



Commands



gh api repos/{owner}/{repo}

gh gist create file.txt

gh release create v1.0

gh alias set co "pr checkout"

gh search repos devops

Observations



Interacted with GitHub API directly



Created and managed gists



Managed releases from terminal



Created custom shortcuts for commands



Searched repositories without browser



Conclusion



GitHub CLI enhances productivity by allowing full control of GitHub from the terminal. It is especially useful for DevOps workflows, automation, and reducing dependency on the browser.



