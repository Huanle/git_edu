# Learning git following Vince Buffalo

## config
git config --global user.name 'Huanle'
git config --global user.email 'elzedliu@gmail.com'
git config --global color.ui true

## initiate 
git init # initialzing a repository from the current existing directory; Alternatively, you can do it by cloning one from github
### a hidden directory -.git was created

## tracking files with git add and git status
	$ git status
	# On branch master
	#
	# Initial commit
	#
	# Untracked files:
	#   (use "git add <file>..." to include in what will be committed)
	#
	#       CMDs.md
	nothing added to commit but untracked files present (use "git add" to track)
	
	**	use git add to tell git to track a file 
	$git add CMDs.md 
	$ git status
	# On branch master
	#
	# Initial commit
	#
	# Changes to be committed:
	#   (use "git rm --cached <file>..." to unstage)
	#
	#       new file:   CMDs.md
	
## staging files with git add and git status
### a file is staged means that it is not only tracked, but its latest changes are staged to be included in the next commit

## git's seperation of the working tree
### all files in your repository >> the staging area (files to be included in the next commit) >> committed changes (a snapshot of a version of your project at some point in time); 
### git add on an untracked file begins tracking  it and stages it, while git add on a tracked file just stages it for the next commit

### make a change to CMDs.md file and call git status
	$ git status
	# On branch master
	#
	# Initial commit
	#
	# Changes to be committed:
	#   (use "git rm --cached <file>..." to unstage)
	#
	#       new file:   CMDs.md
	#
	# Changes not staged for commit:
	#   (use "git add <file>..." to update what will be committed)
	#   (use "git checkout -- <file>..." to discard changes in working directory)
	#
	#       modified:   CMDs.md
	#
	
	$ git add CMDs.md
	$ git status
	# On branch master
	#
	# Initial commit
	#	
	# Changes to be committed:
	#   (use "git rm --cached <file>..." to unstage)
	#
	#       new file:   CMDs.md
	#

## git commit: taking a snapshot of your project
	$git commit -m 'initial import'
	[master (root-commit) 025a0f2] initial import
	1 file changed, 48 insertions(+)
	create mode 100644 CMDs.md
	$ git status
	# On branch master
	nothing to commit, working directory clean
	
## Seeing file differences: git diff
	without any arguments, git diff shows you the differences between the files in your working directory and what has been staged.
	$git diff
	[nothing]
	echo 'project started 2019-05-03' > CMD.md 
	
	
	$ git diff
	diff --git a/CMDs.md b/CMDs.md
	index cdf9987..8620ac8 100644
	--- a/CMDs.md
	+++ b/CMDs.md
	@@ -83,6 +83,9 @@ git init # initialzing a repository from the current existing directory; Alterna
			without any arguments, git diff shows you the differences between the files in your working directory and what has been staged.
			$git diff
			[nothing]
	+       echo 'project started 2019-05-03' > CMD.md
	+
	+       

	$ git add
	$ git diff --staged  #  
	
	diff --git a/CMDs.md b/CMDs.md
	index cdf9987..6600e4e 100644
	--- a/CMDs.md
	+++ b/CMDs.md
	@@ -83,8 +83,25 @@ git init # initialzing a repository from the current existing directory; Alterna
			without any arguments, git diff shows you the differences between the files in your working directory and what has been staged.
			$git diff
			[nothing]
	+       echo 'project started 2019-05-03' > CMD.md
	
	
	+       $ git diff
	+       diff --git a/CMDs.md b/CMDs.md
	+       index cdf9987..8620ac8 100644
	+       --- a/CMDs.md
	+       +++ b/CMDs.md
	+       @@ -83,6 +83,9 @@ git init # initialzing a repository from the current existing directory; Alterna
	+                       without any arguments, git diff shows you the differences between the files in your working directory and what has been staged.
	+                       $git diff
	+                       [nothing]
	+       +       echo 'project started 2019-05-03' > CMD.md
	+       +
	+       +
	+
	+
	+
	+
	
	$ git commit -m 'test git diff'
	[master 30af4c6] test git diff
	$ git diff # nothing
	$ git diff --staged # nothing
	
### Seeing your commit history: git log
	Commits in git are like chains(directed acyclic graphs), with each commit pointing to its parent
	
	$ git log
	commit 30af4c65b1faaac4dc17ceb7111366edf0c33f56
	Author: Huanle <elzedliu@gmail.com>
	Date:   Fri May 3 14:27:22 2019 +0200

		test git diff

	commit bdd7ce025aa018d1d9993275b12b66898909e6d8
	Author: Huanle <elzedliu@gmail.com>
	Date:   Fri May 3 14:22:46 2019 +0200

		initial import

	commit 025a0f21a64a2c6b59ff0bdcef708a873434dd20
	Author: Huanle <elzedliu@gmail.com>
	Date:   Fri May 3 14:13:15 2019 +0200

			initial import
	

### Moving and removing files: git mv and git rm
	$ git mv CMDs.md READEME.md
	$ git status
	# On branch master
	# Changes to be committed:
	#   (use "git reset HEAD <file>..." to unstage)
	#
	#       renamed:    CMDs.md -> READEME.md
	#
	# Changes not staged for commit:
	#   (use "git add <file>..." to update what will be committed)
	#   (use "git checkout -- <file>..." to discard changes in working directory)
	#
	#       modified:   READEME.md
	#
	

### undoing a stage: git reset 
### this line is to test git reset
	$ git add READEME.md
	$ git status
	# On branch master
	# Changes to be committed:
	#   (use "git reset HEAD <file>..." to unstage)
	#
	#       modified:   READEME.md
	#
	
	$ git reset HEAD READEME.md
		.....
	$ git status
	# On branch master
	# Changes not staged for commit:
	#   (use "git add <file>..." to update what will be committed)
	#   (use "git checkout -- <file>..." to discard changes in working directory)
	#
	#       modified:   READEME.md
	#
	no changes added to commit (use "git add" and/or "git commit -a")

### Collaborating with Git: Git remotes, git push, 

