


## **setup**
[Download git for Windows](http://msysgit.github.io/)
[Download git for Linux](http://git-scm.com/book/en/Getting-Started-Installing-Git)
<span style="background-color: #ff0000">
create a new directory, open it and perform a </span>
**`git init`**
<span style="background-color: #ff0000">to create a new git repository.</span>

If want to connect to github remember to put the appropiate credential. 
Now is not enough username and password but use key. 
The procedure is set username e user email with 
**git config --global user.name "TheNameOfUser"**
**git config --global user.email  "TheEmailUser@server.com"**
Then for the password create a personal key on github (from developer settings) copy it and then 
**git config credential.helper store** che salva le password che usi poi fai un push al repository di github e quando chiede la password metti la chiave che hai salvato. Questa coppia username e password verra salvata da credential.helper e si spera che non la chiede piu
* * *
## **checkout a repository**
<span >create a working copy of a local repository by running the command
**`git clone /path/to/repository`**
when using a remote server, your command will be
**`git clone username@host:/path/to/repository`**
</span>
* * *
## **workflow**
<span >your local repository consists of three "trees" maintained by git. the first one is your Working Directory which holds the actual files. the second one is the Index which acts as a staging area and finally the HEAD which points to the last commit you've made.</span>
![b52d9786187ed0db638745e11bdf4090.png](./_resources/b52d9786187ed0db638745e11bdf4090.png)

<span >git add filename
`git add *`
This is the first step in the basic git workflow. To actually commit these changes use
**`git commit -m "Commit message"`**
Now the file is committed to the **HEAD**, but not in your remote repository yet.</span>
* * *
# **pushing changes**
<span style="background-color: #695EFF">Your changes are now in the **HEAD** of your local working copy. To send those changes to your remote repository, execute</span>
**`git push origin master`**
<span style="background-color: #695EFF">Change master to whatever branch you want to push your changes to.
If you have not cloned an existing repository and want to connect your repository to a remote server, you need to add it with</span>
**`git remote add origin <server>`**
<span style="background-color: #695EFF">Now you are able to push your changes to the selected remote server</span>
* * *
## **branching**
<span style="background-color: #d08483">Branches are used to develop features isolated from each other. The *master* branch is the "default" branch when you create a repository. Use other branches for development and merge them back to the master branch upon completion.</span>
![e42b346f36ac217ca2cd6a383cf049ae.png](./_resources/e42b346f36ac217ca2cd6a383cf049ae.png)

<span style="background-color: #d08483">create a new branch named "feature_x" and switch to it using</span>
**`git checkout -b feature_x`**
<span style="background-color: #d08483">switch back to master</span>
**`git checkout master`**
<span style="background-color: #d08483">and delete the branch again</span>
**`git branch -d feature_x`**
<span style="background-color: #d08483">a branch ***is not available to others*** unless you push the branch to your remote repository</span>
**`git push origin <branch>`**
* * *
## **update & merge**
<span style="background-color: #ff0000">to update your local repository to the newest commit, execute</span>
**`git pull`**
<span style="background-color: #ff0000">in your working directory to fetch and merge remote changes.
to merge another branch into your active branch (e.g. master), use</span>
**`git merge <branch>`**
<span style="background-color: #ff0000">in both cases git tries to auto-merge changes. Unfortunately, this is not always possible and results in conflicts. You are responsible to merge those conflicts manually by editing the files shown by git. After changing, you need to mark them as merged with</span>
**`git add <filename>`**
<span style="background-color: #ff0000">before merging changes, you can also preview them by using</span>
**`git diff <source_branch> <target_branch>`**

* * *
## **tagging**
<span style="background-color: #A5A000">
it's recommended to create tags for software releases. this is a known concept, which also exists in SVN. You can create a new tag named 1.0.0 by executing</span>

**`git tag 1.0.0 1b2e1d63ff`**
<span style="background-color: #A5A000">
the 1b2e1d63ff stands for the first 10 characters of the commit id you want to reference with your tag. You can get the commit id by looking at the...</span>
* * *
## **log**
<span style="background-color: #0EA309">in its simplest form, you can study repository history using..</span> **`git log`**
<span style="background-color: #0EA309">iYou can add a lot of parameters to make the log look like what you want. To see only the commits of a certain author:
**`git log --author=bob`**
To see a very compressed log where each commit is one line:
**`git log --pretty=oneline`**
Or maybe you want to see an ASCII art tree of all the branches, decorated with the names of tags and branches:
**`git log --graph --oneline --decorate --all`**
See only which files have changed:
**`git log --name-status`**
These are just a few of the possible parameters you can use. For more, see **`git log --help`**
</span>
* * *
## **replace local changes**
<span style="background-color: #d09413">In case you did something wrong, which for sure never happens ;), you can replace local changes using the command
**`git checkout -- <filename>`**
this replaces the changes in your working tree with the last content in **HEAD**. Changes already added to the index, as well as new files, will be kept.
If you instead want to drop all your local changes and commits, fetch the latest history from the server and point your local master branch at it like this
**`git fetch origin`**
**`git reset --hard origin/master`**
</span>
* * *
## **useful hints**
built-in git GUI **`gitk`**
use colorful git output **`git config color.ui true`**
show log on just one line per commit **`git config format.pretty oneline`**
use interactive adding **`git add -i`**
* * *
## **links & resources**
graphical clients
GitX (L) (OSX, open source)
Tower (OSX)
Source Tree (OSX & Windows, free)
GitHub for Mac (OSX, free)
GitBox (OSX, App Store)
* * *
## guides
[Git Community Book](http://book.git-scm.com/)
[Pro Git](http://progit.org/book/)
[Think like a git](http://think-like-a-git.net/)
[GitHub Help](http://help.github.com/)
[A Visual Git Guide](http://marklodato.github.io/visual-git-guide/index-en.html)
## get help
[`Git User Mailing List`](http://groups.google.com/group/git-users/)
#git on irc.freenode.net