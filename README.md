# GitHubForMe
https://docs.github.com
# Generate ssh key
  Cd ~  
  Ssh-keygen    
  Cd .ssh  
  Cat id_rsa.pub  
# Create a new repository on the command line
  echo "# JsonConcepts" >> README.md  
  git init  
  git add README.md  
  git commit -m "first commit"  
  git remote add origin https://github.com/ravigajul/JsonConcepts.git  
# Push an existing repository from the command line
  git remote add origin https://github.com/ravigajul/JsonConcepts.git  
  git push -u origin master  

# Graphical view of all commits
  Git log --oneline --graph --decorate --all  

# Common and must need commands
  Git status  
  Git add .  
  Git status  
  Git commit -m " this is a test commit"  
 
# Express Commit
  Git commit -am "this is express commit" // This is add the files and commit with message  

# Show Commits
  Git log  //get the commits with most recent on top  

# show the files names in commit
  git log --name-only   
  
# Fix Permission Denied issue
  https://gist.github.com/adamjohnson/5682757  

# to ensure .gitignore is in effect

The .gitignore file ensures that files not tracked by Git remain untracked.
Just adding folders/files to a .gitignore file will not untrack them -- they will remain tracked by Git.
To untrack files, it is necessary to remove from the repository the tracked files listed in .gitignore file. Then re-add them and commit your changes.
The easiest, most thorough way to do this is to remove and cache all files in the repository, then add them all back. All folders/files listed in .gitignore file will not be tracked. From the top folder in the repository run the following commands:
git rm -r --cached .  
git add .  
Then commit your changes:  
git commit -m "Untrack files in .gitignore"  

# To switch remote url from https to ssh
  https://docs.github.com/en/github/getting-started-with-github/managing-remote-repositories  
  
# Branch Commands
  Git branch newbranch --create  branch  
  Git checkout newbranch --switch to newbranch  
  Git checkout -b newbrnach --create and switch to newbranch  
  Git branch -d newbranch --delete a branch  
  Git branch --list all branches.  

# Head
  Points to the last commit on a branch   
  When we switch branches…head also moves with it to the last commit.   

# Add remote Repo
  Git add remote https://sample.com/something.git  

# Display all remote repositories
  Git remote -v  

# Rebase & Squash
  Git rebase master //this will point the base of current branch to latest commit in the master branch.  
  Git rebase -i HEAD~3 //this will display all the 3 commits with pick..update the other two to squash from pick to merge multiple commits into one commit.  

# Cherry-pick
  Git cherry-pick <<commitId>> will merge the particular commit from other branch to current branch  
# Reset changes   
  Git reset --soft HEAD~1  # without loosing the changes latest 1 commit  
  Git reset --hard HEAD~1  # loose all the changes latest 1 commit  

# Revert is undoing
  Git revert 3dsfse //will undo the changes ..if a file was added in previous commit it will delete in this commit.  

# Stash
  Is used to move your files from working area to stash area  
# Git stash
  The files in stash area will be queued  
  To check the list of files in stashing areas    
  Git stash list  
  To see the content of a particular file  
  Git stash show stash@{1}  
  To bring back the file from stashing area to working area  
  Git stash pop stash@{1}  

# Reflog
  Git reflog  
  This shows the commit hashes even for the resets hards and soft so that we can reset the head to a particular commit.  
  








