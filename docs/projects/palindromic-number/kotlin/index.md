---

title: Palindromic Numbers in Kotlin
layout: default
last-modified: 2020-10-07
featured-image:
tags: [palindrome]
authors:
  - anohene1

---

Welcome to the [Palindromic Number](https://sampleprograms.io/projects/palindromic-number) in [Kotlin](https://sampleprograms.io/languages/kotlin) page! Here, you'll find the source code for this program as well as a description of how the program works.

## Current Solution

{% raw %}

```kotlin
fun main(args: Array<String>) {
    var n: Int
    var num: Int
    var digit: Int
    var rev: Int = 0

    try {
        num = args[0].toInt()

        if (num >= 0){
            n = num

            do {
                digit = num % 10
                rev = (rev * 10) + digit
                num = num / 10
            }while (num != 0)

            if (n == rev){
                println(true)
            }else{
                println(false)
            }
        }else{
            println("Usage: please input a non-negative integer")
        }


    }catch(e: Exception){
        println("Usage: please input a non-negative integer")
    }
}
```

{% endraw %}

[Palindromic Number](https://sampleprograms.io/projects/palindromic-number) in [Kotlin](https://sampleprograms.io/languages/kotlin) was written by:

- Blake.Ke
- Isaac Anohene
- Jeremy Grifski

If you see anything you'd like to change or update, [please consider contributing](https://github.com/TheRenegadeCoder/sample-programs).

**Note**: The solution shown above is the current solution in the Sample Programs repository as of Oct 11 2022 01:31:51. The solution was first committed on Oct 08 2020 16:44:11. As a result, documentation below may be outdated.

## How to Implement the Solution

code for palindrome.kt:
```kotlin
    fun main() {
    var n: Int
    var num: Int
    var digit: Int
    var rev: Int = 0

    print("Enter a positive number: ")
    num = readLine()!!.toInt()

    n = num

    do {
        digit = num % 10
        rev = (rev * 10) + digit
        num = num / 10
    }while (num != 0)

    if (n == rev){
        println(true)
    }else{
        println(false)
    }
}

```


## How to Run the Solution

To run the solution to check if a number is a palindrome or not, we first create some variables we will use in the algorithm in the main function as shown here:
```kotlin
    var n: Int
    var num: Int
    var digit: Int
    var rev: Int = 0
 ```
 Then we will prompt the user to input the number that needs to be checked:
 ```kotlin
    print("Enter a positive number: ")
    num = readLine()!!.toInt()
 ```
 Then we use a do while loop to reverse the number that was typed in:
 ```kotlin
    do {
        digit = num % 10
        rev = (rev * 10) + digit
        num = num / 10
    }while (num != 0)
```
Finally, we check if the number and its reverse are the same or not. If they are the same, we tell the user that it's true, otherwise we tell the user that it's false, as shown here:
```kotlin
    if (n == rev){
        println(true)
    }else{
        println(false)
    }
```
