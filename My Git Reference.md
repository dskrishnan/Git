# My Git Reference


### What is Git?  
* It is distributed version control system. This means everybody has complete copy of the data.

* Since it is distributed, it is primarily intended as collaborative version control. So it is normal for Individual user's to feel `Git` too bureaucratic.

* It is written in C, developed by Linus Torvolds to manage Linux Kernel.

* It uses a hidden folder `.git` to store various versions and related informations. This is hidden by default.

* Because of the hidden nature, it is bit more difficult to delete. Most users will accidently delete only the actual files which can be restored from this `.git` folder.

* Git accepts all kinds of file formats including videos, pictures..etc

* But comparing the differences across versions are only in binary form. This means for most formats such as videos & picture, we will know something has changed across versions but won't know what that was precisely.

* Using local folder as Git Local Repository takes more space because of preserving versions.

* GitHub
	* It is a popular remote repository for git.
	* It's free version supports unlimited repositories & unlimited projects.
		* However Repositories have hard limit of 100GB.
		* A polite email might be triggered from GitHub support if it exceeds 1GB and a warning when it reaches 75GB.

### Repository:
All the files related to a project or an application will be kept in a repository.
* It contains files, history, configuration ..everything
* It has two types of repository
	* Local Repository such as Computer
	* Remote Repository such as GitHub

### Three States of Git - These are applicable for both Local & Remote Repository
* Working Directory
	* This is a folder in our Computer that contains all the files
	* It may not be managed by **Git**.
	* However it contains a **".git"** folder which contains the **actual repository**.  
	This repository manages the git commit history.  
	All the files which are finalised are part of this **git repository**.
* Staging Area - Pre Commit holding area
	* This is also referred as Git index. It queues up the changes for the next commit.  
	Since these files are not committed, the files can be moved in & out.  
	These files are not part of **git repository**.
	* Staging is a step before commit process in Git. That is a commit in Git is performed in Two steps: Staging and Actual commit.
	* Any code changes will be recognized as _Modified_ by Git. If it is staged or `git add file-name`, then it is ready for commit. But if it is modified again, then the earlier Staged portion will be committed.
	* Whatever is staged so far will only be committed. If a file is modified after staging, then that modification will not be part of the commit.
* Commit - Git Repository(History)
	* This is where our code is finalized with a meaningful comments.
	* A commit should be done whenever a meaningful work(code block) is completed, such as features, bug fixes.
	* Every commit should represent a meaningful/considerable block of work/code.

# Configuring Git

Type the following in Terminal  
	`git config --global user.name "__________"`  
	`git config --global user.email "_____@____.__"`  

	>Do not use your actual email. Instead find your noreply email from [GitHub Email Settings Page](https://github.com/settings/emails) and use that email.
** To configure the default Text Editor as _Atom_: **
* Type the command `git config --global core.editor "atom --wait"`
* To configure other Text editors refer [Associate Text Editor with Git](https://help.github.com/en/articles/associating-text-editors-with-git).

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

* Add this _My Git Reference.md_ file to the working directory `/Users/__________/documents/programming/Git` locally
* Now check the status of git using the command `git status`. Following status is expected,
>On branch master
Your branch is up to date with 'origin/master'.

	> Untracked files:
  		(use "git add <file>..." to include in what will be committed)

	> `&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;<span style="color:red">_My Git Reference.md_</span>`  

	> nothing added to commit but untracked files present (use "git add" to track)  

* Now lets add the new file to git using the command `git add "My Git Reference.md"`.
* This will move the file from Working Directory to Staging area.{Remember those 3 Stages of Git}. This means file is ready to be committed.
* Checking the `git status` will now give the following message,
> On branch master
Your branch is up to date with 'origin/master'.

>>Changes to be committed:
  (use "git restore --staged <file>..." to unstage)  
	`&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;<space style="color: green">_new file:   My Git Reference.md_</span>`


* At this stage, the file is in Staging area. This means, it is ready to accept changes and can be committed(to move to `.git folder`) after the necessary changes are done.
* Now add this new file to git local repository (.git folder) using the following command,
>`git commit -m `"My Git Reference.md"` file to repository"`
		* It may show email privacy error depending on the settings in [GitHub Email Settings Page](https://github.com/settings/emails).
			** If the appropriate privacy setting is enabled, then use the **do not reply email** from GitHub Email Settings Page](https://github.com/settings/emails) in the `git config --global user.email "_____@____.__"` instead of actual email.  
			** Refer the [email privacy push](https://github.community/t5/How-to-use-Git-and-GitHub/push-declined-due-to-email-privacy-restrictions/m-p/7780#M2641) for errors.
			** Now if the first commit is made with real email, then anybody pulling the repository can look at the initial commits with user email. By using a do not reply email, we can be protected from mysterious roll calls..

* The git status now will be like new repository. So  `git status` will show the following,
>
