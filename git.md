Incase of large number of untracked files in a repository, ensure that file mode change is switched off. To do that issue the following command.
	git config core.filemode false

Unstaged changes left after git reset --hard
	https://stackoverflow.com/questions/11383094/unstaged-changes-left-after-git-reset-hard	

Git Add Remote URL
	git remote add origin https://github.com/user/repo.git

Git Change Remote URL
	git remote set-url origin https://github.com/USERNAME/REPOSITORY.git

# ref
https://help.github.com/articles/adding-an-existing-project-to-github-using-the-command-line/


# Some useful commands
To clear working directory
	`git checkout -- .`
Revert to last-1 commit
	`git reset --soft HEAD~1`
Hard Reset
	`git reset --hard HEAD -`

# Git still shows files as modified after adding to .gitignore
https://stackoverflow.com/questions/9750606/git-still-shows-files-as-modified-after-adding-to-gitignore
To stop this you have to do : `git rm -r --cached .idea/`

