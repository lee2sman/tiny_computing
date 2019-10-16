---
layout: post
title: "Class 8 notes - Intro to Python and PirateBox"
---

### Class schedule

- intro to Python
- class project - PirateBox

### Python

Python, what is it good for?

Python, first released in 1991, is a general purpose language emphasizing easy readability and logical structure and is meant to be *fun to use*.

Some advantages of Python:
- It's a "high level language" meaning that it is further away from machine code with simplified layers of abstraction (variables, loops, arrays, objects, etc)
- It's cross-platform. It works on Mac, PC, Linux, Servers - powerful super computers and tiny Raspberry Pi's. Recently a version has been ported to [control microcontrollers](https://circuitpython.org/).
- There is a huge community of Python programmers. There are so many ways to learn it, and lots of answers available online.
- The Python ecosystem is vast. It can be used to simplify scripting for many other applications, hardware, and even works with lower-level languages like C and C++.
- The syntax is simple and  beginner-friendly
- It is a general purpose language that can work for a variety of tasks: system processes, desktop applications, server software, machine learning, automation, and even mobile apps

### Python's philosophy

> Beautiful is better than ugly.
> Explicit is better than implicit.
> Simple is better than complex.
> Complex is better than complicated.
> Readability counts.
*--from The Zen of Python*

Java and C++ are object-oriented languages. Python is a multi-paradigm language. This means it has several different ways it is generally used, including object-oriented modes.

#### Tutorial

Let's talk about:

- variables
- if statements
- loops
- lists 
  
### Python 2 vs 3

There are 2 main branches of Python. Annoying! 

Over time, languages are refined and improved. Python 2 was released in 2000. Python 3 was a large revision of the language and released in 2008. So many ongoing programs were written in 2 that a decision was made to continue to improve Python 2 even while Python 3 was further developed. Python 2.7 will be *sunset* on January 1, 2020, meaning that the language will not be further developed, de-bugged or supported. When you find code online, check to see whether it is in Python 2 or Python 3.

Generally, most shell's run Python 2 by default. To launch the Python 3 interpreter, type ```python3``` if it's installed.

# Tutorial

#### Hello World!

```
print("hello world")
```

NOTE: In Python2, you can also just do ```print "hello world"```.

#### Indentation

Python uses indentation to specify blocks of code, instead of { }. The amount of indentation indicates your current scope level.

example:

```
if x == 1:
    print "x is 1"
```
### Variables

Python is a dynamic language. You do NOT need to declare the type of variable. You do not need to declare a variable before using it. 

#### Types of Numbers

1. Floats
2. Integers

```
myInt = 7
myFloat = 7.0
```

#### Strings

myString = "some text"

#### Lists

Lists are similar to arrays in other languages. Python has a number of built in methods to work with lists. Lists may contain any mixture of strings and numbers and variables.

```
myList = [1, 2, "three"]
```

#### String methods

```
myList.append('another thing')

myList.insert(0,"zero")

del myList[4]

myList.pop() # removes last item
myList.pop(4) # removes 4th item

myList.remove('zero') #removes a value that matches

myList.sort() #sort
myList.sort(reverse=True) #sort in reverse
myList.reverse() #flip list around

len(myList) # the length of the list
```

### You can loop through lists

```
for item in myList:
    print(item)
    
for value in range(1,6):
    print(value)
```

### Lists of numbers

```
digits = [0, 1, 2, 3]

min(digits) #0
max(digits) #3
sum(digits) #6

print(digits[0:3]) # slicing
```

#### Copying a list

```
newList = digits[] #points to old list
digits.append(4)

print(newList) #0, 1, 2, 3, 4
#copying list just points to old list!
```

#### Tuple: a list that cannot be changed

```
tuple = (0, 1, 2)

tuple[0] = 23 # ERROR!

```

### Dictionary

dictionaries are combinatons of key-value pairs.

```
alien = {'color':'green','age':5}
```

### Functions

```
def hello(username):
    print("hello "+username)
    
hello("Xavier")

def hi(username="Lee"):
    print("hi "+username) 
    
hi() # prints hi Lee, the default parameter
hi("Justine") #prints hi Justine
```

### Modules

Modules are files with variables and functions and classes. You can import them into your program to use them.

There are a number of prebuilt modules, or you can download others' modules.

```
import pizza #imports a file pizza.py

pizza.make_pizza('pepperoni') 
# runs the make_pizza function, with a parameter, from pizza module

# OR
# 

from pizza import make_piza 
#imports just a single function instead of entire module

# OR create an alias for a function

from pizza import make_pizza as mp

mp('pepperoni')

from pizza import * #imports everything
```

### Advanced python

- classes and objects

## Resources / Tutorial
- official [Learn Python](https://www.learnpython.org/)
- [python.org](http://python.org)

# PirateBox project

![Piratebox cc](https://piratebox.cc/_media/piratebox-openwrt.300.gif)

<iframe width="560" height="315" src="https://www.youtube.com/embed/paFoP7ponhg" frameborder="0" allow="accelerometer; autoplay; encrypted-media; gyroscope; picture-in-picture" allowfullscreen></iframe>

<iframe width="560" height="315" src="https://www.youtube.com/embed/DwSh1zpOBVo" frameborder="0" allow="accelerometer; autoplay; encrypted-media; gyroscope; picture-in-picture" allowfullscreen></iframe>

- [documentation website](https://piratebox.cc/raspberry_pi:diy)

- my [nates](https://github.com/lee2sman/PirateBoxExperiments) on altering PirateBox on Pi

```
sudo nano /etc/minidlna.conf
```

- Change the filesharing directory
- change the presented url from piratebox.lan to something else
- add album artwork

# Homework:
- complete your piratebox
- customize it, make it yours. What is the concept? Who does it serve? Where is it deployed? What alterations are you making to it?
- what are you serving? build a nice landing page

The completed Piratebox project should have:

1. Title
2. Purpose/Concept
3. List of parts
4. Custom landing page/intro page
5. Screenshots from you connecting to your piratebox from your own computer
6. **Complete documentation walk through of your building process. Write down every step you took. Make sure you write a description of what you worked on, every 20 minutes!**

