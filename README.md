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

* First, let's open our account `Settings`

  ![GitHub account setting](/resources/github_menu.JPG)
