-----------------------------------GIT BARNCHING---------------------------------------------------------------------------------------------

1)git branch -------> create new branch and stays on current branch
2) git checkout -b -----> create new branch and switch to it
3) git checkout <branch name> -------> only for switching branch
4) git switch <branch_name> ---> modern for branch switching only.
5) diff between git switch and git checkout : git switch is a focused, safer command for changing branches, while git checkout is an older, multi-purpose command used for switching branches, restoring files, and checking out commits.
6) git branch -d <branch name> ----> del a local branch (d if merged, D forced del even if unmerged)
7)git push origin --delete branch-name ---> del remote branch

---------------------------------------------------------------GIT PUSH ORIGIN-----------------------------------------------------------------

1)git remote -v ----> to check the remote url
2) git remote add origin <ssh> ----> adding remote origin to local git
3) git push origin <branch_name>
4) What is the difference between origin and upstream? ---------> origin is your default remote repository (usually your fork), while upstream is the original source repository you forked from.
Why both matter
origin → where you push your changes
upstream → where you pull latest updates from



-----------------------------------------------------------------------------------------------------------------------------------------------


1) git rm --cached -r ------------> removes files from staging area but keeps them safe on local after git add. use only if brand new repo with 0 prior commits
2) diff between git fetch and git pull?
When to use each

Use git fetch when:

You want to see what's changed before updating your branch.
You're working on a shared repository and want more control.
You want to avoid unexpected merge conflicts during a pull.

Use git pull when:

You trust the incoming changes and want to update your branch immediately.
You're quickly syncing your local branch with the remote.
A simple rule of thumb
fetch = "Download, but don't touch my work."
pull = "Download and update my branch."


3)clone vs fork?

3) Difference between clone and fork
Aspect	Clone	Fork
Location	Local machine	GitHub account
Purpose	Get a working copy	Create your own copy of repo
Ownership	Same repo	Your independent repo
Use case	Work locally	Contribute without affecting original

One-line:
Clone = local copy, Fork = personal remote copy.

4) When to use clone vs fork
Use clone when:
You have direct access to the repo
You’re part of the team/project
You can push directly
Use fork when:
You don’t have write access
You want to contribute to open-source
You need your own independent version

Clone → work locally
Fork → create your own GitHub copy
Upstream sync → keeps your fork updated with original repo


5) Keep your fork in sync with original repo
Step 1: Add upstream (original repo)
git remote add upstream https://github.com/<original-owner>/<repo>.git
Step 2: Fetch latest changes
git fetch upstream
Step 3: Merge into your branch
git checkout main
git merge upstream/main
