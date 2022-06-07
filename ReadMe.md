# Tools You'll Need


* **Github** 
    #### - Our repository can be found [here](https://github.com/genesys-samples/cxAsCodeDevlab)

* **New Folder**
    #### - Create and open a folder on your PC where you plan to store code locally. Ex: We created a folder on our Local Disk titled "Dev Projects".

* **GitBash**
    #### -If you are using Git Bash outside of VScode, open Git Bash from this folder by right clicking a blank area within the folder and selecting “Git Bash Here" (see image below)
    ![Gitbash](/images/gitbash.png)
    
* **Microsoft VS Code**
    #### - Can be downloaded [here](https://code.visualstudio.com/download)
    #### -Open VS code from this folder by right clicking a blank area within the folder and selecting "Open With Code" (See image above)
    <br>
* **Hugo**
    #### - Can be downloaded [here] (https://github.com/gohugoio/hugo/releases)
    #### - Follow instructions [here](https://gohugo.io/getting-started/installing/)
# Setup SSH (Secure Shell) & Signatures within Git Bash

* **Generate a SSH Key**
1. Open GitBash and type in the following command: ssh-keygen -t ed25519 -C your_email@example.com <br>
        1.1 Press "enter" when asked for the file name <br>
        1.2 Take note of the file path it is saving the key in. 

2. Create a passphrase (Note: It will not look like you are typing anything so ensure you type this out carefully)
3. Copy the key to your clipobard with this command: clip < ~/.ssh/id_ed25519.pub 
        3.1 Alternatively, you can manually navigate to the .pub file within your file explorer, open it with a text editor, and copy your token to your clipboard
    4. Open Github in browswer > click your portrait in the top right > navigate to "settings">"SSH & GPG keys"> "Add new SSH"> "Give Title"> Paste your copied SSH key here > "Add"

* **Setting up signatures**
1. Download the GPG Command line for the OS at this [link](https://www.gnupg.org/download/)
2. Open GitBash and run the following commands <br>
        2.1 Command: gpg --full-generate-key <br>
        2.2 "Type 1" for the default key type <br>
        2.3 "Type 4096" as your key must be at least that long <br>
        2.4 If you wish to set an expiration time, do so here, but otherwise type "0" <br>
        2.5 For "Real name" insert your Github username <br>
        2.6 For "email" insert your Github email <br>
        2.7 For "Comment" type your full name <br>
        2.8 Command: gpg --list-secret-keys --keyid-format=long <br>
        2.9 Copy the long form of the key id from the list (Note: Copy long form o fkey id to notepad. You will need this later in the exercise). In this example, you want to copy "**3AA5C34371567BD1**"
3. Command: gpg --armor --export **insert key you just copied here**
    3.1 Note: Copy everything including the "---Begin  Public key and ----End Public Key"
4. Follow the instructions [here](https://docs.github.com/en/authentication/managing-commit-signature-verification/adding-a-new-gpg-key-to-your-github-account) to add the key to your Github account
5. Open Git Bash (you will need the long form of the key id from step 2 again) <br>
    5.1 Command: git config --global user.signingkey **insert key id here*
6. After completing this step, you should be able to sign your commits by adding the "-S" flag to the commit <br>
    6.1 For example, "Git committ -S -m "your commit message". Your comments should then show up as "verified" in the repository

    ## _Previous steps are only completed at initial setup. Not every time you are creating a repository!_

# Genesys Workshop Creation

1. Go to Genesys workshop template [repo](https://github.com/genesys-samples/genesys-workshop-template) and click "Use this template" <br>
    1.1 Create the new repo with "Genesys Samples" as the owner (Note: Owner must be manually changed as it will default to you) 
2. Create a fork from this newly generated repo and just have yourself as the owner of the fork
3. Go to your fork and click the Green "Code" button. Click "SSH" and copy that link
4. Open VS Code and choose a folder you want to work in
    4.1 Run the command:Git clone --recursive and paste the SSH link you copied. Then press enter.
    4.2 This should download the folders and files from the repository that you previously created. Because you forked it from the Genesys Workshops template, you should have the folder structure for Hugo
    4.3 You will mainly do your editing under the "content" folder
5. Select "Terminal" at the top of your screen and run a new terminal and let's set your origin and upstream <br>
    5.1 Upstream-this is the original repo that we forked from (the one in Genesys Samples)<br>
    5.2 Origin- this is the repo that you forked into your own personal repository <Br>
    5.3 Run the command:git remote add upstream and paste the SSH link from the original repository (Note: this is not the SSH link from your fork. This is the SSH you can copy from the original repository) <br>
    5.4 Run the command: git remote -v <br>
    5.5 Your personal repo should be set as the Origin and the Genesys Sample repo should be set up as the upstream <br>
6. Edit the "ReadMe.md" file and give it a description for your workshop <br>

    ## _Previous steps only have to be completed one time when first creating the repository. They do not have to be completed every time you work on the workshop!_

# Workshop Guidelines
<br>
1. Before you start working on your repository every day, run the following commands to ensure you are working from the latest version of the Upstream <br>
  &nbsp; 1.1 Git remote-v <br>
&nbsp; 1.2 Git fetch upstream main <br>

2. Periodically, while doing work you should commit your changes. After you’ve finished with your ReadMe, let’s commit those changes and push them to your fork. Run the following commands <br>
&nbsp; 2.1 Git add . (include that period) <br>
&nbsp; 2.2 Git commit -s -m "modified readme" (You can remove the "-s" if you haven't set up GPG keys, but we recommend setting them up) <br>
&nbsp; 2.3 Git push <br>

3. After doing this push, you should be able to view the changes that you made in your personal fork. You also should notice on your personal repo that you are 1 commit ahead of your upstream. You can contribute these changes by clicking the contribute button, and then “Open pull request.” Go ahead and navigate through the pages to create the pull request <br>
&nbsp; 3.1 Note- You don't need to Push or Open a Pull Request for every commit that you do
&nbsp; 3.2 Best practice is to commit frequently, but you only need to push and pull maybe once a day. When you are doing pushes and pulls, you are pushing and pulling multiple commits at once

4. Now that you have opened a Pull request, assign someone to review your work before merging it into the Genesys sample repo. That person will then go in and review your changes. They will either approve the changes and merge them into the Genesys Sample repo or ask you to fix some things before it can be merged

5. Modify the "Content" folder to write your intro page <br>
&nbsp; 5.1 Under content you will find a file named "_index.md". This will be the first page that people are shown when starting the workshop so make it a descriptive introduction to the workshop <br>

6. Let's check out what Hugo framekwork is doing with this markdown file now. Run the following command <br>
&nbsp; 6.1 Run command: Hugo server -D <br>
&nbsp; 6.2 Copy the local host link into your broswer to view your workshop. Be sure to save your files first <br>
&nbsp; 6.3 Run command: CTRL+C <br>
&nbsp; 6.4 This will stop the Hugo web server that was spun up. Leaving the web server running will kill your laptop battery

7. Now let's set up our sections and subsections <br>
&nbsp; 7.1 Under the Content folder you will notice "010-Introduction, 020-Getting Started, and 090-Conclution". You will also notice that the _index.md files that are within these folders are the names of the sections <br>
&nbsp; 7.2 You should also take note of the weight value. The weight value is what puts the sections in order. Notice that the weight of the _index.md file under 010-Introduction is 10 and the weight of the _index.md file under 020-Getting-Started is 20. The lowest weighted file will be the first section and so on <br>
&nbsp; 7.3 Now under the 020-Getting-Started file, you’ll notice that there are two other files other than the _index.md file. They are 10_first.md and 20_second.md. These extra files will be the subsections. These files are not marked as Chapter’s while the _index.md files are. You also should take note that these subsections also will use the same weighted values to decide the order of the subsections <br>

8. Okay you should understand how to organize the sections and subsections. Get after it! And feel free to use the “Hugo server -D” command every now and then just to be sure you’ve got the weighting correct <br>
9. Okay, once you’ve got your sections and subsections outlined, it’s time to get to the real work. Now you need to write up the content in your sections and subsections. Be sure to regularly commit your changes <br>
&nbsp; 9.1 Before commit changes, run Hugo server-D to make sure everything looks good <br>
&nbsp; 9.2 The steps to commit changes are as follows <br>
   &nbsp; &nbsp; &nbsp; _a. Git add_ <br>
    &nbsp; &nbsp; &nbsp; _b. Git committ -s -m "descriptive message"_ <br>
    &nbsp; &nbsp; &nbsp; _c. Git push- this will push it to your forked repo_ <br>
    &nbsp; &nbsp; &nbsp; _d.Follow steps 3 & 4 to pull them into the Genesys Samples repo from your forked repo


