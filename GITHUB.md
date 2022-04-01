# Git & GitHub Cheatsheet 







&nbsp;
- - -
  
## Git & GitHub - The Practical Guide 

[Udemy link ](https://www.udemy.com/course/git-github-practical-guide/learn/lecture/28082344?start=0#overview)

&nbsp;





### Commands
&nbsp;

##### Change Directory
```
cd {DIRECTORY_NAME}

cd ../files/documents
```
The .. means the parent folder
&nbsp;

##### Show files in current folder
```
ls
```
&nbsp;

##### Create folder
```
mkdir {NAME}

mkdir new_folder
```
&nbsp;

##### Create file
```
touch {NAME}.{type}

touch index.html
```
&nbsp;

##### Remove file
```
rm {NAME}.{type}

rm index.html
```
If you remove a file like this, it will  ***NOT*** show in the trash, It will automatically be removed
&nbsp;

&nbsp;
### Git Commands
&nbsp;

##### Git Help
```
git --help
```
It will show all the possible commands available with git:

```
danielsanchez@Daniels-MacBook-Pro-2 Section 3 % git --help
usage: git [--version] [--help] [-C <path>] [-c <name>=<value>]
           [--exec-path[=<path>]] [--html-path] [--man-path] [--info-path]
           [-p | --paginate | -P | --no-pager] [--no-replace-objects] [--bare]
           [--git-dir=<path>] [--work-tree=<path>] [--namespace=<name>]
           [--super-prefix=<path>] [--config-env=<name>=<envvar>]
           <command> [<args>]

These are common Git commands used in various situations:

start a working area (see also: git help tutorial)
   clone     Clone a repository into a new directory
   init      Create an empty Git repository or reinitialize an existing one

work on the current change (see also: git help everyday)
   add       Add file contents to the index
   mv        Move or rename a file, a directory, or a symlink
   restore   Restore working tree files
   rm        Remove files from the working tree and from the index

examine the history and state (see also: git help revisions)
   bisect    Use binary search to find the commit that introduced a bug
   diff      Show changes between commits, commit and working tree, etc
   grep      Print lines matching a pattern
   log       Show commit logs
   show      Show various types of objects
   status    Show the working tree status

grow, mark and tweak your common history
   branch    List, create, or delete branches
   commit    Record changes to the repository
   merge     Join two or more development histories together
   rebase    Reapply commits on top of another base tip
   reset     Reset current HEAD to the specified state
   switch    Switch branches
   tag       Create, list, delete or verify a tag object signed with GPG

collaborate (see also: git help workflows)
   fetch     Download objects and refs from another repository
   pull      Fetch from and integrate with another repository or a local branch
   push      Update remote refs along with associated objects

'git help -a' and 'git help -g' list available subcommands and some
concept guides. See 'git help <command>' or 'git help <concept>'
to read about a specific subcommand or concept.
See 'git help git' for an overview of the system.

```


##### Initialize git
```
git init
```
Creates the .git folder and initialize the project with git.
&nbsp;

##### git status
```
git status
```
It will give you general information about your current directory, 
```
danielsanchez@Daniels-MacBook-Pro-2 Section 3 % git status
On branch master

No commits yet

Untracked files:
  (use "git add <file>..." to include in what will be committed)
	file1.txt

nothing added to commit but untracked files present (use "git add" to track)
```
&nbsp;

##### Add Files to commit
```
git add {FILE}

git add .
```
This will add *ALL* the files ( . ) to the staging area
&nbsp;

##### Commit new changes
```
git commit -m "{MESSAGE or DESCRIPTION}"

git commit -m "First commit of the project"

```
&nbsp;


##### Git log
```
git log

```
It will show ***ALL*** the commits you have made in the current branch

```
danielsanchez@Daniels-MacBook-Pro-2 Section 3 % git log
commit ba27d53647dbdc4ddf0db2c103743085e0299872 (HEAD -> master)
Author: danielsanchezsa <danielsanchez.2000@hotmail.com>
Date:   Thu Mar 31 12:58:53 2022 -0600

    Second Commit Testing

commit b97a182b6a9433ab6ae4a8e78d6ce925da360382
Author: danielsanchezsa <danielsanchez.2000@hotmail.com>
Date:   Thu Mar 31 12:30:37 2022 -0600

    First commit of the project
```
&nbsp;



##### Git checkout



```
git checkout {COMMIT_ID}

git checkout ba27d53647dbdc4ddf0db2c103743085e0299872

```
This will change the current ***commit OR branch*** into the one you specified.
To go back to original commit OR branch:

```
git checkout -
```
&nbsp;

##### Git branch
```
git branch
git branch {BRANCH_NAME}

```
This will create a new branch in our repository.
If you don't specify a name, it will show you the current branch you are in.

To switch to the new brand, you use the [Checkout Command](#git-checkout)

[Explanation](#why-multiple-branches)
&nbsp;

##### Merge Branches
```
git merge {BRANCH_NAME}

git merge testingBranch

```
This will combine the branch you specified in your current branch.

&nbsp;

##### Delete Branches
```
git branch {BRANCH_NAME} --delete

git branch secondBranch --delete

```
This will delete the branch you specify

&nbsp;

##### Git switch
```
git switch {BRANCH_NAME}

git switch secondBranch

```
This will change the current branch to the other one you specified.

&nbsp;


##### Reset Current Commit
```
git reset --hard HEAD && git clean -df

```
This will reset the stage area, and clean the files in the folder you are working on.

&nbsp;


##### Return previous commit
```
git reset --hard HEAD~1 && git clean -df

```
It will do the same as resetting the current commit, but also going back 1 commit, because we specify "*HEAD~1*"

&nbsp;





#### Summary Table

| Command | Description |
|  --- |  --- |
|git init| create git repository|
|git status|check working directory & staging area status|
|git log| display all commits of current branch|
|git ls-files| list data in staging area|
|git add {filename}| Adds the file to staging area|
|git commit -m "{message}"|creates a new commit with a message|
|git checkout {ID}|switch to the commit or branch specified|
|git branch| display all the branches in the project|
|git branch {NAME}| creates a new branch|
|git merge {OTHER_BRANCH}| Combines two branches into the one you are in|
|git reset --hard| deletes all changes in current commit|
|git reset --hard HEAD~1| delete last commit|
|git clean -df| delete untracked files|
|git branch -D {BRANCH_NAME}|deletes the branch you pecify|
- - -















### Git
  - Git is an open source **version control system.**
  - It is used to handle a project timeline, implementations, etc.


&nbsp;

#### Keywords
  - **Working Directory**: All the files of your project included and managed by Git.
  - **Commit**: A snapshot (Copy) of the directory.
  When you make soma changes to your directory, you create a commit, which will then be used to ***compare*** it to the previous commits and save the changes.
  Git does ***NOT*** save the same files on each commit, only the changes that were made.
  - **branch**: To organize the while project (commits, changes, files, etc.), it uses something called *BRANCH*
  - **.git**: This is a hidden folder in your directory which is automatically created when you init git in your project. Here is where it stores all the files git needs to work.
- **HEAD**: it is the latest commit of the branch.
- **detached HEAD**: it is a commit which is in more than one branch.
- **.gitignore**: It is a file used to specify the files that will not be included in the git repository.






&nbsp;
&nbsp;

#### Explanations
&nbsp;


##### Why multiple branches?
When you are trying to implement new things to your proyect, the best way to avoid errors, confusions anr organize yourself, is to ue different branches.

You can think of it as a "*secure*" implementation. If you messed it up, you can change the branch, or if its good, you merge it to the master branch.

Once you want to combine the branches, use the [Merge](#merge-branches) command.

To delete a branch, use the [Delete](#delete-branches) command

- - -


   &nbsp;


### GitHub
- GitHub is a development platform
- It is used to store your git data in a ***Cloud Hosting***
- It also allows you to ***work in teams*** in the cloud simultaneously.
