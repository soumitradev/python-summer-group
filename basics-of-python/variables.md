---
description: >-
  Edited excerpt from the book "Automate the boring stuff with Python" by Al
  Sweigart
---

# Variables

A _variable_ is like a box in the computer’s memory where you can store a single value. If you want to use the result of an evaluated expression later in your program, you can save it inside a variable.

\
_**Assignment Statements**_

You’ll store values in variables with an _assignment statement_. An assignment statement consists of a variable name, an equal sign (called the _assignment operator_), and the value to be stored. If you enter the assignment statement spam = 42, then a variable named spam will have the integer value 42 stored in it.

For example, enter the following into the interactive shell:

```
➊ >>> spam = 40
   >>> spam
   40
   >>> eggs = 2
➋ >>> spam + eggs
   42
   >>> spam + eggs + spam
   82
➌ >>> spam = spam + 2
   >>> spam
   42
```

A variable is _initialized_ (or created) the first time a value is stored in it ➊. After that, you can use it in expressions with other variables and values ➋. When a variable is assigned a new value ➌, the old value is forgotten, which is why spam evaluated to 42 instead of 40 at the end of the example. This is called _overwriting_ the variable. Enter the following code into the interactive shell to try overwriting a string:

```
>>> spam = 'Hello'
>>> spam
'Hello'
>>> spam = 'Goodbye'
>>> spam
'Goodbye'
```

_**Variable Names**_

A good variable name describes the data it contains. Imagine that you moved to a new house and labeled all of your moving boxes as _Stuff_. You’d never find anything! Most of this book’s examples (and Python’s documentation) use generic variable names like spam, eggs, and bacon, which come from the Monty Python “Spam” sketch. But in your programs, a descriptive name will help make your code more readable.

Though you can name your variables almost anything, Python does have some naming restrictions. Table 1-3 has examples of legal variable names. You can name a variable anything as long as it obeys the following three rules:

* It can be only one word with no spaces.
* It can use only letters, numbers, and the underscore (\_) character.
* It can’t begin with a number.

**Table 1-3:** Valid and Invalid Variable Names

| **Valid variable names** | **Invalid variable names**                             |
| ------------------------ | ------------------------------------------------------ |
| current\_balance         | current-balance (hyphens are not allowed)              |
| currentBalance           | current balance (spaces are not allowed)               |
| account4                 | 4account (can’t begin with a number)                   |
| \_42                     | 42 (can’t begin with a number)                         |
| TOTAL\_SUM               | TOTAL\_$UM (special characters like $ are not allowed) |
| hello                    | 'hello' (special characters like ' are not allowed)    |

Variable names are case-sensitive, meaning that spam, SPAM, Spam, and sPaM are four different variables. Though Spam is a valid variable you can use in a program, it is a Python convention to start your variables with a lowercase letter.

This book uses _camelcase_ for variable names instead of underscores; that is, variables lookLikeThis instead of looking\_like\_this. Some experienced programmers may point out that the official Python code style, PEP 8, says that underscores should be used. I unapologetically prefer camelcase and point to the “A Foolish Consistency Is the Hobgoblin of Little Minds” section in PEP 8 itself:

> Consistency with the style guide is important. But most importantly: know when to be inconsistent—sometimes the style guide just doesn’t apply. When in doubt, use your best judgment.
