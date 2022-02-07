A GUIDE TO GIT, GITHUB WITH EXPLANATION, UNDERSTANDING COMMITTER'S NAME IN GIT AND GITHUB AND SWITCHING BETWEEN MULTIPLE GITHUB USER ACCOUNTS

Goals: 
A) Create a repository in github.   
B) Understanding basic git commands.  
C) Upload files in the github repo using git.   
D) Understanding multiple users in commits and switching between different github accounts while pushing the repo  

GOAL A (Create a repo in github)

1. First step is to create a repository (hereinafter repo) in github. Visit github website, login to your account and using the + sign in top right, create a new repo. Give a name to your repo like PornHubToGitHub, ignore other options, and click create repository. Your repo is created. 

2. The repo page consists of various tabs such as Code, Issues, etc. related to your repo. By default, the code tab would be selected.

3. Copy the https link provided in the code tab. Or you can just type it out yourself. The link is structured in this way: https://github.com/YOUR_GITHUB_USERNAME/REPO_NAME.git

4. Change the capital letter portion in the above link structure with your github username and the name of your repo. Though the best way is to just copy the link using copy button provided on the first page after a repo is created or just select the link and copy it. Since there are no files in your repo so far, it is showing the repo link and other ways to upload repo in the code tab. When your repo would have some files, instead of this screen, your code tab would have the files. 

GOAL B (Understanding basic git commands)

1. Install gitbash in your computer. Fairly simple process of installing and setting username, email, etc. in git. You may get plenty of online help on this.

2. Create a folder anywhere, give it a name like PHtoGH, and open it. 

3. Create any file in this folder like why_i_cant_eat_rice_with_chopsticks.txt

4. Shift+right click (Windows OS) in an empty space in the folder and click "git bash here" to open git bash with this folder as its location.

5. In the git bash window type and enter (hereinafter "shoot"): git status
git status command is used to check, well, the status of the files in the repo (the folder you created is now called a repo since you would be creating files for your github repo in this folder). The output of this command right now would be something like: not a git repo.
Therefore, first you need to make this folder as a git repo. How?
shoot: git init 
(Remember "shoot" is a shortcut for "type and enter the text after 'shoot:' in the git bash window)
This would create a ".git" hidden folder in the repo

6. shoot: git status
This would show the file in your repo as untracked file. So, you need to track it. Track it for what? Changes! That's what git does. It tracks changes. But to track changes, you need to add files that you want to track with git. In fact, it's not adding the file but adding the changes because you need to shoot git add again if there is any change in the file. It's not like if you have added the file for tracking, you don't need to add this again. You do if there is any change in the file. In git terminology, this is known as staging.  
If you want to track all files in a repo, just shoot: git add .
That dot is not  a fullstop. It's part of the command. 
Or you can just write the file name.
shoot: git add why_i_cant_eat_rice_with_chopsticks.txt
Write the complete name of the file including the extension.
If your file name has space then use inverted commas like
shoot: git add "why i cant eat rice with chopsticks.txt"

7. shoot: git status
(When you are familiar with git, you don't have to shoot git status these many times. It's just to understand what's happening.)
Now, git would be asking you to commit (that's what she said!). So, you have added the files and git has observed the change (Adding something is considered a change). Committing is like you accept these changes and git should keep a snapshot of the current files and their contents so that you can review it later if the need arises. 
shoot: git commit -m firstCommit
"firstCommit" is the message you need to provide for this commit. You can write anything you want in the message. If the message contains spaces then keep it in inverted commas like
shoot: git commit -m "All right I get it"

8. Now, you have completed one cycle. Let me summarize it: 
git init: one time command, to initialize the repo
git add .: run this if you have changed anything
git commit -m Msg: run this if you want a snapshot of current files and their contents in git

If there is any change after the commit, you need to repeat add and commit commands.

Don't want to write add and then commit? Use a single command:
shoot: git commit -a -m Msg
(Note that this stages all the files that git is tracking and commits)

Suppose you're writing name of 10 animals in a text file. You may do this in a single commit. So, you write all 10 names, add and then commit. Done!
Or you may do it in two commits. Write 4 names, add and then commit. Write 6 names, again add and commit. 
Both achieve the same purpose but the difference is if you have to go back to a these commits in future, you would get all 10 names written in case of first way of commiting while in the second way, you may choose to go back to either all 10 names commit or 4 names commit. 
How would this be useful? Why would I perform the same task in multiple steps when I can complete it in a single step? Because..
Let's say you have written 4 names. Just when you were about to write the 5th name, you thought of getting this work done by your nephew while you jog. You came back tired, saw the 10 names list was complete, you add the file for staging and then committed it. 
Your boss saw the list and got utterly disappointed after reading pebbles and defenestration in the list of animals' names. 
Now you need to rectify it. You know that first 4 names that you wrote are ok. If you had committed at this stage you would have simply compared and checked the two commits-when 4 names were completed and when 10 names were completed.

It depends on you how often do you want to commit. It's recommended that you commit regularly.


	
GOAL C (Upload files in the github repo using git)

1. Your repo is in your local machine and now you want to upload it to github. So, you need to tell git that I have this online space where you need to connect and upload this repo. The world would know that you have finally switched from PH to GH.
shoot: git remote add origin URL
URL is the URL that you copied in step 3 of Goal A
origin is just a custom name to identify with the URL. You may write it like this as well:
shoot: git remote add subtract URL
Now subtract is your git name for the URL
You have to run this command only once for any repo.
You can check all these names that you have created and their URLs using this:
shoot: git remote -v

Let's continue with the origin though.

2. Now you have told git about your remote address. Git is ready to push (upload) you repo to the given url.
shoot: git push origin master
push is you are asking git to uplaod the file
origin is your remote name. Use whatever remote name you gave while adding the remote url
master is the branch name

3. Github login window would appear. Login with your github username and password and you are done. There is an option of login through browser, click it to login through browser.

Open github website. Now you can see your files in the code tab of your repo.
DONE

Goal D (Understanding multiple users in commits and switching between different github accounts while pushing the repo)

(Disclaimer: I am not a git or github pro but I experimented with a few things since I was confused even after reading and watching a lot of tutorials. These are my observations)

1. Committer's Name
shoot: git config -l
This gives a list of configuration settings. You can see your user.name and user.email here that you configured after installing git bash.
You may shoot specific commands for username and email:
shoot: git config user.name 
(This will give the username you are using in git. We will call it UNgit)
shoot: git config user.email
(This will give the user email you are using in git. We will call it UEgit)

This username and email shall be used in commit logs. 
shoot: git log
You can see your name and email.

In github also, you can see the committer's name. But it works differently in github.
Open your repo in github. Go to the code tab. In the section listing files, no. of commits shall be mentioned in top right. Click on it to see all commits. You can see all the people who made the commit in this repo.

In git, if you run git log, you would be able to see UNgit and UEgit listed in the committer's name and email while in github it's not like this.

Github gives the name based on UEgit. If there is an account on github with UEgit, the name shown in commits in github shall be the username of UEgit github account. It doesn't matter what your UNgit is for github.  

Let's say you have the following two accounts on github:
A1: username- everythingIsUnderControl email- eiuc@eiuc.com
A2: username- maybeItsNot email- min@min.com

Let's say your UNgit and UEgit are A1's username and email.
You create a repo in A1. Follow steps mentioned in goals A-C. Remember to authenticate using A1 account when github login window pops up.

Running git log would give UNgit and UEgit which are same as github's A1 account
In github also you can see the name of the committer which would be same as Ungit

Now change your username in git.
shoot: git config user.name FlyingTortoise
Now make some changes and commit again. Using Goal C, step 2, upload the changes on github.
If you run git log in git bash window, the username shall be FlyingTortoise but in the commit log on github account the committer's name shall be same because you have not changed the email.

Now, let's change the email in git
shoot: git config user.email min@min.com

now make some changes in file, commit and upload on github.
In committer's name on github, the name would be maybeItsNot ie the username of min@min.com account on github.
You can click on the photo icon of the committer to visit his/her github account as well.
If Alan Turing were on github, you copy the Turing's github account email and do this:
shoot: git config user.email at@at.com

Now make changes in the file, commit and upload on github. Now you can see that Alan Turing committed in your repo without him actually committing anything.

In case, UEgit has no account on github, then UNgit shall be visible on github as well as the committer's name. There shall be no link to it though as we see when committer's account is on github.

Summary of committer's name in git and github:
git: committer's name and email shown in git log are same as user.name and user.email which you can see after running git config --l
github: committer's name is the username of the github account whose email is same as user.email of git. If no account of user.email on github then name shall be same as user.name of git.

2. Authentication
When you have log in once in your github account through git (Goal C, step 3), it doesn't ask you again to login. So when you push again, it automatically push the repo to the desired destination.

Earlier you authenticated git using account A1 of github. Now, if you make a repo in A2 account following the steps mentioned in goals A-C. You won't be able to push it because your github authentication is for A1 account but your current repo link points to repo of A2 account. So you need to change the authentication. For that first you need to remove the existing authentication.
Two ways to do it:
i) Control panel > search for credential manager > Open it > there would be a github account listed in it > click on it and remove it
ii)shoot: git credential-manager delete https://github.com 

Now, when you push the repo, github login window would appear again. Login with your A2 account now. It would work this time.

Footnotes:
1. Local and global user details
shoot: git config user.name MyNewName
With this you are changing the username in your current repo
shoot: git config --l
This would list both your global username (used in all repos except where you have specified the local username for the repo) and your local username. 
You can see both explicitly:
shoot: git config user.name
This gives your current repo username or local username
shoot: git config --global user.name
This gives your global username
Want to change the username globally?
shoot: git config --global user.name NewGlobalName

Similarly you can view and change local or global email. Use user.email instead of user.name in the above commands.

Remember local username and email dominates over global. If locals are not specified, then global is used. 




