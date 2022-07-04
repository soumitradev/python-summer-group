---
description: >-
  Edited excerpt from the book "Automate the boring stuff with Python" by Al
  Sweigart
---

# Number Types

Remember that expressions are just values combined with operators, and they always evaluate down to a single value. A _data type_ is a category for values, and every value belongs to exactly one data type. The most common data types in Python are listed in Table 1-2. The values -2 and 30, for example, are said to be _integer_ values. The integer (or _int_) data type indicates values that are whole numbers. Numbers with a decimal point, such as 3.14, are called _floating-point numbers_ (or _floats_). Note that even though the value 42 is an integer, the value 42.0 would be a floating-point number.

**Table 1-2:** Common Data Types

| **Data type**          | **Examples**                           |
| ---------------------- | -------------------------------------- |
| Integers               | -2, -1, 0, 1, 2, 3, 4, 5               |
| Floating-point numbers | -1.25, -1.0, -0.5, 0.0, 0.5, 1.0, 1.25 |
| Strings                | 'a', 'aa', 'aaa', 'Hello!', '11 cats'  |

Python programs can also have text values called _strings_, or _strs_ (pronounced “stirs”). Always surround your string in single quote (') characters (as in 'Hello' or 'Goodbye cruel world!') so Python knows where the string begins and ends. You can even have a string with no characters in it, '', called a _blank string_ or an _empty string_. Strings are explained in greater detail in [Chapter 4](https://automatetheboringstuff.com/2e/chapter1/#calibre\_link-152).

If you ever see the error message SyntaxError: EOL while scanning string literal, you probably forgot the final single quote character at the end of the string, such as in this example:

```
>>> 'Hello, world!
SyntaxError: EOL while scanning string literal
```

#### **String Concatenation and Replication** <a href="#calibre_link-92" id="calibre_link-92"></a>

The meaning of an operator may change based on the data types of the values next to it. For example, + is the addition operator when it operates on two integers or floating-point values. However, when + is used on two string values, it joins the strings as the _string concatenation_ operator. Enter the following into the interactive shell:

```
>>> 'Alice' + 'Bob'
'AliceBob'
```

The expression evaluates down to a single, new string value that combines the text of the two strings. However, if you try to use the + operator on a string and an integer value, Python will not know how to handle this, and it will display an error message.

```
>>> 'Alice' + 42
Traceback (most recent call last):
  File "<pyshell#0>", line 1, in <module>
    'Alice' + 42
TypeError: can only concatenate str (not "int") to str
```

The error message can only concatenate str (not "int") to str means that Python thought you were trying to concatenate an integer to the string 'Alice'. Your code will have to explicitly convert the integer to a string because Python cannot do this automatically. (Converting data types will be explained in “Dissecting Your Program” when we talk about the str(), int(), and float() functions.)

The \* operator multiplies two integer or floating-point values. But when the \* operator is used on one string value and one integer value, it becomes the _string replication_ operator. Enter a string multiplied by a number into the interactive shell to see this in action.

```
>>> 'Alice' * 5
'AliceAliceAliceAliceAlice'
```

The expression evaluates down to a single string value that repeats the original string a number of times equal to the integer value. String replication is a useful trick, but it’s not used as often as string concatenation.

The \* operator can be used with only two numeric values (for multiplication), or one string value and one integer value (for string replication). Otherwise, Python will just display an error message, like the following:

```
>>> 'Alice' * 'Bob'
Traceback (most recent call last):
  File "<pyshell#32>", line 1, in <module>
    'Alice' * 'Bob'
TypeError: can't multiply sequence by non-int of type 'str'
>>> 'Alice' * 5.0
Traceback (most recent call last):
  File "<pyshell#33>", line 1, in <module>
    'Alice' * 5.0
TypeError: can't multiply sequence by non-int of type 'float'
```

It makes sense that Python wouldn’t understand these expressions: you can’t multiply two words, and it’s hard to replicate an arbitrary string a fractional number of times.
