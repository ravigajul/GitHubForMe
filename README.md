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
  
## Update remote url to a different repo
```git
git remote -v # checking existing url
git remote set-url origin <new-url>
```

# Branch Commands
  Git branch newbranch --create  branch  
  git checkout <existing_branch>
  git checkout -b <new_branch>  --create and checkout new branch
  Git branch -d newbranch --delete a branch  
  Git branch --list all branches.  

# Head
  Points to the last commit on a branch   
  When we switch branches…head also moves with it to the last commit.   

# Add remote Repo
  Git add remote https://sample.com/something.git  

# Display all remote repositories
  Git remote -v  
# Remove local untracked files
  1. To remove directories, run git clean -f -d or git clean -fd.
  2. To remove ignored files, run git clean -f -X or git clean -fX.
  3. To remove ignored and non-ignored files, run git clean -f -x or git clean -fx.
## Rebase & Squash
  ```
  Git rebase master //this will point the base of current branch to latest commit in the master branch.  
  Git rebase -i HEAD~3 //this will display all the 3 commits with pick..update the other two to squash from pick to merge multiple commits into one commit.  
  //Save the new commit message
  git push --force //now the old commits will not be seen in the git log
```
# Cherry-pick
 ```
 Git cherry-pick <<commitId>> will merge the particular commit from other branch to current branch  
```
# Reset changes   
 ```
  Git reset --soft HEAD~1  # without loosing the changes latest 1 commit  
  Git reset --hard HEAD~1  # loose all the changes latest 1 commit
  Git reset --soft commit id
```
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
  
# How to remove committed files from Git version control
  Create a .gitignore file, if you haven’t already
  Edit .gitignore to match the file/folder you want to ignore
  Execute the following command: 
  git rm --cached path/to/file. Git will list the files it has deleted. 
  The --cached flag should be used if you want to keep the local copy but   remove it from the repository.
  Verify that these files are being deleted from version control using git status
  Push the changes to the repository  

## Download a file from github using curl or wget
wget command is a commonly used CLI to download files from the internet. curl is another command used to transfer data to or from a server.
If you want to download the student.json using the url "https://github.com/ravigajul/NodeJsForMe/blame/master/Playground/student.json" It will just be a github html page and not the actual student.json. In order to dwonload the actual file, we should be using the raw file url from github instead like https://raw.githubusercontent.com/ravigajul/NodeJsForMe/master/Playground/student.json.

## Download a file from bitbucket using curl
Generate and replace the token and use the raw file url
```
  curl -o filename -H "Authorization: Bearer Token" https://bitbucket.com/projects/projectname/repos/reponame/raw/filename?at=refs%2Fheads%2FBranchName
  ```
## Get latest code from master and merge to dev branch
```git
git checkout dev
git pull origin master
```
Alternatively
```git
git fetch origin
git merge origin/master
```
## Remove untracked files
remove files and directories
```git
git clean -f -d
```
To check which fils will be removed by git clean
```git
git clean -f -n
```
To preview the files and directories that will be removed, use the -n option:
```git
git clean -f -d -n
```
To just remove files
```git
git clean -f
```
## Git Pull vs Git Fetch
The main difference between git pull and git fetch is that git pull fetches and merges changes from a remote branch into your local branch in a single command, while git fetch only fetches changes from the remote branch and does not merge them automatically.

## Host html pages on GitHub Gist
create a simple HTML page that demonstrates the autocomplete feature using a basic input field with some predefined options. We'll host this on GitHub Gist and make it shareable.

### Step 1: Create the HTML Page
### Step 2: Create a GitHub Gist

1. **Sign in to GitHub**:
   - Go to [GitHub](https://github.com/) and sign in with your GitHub account.

2. **Create a New Gist**:
   - Go to [GitHub Gist](https://gist.github.com/).
   - Enter a description, for example, "Autocomplete HTML Example".
   - Name the file `practise.html`.
   - Paste the HTML content from above into the text area.

3. **Save the Gist**:
   - Choose whether to make the gist public or secret.
   - Click the "Create public gist" or "Create secret gist" button.

### Step 3: Get the Raw URL and Use RawGit or GitHack

1. **Get the Raw URL**:
   - After creating the gist, click on the "Raw" button to get the raw URL of the HTML file. It should look something like `https://gist.githubusercontent.com/your-username/gist-id/raw/practise.html`.

2. **Use GitHack to Render the HTML**:
   - Go to `https://raw.githack.com/`.
   - Enter the raw URL in the input field and get the formatted URL.

   Example:
   - Raw URL: `https://gist.githubusercontent.com/your-username/gist-id/raw/practise.html`
   - GitHack URL: `https://raw.githack.com/your-username/gist-id/raw/practise.html`

3. **Open the Rendered URL**:
   - Copy the GitHack URL and paste it into a new browser tab to see your autocomplete HTML page rendered properly.

By following these steps, you will have a shareable HTML page that demonstrates the autocomplete feature, hosted on GitHub Gist.

## Install Apps VM
```.ps
#
# Functions
#

function Update-Environment-Path
{
    $env:Path = [System.Environment]::GetEnvironmentVariable("Path","Machine") `
        + ";" + [System.Environment]::GetEnvironmentVariable("Path","User")
}

#Create required directories
New-Item -ItemType directory -Path C:\workdir

#
# IntelliJ
#
choco install intellijidea-community --yes
Update-Environment-Path

#
# Maven
#
choco install maven --yes
Update-Environment-Path

#
# Misc
#
choco install notepadplusplus --yes

#
# Java
#
choco install openjdk --version=17.0.2 --yes
Update-Environment-Path

#
# Update CACERTS files
#
Move-Item "C:\Program Files\OpenJDK\jdk-17.0.2\lib\security\cacerts" -Destination "C:\Program Files\OpenJDK\jdk-17.0.2\lib\security\cacerts.sav" -Force
Copy-Item -Path "C:\VMSetup\cacerts" -Destination "C:\Program Files\OpenJDK\jdk-17.0.2\lib\security"

#
# Environment update
#
[Environment]::SetEnvironmentVariable("IDEA_JDK_64", $Env:java_home, [EnvironmentVariableTarget]::Machine)
```
