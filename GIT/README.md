# GIT



### Installation of GIT:

#### Initializing git repository:


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
```sh
pknviki95@pknviki95-Lenovo-ideapad-330:~/Learning/test_folder/git_study$ ls -lsa
total 12
4 drwxrwxr-x 3 pknviki95 pknviki95 4096 Jul 20 18:11 .
4 drwxrwxr-x 3 pknviki95 pknviki95 4096 Jul 20 18:11 ..
4 drwxrwxr-x 7 pknviki95 pknviki95 4096 Jul 20 18:11 .git
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
