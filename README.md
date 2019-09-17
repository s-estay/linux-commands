## Install git
- `sudo apt-get update`
- `sudo apt-get install git-core`
- `git --version`
- `git config --global user.name "user name"`
- `git config --global user.email "user mail"`
- `git config --list`

## Create project
- show current directory: `pwd`
- list of files in the current directory: `ls`
- list of files in the current directory including hidden files: `ls -la`
- change directory: `cd`
- navigate backwards: `..`
- navigate forwards: `cd` + folder name
- create folder: `mkdir` + folder name
- clear terminal: `clear`
- exit terminal: `exit`

## Install Atom
- go to the [Atom] website
- download and install the .deb-file
- in Atom: File/Add Project Folder
- right-click on the project's name: New File
- start the project with a README.md file

## Git
- **add** all changes/files (to the staging area): `git add --all`
- **commit** changes: `git commit -m` + "comment"
- view commit history: `git log`
- view a specific person's commit history: `git log --author="name"`
- are there new uncommitted changes och new uncommitted files?: `git status`
- add specific file: `git add index.html`
- view differences between working directory and repository: `git diff`
- view differences between staging area and repository: `git diff --staged`
- delete file on working directory and repository (commit to recover file): `git rm` + file name
- rename file: `git mv` + original file name + new file name
- move file to folder inside project folder: `git mv` + file name + folder/file name
- commit directly from the working directory to the repository (don't use when moving/deleting files): skip `git add` and do `git commit -am` + "comment"
- revert changes (make the repository file, the working file): `git checkout --` + file name
- unstage file: `git reset HEAD` + file name
- go back to a previous commit: `git checkout` + commit id + `--` + file name

![](https://github.com/s-estay/linux-commands/blob/master/git-workflow.png)

## Github
- On [Github], create new repository
- Give the repository a name (the same as the project folder) and choose public or private
- Leave *Initialize this repository with a README* unchecked
- Give the address to the newly created repository a short name: `git remote add` + remote repository name (default: origin) + repository address
- Get the short name of the remote repository: `git remote`
- Add files or make changes to the remote repository (**push**): `git push -u` + remote repository name + `master`
- Add image to README.md: move image to the project folder, add, commit, and push, then copy the link to the image and do `![](image link)` and push again

## References
- [Markdown-Cheatsheet]
- [Git staging area]
- [Bucky Roberts's git tutorials playlist]

[Markdown-Cheatsheet]: https://github.com/adam-p/markdown-here/wiki/Markdown-Cheatsheet
[Atom]: https://atom.io/
[Git staging area]: https://dev.to/sublimegeek/git-staging-area-explained-like-im-five-1anh
[Bucky Roberts's git tutorials playlist]: https://www.youtube.com/playlist?list=PL6gx4Cwl9DGAKWClAD_iKpNC0bGHxGhcx
[Github]: https://github.com/
