---
authors:
- rzuckerm
date: 2025-01-14
featured-image: baklava-in-every-language.jpg
last-modified: 2025-01-14
layout: default
tags:
- baklava
- c-star
title: Baklava in C*
---

<!--
AUTO-GENERATED -- PLEASE DO NOT EDIT!

Instead, please edit the following:

- sources/programs/baklava/c-star/how-to-implement-the-solution.md
- sources/programs/baklava/c-star/how-to-run-the-solution.md

See .github/CONTRIBUTING.md for further details.
-->

Welcome to the [Baklava](https://sampleprograms.io/projects/baklava) in [C\*](https://sampleprograms.io/languages/c-star) page! Here, you'll find the source code for this program as well as a description of how the program works.

## Current Solution

{% raw %}

```c\*
void main()
{
    for (int n in -10..11) {
        int num_spaces = abs(n);
        int num_stars = 21 - 2 * num_spaces;
        println(" ".repeat(num_spaces) + string("*".repeat(num_stars)));
    }
}

```

{% endraw %}

Baklava in [C\*](https://sampleprograms.io/languages/c-star) was written by:

- rzuckerm

If you see anything you'd like to change or update, [please consider contributing](https://github.com/TheRenegadeCoder/sample-programs).

## How to Implement the Solution

No 'How to Implement the Solution' section available. [Please consider contributing](https://github.com/TheRenegadeCoder/sample-programs-website).

## How to Run the Solution

No 'How to Run the Solution' section available. [Please consider contributing](https://github.com/TheRenegadeCoder/sample-programs-website).