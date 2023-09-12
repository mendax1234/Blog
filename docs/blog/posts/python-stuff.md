---
date: 2023-09-09
authors: [Daniel Wenbo]
title: Tricky Python stuff
description: >
  This post includes some "tricky" but interesting stuff in python
categories:
  - NTU SCSE Resources
comments: true
links:
---

# Tricky Python stuff
Hey, are you still confused about some interesting functions and methods in Python. Don't worry, after reading this post, maybe you will gain a quick command of these interesting but "tricky" functions and methods in Python. 

<!-- more -->

!!! warning "Important"
    **methods** and **functions** are not the same thing. A **function** is a *piece of code* that performs some operations. i.e. `len()`. Unlike a **function**, a **method** is applied in the context of a particular object. This is indicated by the *dot notation* invocation. i.e. `myList.append()`. 

**Task list for this post:**

- [ ] Add Introduction part
- [ ] Add tuple part
- [ ] Add list part
    * [ ]  Add slice part 
- [x] The difference between Method and Function
- [ ] Add List Functions part
- [ ] Add List Methods part
- [ ] Add String Functions part
- [ ] Add String Methods part
- [ ] Argument and Parameter

## Introduction

> Add something here after finishing the writing of the whole post.

!!! note
    This post is just a study product during my Python learning, so it may not contain all the aspects of interesting Python functions. Also, this post can be used as a reference to SC1003 **Introduction to Computaional Thinking** in NTU SCSE. BTW, if you find something incorrect in this post, please let me know by either [opening a commit]() or [making a pull request]() if you can fix it. Thank you very much!

!!! warning "Important"
    Since I may not have enough time to do all the introduction work of some basic concepts in Python, I will only cover the functions related to a specific topic. If you need some help on basic concepts in Python, try google or something equivalent first, I believe that there are some very useful resources on the Internet. If you are still at a loss, you can also comment at the bottom of this blog. I will help you as soon as possible. Thanks.

## Boolean Operands

1. In Python, you can use either `&` or `and` to implement the **and** operation. Similarly, you can use either `or` or `|` to represent the **or** operation.

## String

### String Methods

#### Upper and Lower Letters

In Python, we will use `myString.upper()` and `myString.lower()` to convert the string to upper or lower letters.

=== "Python"

    ``` py
    myString = "hello world"
    myString.upper() # "HELLO WORLD"
    myString.lower() # "hello world"
    ```

#### Check Upper, Lower and Digit Letters

Python has provided us with some very useful functions, they are `string.isUpper()`, `string.isLower()`, `string.isDigit()`. These functions can help us quickly check whether there is a Upper or lower letter or a digit in the string.

Below is the Demo:

=== "Python"

    ``` py
    # Initialize the flag
    Upper = False
    Lower = False
    Digit = False

    # Use for loop to traverse each letter in the string
    for x in anyString:
        if x.isupper():
            Upper = True
        if x.islower():
            Lower = True
        if x.isdigit():
            Digit = True

    # Check if there is a upper letter, lower letter or digit in this string
    if Upper:
	print("There is at least one Upper letter in this string")
    if Lower:
	print("There is at least one Lower letter in this string")
    if Digit:
	print("There is at least one Digit in this string")
    ```

#### Check Special Letters

!!! note
    This is a tricky question since the definition of **special letter** here is not clearly defined. Maybe it means the special letters on your keyboard, or it may be some other special letters which are not on your keyboard. That's really tricky. But I will still provide two methods to try to solve this question.

1. Use a dictionary to store all the special letters. Then you can easily use `in` keyword to check if there is a special letter in the string.

2. Try using the ASCII table. Firstly, you should convert the letter to ASCII and then see if it is in the correct range of special letters in the ASCII table.

#### Find the first occurrence of the specified value

In Python, we use `myString.find()` method to find the first occurrence of the specified value. If the value is not found, the `find()` method returns `-1`, otherwise it returns the index of the first occurrence of the specified value.

=== "Python"

    ``` py
    myString = "hello world"
    myString.find("world") # 6
    myString.find("worlds") # -1
    ```
#### `.join()` function
In Python, we will `myString.join(target)` method to make a new string by joining all the elements in an iterable (list, tuple, string etc.) separated by `myString`. 

=== "Python"

    ``` py
    myString = "hello world"
    myString.join("123") # "1hello world2hello world3"
    ```

!!! note
    In Python, we can chain **methods** together. i.e. `myString.upper().join("123")` will return `"1HELLO WORLD2HELLO WORLD3"` if `myString = "hello world"`.

### String Functions

#### Calculate the length of a string
In Python, we use `len()` function to calculate the length of a string.

=== "Python"

    ``` py
    myString = "hello world"
    len(myString) # 11
    ```

### Other String Stuff

#### Concatenate strings

In Python, we use `+` operator to concatenate strings.

=== "Python"

    ``` py
    myString = "hello world"
    myString = myString + "123" # "hello world123"
    ```

#### Repeat Strings

In Python, we use `*` operator to repeat strings.

=== "Python"

    ``` py
    myString = "hello world"
    myString = myString * 3 # "hello worldhello worldhello world"
    ```

#### Membership Operations
In Python, we use `in` keyword to check if a string is present in another string. i.e. `if "hello" in myString:`

=== "Python"

    ``` py
    myString = "hello world"
    print(hello in myString) # True
    ```
#### String Slicing
In Python, we use `myString[start:end:step]` to slice a string.

=== "Python"

    ``` py
    myString = "hello world"
    print(myString[0:5:2]) # "hlo"
    ```

##### Extended Slicing

Copy a String using `myString[:]` or `''.join(myString)`

=== "Python"

    ``` py
    myString = "hello world"
    print(myString[:]) # "hello world"
    print(''.join(myString)) # "hello world"
    ```

Reverse a String using `myString[::-1]`

=== "Python"

    ``` py
    myString = "hello world"
    print(myString[::-1]) # "dlrow olleh"
    ```

The index of a String

<p align="center"> <img src="/blog/python-stuff/String-index.png" title = "String Index"> </p>

#### Getting the code
There are two common systems for representing characters: ASCII and Unicode. In Python, we use `ord()` function to get the code of a character. i.e. `ord("a")` will return `97`. And vice versa, we use `chr()` function to get the character of a code. i.e. `chr(97)` will return `"a"`.

<p align="center"> <img src="/blog/python-stuff/ASCII.jpg" title = "ASCII Table"> </p>

#### Escape Characters
In Python, we use `\` to escape characters.

=== "Python"

    ``` py
    myString = "hello \"world\""
    print(myString) # "hello "world""
    ```

## Dictionary, List and Tuple

First, before we talk about Dictionary, List and Tuple, we may need to know what is a **Composite Type**. A Composite Type is a *data type* which is constructed using *primitive* and *other composite types*. Also, it can be regarded as a new data type made from existing ones.

Then, we may need to know about **data structures**. **Data structure** are particular ways of storing data to make some operations easier or more efficient. Different data structures have different characteristics.

And now, you may find the **Dictionary**, **List** and **Tuple** are all data structures in Python. They are also three **Composite Types**. So, let's talk about them one by one.

!!! warning "Important"
    In this section, `myDict`, `myList` and `myTuple` will be the default name of these three types of data structures I will use in Python.

### List
Let's start from **List** because it is the most fundamental one.

**Definition**

Python list is an ordered sequence of items.

!!! note
    **String** is also an ordered sequence of items. But the difference between **String** and **List** is that **String** is immutable while **List** is mutable.

**How to create a list?**

In Python, we can either use `[]` or `list()` to create a list.

=== "Python"

    ``` py
    myList = ["hello", "world", "123"]
    myList = list("hello world 123")
    ```

#### List Methods

#### List Functions

### Dictionary

!!! note
    In this section, `myDict` will be the name of the dictionary that I will use in Python.

#### Keys and Values
Keys and values are two very important concepts in Dictionary. In Python, Dictionaries are used to store data value in key:value pairs. Each key in the Dictionary may have zero or one or multiple values.

**How to assign multiple values to one key?**

Let's say that in Python, we usually use `lists` or `tuples` to store a bunch of values. Similarly, we still can use these two data structures to store different values of a key element in the Dictionary. However, one thing you should notice is that `tuple` is immutable while `list` is mutable.

Below is the demo:

=== "Python"

    ``` py
    # List method
    myDict = {"userName":["Jack","Tom","James","Andy"]} # You can add anything to the "userName"

    # Tuple method
    myDict = {"userName":("Jack","Tom","James","Andy")} # You can't add something or delete something to "userName" since tuple is immutable
    ```
**How to add values to one key in Dictionary?**

Firstly, you need to make sure that you have used the `list` method. Secondly, all you need to do is just using the methods owned by `list` in Python. For example, if you want to add value, you need to use `myList.append()`.

=== "Python"

    ``` py
    myDict.["userName"].append(name)  
    ``` 

!!! note
    If you want to use `.append()` to add values to your key, make sure to initialize your key's value with a `list`. Otherwise, the program will crash because only `list` in Python has the `append()` method.

**Get the `keys` and `values` in the dictionary**

Python is very powerful, if you want to get the `keys` and `values` of a dictionary, you only need to use `myDict.keys()` to get the `keys` and `myDict.values()` to get the `values`.

=== "Python"

    ``` py
    myDict.keys() # Get keys
    myDict.values() # Get values
    ```

!!! note
    Please note that the `myDict.keys()` will return a value with `dict_keys`. Similarly, `myDict.values()` will return a value with `dict_values`. These two results can be treated as `lists`.

a. How to judge whether a string has appeared in your dictionary's `values`?

Don't worry. Python's `in` keyword can do this perfectly. i.e. You want to check whether "Tom" is your `values` in the dictionary. 

=== "Python"

    ``` py
    if "Tom" in myDict.values():
	# Add stuff here
    ```
!!! tip
    `in` is an important keyword in Python. It mainly has two functions. One is to check if a value is present in a sequence (list, range, string etc). The other is to iterate through a sequence in a `for` loop.

**Add new `{keys:values}` pair to Dictionary.**

Python Dictionary has provided a very useful method called `myDict.update()` to let you add new `{keys:values}` pair to your dictionary quickly and conveniently.

Below is the demo:

=== "Python"

    ``` py
    newUser = {"Tom":"123456"} # This is a User:Password pair
    myDict.update(newUser)
    ```

!!! note
    Every time you call the `update()` method, it won't erase your original `{keys:values}` in the dictionary. Instead, it will add a new one at the end of the dictionary.
