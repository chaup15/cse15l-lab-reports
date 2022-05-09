# Lab Report 3 - Week 6
## Task 1: Streamline `ssh` Configuration
---
[![Screen-Shot-2022-05-08-at-1-46-54-PM.png](https://i.postimg.cc/QCNp5rmw/Screen-Shot-2022-05-08-at-1-46-54-PM.png)](https://postimg.cc/ftFtnp6f)
- I used `vim` to open `.ssh/config` and added: 
```
Host ieng6
    HostName ieng6.ucsd.edu
    User cs15lsp22adj 
```
>Where `adj` is my assigned username and `ieng6` after `Host` is my alias. `:x` is used to save and quit the text-editor.


[![Screen-Shot-2022-05-08-at-1-47-39-PM.png](https://i.postimg.cc/ZKcnMMZY/Screen-Shot-2022-05-08-at-1-47-39-PM.png)](https://postimg.cc/0bz96Zbh)
- After setting up the username, I can use the command `ssh ieng6` to log into the `ieng6`.

[![Screen-Shot-2022-05-08-at-1-55-17-PM.png](https://i.postimg.cc/c6qRk5NB/Screen-Shot-2022-05-08-at-1-55-17-PM.png)](https://postimg.cc/30B0d1Nk)
- I used `scp` to copy the `WhereAmI.java` file to my `ieng6` account using only the alias rather than the long `cs15lsp22adj@ieng6.ucsd.edu` login detail.

[![Screen-Shot-2022-05-08-at-1-56-07-PM.png](https://i.postimg.cc/sDvfTDnm/Screen-Shot-2022-05-08-at-1-56-07-PM.png)](https://postimg.cc/fJQhLZQS)
- This screenshot shows that the command `scp` works even when I use only the short alias to transfer my file.

## Task 2: Setup Github Access from ieng6
---
[![Screen-Shot-2022-05-08-at-7-29-31-PM.png](https://i.postimg.cc/bwBttVgt/Screen-Shot-2022-05-08-at-7-29-31-PM.png)](https://postimg.cc/rD5s6JvV)
[![Screen-Shot-2022-05-08-at-12-41-44-PM.png](https://i.postimg.cc/KcHfN44w/Screen-Shot-2022-05-08-at-12-41-44-PM.png)](https://postimg.cc/qg22BJsx)
[![Screen-Shot-2022-05-08-at-7-30-16-PM.png](https://i.postimg.cc/65H7kbDm/Screen-Shot-2022-05-08-at-7-30-16-PM.png)](https://postimg.cc/1fq56BRG)
[![Screen-Shot-2022-05-08-at-7-22-17-PM.png](https://i.postimg.cc/Ss0qCmCM/Screen-Shot-2022-05-08-at-7-22-17-PM.png)](https://postimg.cc/B8CdG9hS)
[![Screen-Shot-2022-05-08-at-7-19-00-PM.png](https://i.postimg.cc/Lsj88xbR/Screen-Shot-2022-05-08-at-7-19-00-PM.png)](https://postimg.cc/HJsgS9mP)
[Commit Link](https://github.com/chaup15/markdown-parser/commit/900200e084f4cf4477d99a1961faf6ae0e8609cc)

## Task 3: Copy whole directories with `scp -r`
---
[![Screen-Shot-2022-05-08-at-7-38-40-PM.png](https://i.postimg.cc/7Zwpvmrj/Screen-Shot-2022-05-08-at-7-38-40-PM.png)](https://postimg.cc/D8pCLQZc)
[![Screen-Shot-2022-05-08-at-7-47-40-PM.png](https://i.postimg.cc/k43QZYkb/Screen-Shot-2022-05-08-at-7-47-40-PM.png)](https://postimg.cc/Y4RLLR2r)
[![Screen-Shot-2022-05-08-at-7-41-16-PM.png](https://i.postimg.cc/528NgPqG/Screen-Shot-2022-05-08-at-7-41-16-PM.png)](https://postimg.cc/RWVBVLYQ)
[![Screen-Shot-2022-05-08-at-7-52-00-PM.png](https://i.postimg.cc/HktjHZcM/Screen-Shot-2022-05-08-at-7-52-00-PM.png)](https://postimg.cc/jDLR4hhq)
[![Screen-Shot-2022-05-08-at-8-16-20-PM.png](https://i.postimg.cc/7Lyc19mK/Screen-Shot-2022-05-08-at-8-16-20-PM.png)](https://postimg.cc/XrQQ4fM5)