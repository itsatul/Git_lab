# Git_lab
Code to work with git

All the step after installing git on computer

open git bash first

1. Set the profile in git bash:
    $ git config --global user.name "King Kong"
    $ git config --global user.email "king-kong@gmail.com"
    
    for better UI use:
    $ git config --global color.ui true
    
2. Create a repo on github and copy the https url

3. Create a dir on your local computer and get in the dir and initialize the dir
    $ mkdir My_local_repo
    $ cd My_local_repo
    $ git init
    
4. Connect the local dir to remote repo
    Check if the local diris connected with remote repo
    $ git remote
    <blank responce> # it is expected as we have not connteced the local dir with rempte repo
  
    $ git remote add origin < https url of remote repo > # this code is for connecting the local dir with remote repo
    
    *You will see the the (master) has appeared on the side of your local dir
    
    $ git remote
    origin  # Now local dir is connected with rempte repo
    
    $ git branch # check for local dir branch
    <blank responce> # Maybe it is because it is in the default branch (master)
  
    $ git branch -r # check for remote repo branch
    <blank responce> # Maybe it is because it does not have the branch info for remote repo
  
    Rename the local branch by typing:
    $ git branch -m <new_name>

    You will see the the (<new_name>) has appeared on the side of your local dir
    
    $ git branch # check for local dir branch
    <blank responce> # Maybe it is because it is in the default branch (<new_name>)
  
    $ git branch -r # check for remote repo branch
    <blank responce> # Maybe it is because it does not have the branch info for remote repo
  
    $ git pull
    remote: Enumerating objects: 3, done.
    remote: Counting objects: 100% (3/3), done.
    remote: Compressing objects: 100% (2/2), done.
    remote: Total 3 (delta 0), reused 0 (delta 0), pack-reused 0
    Unpacking objects: 100% (3/3), 620 bytes | 47.00 KiB/s, done.
    From https://github.com/itsatul/IBM-Data-Science-Professional-Certification
     * [new branch]      main       -> origin/main
    There is no tracking information for the current branch.
    Please specify which branch you want to merge with.
    See git-pull(1) for details.

        git pull <remote> <branch>

    If you wish to set tracking information for this branch you can do so with:

        git branch --set-upstream-to=origin/<branch> main
     
    $ git branch -r # check for remote repo branch
    origin/main # Maybe now it have the branch info for remote repo     
    
    
################################################################################## 

IT IS BETTER TO CLONE THE REMOTE REPO TO LOCAL COMPUTER THAN FOLLOWING STEP 3 & $ 4

  $ cd Desktop
  $ git clone < https url of remote repo >
  $ cd <cloned_dir>
  $ git status
    On branch main
    Your branch is up to date with 'origin/main'.

    nothing to commit, working tree clean
    
  Check the branch info 
  For local dir branch 
  $ git branch
  * main

  For remote repo branch 
  $ git branch -r
  origin/HEAD -> origin/main
  origin/main

##################################################################################

5. Add a file to remote repo
    $ cd My_local_dir (<local branch name>)
    $ vim test.txt
    $ git status # it will show you untracked files
    $ git add test.txt # it will add test.txt file to for staging queue
    $ git commit -m 'adding test.txt file' # it will commit the test.txt file to staging area and file will be ready to push to remote repo
    # remember -m is folowd by the comment for commit
    $ git push origin (<local branch name>) # it will push the local dir with new file to remote repo within branch name as (<local branch name>)
  
6. Add a subdir to remote repo
    $ cd My_local_dir (<local branch name>)
    $ mkdir -p new_subdir # it is important to use -p option it will keep the new_subdir within (<local branch name>) of parent folder
    $ git status # it will show you untracked files
    $ git add My_local_dir # it will add My_local_dir dir to for staging queue
    $ git commit -m 'adding My_local_dir' # it will commit the My_local_dir dir to staging area and file will be ready to push to remote repo
    # remember -m is folowd by the comment for commit
    $ git push origin (<local branch name>) # it will push the local dir with new subdir to remote repo within branch name as (<local branch name>)
  
7. Pull remote repo to local dir
    $ git pull origin (<local branch name>) # it will pull the remote repo to local dir 
      
