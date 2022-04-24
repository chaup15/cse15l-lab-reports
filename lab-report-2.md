# Lab Report 2 - Week 4
Welcome back viewers!

This week's lab report is about incremental development and debugging. The main task is to print out the URLs of the links from a markdown file. 

## Link 1: 
---
- [Test file](https://github.com/chaup15/markdown-parser/commit/b2c7dc312741df0125bf1ac93cb02fb95577c18a)
[![Link-1-Error.png](https://i.postimg.cc/28KLSfSj/Link-1-Error.png)](https://postimg.cc/dLGV5pCg)
- The original code works for correctly formatted inputs, which has `[]` and `()`. However, the failure-inducing input has another pair of `[]` and `()` inside the 1st `[]`. The bug produces a symptom that causes the program to crash because it could not find the second `[` even when `currentIndex` is less than `markdown.length()`. Failure to do so prevents the program from finding the rest of the elements. The inability to find the last `()` prevents the loop from returning the `ArrayList<String> toReturn`.
[![Screen-Shot-2022-04-24-at-11-09-43-AM.png](https://i.postimg.cc/Ss4V8b16/Screen-Shot-2022-04-24-at-11-09-43-AM.png)](https://postimg.cc/NyN1qScF)
> The solution to the error is creating a value for the index of the second `[` in line 19 called `openBracket2`. I added the `if` condition to update the `closeBracket` index if `openBracket2` exists and is located before `closeBracket`. The `while` loop will proceed to search for the link inside the `openParen` and `closeParen` and produce the correct output.  

## Link 2:
---
- [Test 2 file](https://github.com/chaup15/markdown-parser/commit/38f2a1d5836049e7b554ba890aaca405b894a49e)
[![Link-2-Error.png](https://i.postimg.cc/8c5RBpR6/Link-2-Error.png)](https://postimg.cc/G8WTb1SL)
- This failure-inducing input is similar to the previous input where the link is inside the `[]`. This bug causes the error output symptom in the program and produce the same error as the 1st link for the output. There is a different bug in the original code where the program did not take into consideration the case where the `(` and `)` don't exist. However, the program crashed before it reaches the second bug.
[![Error-Fixed.png](https://i.postimg.cc/mkBmP96T/Error-Fixed.png)](https://postimg.cc/xJpv7X2Z)
> TO solve the issue, the same changes from debugging Link 1 are kept. In addition, I added `if` conditions for the `while` loop to `break` when the `openParen` and `closeParen` don't exist. 

## Link 3:
---
[Test 3 file](https://github.com/chaup15/markdown-parser/commit/0d11265e9fc7fede05203b4d57abe21adf7b2d9d)
[![Link-3-Error.png](https://i.postimg.cc/SNtqmkDt/Link-3-Error.png)](https://postimg.cc/bsb4TcXQ)
- The failure-inducing input is similar to Link 2 in a way that there are no `()`. The original code does not handle the link that has no `()` because it is adding the elements inside the `()` to the `ArrayList<String> toReturn`. This bug causes an `IndexOutOfBoundsException` because the index value of `()` are both `-1`.  
[![Error-Fixed.png](https://i.postimg.cc/mkBmP96T/Error-Fixed.png)](https://postimg.cc/xJpv7X2Z)
> Hence the change is the same as the change made in Link 2. The additional `if` statements `break` the `while` loop when the `[]` and `()` don't exist. 