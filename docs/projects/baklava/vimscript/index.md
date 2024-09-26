---
authors:
- rzuckerm
date: 2024-09-26
featured-image: baklava-in-every-language.jpg
last-modified: 2024-09-26
layout: default
tags:
- baklava
- vimscript
title: Baklava in Vimscript
---

Welcome to the [Baklava](https://sampleprograms.io/projects/baklava) in [Vimscript](https://sampleprograms.io/languages/vimscript) page! Here, you'll find the source code for this program as well as a description of how the program works.

## Current Solution

{% raw %}

```vimscript
func! Baklava()
    for l:i in range(-10, 10)
        let l:numSpaces = abs(l:i)
        echo repeat(' ', l:numSpaces) . repeat('*', 21 - 2 * l:numSpaces)
    endfor
endfunc

func! Main()
    call Baklava()
endfunc

```

{% endraw %}

Baklava in [Vimscript](https://sampleprograms.io/languages/vimscript) was written by:

- rzuckerm

If you see anything you'd like to change or update, [please consider contributing](https://github.com/TheRenegadeCoder/sample-programs).

## How to Implement the Solution

No 'How to Implement the Solution' section available. [Please consider contributing](https://github.com/TheRenegadeCoder/sample-programs-website).

## How to Run the Solution

No 'How to Run the Solution' section available. [Please consider contributing](https://github.com/TheRenegadeCoder/sample-programs-website).