# Lab Report 2 - Week 4
Welcome back viewers!

This week's lab report is about incremental development and debugging. The main task is to print out the URLs of the links from a markdown file. 

## Link 1: 
---
[![Debugging-1.png](https://i.postimg.cc/cLCx3TDC/Debugging-1.png)](https://postimg.cc/PCGnsbnn)
- [Test file](https://github.com/chaup15/markdown-parser/commit/b2c7dc312741df0125bf1ac93cb02fb95577c18a)
[![Link-1-Error.png](https://i.postimg.cc/28KLSfSj/Link-1-Error.png)](https://postimg.cc/dLGV5pCg)
- The original code works for correctly formatted inputs, which has one pair of `[]` and `()` each. However, the failure-inducing input has another pair of `[]` and `()` inside the 1st `[]`. The bug produces a symptom that causes the program to crash because it could not find `[`  when the program reaches `)` and `currentIndex` is less than `markdown.length()`. This prevents the program from finding the rest of the elements and prevents the loop from returning the `ArrayList<String> toReturn`.

## Link 2:
---
[![Debugging-2.png](https://i.postimg.cc/gjBYtZjm/Debugging-2.png)](https://postimg.cc/N2mq5LRz)
- [Test 2 file](https://github.com/chaup15/markdown-parser/commit/d3f3893ebb31b90d3aff66849f2fb6e863fbe95f)
[![Link-3-Error.png](https://i.postimg.cc/SNtqmkDt/Link-3-Error.png)](https://postimg.cc/bsb4TcXQ)

- The failure-inducing input has no `()` and no link. The original code does not handle this input because the program is adding the link inside the `()` to the `ArrayList<String> toReturn`. The bug causes an `IndexOutOfBoundsException` because the index value of `()` are both `-1`. To solve the issue, an `if` condition is for the `while` loop to `break` when `openParen` doesn't exist. 

## Link 3:
---
[![Debugging-3.png](https://i.postimg.cc/Hx0xsnxC/Debugging-3.png)](https://postimg.cc/KkzF0ZB9)
[Test 3 file](https://github.com/chaup15/markdown-parser/commit/a061100b146c26d9a215277dfa5147a59dba1885)
[![3-Error.png](https://i.postimg.cc/gjwTHX6C/3-Error.png)](https://postimg.cc/ZvSHTqHH)
-The failure-inducing input has an extra `[`. The original code does not handle extra elements so the program cannot find the indices of the needed elements to produce the output. Hence, this bug causes the `OutOfMemoryError`.