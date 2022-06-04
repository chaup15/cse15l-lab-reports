# Lab Report 5 - Week 10

Hello viewer!

This will be the final lab report of the quarter. The report is about comparing two implementations of `markdown-parser` on tests that produce two different results.

To do this, I used `vimdiff` to compare the `results.txt` in my directory and in the provided directory.

## 1. [Test-file 494](https://github.com/nidhidhamnani/markdown-parser/blob/main/test-files/494.md)

My output: 
[![Screen-Shot-2022-06-04-at-12-47-43-PM.png](https://i.postimg.cc/JzCnNZFX/Screen-Shot-2022-06-04-at-12-47-43-PM.png)](https://postimg.cc/JGKMmDM7) 

Provided output:
[![Screen-Shot-2022-06-04-at-12-47-51-PM.png](https://i.postimg.cc/SQXCVLg1/Screen-Shot-2022-06-04-at-12-47-51-PM.png)](https://postimg.cc/t7js46QF)

VSCode Preview:
[![Screen-Shot-2022-06-04-at-1-07-32-PM.png](https://i.postimg.cc/BvKk3Ppq/Screen-Shot-2022-06-04-at-1-07-32-PM.png)](https://postimg.cc/f3MBjL1F)

As seen in the preview, expected output is `[\(foo\)]` so the provided implementation produced the correct output. My implementation fails to look for the last parentheses when there are multiple `)`.

[![Screen-Shot-2022-06-04-at-1-16-09-PM.png](https://i.postimg.cc/pdVMtJrK/Screen-Shot-2022-06-04-at-1-16-09-PM.png)](https://postimg.cc/LJWbtfzs)

Before taking the `link` between the pair of `()`, I need to add a loop to find the last `)` in case there are multiple `()`, rather than assuming there is only one `()`. This ensures that I include every characters before the outermost `)`.

## 2. [Test-file 497](https://github.com/nidhidhamnani/markdown-parser/blob/main/test-files/497.md)

My output:
[![Screen-Shot-2022-06-04-at-1-23-36-PM.png](https://i.postimg.cc/CKZ5g0zG/Screen-Shot-2022-06-04-at-1-23-36-PM.png)](https://postimg.cc/McSq7h0H)

Provided output:
[![Screen-Shot-2022-06-04-at-1-23-53-PM.png](https://i.postimg.cc/PfMt0JSG/Screen-Shot-2022-06-04-at-1-23-53-PM.png)](https://postimg.cc/MXv2Q6kt)

VSCode Preview:
[![Screen-Shot-2022-06-04-at-1-22-50-PM.png](https://i.postimg.cc/900G3K5s/Screen-Shot-2022-06-04-at-1-22-50-PM.png)](https://postimg.cc/YLc4YXSx)

Both implementations produced the incorrect outputs. However, my implementation produced an output with a link and the provided implementation's output has no link.

[![Screen-Shot-2022-06-04-at-2-31-20-PM.png](https://i.postimg.cc/2SGSswrf/Screen-Shot-2022-06-04-at-2-31-20-PM.png)](https://postimg.cc/VJSwMXJ7)

[![Screen-Shot-2022-06-04-at-2-26-24-PM.png](https://i.postimg.cc/13fGXft2/Screen-Shot-2022-06-04-at-2-26-24-PM.png)](https://postimg.cc/FYXdnF0V)

I think the bug causes `closeParen == -1` for this test file in the provided implementation. There are 3 `(` and 2 `)` so the program could not find the 3rd `)` that corresponds with last `(`. Even though `openParenCount > 0`, `closeParen` now equals `markdown.length()` so the program exits the `while` loop. Since `openParenCount != 0`, the method returns `-1`, causing the program to return `toReturn` with no link. One way to debug this is to add conditions to handle `\` that interferes with not only the pairs of `()` but also the `[]`.