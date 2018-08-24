# Git going
How to get git configured to work with ssh (github) and basic git commands for the terminal.

1. Open terminal.
1. Set git user name & email: 
    ```git config --global user.name "Firstname Lastname"```
    ```git config --global user.email "firstname.lastname@whatever.io"```
1. Set git to use new behavior for git push: 
    ```git config --global push.default simple```
1. Generate a ssh key for your device: 
    ```ssh-keygen```
1. Press **ENTER** (defaults to ~/.ssh/id_rsa)
1. Press **ENTER** (to skipping password)
1. Press **ENTER** (to skipping password)
1. Add ssh key to the ssh-agent: 
    ```eval $(ssh-agent) ssh-add ~/.ssh/id_rsa```
1. Get the ssh public key: 
    ```cat ~/.ssh/id_rsa.pub```
1. **Copy** the output.
1. Open browser.
1. Go to [https://github.com/settings/keys](https://github.com/settings/keys).
1. Click **New SSH key**
1. Enter for example device name in the **Title** field.
1. **Paste** the public key in the **Key** field.
1. Click the **Add SSH key**.
1. Return to terminal.
1. Test your ssh connection:
    ```ssh -T git@github.com```
1. If asked for authenticity of host github.com, enter **yes**.
