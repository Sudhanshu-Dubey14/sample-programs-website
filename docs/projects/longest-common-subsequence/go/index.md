---
authors:
- Parker Johansen
date: 2019-03-17
featured-image: longest-common-subsequence-in-every-language.jpg
last-modified: 2019-03-25
layout: default
tags:
- go
- longest-common-subsequence
title: Longest Common Subsequence in Go
---

<!--
AUTO-GENERATED -- PLEASE DO NOT EDIT!

Instead, please edit the following:

- sources/programs/longest-common-subsequence/go/how-to-implement-the-solution.md
- sources/programs/longest-common-subsequence/go/how-to-run-the-solution.md

See .github/CONTRIBUTING.md for further details.
-->

Welcome to the [Longest Common Subsequence](https://sampleprograms.io/projects/longest-common-subsequence) in [Go](https://sampleprograms.io/languages/go) page! Here, you'll find the source code for this program as well as a description of how the program works.

## Current Solution

{% raw %}

```go
package main

import (
	"encoding/json"
	"fmt"
	"os"
	"regexp"
	"strconv"
	"strings"
)

func lcs(list1 []int, list2 []int) (lcsList []int) {
	if len(list1) <= 0 || len(list2) <= 0 {
		return
	}
	if list1[0] == list2[0] {
		return append(lcs(list1[1:], list2[1:]), list1[0])
	}
	return longest(lcs(list1, list2[1:]), lcs(list1[1:], list2))
}

func longest(list1 []int, list2 []int) []int {
	if len(list1) > len(list2) {
		return list1
	}
	return list2
}

func reverse(list []int) (reversed []int) {
	for i := len(list) - 1; i >= 0; i-- {
		reversed = append(reversed, list[i])
	}
	return
}
func strToSliceInt(strList string) []int {
	list := regexp.MustCompile(", ?").Split(strList, -1)
	if len(list) < 2 {
		exitWithError()
	}
	var nums []int
	for _, num := range list {
		n, err := strconv.Atoi(num)
		if err != nil {
			exitWithError()
		}
		nums = append(nums, n)
	}
	return nums
}

func exitWithError() {
	fmt.Println("Usage: please provide two lists in the format \"1, 2, 3, 4, 5\"")
	os.Exit(1)
}

func sliceIntToString(list []int) (out string) {
	bytes, _ := json.Marshal(list)
	out = strings.Replace(string(bytes), ",", ", ", -1)
	out = strings.Trim(out, "[]")
	return
}

func main() {
	if len(os.Args) != 3 {
		exitWithError()
	}

	list1 := strToSliceInt(os.Args[1])
	list2 := strToSliceInt(os.Args[2])
	fmt.Println(sliceIntToString(reverse(lcs(list1, list2))))
}

```

{% endraw %}

Longest Common Subsequence in [Go](https://sampleprograms.io/languages/go) was written by:

- Parker Johansen

If you see anything you'd like to change or update, [please consider contributing](https://github.com/TheRenegadeCoder/sample-programs).

## How to Implement the Solution

No 'How to Implement the Solution' section available. [Please consider contributing](https://github.com/TheRenegadeCoder/sample-programs-website).

## How to Run the Solution

No 'How to Run the Solution' section available. [Please consider contributing](https://github.com/TheRenegadeCoder/sample-programs-website).