---
authors:
- rzuckerm
date: 2024-01-22
featured-image: josephus-problem-in-every-language.jpg
last-modified: 2024-01-22
layout: default
tags:
- beef
- josephus-problem
title: Josephus Problem in Beef
---

<!--
AUTO-GENERATED -- PLEASE DO NOT EDIT!

Instead, please edit the following:

- sources/programs/josephus-problem/beef/how-to-implement-the-solution.md
- sources/programs/josephus-problem/beef/how-to-run-the-solution.md

See .github/CONTRIBUTING.md for further details.
-->

Welcome to the [Josephus Problem](https://sampleprograms.io/projects/josephus-problem) in [Beef](https://sampleprograms.io/languages/beef) page! Here, you'll find the source code for this program as well as a description of how the program works.

## Current Solution

{% raw %}

```beef
using System;

namespace JosephusProblem;

class Program
{
    public static void Usage()
    {
        Console.WriteLine("Usage: please input the total number of people and number of people to skip.");
        Environment.Exit(0);
    }

    public static Result<T> ParseInt<T>(StringView str)
    where T : IParseable<T>
    {
        StringView trimmedStr = scope String(str);
        trimmedStr.Trim();

        // T.Parse ignores single quotes since they are treat as digit separators -- e.g. 1'000
        if (trimmedStr.Contains('\''))
        {
            return .Err;
        }

        return T.Parse(trimmedStr);
    }

    // Reference: https://en.wikipedia.org/wiki/Josephus_problem#The_general_case
    //
    // Use zero-based index algorithm:
    //
    //    g(1, k) = 0
    //    g(m, k) = [g(m - 1, k) + k] MOD m, for m = 2, 3, ..., n
    //
    // Final answer is g(n, k) + 1 to get back to one-based index
    public static T JosephusProblem<T>(T n, T k)
    where T : IInteger, operator explicit int, operator T + T, operator T % T
    where int : operator T <=> T, operator explicit T
    {
        T g = (T)0;
        for (T m = (T)2; m <= n; m += (T)1)
        {
            g = (g + k) % m;
        }

        return g + (T)1;
    }

    public static int Main(String[] args)
    {
        if (args.Count < 2)
        {
            Usage();
        }

        int32 n = 0;
        switch (ParseInt<int32>(args[0]))
        {
            case .Ok(out n):
            case .Err:
                Usage();
        }

        int32 k = 0;
        switch (ParseInt<int32>(args[1]))
        {
            case .Ok(out k):
            case .Err:
                Usage();
        }

        int32 result = JosephusProblem<int32>(n, k);
        Console.WriteLine(result);
        return 0;
    }
}

```

{% endraw %}

Josephus Problem in [Beef](https://sampleprograms.io/languages/beef) was written by:

- rzuckerm

If you see anything you'd like to change or update, [please consider contributing](https://github.com/TheRenegadeCoder/sample-programs).

## How to Implement the Solution

No 'How to Implement the Solution' section available. [Please consider contributing](https://github.com/TheRenegadeCoder/sample-programs-website).

## How to Run the Solution

No 'How to Run the Solution' section available. [Please consider contributing](https://github.com/TheRenegadeCoder/sample-programs-website).