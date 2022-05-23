# Lab Report 4 - Week 8

Hello viewer!

This is week 8 and the report is about testing implementations.

[My Repository](https://github.com/chaup15/markdown-parser)

[Week 7 Reviewed Repository](https://github.com/calistajlee/lab6-markdown-parser)

## VScode Preview of Test Links
- Snippet 1
[![Screen-Shot-2022-05-22-at-1-04-23-AM.png](https://i.postimg.cc/FHzNVs0w/Screen-Shot-2022-05-22-at-1-04-23-AM.png)](https://postimg.cc/Cz33F0P4)

- Snippet 2
[![Screen-Shot-2022-05-22-at-1-04-28-AM.png](https://i.postimg.cc/DyDYR2t9/Screen-Shot-2022-05-22-at-1-04-28-AM.png)](https://postimg.cc/0bYfwq5n)

- Snippet 3
[![Screen-Shot-2022-05-22-at-1-04-46-AM.png](https://i.postimg.cc/D00BYD5f/Screen-Shot-2022-05-22-at-1-04-46-AM.png)](https://postimg.cc/bSXxZmK4)


## My Implementation
[![Screen-Shot-2022-05-22-at-1-08-05-AM.png](https://i.postimg.cc/qvvycnb0/Screen-Shot-2022-05-22-at-1-08-05-AM.png)](https://postimg.cc/kBL2qVPh)
- I can't think of a small code change that will make the program works for all cases that use inline code with backticks. 
- One way I can edit the program is to add several if conditions for the location of the backticks. If the backtick is before the first `[`, then the string will be ignored by adding `continue`. If the backticks are in between the `[]`, then the link will be valid. If one backtick is after the first `[` and the other after the last `]`, the the link will be ignored. I will also have to update the index of `]` if there are multiple in order to find the last `]`.

[![Screen-Shot-2022-05-22-at-1-08-27-AM.png](https://i.postimg.cc/yx7k142B/Screen-Shot-2022-05-22-at-1-08-27-AM.png)](https://postimg.cc/LY0HD7H0)
- There will be a longer code change to make the program works for all cases with nest parentheses, brackets, and escaped brackets.
- I can add a method to look for last `)` and take the substring inside that pair of `()`. This will need more than 10 lines of code change because I will have to add codes to check for the pairs of `()` and check if the link is valid. I also need to make changes that consider nested links but ignore the link outside of the `[]`.

[![Screen-Shot-2022-05-22-at-1-09-01-AM.png](https://i.postimg.cc/NMc0DvsT/Screen-Shot-2022-05-22-at-1-09-01-AM.png)](https://postimg.cc/d75vQXTt)
- A small code change will make the program works for all cases with newlines in brackets and parentheses. 
- I can use the method `String.trim()` on the `link` before adding it to the `ArrayList<String> toReturn`. 

## Lab 7 Reviewed Implementation

[![Screen-Shot-2022-05-22-at-11-29-57-AM.png](https://i.postimg.cc/mgpxTMH4/Screen-Shot-2022-05-22-at-11-29-57-AM.png)](https://postimg.cc/TKbN9K0N)
- There will be a longer code change to test snippet 1. Same as to my implementation, I would add several if conditions for the location of the backticks. If the backtick is before the first `[`, then the string will be ignored by adding `continue`. If the backticks are in between the `[]`, then the link will be valid. If one backtick is after the first `[` and the other after the last `]`, the the link will be ignored. I will also have to update the index of `]` if there are multiple in order to find the last `]`. 

[![Screen-Shot-2022-05-22-at-11-31-56-AM.png](https://i.postimg.cc/1t6b0jYR/Screen-Shot-2022-05-22-at-11-31-56-AM.png)](https://postimg.cc/vgYPb3sC)
- There will be a longer code change to test snippet 2. Similar to my implementation, I will add a method to look for last `)` in order to get the entire link. However, more changes is needed to consider the link inside pair of `()` after the nested `[]`.

[![Screen-Shot-2022-05-22-at-11-32-29-AM.png](https://i.postimg.cc/L52Qt61v/Screen-Shot-2022-05-22-at-11-32-29-AM.png)](https://postimg.cc/G8gjrRzs)
- There will be a longer code change to test snippet 3. I can use the method `String.trim()` on the `link` before adding it to the `ArrayList<String> toReturn`. The program will also have to look for pairs of `()` in each line of the string to make sure the link is formatted correctly. Meaning the program needs to look for corresponding `(` and `)`.