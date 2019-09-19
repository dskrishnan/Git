# Git Everything

### Repository:
All the files related to a project or an application will be kept in a repository.
* It contains files, history, configuration ..everything
* It has two types of repository
	* Local Repository such as Computer
	* Remote Repository such as GitHub

### Three States of Git - These are applicable for both Local & Remote Repository
* Working Directory
	* It is a folder in our Computer that contains all the files
	* It may not be managed by **Git**.
	* However it contains a **".git"** folder which contains the **actual repository**.  
	This repository manages the git commit history.  
	All the files which are finalised are part of this **git repository**.
* Staging Area - Pre Commit holding area
	* This is also referred as Git index. It queues up the changes for the next commit.  
	Since these files are not committed, the files can be moved in & out.  
	These files are not part of **git repository**
* Commit - Git Repository(History)

# Configuring Git

Type the following in Terminal
	`git config --global user.name "__________"`  
	`git config --global user.email "_____@____.__"`  

	>Do not use your actual email. Instead find your noreply email from [GitHub Email Settings Page](https://github.com/settings/emails) and use that email.

Now to check if the configurations are done right, type the following,  
	`git config --global --list`

### Cloning or Creating our first Local repository from Remote Server(GitHub)  
* In the terminal navigate to the intended directory in Terminal.
	* In this case, it will be `/Users/Santhanakrishnan/documents/programming/`  
* Get the remote server([GitHub](https://github.com)) URL of the [repository](https://github.com/________/Git.git)
* Type the following in the Terminal
	* `git clone https://github.com/________/Git.git`
* This should create a folder with a repository name.
	* This will be `/Users/___________/documents/programming/Git` in this case. This will be our Working directory.
	* Check the status of the git using the command `git status` . Following status is expected,
	> On branch master  
	Your branch is up-to-date with 'origin/master'.  

	>nothing to commit, working directory clean


### Adding a new file to Git Local Repository(.git folder)

* Add this _Git Everything.md_ file to the working directory `/Users/__________/documents/programming/Git` locally
* Now check the status of git using the command `git status`. Following status is expected,
>On branch master
Your branch is up to date with 'origin/master'.

	> Untracked files:
  		(use "git add <file>..." to include in what will be committed)
			
	> &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;<span style="color:red">_Git Everything.md_</span>  

	> nothing added to commit but untracked files present (use "git add" to track)  

* Now lets add the new file to git using the command `git add "Git Everything.md"`.
* This will move the file from Working Directory to Staging area.{Remember those 3 Stages of Git}. This means file is ready to be committed.
* Checking the `git status` will now give the following message,
> On branch master
Your branch is up to date with 'origin/master'.

>>Changes to be committed:
  (use "git restore --staged <file>..." to unstage)  
	&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;<space style="color: green">_new file:   Git Everything.md_</span>

>>Changes not staged for commit:
  (use "git add <file>..." to update what will be committed)
  (use "git restore <file>..." to discard changes in working directory)
	modified:   Git Everything.md  

* At this stage, the file is in Staging area. This means, it is ready to accept changes and can be committed(to move to `.git folder`) after the necessary changes are done.
* Now add this new file to git local repository (.git folder) using the following command,
>`git commit -m "Adding the 'Git Everything.md' file to repository"`
		* It may show email privacy error. In that case

* The git status now will be like new repository. So  `git status` will show the following,
> 
	


