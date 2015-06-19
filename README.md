CheatSheat for GIT

**Create - from existing data**

	cd ~/my_project_directory
	git init
	git add . 

**gitignore**											#dodavanje gitignore fajla posle komita

	git rm -r --cached .
	git add .
	git commit -m ".gitignore is now working"

**Clone**

	git clone ~/existing_repo ~/new/repo
	git clone git://host.org/project.git
	git clone ssh://user@host.org/project.git
	
	git clone [url]                                      #klonira ceo projekat, pulluje najnoviju verziju u folder tog projekta (stoji na kraju url-a)
	git clone [url] myFolder                             #klonira ceo projekat u myFolder
	
 	

**Add**

	git add .                                            #dodaje sve fajlove
 	git add -v 										     #verbose


**Fetch && Pull**

	git fetch                                          #dovlaci sve brancheve i/ili tagove (zajedno cine "refs"), apdejtuje sve trekovane brancheve
	git pull                                           #povlaci sve izmene sa remote repozitorijuma u moj trenutni branch
	git pull origin/[branch_name]                      #povlaci sve promene sa remote branch-a



**Branching**

	git remote show origin                             #izlistava sve remote branch-ove
	git checkout -b [branch_name]					   #pravi novi branch i prelazi u taj branch
	git branch                                         #pokazuje trenutni branch
	git branch -v                                      #pokazuje zadnji komit na trenutnom branchu     
	git branch --all                                   #izlistava sve branch-ove (lokalno i remote)
	git push origin [branch_name]                  	   #push-uje lokalni branch na origin remote server
	git push origin --delete [branch_name]    		   #brise branch sa remote servera
	git branch -d [branch_name]                        #brise branch lokalno
	git branch --merged                                #pokazuje branch-ove koji su merged
	git branch --no-merged                             #pokazuje branch-ove koji jos nisu merged

**Merging**

	git checkout master 							   #prelazim u master branch
	git merge [branch_name]                            #merge-ujem [branch_name] sa masterom
	git push origin master 							   #posle merge obavezno push na master



**Status**


	git status                                         #izlistava fajlove koji nisu merged
	git status -uno                                    #ne prikazuje untracked fajlove (git status --untracked-files=no)
	git log                                            #poslednji komit u lokalnom repozitorijumu
	git diff --name-only --diff-filter=U 			   #Izlistava sve fajlove koji imaju konflikte
	git ls-files . 									   #izlistava sve fajlove u repou
	git ls-files . --ignored --exclude-standard --others	#izlistava git-ignored fajlove
	git ls-files . --exclude-standard --others		   #izlistava untrekovane fajlove
	git clean -f -d                                    #brise untracked fajlove


**Undo**

	git reset										   #undo posle git add .
	git reset --soft HEAD^							   #undo posle git commit -m 'update'
	git reset HEAD [file_name]                         #undo posle git add [file_name] - undo posle dodavanja jednog fajla
	git checkout -- [file_name]                        #diskarduje izmene u jednom fajlu 
	git checkout -- . 								   #diskarduje izmene u svim fajlovima
	git revert b53b3c796b6fdd3e7a02ef06a2e1035db743c137         #revert komit - vraca komit koji je greskom otisao
	git rm --cached [file_name]						   #fajl postaje untracked	



**Diff**

	git diff master master/origin                      #razlike izmedju lokalnog mastera i origin mastera
	git log --graph  --decorate                        #ispisuje log komitova
	git diff [branch_name] [branch_name]               #razlike izmedju dva branch-a
	git diff --name-only  [branch_name] [branch_name]  #pokazuje samo izmenjene fajlove
	git diff [local_branch] [origin/remote_branch]     #razlika izmedju lokalnog i remote branch-a
	git log --oneline fixing_bugs_23-05-2015 ^master   #razlika komitova izmedju dva branch-a
	git log --oneline fixing_bugs_23-05-2015..master   #isto sto i iznad
	git diff -R                                        #diff reversed
    

**Stash**

	git stash                                          #sacuva sve izmene i vraca u najnoviju komitovanu verziju
	git stash save "Poruka"                            #isto sto i ovo gore samo sa deskriptivnom porukom
	git stash list                                     #lista sve stash 
	git stash apply stash@{0}                          #vraca odredjeni stash
	git stash drop stash@{0}                           #brise odredjeni stash, kad ni jedan nije zadat brise zadnji      
	git stash show -p stash@{0}						   #prikazuje sta je u stash-u
    git diff --name-only --diff-filter=U               #fajlovi koji su izmenjeni posle stash apply

**Tags**

	git tag Release-0.0.1 -m "Release of Software on May 22"                #dodaje tag koji oznacava verziju software-a
	git push origin Release-0.0.1                                           #pushuje odredjeni tag na origin remote





