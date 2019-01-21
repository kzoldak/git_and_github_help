# Git vs Github 
[Kevin Markham’s Data School Website](www.dataschool.io) with youtube videos [here](https://www.youtube.com/playlist?list=PL5-da3qGB5IBLMp7LtN8Nc3Efd4hJq0kD) to provide help using git and github.


### Notes:
Git is a system for version control. Github is a website that lets you upload your repositories online. 
Benefits:
-	backs up your files
-	visualization
-	you can access your code from anywhere if it’s on github, because it’s online. 
-	others can have access to your code
-	easy collaboration
Git does not require the use of Github, but it is commonly used. 
Must download git. Can do that on github’s website under “Set up Git” or go to the git-scm.com website. 


# Location of git
My git is located in the `/usr/bin/` directory. 


# Terms
__Repo__ – stands for repository. Will use this for short. 

__Forking__ – gaining a copy of someone elses repository. Downloads a copy so that you can make changes and then pull request for those changes to be accepted (“pulled into”) their version of the repo. 

__Cloning__ – download a repo to your computer. 

__Pushing__ – upload changes you made to a repo to your Github page on that repo. 

__Pull Request__ – request author or owner of the original repo to pull your changes into their repo version. That way your changes will be included for all future users who download their repo. 

__Commit__ – commit changes that you have made to a repo from your computer.

__Fetch__ – fetch changes from upstream. If you download a repo to your computer and don’t touch it for a week before beginning changes, you should fetch the changes from the original repo to ensure you have the most updated copy of the owner’s repo.  

__merging__ – merging is when you take the fetch changes and upload them to your github page on the same repo. Merging and fetching should be done simultaneously. 



# TERMINAL COMMANDS:
	git config --global user.name “your name here”
	git config --global user.email “your email”


# Steps at the Terminal 
** anything in italic needs to be substituted for. Those will be explained after each one. 


`git clone *url*`
url is the url of the github repository you are downloading to your computer. Go to the owner’s repo page and you can click on “get url”. Paste that into the terminal after git clone. There is a .git folder within each repository that stores all the git information of that repository. 

git remote -v
	references to remotes that are not on your computer. 
	this command should return something like:
	origin https://github.com/mtbk24/PyDataScience.git
	There should be 2 of these. One with (fetch) at the end 
	and one with (push) at the end. 

git remote add origin url
	setup a remote. 
	

EDIT SOME OF THE FILES ON YOUR COMPUTER.
FOR EXAMPLE, 

vi README.md
	… make changes to readme file
touch new.md
	… make a new file and put stuff in it. 

git status
	check on the status of the files you edited or created. 
	Should tell you which files you made changes to. 
	You need to stage all files for committing. You do this with the add command. 

git add new.md
	staging a new file before committing it.  
	this is an example of making a new markdown (.md) file. 		
	You would use this to make a new file, but replace new.md with the name of the file. 

git add README.md
	staging an edited file before committing it.
	if your repo doesn't have a README.md file, you need to make one. 

git add .
	Instead of using the last two   git add filename   examples, 
	you can stage all the new and edited files at once using   git add .
	This saves time and takes care of all your files at once. 

git status 
	do a status check to make sure you didn't forget any files. 

git commit -m "edited README.md and added new.md"
	the -m stands for message. For every commit, you must provide a message. 
	It's required!

git status
	check once more to see if everything is read. Git will tell you if everything is clean 
	and there is nothing more to commit.
On branch master
Your branch is ahead of 'origin/master' by 1 commit.
  (use "git push" to publish your local commits)

nothing to commit, working directory clean
	
git log
	check the log files. don't need to do this step, but it's nice to check it. 

git push origin master
	push your changes up to your Github website. 
	you are pushing your master branch to the origin remote. 
	THIS WILL FAIL IF YOU FORGOT TO SET UP A REMOTE. 
	SEE:  git remote add origin url


————
If you perform a lot of changes within a directory, such as moving files around and making new sub directories, using the  git add .  won't get rid of the old files. 
TRY:
git add -A
git commit -m 'blah blah blah'
git push origin master

If things have really gotten bad, try:
git diff --name-only --diff-filter=D -z | xargs -0 git rm --cached
git reset HEAD .
git commit -a
git push origin master

I am uncertain where exactly the command is cleaning up the files on the website because running the git diff line doesn't entirely do it.  For more help, don't forget you can do:  git help rm   for help on removing files. 


	
Making a New Repository
To make a new repo, you first need to make it on your GitHub page by clicking the + sign and clicking on New Repository. Choose a name and write a description. Choose public. 
Check box that says initialize this repo with a README. This repo now exists on Github ONLY and not your local computer. To get it on your local computer, use the steps listed above, under Steps at the Terminal. These steps work for a repo you created yourself as well as one you forked from someone else. 



pull request – when a contributor makes changes to a package’s code and they are requesting the repository owner to pull those changes into the repository and make them permanent. 


The most commonly used git commands are:

   add        Add file contents to the index
   bisect     Find by binary search the change that introduced a bug
   branch     List, create, or delete branches
   checkout   Checkout a branch or paths to the working tree
   clone      Clone a repository into a new directory
   commit     Record changes to the repository
   diff       Show changes between commits, commit and working tree, etc
   fetch      Download objects and refs from another repository
   grep       Print lines matching a pattern
   init       Create an empty Git repository or reinitialize an existing one
   log        Show commit logs
   merge      Join two or more development histories together
   mv         Move or rename a file, a directory, or a symlink
   pull       Fetch from and integrate with another repository or a local branch
   push       Update remote refs along with associated objects
   rebase     Forward-port local commits to the updated upstream head
   reset      Reset current HEAD to the specified state
   rm         Remove files from the working tree and from the index
   show       Show various types of objects
   status     Show the working tree status
   tag        Create, list, delete or verify a tag object signed with GPG

'git help -a' and 'git help -g' lists available subcommands and some
concept guides. See 'git help <command>' or 'git help <concept>'
to read about a specific subcommand or concept.

