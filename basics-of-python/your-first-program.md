---
description: >-
  Edited excerpt from the book "Automate the boring stuff with Python" by Al
  Sweigart
---

# Your First Program

While the interactive shell is good for running Python instructions one at a time, to write entire Python programs, you’ll type the instructions into the file editor. The _file editor_ is similar to text editors such as Notepad or TextMate, but it has some features specifically for entering source code. To open a new file in VSCode, click the **File > New File** button on the top row.

The window that appears should contain a cursor awaiting your input, but it’s different from the interactive shell, which runs Python instructions as soon as you press ENTER. The file editor lets you type in many instructions, save the file, and run the program. Here’s how you can tell the difference between the two:

* The interactive shell window will always be the one with the >>> prompt.
* The file editor window will not have the >>> prompt.

Now it’s time to create your first program! When the file editor window opens, enter the following into it:

```
# This program says hello and asks for my name.

print('Hello, world!')
print('What is your name?')    # ask for their name
myName = input()
print('It is good to meet you, ' + myName)
print('The length of your name is:')
print(len(myName))
print('What is your age?')    # ask for their age
myAge = input()
print('You will be ' + str(int(myAge) + 1) + ' in a year.')
```

Now, you can just run your code using the run button in VSCode.

You should save your programs every once in a while as you type them. That way, if the computer crashes or you accidentally exit Mu, you won’t lose the code. As a shortcut, you can press CTRL-S on Windows and Linux or Cmd-S on macOS to save your file.

The output should look something like this:

```
Hello, world!
What is your name?
Al
It is good to meet you, Al
The length of your name is:
2
What is your age?
4
You will be 5 in a year.
```

When there are no more lines of code to execute, the Python program _terminates_; that is, it stops running. (You can also say that the Python program _exits_.)

#### **Dissecting Your Program** <a href="#calibre_link-97" id="calibre_link-97"></a>

With your new program open in the file editor, let’s take a quick tour of the Python instructions it uses by looking at what each line of code does.

_**Comments**_

The following line is called a _comment_.

```
➊ # This program says hello and asks for my name.
```

Python ignores comments, and you can use them to write notes or remind yourself what the code is trying to do. Any text for the rest of the line following a hash mark (#) is part of a comment.

Sometimes, programmers will put a # in front of a line of code to temporarily remove it while testing a program. This is called _commenting out_ code, and it can be useful when you’re trying to figure out why a program isn’t working. You can remove the # later when you are ready to put the line back in.

Python also ignores the blank line after the comment. You can add as many blank lines to your program as you want. This can make your code easier to read, like paragraphs in a book.

_**The print() Function**_

The print() function displays the string value inside its parentheses on the screen.

```
➋  print('Hello, world!')
   print('What is your name?') # ask for their name
```

The line print('Hello, world!') means “Print out the text in the string 'Hello, world!'.” When Python executes this line, you say that Python is _calling_ the print() function and the string value is being _passed_ to the function. A value that is passed to a function call is an _argument_. Notice that the quotes are not printed to the screen. They just mark where the string begins and ends; they are not part of the string value.

> **NOTE**
>
> _You can also use this function to put a blank line on the screen; just call print() with nothing in between the parentheses._

When you write a function name, the opening and closing parentheses at the end identify it as the name of a function. This is why in this book, you’ll see print() rather than print. We will look into functions in more detail soon.

_**The input() Function**_

The input() function waits for the user to type some text on the keyboard and press ENTER.

```
➌ myName = input()
```

This function call evaluates to a string equal to the user’s text, and the line of code assigns the myName variable to this string value.

You can think of the input() function call as an expression that evaluates to whatever string the user typed in. If the user entered 'Al', then the expression would evaluate to myName = 'Al'.

If you call input() and see an error message, like NameError: name 'Al' is not defined, the problem is that you’re running the code with Python 2 instead of Python 3.

_**Printing the User’s Name**_

The following call to print() actually contains the expression 'It is good to meet you, ' + myName between the parentheses.

```
➍ print('It is good to meet you, ' + myName)
```

Remember that expressions can always evaluate to a single value. If 'Al' is the value stored in myName on line ➌, then this expression evaluates to 'It is good to meet you, Al'. This single string value is then passed to print(), which prints it on the screen.

_**The len() Function**_

You can pass the len() function a string value (or a variable containing a string), and the function evaluates to the integer value of the number of characters in that string.

```
➎ print('The length of your name is:')
   print(len(myName))
```

Enter the following into the interactive shell to try this:

```
>>> len('hello')
5
>>> len('My very energetic monster just scarfed nachos.')
46
>>> len('')
0
```

Just like those examples, len(myName) evaluates to an integer. It is then passed to print() to be displayed on the screen. The print() function allows you to pass it either integer values or string values, but notice the error that shows up when you type the following into the interactive shell:

```
 >>> print('I am ' + 29 + ' years old.')
Traceback (most recent call last):
  File "<pyshell#6>", line 1, in <module>
    print('I am ' + 29 + ' years old.')
TypeError: can only concatenate str (not "int") to str
```

The print() function isn’t causing that error, but rather it’s the expression you tried to pass to print(). You get the same error message if you type the expression into the interactive shell on its own.

```
>>> 'I am ' + 29 + ' years old.'
Traceback (most recent call last):
  File "<pyshell#7>", line 1, in <module>
    'I am ' + 29 + ' years old.'
TypeError: can only concatenate str (not "int") to str
```

Python gives an error because the + operator can only be used to add two integers together or concatenate two strings. You can’t add an integer to a string, because this is ungrammatical in Python. You can fix this by using a string version of the integer instead, as explained in the next section.

_**The str(), int(), and float() Functions**_

If you want to concatenate an integer such as 29 with a string to pass to print(), you’ll need to get the value '29', which is the string form of 29. The str() function can be passed an integer value and will evaluate to a string value version of the integer, as follows:

```
>>> str(29)
'29'
>>> print('I am ' + str(29) + ' years old.')
I am 29 years old.
```

Because str(29) evaluates to '29', the expression 'I am ' + str(29) + ' years old.' evaluates to 'I am ' + '29' + ' years old.', which in turn evaluates to 'I am 29 years old.'. This is the value that is passed to the print() function.

The str(), int(), and float() functions will evaluate to the string, integer, and floating-point forms of the value you pass, respectively. Try converting some values in the interactive shell with these functions and watch what happens.

```
>>> str(0)
'0'
>>> str(-3.14)
'-3.14'
>>> int('42')
42
>>> int('-99')
-99
>>> int(1.25)
1
>>> int(1.99)
1
>>> float('3.14')
3.14
>>> float(10)
10.0
```

The previous examples call the str(), int(), and float() functions and pass them values of the other data types to obtain a string, integer, or floating-point form of those values.

The str() function is handy when you have an integer or float that you want to concatenate to a string. The int() function is also helpful if you have a number as a string value that you want to use in some mathematics. For example, the input() function always returns a string, even if the user enters a number. Enter spam = input() into the interactive shell and enter 101 when it waits for your text.

```
>>> spam = input()
101
>>> spam
'101'
```

The value stored inside spam isn’t the integer 101 but the string '101'. If you want to do math using the value in spam, use the int() function to get the integer form of spam and then store this as the new value in spam.

```
>>> spam = int(spam)
>>> spam
101
```

Now you should be able to treat the spam variable as an integer instead of a string.

```
>>> spam * 10 / 5
202.0
```

Note that if you pass a value to int() that it cannot evaluate as an integer, Python will display an error message.

```
>>> int('99.99')
Traceback (most recent call last):
  File "<pyshell#18>", line 1, in <module>
    int('99.99')
ValueError: invalid literal for int() with base 10: '99.99'
>>> int('twelve')
Traceback (most recent call last):
  File "<pyshell#19>", line 1, in <module>
    int('twelve')
ValueError: invalid literal for int() with base 10: 'twelve'
```

The int() function is also useful if you need to round a floating-point number down.

```
>>> int(7.7)
7
>>> int(7.7) + 1
8
```

You used the int() and str() functions in the last three lines of your program to get a value of the appropriate data type for the code.

```
➏ print('What is your age?') # ask for their age
   myAge = input()
   print('You will be ' + str(int(myAge) + 1) + ' in a year.')
```

> **TEXT AND NUMBER EQUIVALENCE**
>
> Although the string value of a number is considered a completely different value from the integer or floating-point version, an integer can be equal to a floating point.
>
> ```
> >>> 42 == '42'
> False
> >>> 42 == 42.0
> True
> >>> 42.0 == 0042.000
> True
> ```
>
> Python makes this distinction because strings are text, while integers and floats are both numbers.

The myAge variable contains the value returned from input(). Because the input() function always returns a string (even if the user typed in a number), you can use the int(myAge) code to return an integer value of the string in myAge. This integer value is then added to 1 in the expression int(myAge) + 1.

The result of this addition is passed to the str() function: str(int(myAge) + 1). The string value returned is then concatenated with the strings 'You will be ' and ' in a year.' to evaluate to one large string value. This large string is finally passed to print() to be displayed on the screen.

Let’s say the user enters the string '4' for myAge. The string '4' is converted to an integer, so you can add one to it. The result is 5. The str() function converts the result back to a string, so you can concatenate it with the second string, 'in a year.', to create the final message. These evaluation steps would look something like the following:

![](<../.gitbook/assets/image (1).png>)
