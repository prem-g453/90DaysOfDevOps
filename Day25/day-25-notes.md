#### Day 25 – Git Reset vs Revert \& Branching Strategies



##### Task 1: Git Reset — Hands-On



Experiment Observations



git reset --soft

\- Moves HEAD to previous commit

\- Changes remain in staging area

\- Nothing is lost



git reset --mixed (default)

\- Moves HEAD to previous commit

\- Changes remain in working directory

\- Removed from staging



git reset --hard

\- Moves HEAD to previous commit

\- Deletes all changes from staging and working directory

\- Data is lost (destructive)



Answers



Difference between --soft, --mixed, --hard



| Option | HEAD Move | Staging Area | Working Directory |

|--------|----------|-------------|------------------|

| --soft | Yes | Preserved | Preserved |

| --mixed | Yes | Cleared | Preserved |

| --hard | Yes | Cleared | Cleared |



Which one is destructive and why?

\- --hard is destructive because it permanently deletes uncommitted changes.



When to use each one?

\- --soft → When you want to edit last commit

\- --mixed → When you want to unstage changes

\- --hard → When you want to completely discard changes



Should you use reset on pushed commits?

\- No, it rewrites history and can break collaboration



---



##### Task 2: Git Revert — Hands-On



Observations



\- Reverting commit Y creates a new commit that undoes Y

\- Commit Y still exists in history



Answers



How is revert different from reset?

\- Reset removes commits from history

\- Revert adds a new commit to undo changes



Why is revert safer?

\- It does not rewrite history

\- Safe for shared branches



When to use revert vs reset?

\- Use reset for local changes (not pushed)

\- Use revert for shared/public branches



---



##### Task 3: Reset vs Revert — Comparison



| Feature | git reset | git revert |

|--------|----------|-----------|

| What it does | Moves HEAD backward | Creates new undo commit |

| Removes history? | Yes | No |

| Safe for shared branches? | No | Yes |

| When to use | Local undo | Public/shared undo |



---



##### Task 4: Branching Strategies



1\. GitFlow



How it works

\- Multiple branches: main, develop, feature, release, hotfix



Flow

main ← release ← develop ← feature



Used in

\- Large teams, scheduled releases



Pros

\- Structured workflow

\- Stable production code



Cons

\- Complex

\- Slower development



---



2\. GitHub Flow



How it works

\- Single main branch

\- Feature branches → Pull Request → merge



Flow

main ← feature branch → PR → merge



Used in

\- Startups, continuous deployment



Pros

\- Simple

\- Fast development



Cons

\- Less control for large teams



---



3\. Trunk-Based Development



How it works

\- Everyone commits to main (trunk)

\- Short-lived branches



Flow

main ← small frequent commits



Used in

\- High-speed teams



Pros

\- Fast integration

\- Fewer merge conflicts



Cons

\- Requires discipline and strong testing



---



Answers



Best for startup shipping fast

\- GitHub Flow



Best for large team with releases

\- GitFlow



Open-source example

\- Many projects like React use GitHub Flow



---



##### Task 5: Git Commands Reference Update



Reset \& Revert Commands



```bash

git reset --soft HEAD~1

git reset --mixed HEAD~1

git reset --hard HEAD~1



git revert <commit-hash>

git reflog

