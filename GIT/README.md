![GIT WORKFLOW](https://github.com/pknviki95/DevSecops-Learning/blob/main/GIT/Images/git_workflow.png)


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