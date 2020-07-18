## Git tutorial 1
Git was created by Linus Torvalds in 2005 for development of the Linux kernel, with other kernel developers contributing to its initial development.

### Linus Torvalds:The man who created linux
<br><br>
![0*VcMPr1unIjAIHw2j](https://user-images.githubusercontent.com/37455387/87836639-643ff800-c8ae-11ea-8fbb-9656ca4c707e.jpg)<br><br>
Linus Torvalds wanted a distributed system that he could use like BitKeeper, but none of the available free systems met his needs. Torvalds cited an example of a source-control management system needing 30 seconds to apply a patch and update all associated metadata, and noted that this would not scale to the needs of Linux kernel development, where synchronizing with fellow maintainers could require 250 such actions at once. For his design criterion, he specified that patching should take no more than three seconds,[9] and added three more points:
    • Take Concurrent Versions System (CVS) as an example of what not to do; if in doubt, make the exact opposite decision. 
    • Support a distributed, BitKeeper-like workflow. 
    • Include very strong safeguards against corruption, either accidental or malicious

Git is a distributed version-control tool to keep track of source code during the development of a project. It makes it easy for many contributors 
to work on a single project simultaneously, it's free and under the terms of the GNU General Public License.

## Git terms, commands and usages
Staged Area
Before making commit we add changes to a staged area because some time we do not want to commit every change we made rather some changes so we add only some changes 
to that staged area for commit

```git Commit```
It’s like the snapshot of changed files and folders in a project. It’s like it is packed that changes into a box and then assigns a separate unique id to this packet and adds it to the chain of commits. It’s like blockchain but we 
can change that box even after that.

```git commit -m "message"```
You can amend last commit with some new changes after adding changes to staged area with

#### Git Branch
Git maintains branches to maintain different commits like you want to work on certain aspects on one branch and on different aspects in another branch.
To create New branch
```git branch new-branch-name```

To Checkout to new branch
```git checkout new-branch-name```
To create new branch and checkout in single command
```git checkout -b new-branch-name```

To create branch based on remote like there is a branch some-branch which exist only on remote and contain different changes than master, 
When you create a new branch locally then it creates that branch on top of commits which are present on your branch from which you created this branch, but if you don’t want these commits you should create that branch referring to the remote. Like
```git checkout -b remote-branch remote/remote-branch```<br><br>
![images](https://user-images.githubusercontent.com/37455387/87836559-11fed700-c8ae-11ea-8f31-7664e4a1fb7e.jpeg)<br><br><br>
Here remote can be origin or any remote you set

To see branch list use
```git branch```


To see branch list that are present of remote use
```git branch -r```



##### Git Merge
It is used for merging two branches means adding unshared code of two branches into a single branch. A new commit is created when we merge two branches.Like we are in master branch now there exist a new branch with some commits that are not in master then to get these commits in master we merge that branch into master.
git branch another-branch



#### Git Rebase
Rebase is like merge but it does not create new commits rather it takes your commits and puts them on top of other branch commits. Like you are in another-branch and master has some new commits the rebasing another-branch will put another-branch new commits on top of master new commits without affecting master branch.
git rebase master

##### Git Log 
This will show you a list of commits in that branch with commit id, message and author of that commit. It also tells you where the heads of different local branches and remote branches are.It came useful when you want to revert changes and change commits.
```git log```


#### Git Status
This command tells you the status on that branch like which files are changed, and file is added or deleted and what changes are staged and if your branch is up to date with remote branch or is there any commit to push to remote.
git status

#### Git checkout Head
Head will tell you in which commit you are on but you can also treat head as a branch with this branch you can move your head on backward commits. Like with this command
git checkout HEAD^
You move a commit back and with this next command you can specify the number of commits to go back to.
git checkout HEAD~4
It will take head back 4 commits

##### Git reset
With this command you can also go back to certain commit like it never happened
git reset commit-value
Here commit-value is the id assigned to each commit when you type git log, it’s size can 5- full character long like for a commit id “adf3323lad34ls”
You can type “adf332” and it still works the same.

To delete changes you can use git reset like
```git reset --hard```
To unstaged changes use
```git reset``` .
#### Git revert
When working with many other contributor then there is less chance you are going to use git reset because it deleted that commit but when you want to tell others that you don’t want last commit then you use git revert because it create new commit and doing the same thing as git reset which is deleting the changes after the commit which is specify in the command
git revert commit-value


#### Git cherry pick
This command picks some commits from different branch and add them on top of your current branch.
git cherry pick commit1 commit2 commit3
Here commit1,2 and 3 are commits id from different branch.

#### Git stash
This command is very useful. It packed your unstaged changes and make git status clear and you can unpacked these changes anywhere you want with pop like there are some changes you have done in master but you want these changes on different branch like new-branch then in master you type
git stash
And then you can checkout to new-branch and unpacked these changes with 
git stash pop
It’s uses are many above is one example of it.

#### Git remote
With this you can control remote, remote is your repo which is uploaded online for everyone to work together there are many hosting website for version control like github, gitlab ,bitbucket and so on.Now for the commands to add a new remote use
```git remote add-url remote-name remote-branch-url```

To update any remote name that is already present use this
git remote set remote-name remote-branch-url

To see remote list use
```git remote -v```

![c7xz1970t7t21](https://user-images.githubusercontent.com/37455387/87836454-bd5b5c00-c8ad-11ea-8e50-4f6e41c93600.png)

#### Git clone
This is used to pull entire code from remote here is the syntax.
```git clone remote-git-url.git```

Git Fetch
This command fetches commits from remote that are not present in local repo but does not update master rather it only update remote/master
If we want to update out local master the we merge that remote master to our local master
```git fetch```
Now we merge these two
git merge remote/master

Git pull
This is used to pull commits that are not in your local repo and present on remote repo.it does fetch and merge into single commit without creating a new commit.
```git pull remote branch```

```Git push```
This command will push your commits into remote that are not present into remote.
git push remote master

Git -f Command
This command is used with many commands to use forcefully like there is some commit on remote but you want to push your commit and delete that commit then you use -f option. It can be used with merge, rebase , pull, push and many command
