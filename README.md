## Install git
- `sudo apt-get update`
- `sudo apt-get install git-core`
- `git --version`
- `git config --global user.name "user name"`
- `git config --global user.email "user mail"`
- `git config --list`

## Terminal
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

## SSH keys
- check for existing SSH keys: `ls -la ~/.ssh`
  - default public keys filenames:
    - id_dsa.pub
    - id_ecdsa.pub
    - id_ed25519.pub
    - id_rsa.pub
- generate a new SSH key: `ssh-keygen -t rsa -b 4096 -C "your_email@example.com"`
  - when prompted *Enter a file in which to save the key*, press Enter for default location
  - when prompted *Enter passphrase*, enter passphrase
- start the ssh-agent: `eval "$(ssh-agent -s)"`
- add SSH private key to the ssh-agent: `ssh-add ~/.ssh/id_rsa` (default location)
- download and installs **xclip**: `sudo apt-get install xclip`
- copy SSH key to clipboard: `xclip -sel clip < ~/.ssh/id_rsa.pub` (default location)
- on Github, click on profile image, Settings, SSH and GPG keys, New SSH key, add descriptive Title and paste SSH key
- test SSH connection: `ssh -T git@github.com`
- clone repository using SSH key:
  - click **Clone or download**, Clone with SSH, copy link
  - in the terminal, move to the destination folder, `git clone` + copied git link
- when using a SSH key and editing both remotely and locally:
  - `git status`
  - `git add --all`
  - `git commit -m` + comment
  - `git pull` (remote to local)(fetch + merge)(GitHub will ask for the SSH passphrase)
  - `git push` (local to remote)
  
## Add .gitignore
- create file in nano: `nano .gitignore`
  - *.txt (ignore all .txt files)
  - file.text (ignore this file in particular)
  - folder/ (ignore this folder)
- save file and exit nano: Ctrl + X
- remove folder: `rm -rf` + folder
- remove file: `rm` + file
- `git add --all`
- `git commit -m` + comment
- `git push`

## References
- [Markdown-Cheatsheet]
- [Git staging area]
- [Bucky Roberts's git tutorials playlist]
- [Connecting to GitHub with SSH]

[Markdown-Cheatsheet]: https://github.com/adam-p/markdown-here/wiki/Markdown-Cheatsheet
[Atom]: https://atom.io/
[Git staging area]: https://dev.to/sublimegeek/git-staging-area-explained-like-im-five-1anh
[Bucky Roberts's git tutorials playlist]: https://www.youtube.com/playlist?list=PL6gx4Cwl9DGAKWClAD_iKpNC0bGHxGhcx
[Github]: https://github.com/
[Connecting to GitHub with SSH]: https://help.github.com/en/articles/connecting-to-github-with-ssh
