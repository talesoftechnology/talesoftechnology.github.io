---
title: How to add a user on linux (ubuntu) and grant root privilege
date: 2023-04-29
categories: [LINUX ,OPEN SOURCE, OS]
tags: [LINUX, UBUNTU, OPEN SOURCE]
author: Verlaine
---

### **The Tale:**   
Linux seems difficult to use compared to those who use Windows daily with a graphical user interface (Gui), it’s easy to use and always beautiful with a great user interface and colorful icons.

in the world of Linux and server environment, nobody cares about the (GUI), it may consume more resources like Ram and video cards, as we work with different distributions such as **CentOs**, **Rocky Linux**, **Ubuntu**, and **Debian**, learning how to work with the Command line interface (CLI) is paramount to run complex tasks.

The Linux CLI is powerful, and mastering basic tasks is the stepping stone to success in tech.

you always add a different account on Windows quickly with a GUI, how to do that with linux  ?

it starts with the CLI! 

as soon as you practice things will become clear. 

Note: in our short demo we use Ubuntu **18.04 Bionic**
- we add a user 
- we test the new user account with a basic task to see how the system behaves 
- we grant the root access

we need a root privilege to add an account and it’s named **“devops_sandbox”**

![LINUX ARTS](https://user-images.githubusercontent.com/125142880/235300059-25e4935f-40c6-4fbd-a52b-1233196f8cb6.png) 

sudo adduser devops_sandbox 
**sudo** : means super user do the command helps us to have the root privilege (higher) and we need that to add an account.

**adduser** : the command helps us to add a user on Linux

Once the command is runned the user will be added to the system then a password is required for the new user every time to log in.

to do that you have to type a password you will remember, for your security it’s invisible when you set it.


let’s log into the new user account : 

![SUDO](https://user-images.githubusercontent.com/125142880/235300210-9c0cff9c-9733-4b8b-b767-7860a97471bd.png) 

sudo login devops_sandbox 

**sudo**: to run the login command as root 

**login**: to login into the new user account and the password is invisible when we write 


we are into the new user account !, let’s run a command and see what happens  


![Nmap](https://user-images.githubusercontent.com/125142880/235300320-c1c7739e-b893-4221-b3a4-702f1cb9da76.png)

**sudo apt install nmap**: we want to install the Network discovery and audits utility “nmap” After trying to install it with a higher privilege with the new account there’s an error! 

**“devops_sandbox is not in the sudoers file.**

what does it mean? 

the user does not have sudo access to run administrative tasks.
to resolve the issue we have to grant the new user sudo access.

let’s grant the sudo access with **visudo** 

![LGT](https://user-images.githubusercontent.com/125142880/235300839-cc388b8e-53d9-4818-ab96-faa7bee9a672.png)


to grant access we have to log out and go back to the **talesoftechnology** account this is the root account.

the command **“logout”** helps us to do that.

![VSD](https://user-images.githubusercontent.com/125142880/235300936-196cda6a-782a-472e-bbe3-bfbe0d741de1.png) 


we are now on the root account, to access the sudoer file which defines the users and groups with administrative, we run **“sudo visudo”** and a password is required.

 
we are in the sudoer file !


![SDRS](https://user-images.githubusercontent.com/125142880/235301472-65a24152-b9a4-4b93-af70-18c3df933415.png) 


There are some lines inside the file, to grant the sudo access to the new user we have created we have to go to the line **“user privilege specification”** and from there we will add the new user **“devops_sandbox”** as part of the root access for more administrative tasks.


![SDRS TMP](https://user-images.githubusercontent.com/125142880/235301612-117c1420-b49f-460b-b06b-361463a74d61.png)

in Linux it’s important to know the notions of users and groups, in the output root  **ALL=(ALL: ALL) ALL** means the user root if logged in into any hostname may run commands as a user or group.

and **ALL** means any are allowed.


once the user added in the sudoer for sudo access, let’s save by combining CTRL and X keys.


let’s go back now to the devops_sandbox by running : **sudo login devops_sandbox**  


from the devops_sandbox let’s run a command to install nmap

![APT NMAP](https://user-images.githubusercontent.com/125142880/235301831-222c31dc-3b22-4fb0-9bfd-9200c600b3f0.png)

Now that nmap is installed let’s try to run a command ! 

![NMAP1](https://user-images.githubusercontent.com/125142880/235302012-845b3d17-1d38-4cdc-a59e-62babcd66172.png)

**Nmap**: we test if the discovery and audits can work, the output shows the version and an example of how to run some commands.

Knowing the basics of users and groups in Linux is a key skill for network engineers and developers.

now our new users can run advanced administrative tasks without difficulties

- Open a shell 
- add a user 
- install a linux utility 
- are you able to run the utility easily as a new user ? 

here are the most importants commands to know : 

- sudo 

- sudo visudo 

- login 

- logout  

Now you know the basics, how do you stay relevant in the industry? 

you have to practice daily, practice makes perfect! 


open your shell and test something now.

Happy learning and thanks for reading 

More articles Coming soon!

Follow us on [tales of technology](https://talesoftechnology.github.io) for more such articles.

our twitter profile - [toftechnology](https://twitter.com/toftechnology)

Our Linkedin profile to follow 

[Verlaine's linkedin](https://www.linkedin.com/in/verlaine-j-muhungu-363507b2/)

[Herald's linkedin](https://linkedin.com/in/herald126/)


please comment below for any queries or feedback














