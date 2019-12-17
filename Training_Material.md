# Git Usage

## 1. Windows Commands - working directory
- `cd <file path>` : change to specified directory  
- `cd ..` : change to parent directory
- `ls` or `dir` : gets the files and folders in working directory 

## 2. Git Setup
1. Install Git for Windows
    - [link](https://gitforwindows.org/)
1. Setting in Windows
    - Register your name:  
      `git config --global user.name "Your Name"`
    - Register your email address:  
      `git config --global user.email "email@example.com"`
    - Check setting  
      `git config -l`
1. Add SSH Key to Gitlab
    - [help page](https://gitlab.fftech.info/help/ssh/README#generating-a-new-ssh-key-pair)
    - If you don't have SSH key, generate it in the following way
        1. Open Git Bash on Windows
        1. Generate a new ED25519 SSH key pair:  
           `ssh-keygen -t ed25519 -C "email@example.com"`  
           Or, if you want to use RSA:  
           `ssh-keygen -o -t rsa -b 4096 -C "email@example.com"ssh-keygen -o -t`
        1. Next, you will be prompted to input a file path to save your SSH key pair to.  
           If you don't already have an SSH key pair, use the suggested path by pressing Enter. 
        1. Once the path is decided, you will be prompted to input a password to secure your new SSH key pair.   
        It's a best practice to use a password, but it's not required and you can skip creating it by pressing `Enter` twice.
    - Adding an SSH key to Gitlab account
        1. Copy your **public** SSH key to the clipboard:  
           `cat ~/.ssh/id_ed25519.pub | clip`
        2. Add your public SSH key to your GitLab account by clicking your avatar in the upper right corner and selecting **Settings**.  
        From there on, navigate to **SSH Keys** and paste your public key in the "Key" section.  
        If you created the key with a comment, this will appear under "Title".  
        If not, give your key an identifiable title like Work Laptop or Home Workstation, and click **Add key**.

## 3. Git Commands
### Initial Setup
- `git init` : convert an existing directory to a git repository
- `git remote add origin <url>` : connect the directory to a remote repository on Gitlab

### Commit
(*) frequently used
- `git status` : display the differences from the previous state 
- `git add .` : propose changes (*)
- `git commit -m <comment>` : commit changes with comments (*)
- `git push origin master` : send changes to the remote repository (*)
- `git log` : display repository history
- `git checkout <filename>` : go back to a specified commit
    - `git checkout master` : return to the latest commit  


### Copy from a repote repository 
- `git clone <url>` : create a working copy from a remote repository on Gitlab
- `git pull origin master` : incorporate changes from a remote repository on Gitlab

---

## Notes
### Staging Area
Unlike the other systems, Git has something called the "staging area" or "index". This is an intermediate area where commits can be formatted and reviewed before completing the commit.
<br/><br/>
<img src="Misc/staging_area.png" width=50%>
