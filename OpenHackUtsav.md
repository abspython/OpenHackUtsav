[![made-with-Markdown](https://img.shields.io/badge/Made%20with-Markdown-1f425f.svg)](http://commonmark.org) [![Open Source Love png1](https://badges.frapsoft.com/os/v1/open-source.png?v=103)](https://github.com/ellerbrock/open-source-badges/) 

# [OpenHackUtsav](http://fossers.vidyaacademy.ac.in/OpenHackUtsav.html) @[VAST](http://www.vidyaacademy.ac.in/) 2018

##### A [Hacktoberfest](https://hacktoberfest.digitalocean.com/) program.. 

#### Table of Contents  
  * [Session 1](#session-1)
      - [Setting up the system](#setting-up-the-system)
      - [Basic git commands](#basic-git-commands)
  * [Session 2](#session-2)
      - [1. Fork the repository](#1-fork-the-repository)
      - [2. Editing](#2-editing)
      - [3.Update your edits](#3update-your-edits)
      - [4.Create Pull Requests](#4create-pull-requests)
  * [Session 3](#session-3)
      - [Rescuing Kerala A Look At Tech presentation](#rescuing-kerala-a-look-at-tech-presentation)
  * [About](#about)


## Session 1

This session is lead by Ambady Anand, a Software developer, Free Software Enthusiast and Privacy Advocate.

#### Setting up the system

------

Before going to use git we want  to check whether your system has [git](https://git-scm.com/).

For checking whether you have git type the following,

```bash
$ git --version
```

For installing git in your system

```bash
$ sudo apt-get install git
```

Then open up the terminal and update your git account.

```bash
$ git config --global user.email "username@example.com"

$ git config --global user.name "Your Name"
```

For clone a git repository use,

```bash
$ git clone https://github.com/....
```



#### Basic git commands

------

For checking the status of your edit,

```bash
$ git status
```



For adding your edit to the origin/master branch,

```bash
$ git add .
```



For committing your edit to the master branch,

```bash
$ git commit -m "Some random message"
```



For pushing your code to remote server,

```bash
$ git push
```



If you got conflict error the update the git repository by,

```bash
$ git pull
```

and call 

```bash
$ git mergetool
```

for fixing the conflict.

Use the default conflict resolver ``meld`` for graphical conflict resolving.



## Session 2

Here were are going to do some action in Github.

The main steps in done in this program

1. Fork the repository
2. Edit the necessary files/Add new ones
3. Update your edits
4. Create Pull Request (**PR**)



#### 1. Fork the repository

------

First fork the repository from the source or from group leader by clicking on the fork button on the right-most part of the repository.

Now you have got a duplicate of the repository.

Now we need to save our repository to our local system or computer. We need to copy the URL of your repository and do following command.

```bash
$ git clone https://github.com/examplerepo
```

Now we have successfully saved the repository to your system.

Then make a duplicate of ``index.html``file as ``gimp.html``file by using the below command. You can use your own filename but be careful that it must be a ``.html``file.

```bash
$ cp index.html gimp.html
```

#### 2. Editing

------

Edit your files by using text editors like gedit,sublimetext,etc.

It is recommended to commit every edits you do as it will easier for you to return to previous code. So for committing your edits do the below code.

```bash
$ git add .
$ git commit -m "Edited file!!"
```

#### 3.Update your edits

------

After editing your file, we now have to update your repository in the remote server ,i.e in Github's server. For this we use ``push`` command.

```bash
$ git push
```

After this , we have successfully updated the repository in the server.

Note : At this stage you may have encountered an error due to mail privacy. To solve this just uncheck the Email privacy in the Email Tab in your Profile Settings. For more info regarding this error, click here.

#### 4.Create Pull Requests

Now we have reached to the last and important stage of our session. Creating  pull request is basically adding your new features to the master branch of the repository.

To create **PR**, click on 'New Pull Request' in th 'Pull Request' Tab in your repository. Then compare both of your edits and apply for **PR**. Now a dialog box will come and add some details. Then click submit.

Now you have made your Pull Request or simply your **PR** !!

## Session 3

#### Rescuing Kerala A Look At Tech presentation

This section mainly deals with the technical side of hosting a website. This session was led by [Biswas](https://biswas.me), an active S7 C.S.E student from G.E.C Palakad and a Web developer based on Django framework in Python. He is the main hero during  Kerala Floods and the brain behind [keralarescue.in](keralarescue.in).

The main framework/services used for development of the website was,

1. [Heroku](https://www.heroku.com/)
2. [Cloudflare](https://www.cloudflare.com/)
3. [Django framework](https://www.djangoproject.com/)

He also described about the challenges faced by him on the Flood days and also gave a brief introduction to the above services/framework used.

## About

This notes are written by [Abhijith Sheheer](mailto:abhijithsheheer@gmail.com) , C.S.E student in Vidya Academy of Science and Technology. The application used here [Typora](http://typora.io/).


Made with :heart: and [Markdown](https://daringfireball.net/projects/markdown/syntax)
