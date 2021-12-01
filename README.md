# Intro_to_Git_commands
A readme file - Git and GitHub intro with commands (Basic and Advanced)

#Git 
Is a local repository to track your project

#Github
Remote repository to store and track your projects 

#Let's see the setup of Git (Local)
Download and install Git from official Git website. Go to command promt and type git --version (to check whether Git is installed successfully)

#Let's see the setup of GitHub (Web)
Create your account in GitHub (Sign up)

#After setting up Git and GitHub, let's link them both
#Using email provided during GitHub sign up, we can link Git and GitHub

Create a rsa public and private key
In cmd, 
> ssh-keygen -t rsa -b 4096 -C "radhika.jayaraman091@gmail.com"
> Enter file in which to save the key (C:\Users\manoj/.ssh/id_rsa): mygitkey

Once the key is created, search the key in cmd 
>dir
mygitkey
mygitkey.pub

both private and public keys are generated. Now, copy-paste your public key (mygitkey.pub) in your GitHub account,
>cat mygitkey.pub
Go to, GitHub account --> Settings --> SSH and GPG Keys --> paste contents of mygitkey.pub in key field --> Click on Add SSH Key

GitHub has public key, now tell Git about the generated key,
In bash (git bash),
Start SSH agent > eval "$(ssh-agent -s)"
Add private key to SSH agent, > ssh-add mygitkey
With that, your Git and GitHub is linked!

#If you want to clone your repository to your local machine, how?
Open any code editor (VScode), create a new folder for the particular project, open terminal, type git clone along with the project link from your GitHub repo
>git clone https://github.com/radhikajayaraman/Intro_to_Git_commands.git
ssh link works for public repo, however use https link as above for private repo

Once the cloning is successful, now you can read/write/edit the folders of the project using your VScode. After making the changes or adding code/content to the project, you have to commit to the local git and then push the code to GitHub repo. 

#Saving the changes to local Git
If the existing files from GitHub repo project is edited, then you can just commit the changes.
If you add a new file to the project, then you have to help git to track it. So add the file before commit,
>git add <filename> or >git add . #Period symbol is used to track all files
The status of all files can be known using,
>git status
#PS C:\Users\manoj\Desktop\WorkRelated\Intro_to_Git_commands\Intro_to_Git_commands> git status

Now, commit the changes,
>git commit -m "updated readme document"
#commit always requires a message -m for message box 
#another -m is optional, and that describes the description box

>git commit -m "updated readme document" -m "Added commands for push, pull and commit"
#if the commit isn't allowed because it doesn't recognise you, then 
>git config --global user.email "radhika.jayaraman091@gmail.com"
#After commiting your code to git, you have to send the code to github to store,
use push command
>git push origin master

#Even there are any code change in github repo, then you can pull those changes to your local,
use pull command
>git pull origin master

#In case you want to add a new folder, then it won't be a git folder, so you need to initiate the folder as git,
>git init
#After initiating a git folder, you need to clone before pushing the changes/code
Create a new repository in GitHub and clone
>git remote add origin <git ssh copied to clone>
#Now, you can push the code to new repo in GitHub
>git push origin master

#In case you want to create a branch and merge the branch to the master branch then,
>git checkout -b <branch_name>
#check for conflicts and merge
>git merge master

#Editing/reset
>git log #to know the log/hash of coomits
>git log --oneline
>git reset <name_of_file_to_unstage>
>git reset <hash_of_commit>
>git reset HEAD~1 #to reset/unstage the last commit
#undo
>git reset --hard <hash_of_commit> #to completely remove/undo not just unstage

#As other repos cannot be edited, just go to GitHub repo and click on fork
#Now, the repo will be under your user profile, and can be edited and used.


#Advanced Git Commands #interactive rebase
#Edit commit messages
>git rebase -i <hash_value_of_commit> or >git rebase -i HEAD~3 #All the commits after three pointer head will be displayed, and change the <pick> keyword to <reword>, save and close. In the open new file, change the commit message as required.

#combine two commits
Give the second commit as squash
>git rebase -i HEAD~3
In the file, replace <pick> with <squash> for the second commit which needs to be merged to the one before.

#get the deleted branches
>git reflog #to get the hash of needed branch
>git branch <branch_name> <hashnumber>

