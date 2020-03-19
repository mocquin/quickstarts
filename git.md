
# Quickstart
```
git init : create a repo in current dir
git status : state of the repo  
git add <file> : add file to index  
git commit -m "message" : commit with message  
git log : commit log  
git diff : diff between last commit and current state  
git checkout : check state at specific commit  
```

# Full Command list

## git add
```
git add <file_name> : add file to repo's index  
git add . : add all file to index  
git add "*.html" : add all html files to index  
git add --all : add all untracked files to index (same as -A)
git add -u : add updates for tracked files
git add -A : add all changes (new files and modified files)
git add -p <file_name> : add only patch/chunk of filename for commit

    y stage this hunk for the next commit
    n do not stage this hunk for the next commit
    q quit; do not stage this hunk or any of the remaining hunks
    a stage this hunk and all later hunks in the file
    d do not stage this hunk or any of the later hunks in the file
    g select a hunk to go to
    / search for a hunk matching the given regex
    j leave this hunk undecided, see next undecided hunk
    J leave this hunk undecided, see next hunk
    k leave this hunk undecided, see previous undecided hunk
    K leave this hunk undecided, see previous hunk
    s split the current hunk into smaller hunks
    e manually edit the current hunk
    ? print hunk help
```
([source](https://stackoverflow.com/questions/1085162/commit-only-part-of-a-file-in-git)) 

## git blame
```
git blame <filename> : list commits concerning a file
```

## git branch
```
git branch : list all branches with * on current branch
git branch -r : list remote tracked branches
git branch -a : list all branches (local and remote)
git branch branch_name : create branch called branch_name
git branch –d branch_name : delete branch with check for unmerged commits
git branch –D branch_name : delete branch
git branch branch_name tag_name : create branch from tagged commit
```

Other commands about branches : 
```
git checkout branch_name : Change branch
git merge branch_to_merge : go to 'main' branch, then this merges branch_to_merge on current branch 
git push origin origin:refs/heads/new_name_branch : create branch on server (then track that branch!)
git push origin :heads/branch_name : delete branch of server
```

About branches : 
There are 2 types of branches :
 - local branches, stored in .git/refs/heads
 - remote-tracked branches, stored in .git/refs/remotes

Pulls/pushes only concern current branch, not all tracked branches.

## git config 
```
git config --list : list configs
git config --global -e : edit global config file
git config --global user.name "toto28" : to setup name
git config --global user.email toto28@me.com : to setup mail
git config --global core.editor "code -w": to setup default editor ("code" for vscode), with -w or --wait to specify git to wait until the editor is closed
git config --global --get diff.tool : check if a diff tool is configured
git config --global alias.hist "log --oneline --graph --all --decorate" : create a "git hist" alias
git config --global fetch.prune true : activate auto prune when fetching (git fetch origin is now equivalent to git fetch origin --prune)
```

## git checkout
```
git checkout SHA : set on commit numbered SHA
git checkout –b branch_name : create new branch from HEAD, and set on new branch
git checkout branch_name : set on branch_name
git checkout master : se positionner sur le commit le plus récent = branche principale
git checkout SHA file_name : reset file_name state of commit SHA
git checkout -b feature-2 origin/feature-2 : create a local branch to track remote branch from origin
git checkout –file : reset file in cwd from index
git checkout -- file : reset file in cwd from last commit
git checkout –p : reset chunks in cwd from index
git checkout -b new_branch existing_branch : create new_branch from existing branch, and set on new branch
```

Usually, HEAD points to a branch's tip, often master. git checkout only moves HEAD to the pointer being checkedout. When checking out a specific commit, head is detached (detached-head). 
    
## git cherry-pick
```
git cherry-pick SHA : apply SHA commit to current HEAD
git cherry-pick --abort : abort current cherry-picking
git cherry-pick --continue : commit conflict resolution changes
```

## git clean
Remove untracked files from the working tree
```
git clean -d -f -x : delete directories, force deletion without confirmation, -x to delete also directories in the ignore list
git clean -n : (or --dry-run) dry run clean (to check what would be deleted)
git clean -fd : delete directories
git clean -fX : delete ignored files
git clean -fx : delete ignored and non-ignored files
git clean -X : remove only files ignored by git
git clean -i : interactive clean
```
    
## git clone
```
git clone https_github_link : clone github repo in current dir
git clone https_github_link new_name : clone repo with a custom new_name folder
```

## git commit
```
git commit : create commit (then type :wq for :write/quit in vi)
git commit –m "message" : create commit with message
git commit my.file -m "blah blah" : add and commit one file
git commit –a –m "update file" : create commit on indexed files only
git commit –a : commit already indexed files (ie updates allready tracked files but doesn't add files to index)
git commit -am "commit message" : add and commit
git commit --amend : open editor to change commit message
git commit --amend –m "new message" : change last commit's message
git commit -m "Title" -m "Description..." : commit with message and description
```
See also git add -p <file_name> : add only patch/chunk of filename for commit.

See also [here](https://stackoverflow.com/questions/1085162/commit-only-part-of-a-file-in-git) and [here](https://stackoverflow.com/questions/179123/how-to-modify-existing-unpushed-commit-messages).

## git diff
```
git diff : diff between cwd and staging area (cwd vs index)
git diff HEAD : diff between cwd and last commit (cwd vs repo)
git diff --staged HEAD : diff between staging area and last commit (index vs repo)
git diff -- filename : diff between cwd and staging area (cwd vs index) for filename
git diff HEAD HEAD^ : diff between last commit and second-to-last commit
git diff –-cached : diff between current index and last commit - allows to check what is about to be commited
git diff –-staged : synonym for --cached
git diff -p : equivalent to git diff -u or git diff --patch : diffs are reprensented with patches
git diff tag_name HEAD : diff between commit tag_name and last commit
git diff file_name : diff from last commit for file_name
git diff --staged : diff between staged and last commit 
git diff sha1 sha2 : diff between 2 commits
git diff master..test : diff between 2 branches
git diff master test : diff between 2 branches
git diff master...test : diff between the common parent of master and test branch
git diff --stat : only display stats, not patches
```

## git difftool
same as git diff, but with the git difftool

## git fetch
```
git fetch origin master : fetch changes of master branch from origin remote
```

## git init
```
git init : create repo in cwd
git init --bare : bare repos only contains the historic, not the files themselves
```

## git log
```
git log : list all commits
git log -p : list commits as patches
git log --stat –-summary : summup of each commit
git log -n 2 : list last 2 commits
git log --oneline : display commits on one line
git log -p file_name : list commits concerning file_name
git log --stat : list file names and number of lines commited
git log --oneline --abbrev-commit --all --graph --decorate –color
git log --oneline -- <filname> : oneline log for file
git log --author="<pattern>" : display commits made by author
git log --grep="<pattern>" : display commits with pattern in commit's message
git log <since>..<until> : list commits between the 2 revisions
git log <file> : list commits concerning file
```

## git merge
```
git merge branch_name : merge branch_name on current branch
git merge feature master : equivalent to "git checkout master" then "git merge master"
git merge --no-ff : merge without fast-forward.
git merge sha1 : merge every commit between HEAD and sha1
git merge publisher/master : merge the master branch of the publisher remote repo to our local current branch
git merge origin master : after fetching origin/master, will merge local master with fetched origin/master branch
```
## git mergetool
same as merge, but with the merge tool
in MERGING state, `git mergetool`, resolve conflicts, and then commit "resolving merge"

## git mv
```
git mv file new_name : rename the file using git, and stage the change 
```

## git push
```
git push origin master : send commits in master branch of remote origin
git push --set-upstream origin master : equivalent to -u : push and set tracking reference for branch master on remote origin (check after with remote -v)
git push repo branch : push branch on repo
git push --force origin feature-branch : overrides origin/feature-branch with local feature-branch
git push origin feature:feature : push a branch without checking it out (here, push feature onto origin/feature)
git push --delete origin feature : delete feature branch from remote origin
git push --tags : push, including tags
git push --delete origin tagname : delete from remote
```

## git pull
```
git pull origin master : pull commits from master branch of origin server
git pull –-rebase : fetch then rebase (as opposed to pull that fetch then merge)
git pull --rebase origin master : equivalent to git pull --rebase
``` 

## git restore 
```
git restore <file> : restore changes in file compared to last commit
git restore --staged <file> : restore changes of index to the cwd state
```

## git rebase
```
git rebase -I : interactive rebase
git rebase –onto master sha1 : fait un rebase de la branche de travail, jusqu’au sha1 exclus, et rebase sur master
git rebase -i HEAD~3 : rebase interactif sur les 3 dernier commits
```

## git reflog
```
git reflog : show full log of coommit
git reflog HEAD@{20} : show the reflog as when HEAD was at HEAD{20}
git reflog HEAD@{3.days.ago} : show the reflog as when HEAD was 3 days ago
git reflog master@{3.days.ago} : show the reflog for master as was 3 days ago
git reflog master@{2020.04.16} : show the reflog for master at a date
```


## git reset
```
git reset –-hard : reset to last commit
git reset –soft HEAD^1 : moves HEAD to HEAD^1, and put differences to staged
git reset –mixed HEAD^1 : equivalent to "git reset HEAD^1"  : moves HEAD to HEAD^1, and put differences to cwd
git reset –hard HEAD^1 : moves HEAD to HEAD^1, and delete changes
git reset -p : unstage patches
git reset --hard origin/master : reset everthing to the server state
```

Summary : 
- git reset == git reset HEAD == git reset --mixed == git reset HEAD --mixed 
- git reset HEAD^1 –-soft: moves HEAD to HEAD^1, and place changes into index
- git reset HEAD^1 --mixed : == git reset HEAD^1 : moves HEAD to HEAD^1, and place changes into cwd
- git reset HEAD^1 -–hard : moves HEAD to HEAD^1 and delete changes
- git reset file.py : delete file.py from index, to match state of last commit
- git reset --merge SHA_before_commit : cancel merge commit
- git reset -i HEAD^2 --preserve-merges : interactive rebase on last 2 commits

To hard reset a file : `git checkout HEAD -- my-file.txt`


## git rm
```
git rm --cached file_name : delete/remove file from index (kinda like unstage/untrack)
git rm -r --cached folder : delete folder from index
git rm file : delete file using git, and add change to index
```
   
## git remote
```
git remote : list remote repos names
git remote -v : list remote repos tracked with associated urls
git remote add origin https://my/repo : add a repo as remote
git remote add publisher https://publisher.com/book.git : add a remote repo (git folder) called publisher
git remote add [name] [url] : add a remote repo
git remote rename old_name new_name : rename branch
git remote rm repo : remove remote repo
```
    
## git revert 
```
git revert SHA : apply reverse effect of commit SHA (and places it in a new commit)
git revert : apply reverse of last commit (and place it in a new commit)
git revert –e == git revert –edit == git revert : open text editor to add message to revert commit
git revert HEAD^ : create a new that's the inverse of the last commit before HEAD (second-to-last)
git rever –no-edit : add no message to revert
git revert –n –no-commit : apply reverse commit only to cwd and index, but not in a commit
git revert master~5..master~2 : revert all commits from ~5 to ~2 included.
```

## git show
```
git show SHA : affiche le détail du commit SHA
git show HEAD : show HEAD commit
git show HEAD^ : show du parent du dernier commit
git show <branchname> : show du dernier commit de la branche
git show : equivalent to git show HEAD
```

## git stash
```
git stash : place content of cwd in top of stash
git stash apply stash@{X} -index : apply last stash content if no stash is providded, else apply stash number X.
git stash apply stash@{X} -index : also reapply index content
git stash pop stash@{X} : apply and delete last stash
git stash list : list stashes
git stash drop stash@{X} : delete stash
git stash clear : clear all stash content
git stash branch stash@{0} : create branch based on stash
git stash show stash@{X} -p : to see the stash content as patches
git stash save "message" -u : to add a messsage to stash, -u to stash untracked files
```

## git status
```
git status : give current state of cwd compared to staging area
git status -s : short version of git status
```

## git tag
```
git tag 1.0.0 SHA : create a tag ("version") on commit SHA
git tag -d tagname : delete a tag
git tag tagname : create "ligth" tag on current commit
git tag -a tagname -m "message": create "annotated" tag on current commit, with message
```
To delete a tag from remote : `git push --delete origin tagname`
By default, tags are not pushed when ; use `git push --tags` to push them.

# Usefull refs

## git commands
```
git ls-tree -r master --name-only : list tracked files
git ls-files : list tracked files
git log --oneline --decorate --all --graph
```

## Upload/clone project to Github 
 - Create a repo on github
 - Copy link of this repo
 - Add distant repo to local repo : git remote add origin url
 - Check these repo : git remote -v
 - Commit : git push -u origin master
OR
 - git clone https://github.com/mocquin/dimension.git
 - move files
 - git status
 - git add files
 - git commit
 - git push -u origin master

# Concepts
## git ignore
The hidden file '.gitignore' contains the file list to be ignored by git. This file can be tracked by the repo just like any other file.  
Use '\*.tmp' to ignore all files ending in '.tmp'.  
Use 'tmp/*' to ignore all content of dir 'tmp/'.  
Use 'tmp' to ignore the tmp folder

## git config
The git config file is located in the home dir. It is a hidden file (CMD+fn+MAJ+; to display hiddenf file on Azerty/MAC OS).
It could look like this : 
```
[user]
	name = John Doe
	email = john@doe.com
[color]
	diff = auto
	status = auto
	branch = auto
	ui = true
[core]
	excludesfile = /Users/JohnDoe/.gitignore_global
[alias]
		ci = commit
		co = checkout
		st = status
		br = branch
```

To manipulate configs:
```
git help config : open config help
git config --list : list all config
git config --global alias.lg "log --oneline --decorate --all --graph". You can then use git lg

git config --global user.name "mocquin" : to setup name
git config --global user.email mocquin@me.com : to setup mail

git config --global color.diff auto
git config --global color.status auto
git config --global color.branch auto 
git config --global color.ui true

alias gg='git log --oneline --abbrev-commit --all --graph --decorate --color'
git config --global alias.graph "log --graph --oneline –decorate=short"
```

### editor
```
git config --global core.editor "command to launch" : create a command to launch editor for git
```

### merge tools
To setup a merge tool :
follow : 
```
git config --global merge.tool p4merge : create a tool to merge called p4merge
git config --global mergetool.p4merge.path "path_to_p4merge.exe" : tell git where the tool is located
git config mergetool.prompt false : so git doesn't ask every time to confirm to open mergetool
```
### diff tool
then to setup a diff tool : 
```
git config --global diff.tool p4merge : create a tool to diff called p4merge
git config --global difftool.p4merge.path "path_to_p4merge.exe" : tell git where the tool is located
git config difftool.prompt false : so git doesn't ask every time to confirm to open difftool
```
finaly, check with git config -e


## origin
origin is the default name from which a repo is cloned

## Merging, rebasing, pushing, pulling
Rebase is basically "unbuilding" the branch's commits, then applying them on master, and fast forward.
By default, a merge will try to fastforward, and delete the historic of the 2 branches.

### rebase
Rebase allows you to rewrite the history with -I

### fast forward, true merge
Git merge --no-ff : merge without fast-forward, allowing "true merge": a fast-forward can be done when master has no new commit since the branch was created, so that the ref pointer to master could be moved to the head of the branch being merged. This allow to keep the historic separated, and create a merge commit for that branch.

If you don't want to keep a separated branch : 
 - If master has no new commit, a merge will do a fast-forward by default (and give the same result as a rebase).
 - If master has new commit, a merge will create a merge commit, which you don't want. Use rebase to make fast-froward possible.

Difference between rebase and merge :
 - A merge will create a merge commit.
 - A rebase will "rewrite" the history of the branch, by changing the divergence point of the branch to take into account the new commit since the creation of the branch. It change the base of the branch. Consist in dismounting the branch commit by commit, move the branch starting commit, and reapply commit on the top.

Note you should NEVER use rebase on a public branch.

A rebase is a good occasion to interactively refactor commit with git rebase -I.

If branch is a LOCAL, temporary branch : starting from an updated master, and moving through commit without pushing them : no reason to keep a distinct branch in tree : use a rebase if there are new commits, or merge with fast-forward otherwise.

If the branch is known/identified (about an issue, a sprint, etc) : you want to keep track of that branch in history, so you need a merge commit BUT if master has no new commit, git will try to fast-forward.

Git pull –-rebase : fait un fetch puis un rebase (contraintement à git pull qui fait un fetch puis un merge)

Merging safely :
 - Method 1 : Create a branch on master called "savepoint", but don't move to it. Merge the feature branch on master. If successful, delete savepoint branch. Else, do git reset --hard savepoint to go back to savepoint.
 - Method 2 : Create a branch on master called "scout", and move to it. Merge feature branch on scout. If successful, merge scout on master (which should simply be a fast-forward of master). Else, go back on master and delete scout.

### pulling
Always pull before pushing. 
A pull is basically a fetch followed by merge

In detached-HEAD mode, HEAD is no longuer pointing to a branch tip. At this point, commiting will create an anonymous branch, and leaving that branch for another will make this commit "orphan", and so you will not be able to come back to it - there is no reference (ref or parent commit). You have to create a branch for that commit


## git’s objects
Objects are stored in the .git/objects
git cat-file commit a6dbf05551541dc86b7a49212b62cfe1e9bb14f2 : display a user friendly text of the commit object
git ls-tree f89e64bdfcc08a8b371ee76a74775cfe096655ce : display a user friendly text of the tree object
git cat-file blob 5d92c127156d3d86b70ae41c73973434bf4bf341 : display a user friendly text of a file
 
A commit objects basically represents a commit : it has its own SHA, and points to a tree object.
A tree object has its own SHA, and points to files objects – which are called blob objects
When a file is modified and the changes are commited : git first creates a new blob object representing the new content of that file. Then creates a new tree object, with a pointer to the new file blob, and pointers to files that were not changed (it is reusing the same blob object). Then creates a commit object, with a pointer to its new tree object, AND a pointer to the last commit object – its parent commit. When a file is deleted and the change is commited : in the new commit object (that also points to its parent commit and its tree object), the tree object has no reference to a blob object for that file : it doesn’t know it, only the previous commits have references to a blob file for that file. When a folder is created and the change commited, the commit object points to a tree object – the main folder-, and that tree object points to : blob objects for files in that directory, and a tree object for each subfolder (each of them having reference to blob objects for files that they contain).
 
Blob objects :
-          Key : SHA-1, used as object’s name
-          Value : content, content of the file
Commit object :
-          Last commit object (parent)
-          Pointer to the tree object
-          Commiter name
-          Commit message
 
For each object, the SHA-1 used the first 2 character as directory name, and 38 characters left as object’s filename
 

git cat-file -t 70c379b63ffa0795fdbfbc128e5a2818397b7ef8 : return git object type
git cat-file -p f29f2741b30ecc1529da7dbae4aff9974b69e271 : return git object content
git hash-object toto : return git has for toto file. This is only an image of the file content, not its name.
When adding a file to the index, a blob object is created. It is not deleted if the file is deleted/reseted.

    
    
## HEAD and references (branches)
References are stored in the .git/refs/heads
cat .git/refs/heads/master : display a user friendly text of the reference
cat .git/HEAD : display a user friendly text of the current HEAD pointer
 
A branch is tracked by git by tracking the last commit SHA of that branch. Since every commit object has a pointer to its parent commit object, a branch is entirely defined by its last commit. That is because a commit ALWAYS has ONE parent commit.
A reference is basically a branch, or branch name, that contains the SHA of the last commit of that branch
Creating a new branch will simply create a new file in .git/refs/heads, containing the commit SHA of that branch.
 
## index
Index is truly a file that keeps track of the file changes of the 3 areas : working tree, staging area, and repository.
 
When switching branch from master to feature with a checkout, git first moves the HEAD to the feature ref. That ref is a pointer to the last commit of that branch, which is a commit object, pointing to a tree object and blobs objects (files in a given state). Then, git updates the content of the .git/index file, with for each file, a last update date, and a SHA for the wdir, a SHA for the staging area, and a SHA for the repo. Finally, git will change the wdir content to match that of the commit HEAD is pointing to. Hence, after a checkout, all files has the same content : in the wdir, in the index where the 3 areas have the same checksums for all files, and the repo.
When a file is changed, git first keeps track of that change in the index, where it creates a new checksum for that file for the wdir area, and compare that checksum to that of the staging area of the index for that file. A git status will so tell us that there are changes that are not staged. Using git add will add this change to the staging area in the index. Then git creates a new blob object to match this new file content. At this point, there is a new blob object in the repo, but it isn’t attributed to any tree/commit object. A git status will then tell us that there are changes that are about to be commited. A git commit will then : (1)create a new commit object and a new tree object, that points to the new file blob (and the other file blobs that were not changed). (2) Move the feature ref pointer to the new commit (3) update the repo in the index (then all the area of the index are the same again).


## miroring a repo
```
git clone --bare https://github.com/exampleuser/old-repository.git
cd old-repository.git
git push --mirror https://github.com/exampleuser/new-repository.git
cd ..
rm -rf old-repository.git
```

# Others refs

## quickstart VI/VIM
 - delete character : x
 - write then quit : :wq
 - insert mode : i
 - exit : :q!
 - delete whole line : d+d
 - replace : r + NEWCHAR
 - save : ws
 - search word in text : ?word
    
## quickstart Cat
Save and exit : CTRL+D


# Ressources
 - https://git-scm.com/book/en/v2
 - http://ndpsoftware.com/git-cheatsheet.html#loc=remote_repo;
 - https://longair.net/blog/2009/04/16/git-fetch-and-merge/
 - https://blog.osteele.com/2008/05/my-git-workflow/
 - https://www.atlassian.com/git/tutorials/learn-git-with-bitbucket-cloud
 - http://marklodato.github.io/visual-git-guide/index-en.html
 - onlywei.github.io/explain-git-with-d3/
 - https://github.com/pluralsight/git-internals-pdf
 - http://think-like-a-git.net/sections/graphs-and-git.html
 - https://www.youtube.com/watch?v=uR6G2v_WsRA
 - (fr) https://delicious-insights.com/fr/articles/bien-utiliser-git-merge-et-rebase/#le-pi-ge-de-git-pull-et-du-r-flexe-pull-push
 - http://alx.github.io/gitbook/index.html
 - http://www.gitguys.com/
 - https://gist.github.com/hofmannsven/6814451
 - https://archive.ochronus.com/git-tips-from-the-trenches/
 - https://hackernoon.com/https-medium-com-zspajich-understanding-git-data-model-95eb16cc99f5
 - https://hackernoon.com/understanding-git-branching-2662f5882f9
 - https://hackernoon.com/understanding-git-index-4821a0765cf
 - https://github.com/joshnh/Git-Commands 
 - https://stackoverflow.com/questions/1057564/pretty-git-branch-graphs/54532734
 - https://dev.to/kodekage/git-backend-behind-the-scene-12l5 
 - https://www.youtube.com/watch?v=dBSHLb1B8sw
 - https://www.youtube.com/watch?v=ZDR433b0HJY
 - https://www.youtube.com/watch?v=xbLVvrb2-fY
 - https://stackoverflow.com/questions/6930216/git-what-goes-behind-the-scene
 - https://wildcardcorp.com/blogs/what-the-heck-is-git-doing
 - https://teamtreehouse.com/library/branches-behind-the-scenes
 - http://www.git-scm.com/book/en/v2
 - https://codewords.recurse.com/issues/two/git-from-the-inside-out
 - https://jwiegley.github.io/git-from-the-bottom-up/
 - https://www.youtube.com/watch?v=8ET_gl1qAZ0
 - https://www.codeschool.com/courses/git-real
 - https://www.codeschool.com/courses/git-real-2
 - http://marklodato.github.io/visual-git-guide/index-en.html

SO : 

Articles on topics : 

Interactive visual representation : 
 - http://www.ndpsoftware.com/git-cheatsheet.html
 - http://onlywei.github.io/explain-git-with-d3/#commit
 - https://learngitbranching.js.org/?locale=fr_FR
 - http://git-school.github.io/visualizing-git/

Video Tutorials : 
 - udemy
 
 

# Learning/explaning git
## First, on a local project, on one branch :
Commands to review : 
 - git config 
    - git config --global user.name "mocquin" : to setup name
    - git config --global user.email mocquin@me.com : to setup mail
 - git add
 - git checkout
 - git commit
 - git diff
 - git init
 - git log
 - git rebase
 - git reset
 - git rm
 - git show
 - git status
 - git rebase
Concepts to explain : 
 - CWD / index / .git
 - .gitignore
 - master, HEAD
 - commit, SHA
 - .git folder
    - config file
    - refs
    
## amending 
Amending actually rewrite the last commit to match the current index state.
Only ammend on local unpushed branch
 - To change only the message : with an empty index : `git commit --amend -m "new message"`
 - To add other changes : make the changes, add the file to index : `git commit --amend -m "new message"`
 
## reflog

## rebasing
    
## reset and revert
never reset server branches
if unwanted commit already on server, use a revert
clean before pushing
only push when finished 
differences between reset and revert
when to use which
    
## with branches

Merging : 
 - happy path with ff
 - happy path without ff
 - automatic merge
 - merge with conflicts
 
Rebasing : 
 - happy rebase (empty)
 - happy rebase
 - rebase with conflicts
    
## With a remote
a remote is just another git folder with a CWD/index/.git

basic setup for :
 - github
 - bitbucket
 - gitlab

