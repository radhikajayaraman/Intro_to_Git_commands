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
In bash,
Start SSH agent > eval "$(ssh-agent -s)"
Add private key to SSH agent, > ssh-add mygitkey
With that, your Git and GitHub is linked!

#If you want to pull your repository to your local machine, how?
Open any code editor (VScode), create a new folder for the particular project, open terminal, type git clone along with the project link from your GitHub repo

