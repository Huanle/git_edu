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
	
## Seeing file differences: git differences
	without any arguments, git diff shows you the differences between the files in your working directory and what has been staged.
	$git diff
	[nothing]
	
	
	





