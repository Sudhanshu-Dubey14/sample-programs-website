---
authors:
- rzuckerm
date: 2023-02-19
featured-image: prime-number-in-every-language.jpg
last-modified: 2023-02-19
layout: default
tags:
- euphoria
- prime-number
title: Prime Number in Euphoria
---

<!--
AUTO-GENERATED -- PLEASE DO NOT EDIT!

Instead, please edit the following:

- sources/programs/prime-number/euphoria/how-to-implement-the-solution.md
- sources/programs/prime-number/euphoria/how-to-run-the-solution.md

See .github/CONTRIBUTING.md for further details.
-->

Welcome to the [Prime Number](https://sampleprograms.io/projects/prime-number) in [Euphoria](https://sampleprograms.io/languages/euphoria) page! Here, you'll find the source code for this program as well as a description of how the program works.

## Current Solution

{% raw %}

```euphoria
include std/io.e
include std/types.e
include std/text.e
include std/get.e as stdget
include std/math.e
include std/utils.e

-- Indices for value() return value
enum VALUE_ERROR_CODE, VALUE_VALUE, VALUE_NUM_CHARS_READ

-- Indices for parse_int() return value
enum PARSE_INT_VALID, PARSE_INT_VALUE

function parse_int(sequence s)
    -- Trim off whitespace and parse string
    s = trim(s)
    sequence result = stdget:value(s,, GET_LONG_ANSWER)

    -- Error if any errors, value is not an integer, or any leftover characters
    boolean valid = (
        result[VALUE_ERROR_CODE] = GET_SUCCESS
        and integer(result[VALUE_VALUE])
        and result[VALUE_NUM_CHARS_READ] = length(s)
    )

    -- Get value if invalid
    integer value = 0
    if valid
    then
        value = result[VALUE_VALUE]
    end if

    return {valid, value}
end function

procedure usage()
    puts(STDOUT, "Usage: please input a non-negative integer\n")
    abort(0)
end procedure

function is_prime(integer value)
    -- If less than 2 or (not 2 and even), composite
    -- Else, check if prime by checking divisibility by odd numbers from 3 to sqrt(value)
    if value < 2 or (value != 2 and is_even(value))
    then
        return FALSE
    end if

    integer q = floor(sqrt(value))
    for n = 3 to q by 2
    do
        if mod(value, n) = 0
        then
            return FALSE
        end if
    end for

    return TRUE
end function

-- Check 1st command-line argument
sequence argv = command_line()
if length(argv) < 4 or length(argv[4]) = 0
then
    usage()
end if

-- Parse 1st command-line argument
sequence result = parse_int(argv[4])
integer value = result[PARSE_INT_VALUE]
if not result[PARSE_INT_VALID] or value < 0
then
    usage()
end if

-- Indicate whether prime or composite
puts(STDOUT, iif(is_prime(value), "Prime\n", "Composite\n"))

```

{% endraw %}

Prime Number in [Euphoria](https://sampleprograms.io/languages/euphoria) was written by:

- rzuckerm

If you see anything you'd like to change or update, [please consider contributing](https://github.com/TheRenegadeCoder/sample-programs).

## How to Implement the Solution

No 'How to Implement the Solution' section available. [Please consider contributing](https://github.com/TheRenegadeCoder/sample-programs-website).

## How to Run the Solution

No 'How to Run the Solution' section available. [Please consider contributing](https://github.com/TheRenegadeCoder/sample-programs-website).