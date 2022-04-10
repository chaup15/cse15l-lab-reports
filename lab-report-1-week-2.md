# Lab Report 1 - Week 2

Hello viewers!

Today's main topic will be about how to **access machines or computers remotely**; specifically connecting to computers in the UCSD basement lab by logging into the course-specific account `ieng6` remotely using our own device. Cool idea right?!

So now, I will be demonstrating *6 steps* to complete this magical process:

1. Installing Visual Studio Code
- Visit the [Visual Studio Code](https://code.visualstudio.com/) website to download and install VSCode onto the computer. 
- Once installed and opened, the home page of VSCode should look something like the image below:
[![vscode.png](https://i.postimg.cc/90sfzVt7/vscode.png)](https://postimg.cc/QKkDn2z8)
- In VSCode, open a terminal by going to tab `Terminal` on the top bar and click on `New Terminal`.
[![vscodeterminal.png](https://i.postimg.cc/NFXK6504/vscodeterminal.png)](https://postimg.cc/MfWZxZVM)

2. Remotely Connecting
- In the terminal, type in `$ ssh cs15lsp22zz@ieng6.ucsd.edu` (where `zz` is replaced your assigned username)
- A series of messages will pop up when logging into the account for the first time along with the question:
> `Are you sure you want to continue connecting (yes/no/[fingerprint])?`
>> Don't be scared; just type `yes` and enter. Everything will be okay. I promise. Otherwise, ask Professor Gerald or tutors for help.
- Finally, enter your passcode. If you are greeted by the system like this:
[![ieng6](https://i.postimg.cc/660Ykq6S/Screen-Shot-2022-04-10-at-7-16-55-AM.png)](https://postimg.cc/G94FYcyJ)
**CONGRATULATION!!** You have successfully connected to the server remotely. So now, let's try out some commands.
3. Running Some Commands
- 
4. Moving files with `scp`
5. Setting an SSH key
6. Optimizing Remote Running
