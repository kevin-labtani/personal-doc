# Git and Github

## Create a new repository

1. create the repo on github
1. initialize it with a README.md and a gitignore, as needed
1. clone it with `git clone https://github.com/user-name/name-of-repo.git`

## Add an existing project to GitHub

1. Create a new repository on GitHub. To avoid errors, do not initialize the new repository with README, license, or gitignore files.
1. `git init`
1. `git add .`
1. `git commit -m "First commit"`
1. `git remote add origin https://github.com/user-name/name-of-repo.git`
1. `git remote -v` Verifies the new remote URL
1. `git push -u origin master`

## How it works:

![How it Works](/assets/git-how-it-works.png)

## Observe your repo

- List new or modified files not yet committed  
   `git status`
- Show the changes to files not yet staged  
   `git diff`
- Show the changes to staged files  
   `git diff --cached`
- Show all staged and unstaged file changes  
   `git diff HEAD`
- Show the changes between two commit ids  
   `git diff commit1 commit2`
- List the change dates and authors for a file  
   `git blame [file]`
- Show the file changes for a commit id and/or file  
   `git show [commit]:[file]`
- Show full change history  
   `git log`
- Show change history for file/directory including diffs  
   `git log -p [file/directory]`

## Branching

[A successful Git branching model](https://nvie.com/posts/a-successful-git-branching-model/)  
![Branching Model](/assets/git-branching-model.png)  
Don't work on the **Master** branch! Work on a **Develop** branch

- List all local branches  
   `git branch`
- List all branches, local and remote  
   `git branch -av`
- Switch to a branch, my_branch, and update working directory  
   `git checkout my_branch`
- Create a new branch called new_branch  
   `git branch new_branch`
- Delete the branch called my_branch  
   `git branch -d my_branch`
- Merge branch_a into branch_b  
   `git checkout branch_b`  
   `git merge branch_a`
- Create a branch called new_branch and switch to it  
  `git checkout -b my_branch`

## Tagging

- Tag the current commit and add a tagging message  
   `git tag -a v1.1 -m "my version 1.1"`
- See list of tags  
  `git tag`
- Sharing tags  
  `git push origin tag-name`
- Switch to a tag  
   `git checkout tag-name`

## Make a change

- Stages the file, ready for commit  
   `git add [file]`
- Stage all changed files, ready for commit  
   `git add .`
- Commit all staged files to versioned history  
   `git commit -m “commit message”`
- Commit all your tracked files to versioned history  
   `git commit -am “commit message”`
- Unstages file, keeping the file changes  
   `git reset [file]`
- Revert everything to the last commit  
   `git reset --hard`

## Synchronize

- Get the latest changes from origin (no merge)  
   `git fetch`
- Fetch the latest changes from origin and merge  
   `git pull`
- Fetch the latest changes from origin and rebase  
   `git pull --rebase`
- Push local changes to the origin  
   `git push`  
   use `git push -u` to capture the remote branch you intend to track
