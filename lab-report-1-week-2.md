# Lab Report 1 - Week 2

Hello viewer!

Today's main topic will be about how to **access machines or computers remotely**; specifically connecting to computers in the UCSD basement lab by logging into the course-specific account `ieng6` remotely using our own device. Cool idea right?!

So now, I will be demonstrating *6 steps* to complete this magical process:

## 1. Installing Visual Studio Code
- Visit the [Visual Studio Code](https://code.visualstudio.com/) website to download and install VSCode onto the computer. 

- Once installed and opened, the home page of VSCode should look something like the image below:
[![vscode.png](https://i.postimg.cc/VNRX2g22/vscode.png)](https://postimg.cc/wt1tmXqk)

- In VSCode, open a terminal by going to tab `Terminal` on the top bar and click on `New Terminal`.
[![vscodeterminal.png](https://i.postimg.cc/NFXK6504/vscodeterminal.png)](https://postimg.cc/MfWZxZVM)

## 2. Remotely Connecting
- In the terminal, type in `$ ssh cs15lsp22zz@ieng6.ucsd.edu` (where `zz` is replaced your assigned username)

- A series of messages will pop up when logging into the account for the first time along with the question:

>`Are you sure you want to continue connecting (yes/no/[fingerprint])?`

>Don't be scared; just type `yes` and enter. Everything will be okay. I promise.

- Finally, enter your passcode. If you are greeted by the system like this:


[![ieng6.png](https://i.postimg.cc/9QBpjc7x/ieng6.png)](https://postimg.cc/87jWRQwW)

**CONGRATULATION!!** You have successfully connected to the server remotely. So now, let's try out some commands.
## 3. Running Some Commands
- Below is an example of some of the commands and the outputs that running these commands will produce:
[![commands.png](https://i.postimg.cc/dtjdh4V3/commands.png)](https://postimg.cc/3dWW6jpQ)

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
- Another thing you can do is copying and transferring files from your computer to the remote computer. You can do this by using the `scp` command, which stands for **secure copy**.

- You can first create a java file or use a preexisting java file. In the terminal of your local computer, run the command:

`scp <filename>.java cs15lsp22zz@ieng6.ucsd.edu:~/`

[![transfer-file.png](https://i.postimg.cc/zfHM82rF/transfer-file.png)](https://postimg.cc/GBrzjQ94)
>Again, remember to replace `zz` with your assigned username. Also, `<filename>` is replaced with the name of your file. The example above is using `WhereAmI.java` file.

- Then, log into your `ieng6` account with `ssh` and run the command `ls`. You should be able to see the java file in the home directory.

- The files can now be run on the ieng6 server using `javac` and `java` commands

[![run-file-remotely.png](https://i.postimg.cc/TwXkGRQT/run-file-remotely.png)](https://postimg.cc/FfDbVX26)

## 5. Setting a SSH key
- You may have noticed that you have to put in the password everytime you log in or run `scp`. To overcome this repetitive process, `ssh-keygen` is the solution.

- In the terminal of your local computer, type `$ ssh-keygen`. When you see `Enter file in which to save the key (/Users/<username>/.ssh/id_rsa):`, copy and paste your `/Users/<username>/.ssh/id_rsa`. Then, the next line will say `Enter passphrase (empty for no passphrase):`. Proceed to press enter without typing in anything. Press enter again when the program ask to `Enter same passphrase again:`.

[![ssh-keygen](https://i.postimg.cc/4dT00Rx1/Screen-Shot-2022-04-10-at-5-38-37-PM.png)](https://postimg.cc/Z9Vj9g39)
>Source: screenshot taken from Lab 1 Write-up

- These actions generate two keys, private and public. This is shown in file `id_rsa` and `id_rsa.pub`, respectively. You will only need to copy the public key for later. Then, log into the `ieng6` account, and make a directory by running the command `$ mkdir .ssh`. Logout of the server by typing `exit` into the terminal *or* press `Ctrl-D`. Now, type in: 
`$ scp /Users/<username>/.ssh/id_rsa.pub cs15lsp22zz@ieng6.ucsd.edu:~/.ssh/authorized_keys` (use the public key from earlier to replace the path after `scp` and replace `zz` with your username)

[![no password](https://i.postimg.cc/zGjdD28J/Screen-Shot-2022-04-10-at-8-39-50-PM.png)](https://postimg.cc/Jss3Pqsg)
Yay! Now you can log in without having to put in the password every time.
## 6. Optimizing Remote Running
- There are several ways you can speed up the process of editting, copying, and running files in the remote server.

- One method is to write commands in quotes when running the `ssh` command to run it directly.

- Another method is using semicolon ( ; ) to run multiple commands in one line.

- A common and quick way to rewrite the previous code is using the up-arrow (↑) on the keyboard

[![optimizing remote running](https://i.postimg.cc/7YmNzGJ4/Screen-Shot-2022-04-10-at-8-53-02-PM.png)](https://postimg.cc/4mHtk312)
What I did to optimize remote running in the image above was: editting the local file, copying the file using `$ scp <file> <destination>`, and combining the commands `javac WhereAmI.java; java WhereAmI` to compile and run the program in the remote server in one line.

## Summary
Those are the 6 steps of accessing computers remotely. And here is a brief review of what we did:

1. Install VSCode
2. Connect remotely into the `ieng6` server using `ssh` command
3. Run some of the Linux commands
4. Copy and transfer files using `scp`
5. Set SSH keygen so you don't have to input password everytime logging in
6. Optimize remote running using quotations (" "), semicolon ( ; ), and the up-arrow (↑)

I hope you had fun with remote access. Thank you for reading!