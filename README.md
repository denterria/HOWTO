# tests

HOWTO:

===============
ONLINE GITHUB:
===============

* https://github.com/denterria
* https://gitlab.cern.ch/profile

0) CREATE/CLONE a given repository.
1) Start a new BRANCH: Copying master (default branch) to edit
2) COMMIT: Making mods and saving files changes into branch (with associated message)
3) Open a PULL request: Propose your changes with a message, request someone reviews 
   and pulls in your contribution and merge them into their branch. 
   Pull requests show diffs, or differences, of the content from both branches.
4) MERGE a pull request: Bring in your branch edits into the master branch.

============
LOCAL REPO:
============

0) CLONE repo:

git clone /path/to/repository
git clone username@host:/path/to/repository
git config color.ui true  (nice looking)
 
e.g. git clone https://github.com/jniedzie/LightByLight2018.git

If you have not cloned an existing repository and want to connect your repository to a remote server, you need to add it:

git remote add origin <server> 

Local repo = 3 "trees": Working Directory (actual files), Index (staging area), HEAD (points to the last commit you've made). 

1) Add changes to your Index:

git add <filename>
git add -i *

2) COMMIT: (to your local working HEAD, but not yet in your remote repository):

git commit -m "Commit message"

3) PUSH: (changes to your remote repository):

git push origin master/branch

4) BRANCHES:

- Create a new branch named "feature_x" and switch to it: 

git checkout -b feature_x

- Switch back to master:

git checkout master

- Delete the branch again:

git branch -d feature_x

- Push the branch to remote repository:

git push origin <branch>
   
- Update your local repository to the newest commit (fetch and merge remote changes):

git pull

git merge <branch>
 
- Edit conflicts manually, and preview changes:

git diff <source_branch> <target_branch>

- After changing, you need to mark them as merged:

git add <filename>

5) TAGGING:

tagging

- Create tag for software release:  git tag 1.0.0 1b2e1d63ff  

(1b2e1d63ff = first 10 characters of the commit id you want to reference with your tag. 

6) LOG: Inspect changes in repo:

git log
git log --author=bob
git log --pretty=oneline
git log --graph --oneline --decorate --all
git log --name-status   (see only which files have changed)

6) Replace local changes:

- Replace the changes in your working tree with the last content in HEAD (changes already added to the index, as well as new files, will be kept):

git checkout -- <filename> 

- Drop all your local changes and commits, fetch the latest history from server and point your local master branch:

git fetch origin
git reset --hard origin/master
