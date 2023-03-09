## Git Commonly Used Commands

###  $ git init 
**---> initiate git in working directory**

###  $ git remote add origin(custom name) "htts://dcdv.f" 
**---> this will add remote repository origin to your git folder configuration, using this this command we can add multiple remote with different origin name like -origin,test origin etc**

###  $ git remote -v 
**---> shows all the remote origin list(git provide 2 url one for push and one for fetch but 99% time both url same  )**

###  $ git show 
**---> shows the changes in last commit**

###  $ git ls-files
**---> it will track only modified file in staging not new file**

### $ git restore --staged <file>
**---> to unstage any file which is added in git stage by git add .**

###  $ git reset HEAD README.md
**---> This will reset file from git staging even if it is git added, but shows in modified**

###  $ git checkout --README.md
**---> This will reset file and remove all the changes done in file and not track ads modified(modified file if add in stagged state then it get removed)**

###  $ git log --oneline --graph --decorate --all
**---> it will provide online info, with asterisk based graph(branching hierarchy), decorate give colorful branch, all will provide history of all branches**

###  $ git config --global alias.history "log --oneline --graph --decorate --all"
**---> this will create new custom command for git log with global scope and oneline,graph etc like feature in build**

###  $ git config --global --list
**---> This wil give us list of global commands**

###  $ git mv test.txt  demo.txt
**---> it will rename file**

###  $ git rm demo.txt
**---> remove file**

###  $ gitk
**---> This command will display all logs in graph**

###  $ git add -u 
**---> This will add updated file in stagging**

###  $ git add -A 
**---> Add all file in staging --modified as well as newly created**

###  $ .gitignore 
**---> Excluding/Ignoring File (*.log this means all file with log extension ignore)**

###  $ git diff last-sha/branch-name
**---> This will compaire last provided SHA commit with current**

###  $ git branch
**---> THis command Will give list of branch created**

###  $ git branch -a 
**---> THis command Will give list of branch created on local as well as branches on remote below(only until last pull/fetch)**

###  $ git checkout master
**---> This will checkout/switch to master branch**

###  $ git switch -c developer OR $ git switch -c developer  master
**---> This will create new branch developer(from master)**

###  $  git commit --allow-empty -m "added empty commit message even no changes done"
**---> This will add commit even it doent have changes made and git add done** 

###  $ git merge branch-name OR $ git merge --ff branch-name (fast forward merging)
**---> This will be a fast forward merge all commits from (target)branch will be merge with destination branch(current) and head will point to current branch(where in to merge), no merge point commit added by git, if we provided any message with merge command it will be ignored**

###  $ git merge --no-ff branch-name 
**---> This will be a no fast forward merge, all commits from (target)branch will be merge with destination branch(current)  with commit of merge point added by git or we provided any message with merge command while merging**

###  $ git merge --squash branch-name 
**--->This command squshes all the commits from branch which is being merge in one commit, After this command we will get automatic merge went well message may with stooed before commiting then we have to run git commit -m "message " command after above command.**

## If first time branch merge with --no-ff then it will be ignore git merge -ff 

###  $ git branch -d branch -name
**--->This will delete branch**

###  $ git pull --rebase
**--->Suppose we have made sa=ome changes locally and wanted to keep it on top on all the changes coming from remote then, instead of using git pull (it will merge remote changes and local changes) use rebase, For rebase remote branch will be base and our local changes will be place over it**

###  $ git push origin :branch-name
**--->This will delete branch from remote git console, run this command after delete branch from locally**

###  $ git checkout -b branch-name 
**---> This will create new branch**

###  $ git checkout -b branch-name origin/remote-branch-name(starting_point)
**---> This will create new branch with starting point as mentioned to remote branch name**

## TAGS - Tags are check points, tags never push directly to remote we have to specifically push it 

###  $ git tag mytag OR $ git tag mytag branch-name
**---> This will create git tags**

###  $ git push origin tag_name
**---> push tags to remote**

###  $ git push --tags
**---> push all the tags simultaneously to the remote**

###  $ git tag -d mytag
**---> This will delete tag**

###  $ git tag -a v1.0 -m "Release 1.0"
**---> This will add tag with note**

###  $ git show v1.0
**---> This command shows tag and date code and commit message associated with tag, help to know major milestone**

###  $ git tag -f v1.0 SHA (changed SHA)
**---> This will update tag SHA it will change on local**
###  $ git push --force origin V00 
**---> To update tag on remote then use above command**

## STASH  --------------------------------

###  $ git stash list
**---> This will shows stashes created**

###  $ git stash 
**--->  It will save working directory and file, index(head pointer) state, save your work in progress. By default, git stash stores (or "stashes") the uncommitted changes (staged and unstaged files) and overlooks untracked and ignored files. Working branch and directory will be clean**

###  $ git stash -u or git stash --include-untracked 
**---> stash untracked files.**

###  $ git stash -a or git stash --all 
**---> stash untracked files and ignored files.**

###  $ git  stash save "message"
**---> Saved working directory and index state On master:  mmessage**

###  $ git stash pop 
**---> This will pop out top index from stash stack**

## --------------------------------

###  $ git rest SHA --soft
**---> It will reset with soft, here SHA is commit code**

###  $ git branch <new-branch-name> be64979
**---> This will create new branch with provided SHA**

###  $ git reflog
**---> This will give log shows commit id but reflog shows action all done in repository like merge, checkout, push etc**

###  $ ssh-keygen -t  rsa  -C "email_id" 
**---> use email id which is set as username on github , it will create id_rsa and id_rsa.pub file then open public key and copy all contains**

###  $ git config --get remote.origin.url
**---> Get http url of repository** 

###  $ git remote -v 
**---> To check the remote host available in git config** 

###  $ git remote show OR $ git remote
**---> This will show name of remote origin** 

###  $ git push --delete origin test2
**--->This command will delete branch from remote, 'git branch -d branch_name' Or  'git branch -D branch_name'(force delete without merging with other branch) will delete from local only** 

###  $ git cherry-pick SHA(from feature branch from where we want to cherry-pick)
**--->This command will pick selected sha(commit) from other branch like feature branch and then put it on current branch(must be in branch where we wanted to add new commit from other branch) It is contrast to merge or rebase where all commits attach to new branch where as cherry pick do it for only 1** 
**If you have notes attached to the commit they do not follow the cherry-pick. To bring them over as well, You have to use: $ git notes copy <from> <to>**


###  $ git push all --all
**---> This command will push code to all remotes**

###  $ git remote set-url origin git@github.com:Im-Programmatist/Git_Hub_Ultimate.git
**---> This command will clone using SSH url**

###  $ git branch --set-upstream-to=origin/<branch> developer
**---> If you wish to set tracking information for this branch you can do so with above command**    

###  $ git config --global push.default current OR $ git push -f --set-upstream origin master
**---> The current branch master has no upstream branch error can resolve and make default branch to push pull, after this command we need just git pull/push**

###  $ git config core.fileMode false
**---> This command will not send file permission(sudo or 777) to remote repository with push**

###  $ git config --global -e
**---> Show all global default config setting**

## Version Tags Related Command  --------------------------------

###  $ git tag -a v1.0 SHA_of_commit_to_which_connect
**--->Create annotation Tag**

###  $ git tag -d v1.0
**--->Delete Tag**

###  $ git pull origin --tags
**--->Pull Tags From Remote**

###  $ git push origin --tags
**--->Push all created tag (new should not exist on remote)**

###  $ git tag -n 
**--->See git tags list**

###  $ git show v1.0
**--->Show All details of tag with commit attached**

## --------------------------------

## Error like - GIT BASH - error: pathspec '…' did not match any file(s) known to git
###  $ git remote update

###  $ git fetch OR $ git fetch --all
**---> Fetch from remote to local with all branches even that not created on local yet**

###  $ git checkout --track origin/<BRANCH_NAME11>
**---> This will only create 'BRANCH_NAME11', not a branch with a different name**

###  $ git checkout -b branch2 origin/branch1
**---> This command will create branch2 and track branch1**

## rebase Related Commands --------------------------------

###  $ git rebase <branch name> OR git rebase -i 
**---> (here i for interactive and no need to specify branch beacuse we are on current branch ) Rebase - It is an alternative of git merge command. It is a linear process of merging.In Git, the term rebase is referred to as the process of moving or combining a sequence of commits to a new base commit. Merge merges all commits as a single commit where as rebase creates a linear track of commits.**

###  $ git rebase --continue  
**---> The above command is used to continue with the changes you made.**

###  $ git rebase --skip  
**---> If you want to skip the change, you can skip**

###  $ git rebase --quit  
**---> If you want to quit the rebase**

## --------------------------------

**Merging integrates the content of the feature branch with the master branch. So, the master branch is changed, and feature branch history remains consistence.	Rebasing of the master branch may affect the feature branch. Merging preserves history.	Rebasing rewrites history. Git merge presents all conflicts at once.	Git rebase presents conflicts one by one.**

# after rebase SHA change but commit changes not vanishes

## Stash --------------------------------

**to store changes and go back to previous commit, it will store all changes aside.**
###  $ git stash 
**---> This command will store recent changes and go back to last/previous commit**

###  $ git stash apply
**---> It will apply all stored changes in stash to current stage, It will apply latest stash changes from list**

###  $ git stash apply 1/2/3 (number from stash list)
**---> This will apply stage changes according to number in stash list**

###  $ git stash list
**---> It will show list of all stash stages we have kept aside**

###  $ git stash clear
**--->stash list will be clear from here**

###  $ git stash push -m "added description to identify stage changes"

###  $ git stash pop 1
**---> Popup 1 index stash saved changes**

## --------------------------------

## If we add and commit pop up stash changes then it automatically removed from stash list

###  $ git stash drop 2 (index number in stash list) - delete stash in list 

###  $ git commit -m "message , close #issue_number"
**---> This will attach commit with issue on git lab and close it**

### https://dev.to/stefant123/basic-git-commands-explained-1cjd#remote-add
