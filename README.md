**CheatSheat for GIT**



**Config - setup git**

	git config --global user.name "Username"
	git config --global user.email "some@email.com"
	

**Create - from existing data**

	cd ~/my_project_directory
	git init
	git add . 



**Clone**

	git clone ~/existing_repo ~/new/repo
	git clone git://host.org/project.git
	git clone ssh://user@host.org/project.git
	
	git clone [url]                                      #clone the whole project, draws the latest version into the project folder (it's at the end of the url)
	git clone [url] myFolder                             #Clone the whole project in myFolder
	
 	

**Add**

	git add .                                            #adds all files
 	git add -v 					     #adds all verbose files
 	git add . -u 					     #add all of the changed files I have been unchecked

**Merging and pushing**

    git commit -a -m "your message - Added extra test cases for contact service"    #Adding and committing multiple files.
    git push --set-upstream origin "your branch name- feature/GAFABOTS-149-Test" #Push to your branch.

**Fetch && Pull**

	git fetch                                          #pulls all bugs and / or tags (together make up "refresh"), updates all the treked bunches
	git pull                                           #drags all changes from the remote repository to my current brench
	git pull origin/[brench_name]                      #Cancels all changes from remote brench to a specific local brench



**brenching**

	git remote show origin                             #list all the remote brenches
	git checkout -b [brench_name]			   #he makes a new brench and goes into that brench
	git brench                                         #shows the current brench
	git brench -v                                      #shows the last comit at the current bunker     
	git brench --all                                   # List all brench (local and remote)
	git push origin [brench_name]                  	   #pushes the local brench to the origin remote server
	git push origin --delete [brench_name]    	   # Deletes a bit from a remote server
	git brench -d [brench_name]                        #brise brench lokalno
	git brench --merged                                #pokazuje brench-ove koji su merged
	git brench --no-merged                             #shows the bots that were merged
	git remote update origin --prune                   #updates branch list both remote and local

**Merging**

	git checkout master 				   #I'm going to master brench
	git merge [brench_name]                            #merge the [brench_name] with the master
	git merge origin/development			   #Merge devel with the master

**Status**


	git status                                              #list files that are not merged
	git status -uno                                         #does not display untracked files (git status --untracked-files = no)
	git log                                                 #list of committees
	git ls-files . 					        #list all the files in the repos
	git ls-files . --ignored --exclude-standard --others	#list git-ignored files
	git ls-files . --exclude-standard --others		#list unread file
	git clean -fd                                           #delete untracked files


**Undo**

	git reset					   #undo after git add.
	git --hard                     #updo the deleted files. Or retrieve the deleted files.
	git reset --soft HEAD^				   #undo posle git commit -m 'update'
	git reset HEAD [file_name]                         #undo after git add [file name] - undo after adding a single file
	git checkout -- [file_name]                        #discard changes in a single file
	git checkout -- . 				   #disclaims changes in all files
	git revert b53b3c796b6fdd3e7a02e		   #revert comit - returns comit that is wrong (list of all git logs)

**Reset current branch to be as remote master**

	git fetch origin
	git reset --hard origin/master


**Diff**

	git diff --name-only --diff-filter=U 		   #list all files that have conflicts after stash
	git diff master master/origin                      #the differences between the local master and the master master
	git log --graph  --decorate                        #graph brench and comit
	git diff [brench_name] [brench_name]               #differences between the two Banks
	git diff --name-only  [brench_name] [brench_name]  #the differences between the two brenes are only the files
	git diff [local_brench] [origin/remote_brench]     #the difference between local and remote brench
	git log --oneline [brench_name] ^master   	   #the difference between the teams between the two brenes
	git log --oneline [brench_name]..master            #the same as above
	git diff -R                                        #diff reverse
    

**Stash**

	git stash                                          #saves all changes and returns to the most recent version
	git stash save "Poruka"                            #the same as this only with a descriptive message
	git stash list                                     #List all stash
	git stash apply stash@{0}                          #returns stash @ {0}
	git stash drop stash@{0}                           #it wipes a certain stash, (when no one is assigned a swipe last)
	git stash show -p stash@{0}			   #shows what's in the stash
	git diff stash@{0}  				   #differences in stash


**gitignore**											#adding a gitignore file after a comit

	git rm -r --cached .
	git add .
	git commit -m ".gitignore is now working"


**Remove files from repo**

	git rm --cached [file_name]					   #deleted a file from the repository, not physically
	git rm --cached -r [dir_name]					   #deleted directory from repository, not physical


**Tags**

	git tag Release-0.0.1 -m "Release of Software on May 22"                #adds a specific tag
	git push origin Release-0.0.1                                           #pushes a certain tag on the origin remote
	
**Store passowrd**
    
    git config credential.helper store              #This will store your password then do git pull
    git pull                                        # git pull will ask for your password then it will autometically save your password.

**See Full branch Tree**
git log --graph --pretty=oneline --abbrev-commit
