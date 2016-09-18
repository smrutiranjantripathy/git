#**Cracking the Git Version Control System**

##What is Git ?
Git is the most widely used version controls system by developers community. As a distributed revision control system it is aimed at speed, data integrity, and support for distributed, non-linear workflows.As with most other distributed version control systems, and unlike most client–server systems, every Git directory on every computer is a full-fledged repository with complete history and full version-tracking capabilities, independent of network access or a central server.    
*Sources: https://en.wikipedia.org/wiki/Git*⋅⋅  

## Git Brief History
Git was developed by Linus Trovalds for managing the linux source code.Earlier in 1998 before *Git*  *Bitkeeper* was considered as a solution for managing the linux source code. Bitkeeper used to provide access to the system for certain open source or free software projects, one of which was the source code of the Linux kernel. The license for the "community" version of BitKeeper had allowed for developers to use the tool at no cost for open source or free software projects, provided those developers did not participate in the development of a competing tool (such as Concurrent Versions System, GNU Arch, Subversion or ClearCase) for the duration of their usage of BitKeeper plus one year. This restriction applied regardless of whether the competing tool was free or proprietary. The decision made in 2002 to use BitKeeper for Linux kernel development was a controversial one.But this decision was not suipported by some developers becuase of the licensing clauses. They believed the project was ceding some control to a proprietary developer.In 2005 Bitmover removed the free version to all the OSDL employess including Linus Trovalds because of a client developed by one of the OSDL employee Andrew Tridgell which mimics one of the core features of version control system provided by Bitkeep.It lead to the need of the development of a version control system which could match the needs of the linux project.
*Sources: https://en.wikipedia.org/wiki/BitKeeper*

##Installation 
- For Redhat or cent-os like systems:
  - `sudo yum install git-all`
- For debian-based distribution systems like Ubuntu:
  - `sudo apt-get install git-all`
- Checking the Git version:
  - `git --version`
   
##Minimal Configuration
- User's Name:
  - `git config --global user.name "Your Name"`
- User's Email:
  - `git config --global user.name "Your Name"`
- To check global configuration:
  - `git config --global --list` 
- To edit the global configuration:  
  - `git config --global -e`

## Get Help
- To get the list of commands avialble in Git
  - `git help`
- To get command specific help
  - `git <command> --help`   `eg: git add --help`
  
## To Initiate a Local Git Repository:
- `git init <repo-name>`
- `eg: git init my-repo` -> "This will initiate a repo named my-repo"
- `git init` inside a directory will initiate a repo with that name. 
    
## Git Structure
1. Working Directory: This conatins all the files which are present in the local system which may or may not be a part of git version control system.
2. Satging Area: This contains all the files which are present in Staging Area.
3. Repository: This contains the files which are commited to git repository.
4. Remote-Repo: This is the repo where files are finally pushed after commit.eg *github.com or bitbucket.com*. The remote repo is a manifestation of the above three steps but it is maintained in a 3rd party server.

##Normal Commit Procedure
1. Modify the files or create new files using editor.
2. Get the status of modified or added files using:
  - `git status`
3. Revert a modified file
  - `git checkout <file name>`
. Check the difference in modification using git diff
  - `git diff`(if there is one file) 
  - `git diff <file name>` (if there are many files)
4. Add the files to the Git Staging Area Using Git add:
  - `git add --all`(if you intend to add all files) 
  - `git add <file name>`(if you intend to add a particular file)
  - If you intend too remove the added files
    - `git reset HEAD`(if you intend to remove all files)
    - `git reset HEAD <file>` (if you intend to remove a particular file)
5. Commit the file
   - `git commit -m "Commit Message"` ( To commit the files)
   - `git commit` (This will open the editor to draft the commit message)
   - Express Commit: Express commit can be used only if the files are a part of version control system.
     - How to get a list fo files which are a part of version control system ?
       - `git ls-files`
     - Express commit adds and commits in one command
       - `git commit -am "Commit Message"` (This will add and commit all those files which are part of version control) system and has been modified.
       - `git commit -am "Commit Message" <file name>` ( If you intend to add and commit one file out of all those modified files which are a part of version control system. )
    - To revert a local commit which has not been pushed to remote repository
      - `git reset HEAD~`(HEAD: Points to Last commit of Current branch)
      
## Git Logs
1. To Get logs
  - `git log`
2. To get logs in meaningful format
  - `git log --online --graph --decorate --all`
    - --online : which will provide a simplified commit entry.
    - --graph :provide an asterik based graph denoting branching hiearchy.
    - --decorate : which will tell us which commits are a part of which branches.
    - --all : which will provide the history of all branches that are available in the repository.
3. To get logs of a particular file
  - `git log <file name>`
  
## Setting Alias for long commands
- `git config --global alias.<alias -name> "<command>"`
  - `eg: git config --global alias.hist "log --oneline --graph --decorate --all"`

## Git Branching
Branches are timelines of commits.Branch names are labels to track those timeline of commits.
  - To create a branch 
    - `git brnach <branch-name>` 
  **Important**: When we create a branch "A" while currently checked in at branch "B" , then branch A will get created and copy the contents of branch "A".Keep this in mind while creating branches.
  - To change a branch:
    - `git checkout <branch-name>`
  - To checkout and Create a branch in one command:
    - `git checkout -b <branch-name>`
  - To delete a branch:
    - `git branch -D <branch-name>`
  - If a branch is not created locally but is present remotely then checking out to that branch will bring the branch locally provided there is one remote , on the other hand if there are multiple remotes pointing to multiple repositories and they have branches with the same name, then `git checkout <branch-name>` won't work and we will have to explicitly mention the remote name as : `git checkout -b <branch name> <remote name>/<branch name>`  
  `git checkout -b develope origin/develope` (To Checkout to branch develope of origin remote).
  - To get a list of branches present in our local repository:
    - `git branch`
  - To get a list of local branches and references to remote branches:
    - `git branch -a`
  
## Git Clone
We use git clone to clone a remote-repository in to local system.Cloning is done using https and ssh.Public repsitories can be cloned without authentication, but for private repositories exclusive permission is required.For ssh cloning of private repositories we need to add public key at github or bitbucket settings.Https cloning requires username and password.Cloning by default clones the master branch and brings the reference to all remote branches in repository.It sets the default remote "origin" to the remote branch.
- How to add ssh keys ?
  - Open Terminal Check if you have existing ssh key or not.
    `ls -al ~/.ssh`
  - If key is priorly genertaed then you will find a file as id_rsa.pub.
    `cat ~/.ssh/id_rsa.pub and copy the contents to your clipboard.`
  - If you don't have a ssh key generate ssh key as:
    `ssh-keygen -t rsa -c <email>`
    `eg: ssh-keygen -t rsa -b 4096 -C "your_email@example.com"`
  - Go to bitbucket or github settings page and add the keys in ssh section.
  - Check your access as :
    - `ssh -T git@bitbucket.org` (for bitbucket)
    - `ssh -T git@github.com` (for github)
  - Clone Commands:
    - `git clone "ssh url"`
    - `git clone "https url"
    -  To clone a particular branch:
    -  git clone "ssh url/https url" -b <branch name>`
 - To check the remotes:
   - `git remote -v` (It will show the remotes and the repositories to which they are pointing.
   - 

#Git Fetch 
We do git fetch to update the refereces in the local repository to the newly created branches. Besides fetch also fetches the tags in remote repository and the commits.But fetch doesn't merge them with the local repository.
  - `git fetch <remote-name>` - To fetch from the concerned remote.

#Git Pull
Git Pull is "*Git Fetch + Git Merge*". We do a git pull to update the local respository with the contents of remote repository.Its becuase git won't allow us to push changes in remote branch if our local branch is not updated with our remote branch.
  - `git pull <remote-name> <branch-name>`
  - `eg: git pull origin master`
**Important**: Pretty often we come across this scenario when our local branch is not updated with our remote branch and we are not able to push our commit to the remote branch.In that case the quickest solution is to do a pull and rebase simultaneouly.Rebase rewinds our commits , then pulls the commits from the reomote repositoriy's branch and plays our commit on top of it . `git pull --rebase <remote-name> <branch-name>` `eg: git pull --rebase origin master`













  



  
  

     
   
    
















 





    
  

   
  































