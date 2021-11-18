# Version Controllers & Git
## About this document
This is a markdown document about a presentation giving in cloud computing module about version controllers and Git. The dodument is summarizing the presentation that was splitted into 2 parts : general presentation and workshop (The workshop is the tutorials in table of contents).
Author: 
- Safoine EL KHABICH [Linkedin](https://www.linkedin.com/in/safoinme/)  <safoine.elkhabich@um5r.ac.ma>  
- Younes OUASSINE [Linkedin](https://www.linkedin.com/in/younes-ouassine-b629a71a4/)  <younes.ouassine@um5r.ac.ma>  

Markdown is a lightweight markup language based on the formatting conventions
that people naturally use in email.
As [John Gruber] writes on the [Markdown site][df1]

> The overriding design goal for Markdown's
> formatting syntax is to make it as readable
> as possible. The idea is that a
> Markdown-formatted document should be
> publishable as-is, as plain text, without
> looking like it's been marked up with tags
> or formatting instructions. 

## Table of Contents
+ [I : Version controllers systems](#Version-controllers-systems)
     + [1 : What is a version controller](#what-is-a-version-controler-system-)
     + [2 : The benefits of version controller](#benefits-of-the-version-control-system)
     + [3 : The use of version controller](#use-of-version-control-system)
     + [4 : Types of version controller](#types-of-version-control-systems)
+ [II: Git as a version controller](#git-as-a-version-controller)
    + [1 : Introduction ](#introduction)
    + [2 : Git structure ](#git-repository-structer)
+ [III: Tutorial - Setup Local Git server ](#setting-up-the-server)
+ [IV: Tutorial - Basic usage of git ](#basic-usage-of-git)
    + [First Commit](#first-commit)
    + [Check The Current Status Of The Directory](#check-the-current-status-of-the-directory)
    + [git automatically finds out the changes in working directory](#git-automatically-finds-out-the-changes-in-working-directory)
    + [stage the changes](#stage-the-changes)
    + [View Commit History](#view-commit-history)
    + [Get history versions](#get-history-versions)
    + [Undoing Things](#undoing-things)
      - [Unmodifying a Modified File](#unmodifying-a-modified-file)
      - [Unstaging a Staged File](#unstaging-a-staged-file)
      - [Undoing Committed Changes](#undoing-committed-changes)
    + [Git Branching](#git-branching)
      - [Creating A Branch](#creating-a-branch)
      - [Navigating Branches](#navigating-branches)
      - [Merging Branches](#merging-branches)
    + [Resolving Conflicts](#resolving-conflicts)

## [Version controllers systems](https://git-scm.com/book/en/v2/Getting-Started-About-Version-Control)
##### _What is a "version controler system" ?_
Version control systems are a category of software tools that helps in recording changes made to files by keeping a track of modifications done to the code. 
##### _Benefits of the version control system_

- Assuring the project development speed by providing efficient collaboration.
- Expedite product delivery, and skills of the employees through better communication and assistance.
- Reduce possibilities of errors and conflicts meanwhile project development through traceability to every small change.
- Employees or contributor of the project can contribute from anywhere irrespective of the different geographical locations. 
- Helps in recovery in case of any disaster or contingent situation.
- Informs us about Who, What, When, Why changes have been made.

##### _Use of Version Control System:_
- **A repository** : It can be thought of as a database of changes. It contains all the edits and historical versions (snapshots) of the project.
- **Copy of Work (sometimes called as checkout)** : It is the personal copy of all the files in a project. You can edit to this copy, without affecting the work of others and you can finally commit your changes to a repository when you are done making your changes.

##### _Types of Version Control Systems:_
- **Local Version Control Systems** : It is one of the simplest forms and has a database that kept all the changes to files under revision control. RCS is one of the most common VCS tools. It keeps patch sets (differences between files) in a special format on disk. By adding up all the patches it can then re-create what any file looked like at any point in time. 
- **Centralized Version Control Systems** : Centralized version control systems contain just one repository and each user gets their own working copy. You need to commit to reflecting your changes in the repository. It is possible for others to see your changes by updating.
- **Distributed Version Control Systems** : Distributed version control systems contain multiple repositories. Each user has their own repository and working copy. Just committing your changes will not give others access to your changes. This is because commit will reflect those changes in your local repository and you need to push them in order to make them visible on the central repository. Similarly, When you update, you do not get other’s changes unless you have first pulled those changes into your repository. 
![system archtecture](https://www.ecanarys.com/Portals/0/xBlog/uploads/2020/5/13/5.jpg)

## [Git as a version controller](https://git-scm.com/docs/git)

##### _Introduction:_
- Git is a **free** and **open source** distributed version control system designed to handle everything from small to very large projects with speed and efficiency.

- Git relies on **the basis of distributed development** of a software where more than one developer may have access to the source code of a specific application and can modify changes to it which may be seen by other developers.

- Initially designed and developed by **Linus Torvalds** for **Linux kernel** development in 2005.

- Every git working directory is a **full-fledged repository** with complete history and full version-tracking capabilities, independent of network access or a central server.

- Git allows a team of people to work together, all using the same files. And it helps the team cope up with the confusion that tends to happen when multiple people are editing the same files.

##### _Git repository structer:_

- **Branch :** 
A version of the repository that diverges from the main working project. Branches can be a new version of a repository, experimental changes, or personal forks of a repository for users to alter and test changes.

- **Git Checkout :** 
The **_git checkout command_** is used to switch branches in a repository. _git checkout testing-el_ would take you to the testing-el branch whereas **_git checkout maain_** would drop you back into main. Be careful with your staged files and commits when switching between branches.

- **Clone :** 
A clone is a copy of a repository or the action of copying a repository. When cloning a repository into another branch, the new branch becomes a remote-tracking branch that can talk upstream to its origin branch (via pushes, pulls, and fetches).

- **Fetch :**
By performing a Git fetch, you are downloading and copying that branch’s files to your workstation. Multiple branches can be fetched at once, and you can rename the branches when running the command to suit your needs.

- **HEAD :**
HEAD is a reference variable used to denote the most current commit of the repository in which you are working. When you add a new commit, HEAD will then become that new commit.

- **main :**
The primary branch of all repositories. All committed and accepted changes should be on the main branch. You can work directly from the main branch, or create other branches. 
🧑🏻‍💻 ⚠️ : [The original name for the primary branch was master and got changed to main](https://www.theserverside.com/feature/Why-GitHub-renamed-its-master-branch-to-main)
- **Origin :**
The conventional name for the primary version of a repository. Git also uses origin as a system alias for pushing and fetching data to and from the primary branch. For example, git push origin main, when run on a remote, will push the changes to the main branch of the primary repository database.

- **Pull/Pull Request :**
If someone has changed code on a separate branch of a project and wants it to be reviewed to add to the main branch, that someone can put in a pull request. Pull requests ask the repo maintainers to review the commits made, and then, if acceptable, merge the changes upstream. A pull happens when adding the changes to the main branch.

- **Push :**
Updates a remote branch with the commits made to the current branch. You are literally “pushing” your changes onto the remote.


## Setting Up the Server

First, you create a git user account and a .ssh directory for that user.
```
$ sudo adduser git
$ su git
$ cd
$ mkdir .ssh && chmod 700 .ssh
$ touch .ssh/authorized_keys && chmod 600 .ssh/authorized_keys
```
> `chmod 700` 700 permissions Protects a file against any access from other users, while the issuing user still has full access.
> `chmod 600` 600 permissions means that only the owner of the file has full read and write access to it.
> For more detailed informations about permessions check [Manage file permissions on Unix-like systems](https://kb.iu.edu/d/abdb) 

Now let's add our developers teams SSH public keys to the authorized_keys file for the git user so they have access.

```sh
$ cat id_rsa.younes.pub >> ~/.ssh/authorized_keys
$ cat id_rsa.bilal.pub >> ~/.ssh/authorized_keys
$ cat id_rsa.nada.pub >> ~/.ssh/authorized_keys
```
Example of how SSH public key looks.
```sh
$ cat id_rsa.youssef.pub
ssh-rsa AAAAB3NzaC1yc2EAAAADAQABAAABAQCB007n/ww+ouN4gSLKssMxXnBOvf9LGt4L
ojG6rs6hPB09j9R/T17/x4lhJA0F3FR1rP6kYBRsWj2aThGw6HXLm9/5zytK6Ztg3RPKK+4k
Yjh6541NYsnEAZuXz0jTTyAUfrtU3Z5E003C4oxOj6H0rfIF1kKI9MAQLMdpGW1GYEIgS9Ez
Sdfd8AcCIicTDWbqLAcU4UpkaX8KyGlLwsNuuGztobF8m72ALC/nLF6JLtPofwFBlgc+myiv
O7TCUSBdLQlgMVOFq1I2uPWQOkOWQAHukEOmfjy2jctxSDBQ220ymjaNsHT4kgtZg2AYYgPq
dAv8JggJICUvax2T9va5 gsg-keypair
```

Now can set up an empty repository for them by running git init with the --bare option, which initializes the repository without a working directory:
```sh
$ cd
$ mkdir ipsgitproject.git
$ cd ipsgitproject.git
$ git init --bare
Initialized empty Git repository in /ipsgitproject.git/
```
Next step is on of our developers can push the first version of their project into that repository by adding it as a remote and pushing up a branch. Note that someone must shell onto the machine and create a bare repository every time you want to add a project.
```sh
# on Younes computer
$ cd ipsgitproject
$ git init
$ git add .
$ git commit -m 'Initial commit for ips project'
# Our server ip adresse should be after the user@ip_adress:path_to_project_folder
$ git remote add origin git@165.232.116.220:ipsgitproject.git
$ git push origin main
```
After younes has pushed the first we can see that our project folder contains this files
```sh
$ cat /ipsgitproject
HEAD  branches  config  description  hooks  info  objects  refs
```
## Basic usage of git
After the initialization of our project and pushing the first copy of our project we can now start show the basic usage of git and why it's considered very crucial tool in development prject.

#### First Commit
```
$ git add .
$ git commit -m "comment what you are adding, changing or deleting"
$ git push origin main
```
`git add <file>` add changes in files to the next commit

The string afters `-m` is the commit message, it's always a good
idea to remind yourself why this commit is necessary and what's
changed

#### Check The Current Status Of The Directory
```sh
$ git status
On branch main
nothing to commit, working tree clean
```
The output says there isn't any untracked change from last commit

#### git automatically finds out the changes in working directory
```
$ git status
On branch main
Changes not staged for commit:
  (use "git add <file>..." to update what will be committed)
  (use "git checkout -- <file>..." to discard changes in working directory)
no changes added to commit (use "git add" and/or "git commit -a")
```

#### stage the changes
```
$ git add .
$ git status
On branch main
Changes to be committed:
  (use "git reset HEAD <file>..." to unstage)
  modified:   ...
```
When using `git add`, changes are tracked in the staging area.
Think staging area as accepted changes. Next `git commit` will record all changes in staging area.

        
#### View Commit History
```
$ git log
commit 16c465e96776c5bdf0535905f5d2c6fa942bc028
Author: MACRPO <macrpo@MACRPOs-MacBook-Pro.local>
Date:   Tue Nov 16 22:27:27 2021 +0100

    the seconde commit

commit 394046b1b7bf13856d54f36c2210c517bb0a0e2e
Author: MACRPO <macrpo@MACRPOs-MacBook-Pro.local>
Date:   Tue Nov 16 22:18:44 2021 +0100

    the first commit
```
We can see the two commits made to this repository.

#### Get history versions

What's a version control system good for if we cannot revert back to old versions?  
Luckily, git allows us to easily travel back and force in commit.
Think your commits as snapshots of the repository.

Using the `git log` command, you can find the hash for every commits. 
Think hash as identifier for each commit.  

Your hash might be different from what I have:
```
git log
commit 5bf24593972643d8a6629238f5ee438e5142b2e6 (HEAD -> main, origin/main)
```

```
$ git checkout 5bf24593972643d8a6629238f5ee438e5142b2e6
Note: switching to '5bf24593972643d8a6629238f5ee438e5142b2e6'.

You are in 'detached HEAD' state. You can look around, make experimental
changes and commit them, and you can discard any commits you make in this
state without impacting any branches by switching back to a branch.

If you want to create a new branch to retain commits you create, you may
do so (now or later) by using -c with the switch command. Example:

  git switch -c <new-branch-name>

Or undo this operation with:

  git switch -

Turn off this advice by setting config variable advice.detachedHead to false

HEAD is now at 5bf2459 test2
``` 
**HEAD** is where we are currently at.

`git checkout <hash>`takes us back to the commit specified by the hash.

> main is the name of the default branch.
> By checking out a branch by name, you go to the latest version of that branch.

Use `git checkout main` to go back to latest commit.

#### Undoing Things
##### Unmodifying a Modified File 
First, go back to main version `git checkout main`.

If you run `git status`, git should report *working directory clean*.

Pretend we have made some unwanted changes which haven't not been staged (we have not run `git add`) yet.  
`echo "Unwanted Change" >> ips_names/bilal.txt`  
This command appends one line with string "Unwanted Change" to the end of the file.

When we run `git status` again, we will see d3-demo.html has been modified but changes have not been staged.

```
$ git status
On branch main
Your branch is up to date with 'origin/main'.

Changes not staged for commit:
  (use "git add <file>..." to update what will be committed)
  (use "git restore <file>..." to discard changes in working directory)
	modified:   ips_names/bilal.txt

no changes added to commit (use "git add" and/or "git commit -a")
```

As it suggests, we can use `git checkout ips_names/bilal.txt` to discard the changes we have made.  
You can confirm that the appended line has disappeared using `tail ips_names/bilal.txt`, a command to see the last lines of the file.

##### Unstaging a Staged File
Pretend we have made some unwanted changes and have staged these changes 
Let's add something into bilal.txt file
```bash
$ git add .
$ git status
On branch main
Your branch is up to date with 'origin/main'.

Changes to be committed:
  (use "git restore --staged <file>..." to unstage)
	modified:   ips_names/bilal.txt
```

Similarly, we can follow what the `git status` instructs us to do:  
`git reset HEAD .`  
Since we have checked out main branch, HEAD is equivalent to main and refers to files in most recent commit.

However, we are not done yet, if you run `git status` again, you will find we end up in previous situation:
we have made some changes but have not staged these changes yet (the "Unwanted Change" line is still there).  
Run `git checkout .` to reset the file.

If it's okay to discard all changes (staged or unstaged), you can directly run `git checkout <hash>` to go back to a specific commit.
    
##### Undoing Committed Changes
Pretend we have made some unwanted changes and have committed these changes
Let's change something in bilal.txt, add it to git and commit it.
```bash
$ git add .
$ git commit -m "unwanted changes committed"
```

To revert back, we basically create an overwriting commit.  
*You can achieve the same effect by remove unwanted changes, add the file, and commit.*  

`git revert HEAD --no-edit` 
> [git-revert](https://git-scm.com/docs/git-revert) revert the changes that the related patches introduce, and record some new commits that record them.
>
> git revert is used to record some new commits to reverse the effect of some earlier commits (often only a faulty one).
> If you want to throw away all uncommitted changes in your working directory, you should see git-reset[1], particularly the --hard option.
> If you want to extract specific files as they were in another commit, you should see git-checkout[1], specifically the git checkout <commit> -- <filename> syntax.
> Take care with these alternatives as both will discard uncommitted changes in your working directory.

#### Git Branching
##### Creating A Branch
Typically, a stable version of an application is stored in the main branch. 
When we plan to make some changes, we open a new branch and store changes in the new branch.
By separating the development application and the deployment application (the stable version),
we can make changes without worrying about potentially damaging effects.

We can create a new branch using 
`git checkout -b <branchname>`

> The command is a shortcut for `git branch <branchname>` followed by a `git checkout <branchname>`.

##### Navigating Branches
You can use `git branch` to view all branches and use `git checkout <branchname>` to navigate around branches.

##### Merging Branches 

First, let us introduce a divergence -- we add a README in dev branch while make some changes to d3-demo.html in main branch.

+ changes in dev branch
  ```sh
  $ git checkout dev
  Switched to branch 'dev'
  $ echo "This is a document for git presentation" >> README.md
  $ ls
  IPSStudents.wsgi	__pycache__		dev			requirements.txt	
  templates   'README.md'		app.py			ips_names		static
  $ git add README.md
  $ git commit -m "Added README"
  ```
    we can see that our README.dm is added to our dev branch, now if we switch back to our main branch we will not be finding the README file.
+ changes in main branch
  ```sh
  $ git checkout main
  Switched to branch 'main'
  $ ls
  IPSStudents.wsgi	app.py			ips_names		static
    __pycache__		dev			requirements.txt	templates
  ```


We can view the branches and how they diverge using  
```
$ git log --all --graph
* commit 6116dbad24d7ec36c1ed5fe0528038e2aa14ce19 (origin/dev, dev)
| Author: safoin <safoinpers@Safoines-MacBook-Pro.local>
| Date:   Wed Nov 17 15:03:39 2021 +0100
| 
|     adding README
| 
* commit 2d1c85ab91ca7a349a5439cfec42e6563cab106f (HEAD -> main)
| Author: safoin <safoinpers@Safoines-MacBook-Pro.local>
| Date:   Wed Nov 17 14:55:40 2021 +0100
| 
|     Revert "unwanted changes to bilal.txt"
|     
|     This reverts commit 5b6c79a0a7876ccd175644f2e1c1cd5dd2598256.
| 
* commit 5b6c79a0a7876ccd175644f2e1c1cd5dd2598256
| Author: safoin <safoinpers@Safoines-MacBook-Pro.local>
| Date:   Wed Nov 17 14:55:14 2021 +0100
| 
|     unwanted changes to bilal.txt
| 
```

> The --all flag makes sure that we see all the branches. The default is to show only the current branch.  
> Adding the --graph option to git log causes it to draw the commit tree using simple ASCII characters. 

Often we want to merge the changes in main branch to our development branch so that the developemnt branch
is up to date with recent changes in main while keep its local changes unaffected.
Now both branches contain independent changes. We can merge the changes from the main branch by:
```
$ git checkout dev
$ git merge main
$ git log --all --graph
*   commit 2b1918dfadc6d33f7b1a1f2e2ad67faadbe63bcf (HEAD -> dev)
|\  Merge: 6116dba c0a8603
| | Author: safoin <safoinpers@Safoines-MacBook-Pro.local>
| | Date:   Wed Nov 17 15:19:11 2021 +0100
| | 
| |     Merge branch 'main' into dev
| | 
| * commit c0a86030f1cb23e6cba5f788ff67ac60074aa5e0 (origin/main, origin/HEAD, main)
| | Author: safoin <safoinpers@Safoines-MacBook-Pro.local>
| | Date:   Wed Nov 17 15:13:16 2021 +0100
| | 
| |     modifying bilal in main branch
| | 
* | commit 6116dbad24d7ec36c1ed5fe0528038e2aa14ce19 (origin/dev)
|/  Author: safoin <safoinpers@Safoines-MacBook-Pro.local>
|   Date:   Wed Nov 17 15:03:39 2021 +0100
|   
|       adding README
| 
```

If we show the conetent of the bilal.txt file we can see that the modification from main branch has been added to the dev branch.

However, the new README.md in dev is not present if we switch to main branch.

Another way to achieve the same effect is using [rebase](https://git-scm.com/docs/git-rebase) command.
Instead of running `git merge main`, we will run `git rebase main` in dev branch.

> Merge VS Rebase
> 
> The final result of the rebase is very similar to the merge. The greet branch now contains all of its changes, as well as all the changes from the main branch. However, the commit tree is quite different. The commit tree for the greet branch has been rewritten so that the main branch is a part of the commit history. This leaves the chain of commits linear and much easier to read.
> 
> When to Rebase, When to Merge?
> 
> Don't use rebase :
>
> If the branch is public and shared with others. Rewriting publicly shared branches will tend to screw up other members of the team.
> When the exact history of the commit branch is important (since rebase rewrites the commit history).
> Given the above guidelines, I tend to use rebase for short-lived, local branches and merge for branches in the public repository.
> 

#### Resolving Conflicts

Sadly, things do not always go smoothly. Conflicts arise when you are merging two branches with conflicting changes.

+ changes to dev branch
  + Checkout the dev branch. `git checkout dev`
  + Modify the bilal.txt from other machine push it to the repo and at same time modify the same file in the current machine.
  + Commit this change. `git add .` and `git commit -m "modifying bilal.txt to make conflit"`


If we try to merge two branches, we will get a merge conflict.
```sh
$ git checkout dev
$ git merge dev
 * branch            dev        -> FETCH_HEAD
Auto-merging ips_names/bilal.txt
CONFLICT (content): Merge conflict in ips_names/bilal.txt
Automatic merge failed; fix conflicts and then commit the result.
```

If you open the d3-demo.html, it will look like:
```
<<<<<<< HEAD
Bilal LOTFI, 0796857855
=======
ilall LOTFI, 0796857855
>>>>>>> d03df6970cc1bfc94b4b871bf481d08ba09c7a48
```

> The first section is the version on the head of the current branch (dev). 
> The second section is the new version.

We need to manually resolve the conflict. 
Some possible ways to resolve this conflict includes deleting one section and merging two sections.

For merging, we can modify the conflict part to be:
```
Bilal LOTFI, 0796857855
```

Then we can commit the conflict resolution by `git add .` and `git commit -m "resolving the conflit"`.

As it is a hassle to fix merge conflicts, it is preferable to avoid conflicts at the beginning.

**The end ! Thank you all** 

Big Thanks to our supervisor and Cloud Computing Professor :
- Ahmed EL-YAHYAOUI <a.elyahyaoui@um5r.ac.ma>  


[//]: # (These are reference links used in the body of this note and get stripped out when the markdown processor does its job. There is no need to format nicely because it shouldn't be seen. Thanks SO - http://stackoverflow.com/questions/4823468/store-comments-in-markdown-syntax)

   [git]: <https://git-scm.com>
   [git-setup-server]: <https://git-scm.com/book/en/v2/Git-on-the-Server-Setting-Up-the-Server>
   [john gruber]: <http://daringfireball.net>
   [df1]: <http://daringfireball.net/projects/markdown/>
   [markdown-it]: <https://github.com/markdown-it/markdown-it>
   [Original-article-inspired-from]: <https://cs.brown.edu/courses/csci1320/tutorials/cs132-git-markdown-tutorial/markdown-git.html#git>

