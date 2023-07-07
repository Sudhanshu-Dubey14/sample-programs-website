---
authors:
- Daffa Daraz
- Jeremy Grifski
date: 2019-10-14
featured-image: prime-number-in-every-language.jpg
last-modified: 2022-10-10
layout: default
tags:
- c-plus-plus
- prime-number
title: Prime Number in C++
---

Welcome to the [Prime Number](https://sampleprograms.io/projects/prime-number) in [C++](https://sampleprograms.io/languages/c-plus-plus) page! Here, you'll find the source code for this program as well as a description of how the program works.

## Current Solution

{% raw %}

```c++
#include <iostream>
#include <stdlib.h>
#include <string.h>

using namespace std;

int main(int argc, char **argv)
{
    if (argc == 1)
    {
        cout << "Usage: please input a non-negative integer\n";
        return 1;
    }
    string tmp = argv[1];
    if (argc == 1 || argv[1][0] == '\0' || (atoi(argv[1]) == 0 && strcmp(argv[1], "0") != 0) || atoi(argv[1]) < 0 || tmp.find(".") != string::npos)
    {
        cout << "Usage: please input a non-negative integer\n";
    }
    else
    {
        int input = atoi(argv[1]);
        if (input == 0 || input == 1)
        {
            cout << "composite\n";
            return 0;
        }
        for (int i = 2; i < input; ++i)
        {
            if (input % i == 0)
            {
                cout << "composite\n";
                return 0;
            }
        }
        cout << "Prime\n";
    }

    return 0;
}

```

{% endraw %}

Prime Number in [C++](https://sampleprograms.io/languages/c-plus-plus) was written by:

- Daffa Daraz
- Jeremy Grifski

If you see anything you'd like to change or update, [please consider contributing](https://github.com/TheRenegadeCoder/sample-programs).

## How to Implement the Solution

No 'How to Implement the Solution' section available. [Please consider contributing](https://github.com/TheRenegadeCoder/sample-programs-website).

## How to Run the Solution

No 'How to Run the Solution' section available. [Please consider contributing](https://github.com/TheRenegadeCoder/sample-programs-website).