# GIT


### Installation of GIT:

### Version of git:

- Shows the current version of your Git

#### command:

```sh
git --version
```
#### output:

```sh
pknviki95@pknviki95-Lenovo-ideapad-330:~/Learning/DevSecops-Learning/GIT$ git --version
git version 2.34.1
```
#### command:
```sh
which git
```
#### output:
```sh
pknviki95@pknviki95-Lenovo-ideapad-330:~/Learning/DevSecops-Learning$ which git
/usr/bin/git
```
### Basic workflow of GIT:


```Workspace``` -> ```Index/Staging area``` -> ```Local Git repository``` -> ```Remote git repository```

![GIT WORKFLOW](https://github.com/pknviki95/DevSecops-Learning/blob/main/GIT/Images/git_workflow.png)

### Three stages of git:

- Untracked
- Staged
- Committed

#### Untracked: 
-  The file exists, but is ```not part of git's version control```.
#### Staged: 
- The file has been ```added``` to git's version control but changes have not been committed
#### Committed: 
- The change has been ```committed```

### Initializing git repository:


```sh
git init
```
#### output:

```sh
pknviki95@pknviki95-Lenovo-ideapad-330:~/Learning/test_folder/git_study$ git init
hint: Using 'master' as the name for the initial branch. This default branch name
hint: is subject to change. To configure the initial branch name to use in all
hint: of your new repositories, which will suppress this warning, call:
hint: 
hint: 	git config --global init.defaultBranch <name>
hint: 
hint: Names commonly chosen instead of 'master' are 'main', 'trunk' and
hint: 'development'. The just-created branch can be renamed via this command:
hint: 
hint: 	git branch -m <name>
Initialized empty Git repository in /home/pknviki95/Learning/test_folder/git_study/.git/
```
- Once git is initialized it creates ```.git``` folder inside the workspace.
- It helps to perform all git operation for that workspace.

```sh
pknviki95@pknviki95-Lenovo-ideapad-330:~/Learning/test_folder/git_study$ ls -lsa
total 12
4 drwxrwxr-x 3 pknviki95 pknviki95 4096 Jul 20 18:11 .
4 drwxrwxr-x 3 pknviki95 pknviki95 4096 Jul 20 18:11 ..
4 drwxrwxr-x 7 pknviki95 pknviki95 4096 Jul 20 18:11 .git
```
### Status of git repository:

- Gives the current status of the git repository
- with this we can check the files that are ```untracked``` or ```modified``` or if the files are ```newly added``` etc.,

```sh
git status
```

```sh
pknviki95@pknviki95-Lenovo-ideapad-330:~/Learning/DevSecops-Learning$ git status
On branch main
Your branch is up to date with 'origin/main'.

Changes not staged for commit:
  (use "git add <file>..." to update what will be committed)
  (use "git restore <file>..." to discard changes in working directory)
	modified:   GIT/README.md

no changes added to commit (use "git add" and/or "git commit -a")
```

### GIT configuration:

```sh
pknviki95@pknviki95-Lenovo-ideapad-330:~/Learning/test_folder/git_study$ cat .git/config 
[core]
	repositoryformatversion = 0
	filemode = true
	bare = false
	logallrefupdates = true
```

```sh
git config user.name "username"
```

```sh
pknviki95@pknviki95-Lenovo-ideapad-330:~/Learning/test_folder/git_study$ git config user.name "Vigneshwaran M"
```

```sh
git config user.email "user email"
```

```sh
pknviki95@pknviki95-Lenovo-ideapad-330:~/Learning/test_folder/git_study$ git config user.email "vikidotcom95@gmail.com"
```

```sh
pknviki95@pknviki95-Lenovo-ideapad-330:~/Learning/test_folder/git_study$ cat .git/config 
[core]
	repositoryformatversion = 0
	filemode = true
	bare = false
	logallrefupdates = true
[user]
	name = Vigneshwaran M
	email = vikidotcom95@gmail.com
```

pknviki95@pknviki95-Lenovo-ideapad-330:~/Learning/test_folder/git_study/learning$ git submodule add https://github.com/pknviki95/Python.git
Cloning into '/home/pknviki95/Learning/test_folder/git_study/learning/Python'...
remote: Enumerating objects: 1031, done.
remote: Counting objects: 100% (743/743), done.
remote: Compressing objects: 100% (511/511), done.
remote: Total 1031 (delta 261), reused 662 (delta 185), pack-reused 288 (from 1)
Receiving objects: 100% (1031/1031), 225.47 KiB | 1.76 MiB/s, done.
Resolving deltas: 100% (325/325), done.
pknviki95@pknviki95-Lenovo-ideapad-330:~/Learning/test_folder/git_study/learning$ git status
On branch main
Your branch is up to date with 'origin/main'.

Changes to be committed:
  (use "git restore --staged <file>..." to unstage)
	new file:   .gitmodules
	new file:   Python

pknviki95@pknviki95-Lenovo-ideapad-330:~/Learning/test_folder/git_study/learning$ git diff --staged
diff --git a/.gitmodules b/.gitmodules
new file mode 100644
index 0000000..9d064a4
--- /dev/null
+++ b/.gitmodules
@@ -0,0 +1,3 @@
+[submodule "Python"]
+       path = Python
+       url = https://github.com/pknviki95/Python.git
diff --git a/Python b/Python
new file mode 160000
index 0000000..8e8fe5f
--- /dev/null
+++ b/Python
@@ -0,0 +1 @@
+Subproject commit 8e8fe5f70db16b8de6f80d6c94bd67c9ce262146
