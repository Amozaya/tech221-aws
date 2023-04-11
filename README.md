# SSH Guide
## How to connect your local repository to GitHub using SSH

### **Create your keys**

**Step 1. Create a folder to save your keys**

![Create directory for keys](/resources/create_directory_for_ssh_keys.JPG)

First, I create a new directory inside "Home" folder using `mkdir .ssh` command. It creates a new folder called `shh` and `.` before the name makes the folder hidden.
Then, I'm using `cd .ssh` command to navigate inside the folder.

**Step 2. Create your keys**

![Create the keys](/resources/create_a_key.JPG)

Inside `ssh` folder i use this command in order to generate a new pair of keys (public/private), where:

* `ssh-keygen` - using keygen to generate keys
* `-t rsa` - type of the key
* `-b 4096` - size of the key
* `-C "olegfursa93@hotmail.com` - email account linked to these keys

After you press `Enter` it will ask you to give the name to your keys, I entered `oleg_github_key`, and also if you want to set a password. If you want to leave it blank just press `Enter` without typing anything:

![Keys created and verified](/resources/key_created_and_verified.JPG)

In order to verify that it was created I used an `ls` command to check for existing files.

### Step 3. Add your public key to GitHub
Before we go and create a new public key on out GitHub we have to copy the value from our public key that we generated:

![Public key value](/resources/open_public_key.JPG)

To copy the value of our public key I have to open the file by using `cat` command, and then I can copy the value.

**_Important! When you copy, ensure you don't copy empty spaces at the end of your key, as it will still count as characters!!_**

Now, let's go to our GitHub account and add a key:

* First, let's open our account `Settings`:

  ![GitHub account setting](/resources/github_menu.JPG)


* There, you need to select `SSH and GPG keys`:

    ![GitHub ssh setting](/resources/gihub_ssh_settings.JPG)


* In the new window select `New SSH key`:

    ![Create new SSH key](/resources/new_ssh_key.JPG)


* There, you have to give a name to your key (you can use the same name as you gave when generating the keys), 
  and then paste the value from your public key. Once it's done, click on `Add SSH key`:

    ![Paste key value](/resources/add_ssh_key.JPG)


* Once key is added, you will see it in your GitHub Settings:

    ![Key added](/resources/github_key_added.JPG)


### Step 4. Register your key

Before you establish connection with GitHub and can push your code you have to register your key and authenticate your connection using following lines of command:

![Authenticate connection](/resources/add_key_to_register.JPG)

* ``eval `ssh-agent -s` ``  - to activate ssh-agent
* `ssh-add oleg_github_key` - add private key to register
* `ssh -T git@github.com` - authenticate your connection to GitHub


### Step 5. Create new repository on GitHub and push your commits

Now, it's time to create a new repository so we can push our code there:

1. Go to your GitHub and use `+` button to open the menu and select `New Repository`:
    
    ![Create repository](/resources/new_repository.JPG)

2.  Give a name to your repository, rest of the settings you can leave by default, and then click on `Create repository`:

    ![Create_new repository](/resources/create_new_repository.JPG)

3. Once repository is created you need to ensure you have `SSH` enabled in order to connect using SSH. You can use the instructions on your newly created repository to establish connection with your local repository and push any commits to your GitHub:

    ![Repository created and SSH connection selected](/resources/repository_ssh_connection.JPG)

4. Make your first commit (I used PyCharm):


   ![First Commit](/resources/first_commit.JPG)


5. Now `push` your commit to your GitHub (push was done in gitBash due to technical problems with PyCharm connection):

    ![Push to GitHub](/resources/push_changes_to_git.JPG)

6. Finally, refresh your browser and see the changes on your GitHub repository:

    ![Repository updated](/resources/connection_established.JPG)
    


