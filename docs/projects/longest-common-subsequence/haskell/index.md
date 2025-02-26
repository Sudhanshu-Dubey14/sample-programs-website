---
authors:
- Parker Johansen
date: 2018-10-20
featured-image: longest-common-subsequence-in-every-language.jpg
last-modified: 2019-03-26
layout: default
tags:
- haskell
- longest-common-subsequence
title: Longest Common Subsequence in Haskell
---

<!--
AUTO-GENERATED -- PLEASE DO NOT EDIT!

Instead, please edit the following:

- sources/programs/longest-common-subsequence/haskell/how-to-implement-the-solution.md
- sources/programs/longest-common-subsequence/haskell/how-to-run-the-solution.md

See .github/CONTRIBUTING.md for further details.
-->

Welcome to the [Longest Common Subsequence](https://sampleprograms.io/projects/longest-common-subsequence) in [Haskell](https://sampleprograms.io/languages/haskell) page! Here, you'll find the source code for this program as well as a description of how the program works.

## Current Solution

{% raw %}

```haskell
module Main where

import System.Environment
import System.Exit (exitWith, ExitCode(ExitFailure))
import Data.List (intercalate)

-- Recursively find longest common subsequence
lcs :: Eq a => [a] -> [a] -> [a]
lcs [] bs = []
lcs as [] = []
lcs (a:as) (b:bs)
  | a == b    = (lcs as bs) ++ [a]
  | otherwise = longest (lcs (a:as) bs) (lcs as (b:bs))


-- Returns the longer of two lists
longest :: Foldable t => t a -> t a -> t a
longest l1 l2
  | length l1 > length l2 = l1
  | otherwise             = l2


-- Converts string in format "1, 2, 3" to a list of integers
stringToList :: String -> [Int]
stringToList str = read $ "[" ++ str ++ "]" :: [Int]


listToString :: [Int] -> String
listToString = intercalate ", " . map show


main :: IO ()
main = do
  args <- getArgs
  let l1 = stringToList $ head args :: [Int]
  let l2 = stringToList $ head $ tail args :: [Int]
  if length args /= 2 then do
    putStrLn "Usage: please provide two lists in the format \"1, 2, 3, 4, 5\""
    exitWith $ ExitFailure 1
  else
    putStrLn $ listToString $ reverse $ lcs l1 l2

```

{% endraw %}

Longest Common Subsequence in [Haskell](https://sampleprograms.io/languages/haskell) was written by:

- Parker Johansen

If you see anything you'd like to change or update, [please consider contributing](https://github.com/TheRenegadeCoder/sample-programs).

## How to Implement the Solution

No 'How to Implement the Solution' section available. [Please consider contributing](https://github.com/TheRenegadeCoder/sample-programs-website).

## How to Run the Solution

No 'How to Run the Solution' section available. [Please consider contributing](https://github.com/TheRenegadeCoder/sample-programs-website).