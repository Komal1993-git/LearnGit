# LearnGit 
C:\Users\vijay>git --version
git version 2.35.1.windows.2

** Create README file in LearnGit folder

C:\Users\vijay\Documents\LearnGit>echo "# LearnGit" >> README.md

**Initialize git

C:\Users\vijay\Documents\LearnGit>**git init**

Initialized empty Git repository in C:/Users/vijay/Documents/LearnGit/.git/

**It will show untracked files
C:\Users\vijay\Documents\LearnGit>git status
On branch master
No commits yet
Untracked files:
  (use "git add <file>..." to include in what will be committed)
        README.md
  
nothing added to commit but untracked files present (use "git add" to track)

**Add file on git
  
C:\Users\vijay\Documents\LearnGit>**git add README.md**

**commit changes (save)
C:\Users\vijay\Documents\LearnGit>git commit -m "add readme file"
Author identity unknown
*** Please tell me who you are.
Run
  git config --global user.email "you@example.com"
  git config --global user.name "Your Name"
to set your account's default identity.
Omit --global to set the identity only in this repository.
fatal: unable to auto-detect email address (got 'vijay@VASTUNIRMAN.(none)')

C:\Users\vijay\Documents\LearnGit> git config --global user.email "komalkumbhar1993@gmail.com” 
  
C:\Users\vijay\Documents\LearnGit> git config --global user.name "Komal Kumbhar"
  
**Commit changes to master  
  
C:\Users\vijay\Documents\LearnGit>git commit -m "add readme file"
  
[master (root-commit) b651fc3] add readme file
 1 file changed, 1 insertion(+)
 create mode 100644 README.md

**Sync local to git repo.(Manual create repo called LearnGit)
  
C:\Users\vijay\Documents\LearnGit>**git remote add origin https://github.com/Komal1993-git/LearnGit.git**

**Push Changes to master
C:\Users\vijay\Documents\LearnGit>git push -u origin master
info: please complete authentication in your browser...
fatal: An error occurred while sending the request.
fatal: The request was aborted: Could not create SSL/TLS secure channel.
Username for 'https://github.com': komalkumbhar1993@gmail.com
Password for 'https://komalkumbhar1993@gmail.com@github.com':
remote: Support for password authentication was removed on August 13, 2021. Plea
se use a personal access token instead.
remote: Please see https://github.blog/2020-12-15-token-authentication-requireme
nts-for-git-operations/ for more information.
**Error----->fatal: Authentication failed for 'https://github.com/Komal1993-git/LearnGit.git/**

**Solution**: 
Create Personal Access Token on GitHub From your GitHub account, go to Settings => Developer Settings => Personal Access Token => Generate New Token (Give your password) => Fillup the form => click Generate token => Copy the generated Token, it will be something like ghp_sFhFsSHhTzMDreGRLjmks4Tzuzgthdvfsrta Now follow below method based on your machine: 
  
For Windows OS ? Go to Credential Manager from Control Panel => Windows Credentials => find github.com => Edit => On Password replace with with your GitHub Personal Access Token => You are Done If you don’t find github.com => Click on Add a generic credential => Internet address will be github.com and you need to type in your username and password will be your GitHub Personal Access Token => Click Ok and you are done
  
**Push changes to master
  
C:\Users\vijay\Documents\LearnGit>**git push -u origin master**

fatal: An error occurred while sending the request.
fatal: The request was aborted: Could not create SSL/TLS secure channel. 
Username for 'https://github.com': komalkumbhar1993@gmail.com 
Password for 'https://komalkumbhar1993@gmail.com@github.com': **<ENTER TOKEN>**
Enumerating objects: 3, done. Counting objects: 100% (3/3), done. Writing objects: 100% (3/3), 240 bytes | 60.00 KiB/s, done. Total 3 (delta 0), reused 0 (delta 0), pack-reused 0 To https://github.com/Komal1993-git/LearnGit.git

[new branch] master -> master branch 'master' set up to track 'origin/master'.

#Working on branch

**Create new Branch
  
C:\Users\vijay\Documents\LearnGit>git branch b1

C:\Users\vijay\Documents\LearnGit>git branch --list
  
  b1
  
* master

**Switch working from master to branch
  
C:\Users\vijay\Documents\LearnGit>**git checkout b1**
  
Switched to branch 'b1'

C:\Users\vijay\Documents\LearnGit>echo "# b1" >> style.css

C:\Users\vijay\Documents\LearnGit>**git status**
  
On branch b1
Untracked files:
  (use "git add <file>..." to include in what will be committed)
        style.css

nothing added to commit but untracked files present (use "git add" to track)

C:\Users\vijay\Documents\LearnGit>git commit -m "Add STyle.css to b1"
  
On branch b1
Untracked files:
  (use "git add <file>..." to include in what will be committed)
        style.css

nothing added to commit but untracked files present (use "git add" to track)

C:\Users\vijay\Documents\LearnGit>git push
  
fatal: The current branch b1 has no upstream branch.
To push the current branch and set the remote as upstream, use

    git push --set-upstream origin b1

**Push changes to branch
  
C:\Users\vijay\Documents\LearnGit>**git push --set-upstream origin b1**
  
Total 0 (delta 0), reused 0 (delta 0), pack-reused 0
remote:
remote: Create a pull request for 'b1' on GitHub by visiting:
remote:      https://github.com/Komal1993-git/LearnGit/pull/new/b1
remote:
To https://github.com/Komal1993-git/LearnGit.git
 * [new branch]      b1 -> b1
branch 'b1' set up to track 'origin/b1'.


# Reverting changes made

*You have to copy commit ID to revert the change. Use git log command for this.

C:\Users\vijay\Documents\LearnGit>git revert af489ca3d19fd6afc0101616e342bd3bbc4
02b67

On branch master
Your branch is ahead of 'origin/master' by 1 commit.
  (use "git push" to publish your local commits)
nothing to commit, working tree clean

C:\Users\vijay\Documents\LearnGit>git push

Enumerating objects: 4, done.
Counting objects: 100% (4/4), done.
Delta compression using up to 4 threads
Compressing objects: 100% (2/2), done.
Writing objects: 100% (3/3), 357 bytes | 119.00 KiB/s, done.
Total 3 (delta 0), reused 0 (delta 0), pack-reused 0
To https://github.com/Komal1993-git/LearnGit.git
   e6e2eda..9119394  master -> master

# Added changed that committed before

**Use git checkout <commit Id> <file name>

C:\Users\vijay\Documents\LearnGit>git checkout 5cb1cb21e8d6ddb741c3fddeaf6c0dbb7
c52b2d7 README.md

Updated 1 path from a2e22da

C:\Users\vijay\Documents\LearnGit>git status

On branch master
Your branch is up to date with 'origin/master'.

Changes to be committed:
  (use "git restore --staged <file>..." to unstage)
        modified:   README.md


C:\Users\vijay\Documents\LearnGit>git add .

C:\Users\vijay\Documents\LearnGit>git commit -m "Edit README after reverting fro
m deletion"

C:\Users\vijay\Documents\LearnGit>git push -u origin master


