# Lab Report 1 - Week 2

Hello viewers!

Today's main topic will be about how to **access machines or computers remotely**; specifically connecting to computers in the UCSD basement lab by logging into the course-specific account `ieng6` remotely using our own device. Cool idea right?!

So now, I will be demonstrating *6 steps* to complete this magical process:

## 1. Installing Visual Studio Code
- Visit the [Visual Studio Code](https://code.visualstudio.com/) website to download and install VSCode onto the computer. 

- Once installed and opened, the home page of VSCode should look something like the image below:
[![vscode.png](https://i.postimg.cc/90sfzVt7/vscode.png)](https://postimg.cc/QKkDn2z8)

- In VSCode, open a terminal by going to tab `Terminal` on the top bar and click on `New Terminal`.
[![vscodeterminal.png](https://i.postimg.cc/NFXK6504/vscodeterminal.png)](https://postimg.cc/MfWZxZVM)

## 2. Remotely Connecting
- In the terminal, type in `$ ssh cs15lsp22zz@ieng6.ucsd.edu` (where `zz` is replaced your assigned username)

- A series of messages will pop up when logging into the account for the first time along with the question:

>`Are you sure you want to continue connecting (yes/no/[fingerprint])?`

>Don't be scared; just type `yes` and enter. Everything will be okay. I promise. Otherwise, ask Professor Gerald or tutors for help.

- Finally, enter your passcode. If you are greeted by the system like this:
[![ieng6](https://i.postimg.cc/0yQ25Qwr/Screen-Shot-2022-04-10-at-7-31-50-AM.png)](https://postimg.cc/3dsHn39H)
**CONGRATULATION!!** You have successfully connected to the server remotely. So now, let's try out some commands.
## 3. Running Some Commands
- Below is an example of what some of the commands are and the outputs that running these commands will produce:
[![Commands](https://i.postimg.cc/90ytM2rN/Screen-Shot-2022-04-10-at-8-23-53-AM.png)](https://postimg.cc/ct489V7Q)

- The commands I ran were:
```
ls: list files
cd: change directory
cd ~: change to home directory
pwd: print working directory
ls -l: list files along with their permissions, sizes, types, ownerships, etc.
ls -a: list files along with other hidden files
```
- Now it's your time to try out some yourself !

## 4. Moving files with `scp`
## 5. Setting an SSH key
## 6. Optimizing Remote Running
