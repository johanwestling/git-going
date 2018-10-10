# Git going
How to get git configured to work with ssh (github) and commonly used git commands for the terminal.

## Installation
There are multiple option how to get git installed on your system, and some operating system have it installed by default.

Lets check if git is already installed on your system:
1. Open terminal.
1. Check the git version:
    ```git --version```

If you didn't get a output looking like ```git version X.X.X``` you'll need to install git for your system.
* [Windows](./docs/git-windows.md)

## Configuration
1. Open terminal.
1. Set git user name & email:
    ```
    git config --global user.name "Firstname Lastname"
    ```
    ```
    git config --global user.email "firstname.lastname@whatever.io"
    ```
1. Set git to use new behavior for git push:
    ```
    git config --global push.default simple
    ```
1. Generate a ssh key for your device:
    ```
    ssh-keygen
    ```
1. Press **ENTER** (defaults to ~/.ssh/id_rsa)
1. Press **ENTER** (to skipping password)
1. Press **ENTER** (to skipping password)
1. Add ssh key to the ssh-agent:
    ```
    eval $(ssh-agent) ssh-add ~/.ssh/id_rsa
    ```
1. Get the ssh public key:
    ```
    cat ~/.ssh/id_rsa.pub
    ```
1. **Copy** the output.
1. Open browser.
1. Go to [https://github.com/settings/keys](https://github.com/settings/keys).
1. Click **New SSH key**
1. Enter for example device name in the **Title** field.
1. **Paste** the public key in the **Key** field.
1. Click the **Add SSH key**.
1. Enable SSO for your SSH key (if Single Sign On is activated for your account):
    * Click **SSO** _(next to Delete button)_.
    * Complete SSO authentication.
1. Return to terminal.
1. Test your ssh connection:
    ```
    ssh -T git@github.com
    ```
1. If asked for authenticity of host github.com, enter **yes**.

## Commonly used commands

### Clone & pull

How you "download" and "update" your local copy of files from the server.

#### git clone *git@git-repo.git*
Downloads the content of master branch in the git repository.

#### git clone -b *branch-name* *git@git-repo.git*
Downloads the content of a specific branch in the git repository.

#### git pull
Get latest changes from the server.

### Branches

How you can contain and group your changes depending on what you're working on.

#### git branch -a
Lists all branches in your machine.

#### git branch *"new-branch-name"*
Creates a branch.

#### git branch -b *"new-branch-name"*
Creates a branch & switches to it.

#### git checkout *"branch-to-checkout"*
Switch to a different branch.

#### git branch -d *"branch-to-delete"*
Delete a branch. Make sure you are not checked out on the branch to delete.

### Commit & Push

How you manage changed files and submit them to the server.

#### git status
Show changed files and what files has been marked for add.

#### git add *file-to-add.ext*
Adds a file to the staged files list. You may also use patterns to add multiple files, for example **src/*** to add all files in src folder.

#### git commit -m *"Short description of what changes you've made"*
Create a commit to the currently checked out branch.

#### git push
Pushes the new commits to the server.

### Random

Various commands that might be needed from time to time.

#### git checkout .
Resets all files to the branch initial state (except new files).

#### git reset --hard
Resets all files to the branch initial state.

#### git clean -xdf
Removes all untracked files from the file system.
