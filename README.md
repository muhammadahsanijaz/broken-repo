# Broken Repo

## Overview

Repo had several issues, below is a summary of what I found and how I fixed them.


## Task 1 - Overviewing the project and finding issues

Identified 3 problematic commits:
Most major was commit of the secret key as it cause vulnerability and dataleak.
Reviewed the commit history and identified three problematic commits. 
Found a mixed commit with unrelated changes, a commit with incorrect content in todo.txt.

Please see full details in `TASK1_FINDINGS.md`

## Task 2: Splitting the "qick fix" Commit into 3 seperate commit

First, used interactive rebase this `quick fix` and I inserted the edit to the commit to keep the history. Then Added all 3 files in 3 different commits and commit them with proper messages.


## Task 3: Fix the Mistake

It was simple. Just used revert to keep history intact and bad commit was also removed.
Safe for the team whole have already pulled.

## Task 5: Leaked Secret

I did this before task 4 as this those two were relevant. 
As mentioned in the guidlines, I used the unblocking of the secret to pushable to the github. If in the real case I will do the `filter-repo` to check all the secret if any released before and then force push cleaning them after coordinating the team. Best approach here should be envrionment variables or use the secrets manager.

## Task 4: Merge Conflict
I merged the feature/login branch into main. The I resolved conflicts in notes.txt and README.md files to preserving both changes as asked.


## Task 6: Rebase vs Merge

I rebased feature/login onto the latest main to bring it up to date. I chose rebase over direct merge to keep the history clean and avoiding unnecessary merge commits.


## Task 7: Recovering Lost Commit

I used git reflog to locate a commit that was lost during rebase. I recovered its data by checking out the commit hash to a new branch, preserving the work that contained project notes. I think that was best approach.

## How to Avoid These Issues on a Team

- Use branch protection rules - no direct pushes to main
- Never hardcode secrets - use `.env` files and add them to `.gitignore`
- Always use `git revert` on shared branches, never `git reset`
- Small, focused commits - one logical change per commit