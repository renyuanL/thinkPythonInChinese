===============
Python Keywords
===============

Keywords in Python (and in most programming languages)
are words that have special meaning. They
are used as part of the programming language itself,
and therefore must not be used for anything else. For
example, if you try to use keywords as variables, or
use them in the wrong way, you will get strange (sometimes
funny, sometimes confusing) error messages
from the Python console.
This appendix describes each of the Python keywords.
You should find this to be a handy reference as
you continue to program.


>>> print("Hello, World!(嗨，全世界！)")


    .. sourcecode:: python3
        
        >>> print("Hello, World!(嗨，全世界！)")

---
and
---

The keyword **and** is used to join two expressions together in a statement
(like an *if* statement) to say that both expressions must be
true. Here’s an example:

.. sourcecode:: python3
    :linenos:

    if age > 10 and age < 20:
        print('Beware the teenager!!!!')

This code means that the value of the variable age must be
greater than 10 and less than 20 before the message will be printed.

------
as
------

The keyword **as** can be used to give another name to an imported
module. For example, suppose you had a module with a very
long name:

*i_am_a_python_module_that_is_not_very_useful*

It would be enormously annoying to need to type this module
name every time you wanted to use it:

.. sourcecode:: python3
    :linenos:
    
    import i_am_a_python_module_that_is_not_very_useful
    
    i_am_a_python_module_that_is_not_very_useful.do_something()
    i_am_a_python_module_that_is_not_very_useful.do_something_else()
    
Instead, you can give the module a new, shorter name when
you import it, and then simply use that new name (a bit like a
nickname), as follows:

.. sourcecode:: python3
    :linenos:
    
    import i_am_a_python_module_that_is_not_very_useful as notuseful
    
    notuseful.do_something()
    notuseful.do_something_else()
    
------
assert
------

**assert** is a keyword used to say that some code must be true. It’s
another way of catching errors and problems in code, usually in
more advanced programs (which is why we don’t use assert in this
book). Here’s a simple assert statement:

.. sourcecode:: python3

    >>> mynumber = 10
    >>> assert mynumber < 5
    Traceback (most recent call last):
    File "<pyshell#1>", line 1, in <module>
    assert a < 5
    AssertionError

In this example, we assert that the value of the variable
mynumber
is less than 5. It isn’t, and so Python displays an error
(called an AssertionError).

------
break
------

The **break** keyword is used to stop some code from running. You
might use a break inside a for loop, like this:

.. sourcecode:: python3
    :linenos:
    age = 10
    for x in range(1, 100):
        print('counting %s' % x)
        if x == age:
            print('end counting')
            break

Since the variable age is set to 10 here, this code will print out
the following:

.. sourcecode:: python3
    counting 1
    counting 2
    counting 3
    counting 4
    counting 5
    counting 6
    counting 7
    counting 8
    counting 9
    counting 10
    end counting

Once the value of the variable x reaches 10, the code prints the
text “end counting” and then breaks out of the loop.


------
class
------

The keyword **class** is used to define a type of object, like a vehicle,
animal, or person. Classes can have a function called __init__,
which is used to perform all the tasks an object of the class needs
when it is created. For example, an object of the class Car might
need a variable color when it’s created:

class Car:
def __init__(self, color):
self.color = color
car1 = Car('red')
car2 = Car('blue')
print(car1.color)
red
print(car2.color)
blue

------
continue
------

The continue keyword is a way to “jump” to the next item in a
loop—so that the remaining code in the loop block is not executed.
Unlike break we don’t jump out of the loop, we just carry on with
the next item. For example, if we had a list of items and wanted to
skip items starting with b, we could use the following code:
u >>> my_items = ['apple', 'aardvark', 'banana', 'badger', 'clementine',
'camel']
v >>> for item in my_items:
w if item.startswith('b'):
x continue
y print(item)
apple
aardvark
clementine
camel
We create our list of items at u, and then use a for loop to loop
over the items and run a block of code for each at v. If the item
starts with the letter b at w, we continue to the next item at x.
Otherwise, at y we print out the item.
www.it-ebooks.info
Python Keywords 297

------
def
------

The def keyword is used to define a function. For example, to create
a function to convert a number of years into the equivalent
number of minutes:
>>> def minutes(years):
return years * 365 * 24 * 60
>>> minutes(10)
5256000

------
del
------

The del function is used to remove something. For example, if you
had a list of things you wanted for your birthday in your diary, but
then changed your mind about one of them, you might cross it off
the list and add something new:
remote controlled car
new bike
computer game
roboreptile
In Python, the original list would look like this:
what_i_want = ['remote controlled car', 'new bike', 'computer game']
You could remove the computer game by using del and the
index of the item you want to delete. You could then add the new
item with the function append:
del what_i_want[2]
what_i_want.append('roboreptile')
And then print the new list:
print(what_i_want)
['remote controlled car', 'new bike', 'roboreptile']

------
elif
------

The keyword elif is used as part of an if statement. See the
description of the if keyword for an example.
www.it-ebooks.info
298 Appendix

------
else
------

The keyword else is used as part of an if statement. See the
description of the if keyword for an example.
except
The keyword except is used for catching problems in code. It’s
typically
used in fairly complicated programs, so we don’t use it
in this book.

------
finally
------

The keyword finally is used to make sure that if an error occurs,
certain code runs (usually to tidy up any mess that a piece of code
has left behind). This keyword isn’t used in this book because it’s
for more advanced programming.

------
for
------

The for keyword is used to create a loop of code that runs a certain
number of times. Here’s an example:
for x in range(0, 5):
print('x is %s' % x)
This for loop executes the block of code (the print statement)
five times, resulting in the following output:
x is 0
x is 1
x is 2
x is 3
x is 4

------
from
------

When importing a module, you can import just the part you need
using the from keyword. For example, the turtle module introduced
in Chapter 4 has a class called Pen, which we use to create
a Pen object (the canvas on which the turtle moves). Here’s how we
import the entire turtle module and then use the Pen class:
import turtle
t = turtle.Pen()
www.it-ebooks.info
Python Keywords 299
You could also just import the Pen class on its own, and then
use it directly (without referring to the turtle module at all):
from turtle import Pen
t = Pen()
You might do this so that the next time you look at the top
of that program, you can see all the functions and classes that
you’re using (which is particularly useful in larger programs that
import a lot of modules). However, if you choose to do this, you
won’t be able to use the parts of the module you haven’t imported.
For example, the time module has functions called localtime and
gmtime, but if you import only localtime and then try to use gmtime,
you’ll get an error:
>>> from time import localtime
>>> print(localtime())
(2007, 1, 30, 20, 53, 42, 1, 30, 0)
>>> print(gmtime())
Traceback (most recent call last):
File "<stdin>", line 1, in <module>
NameError: name 'gmtime' is not defined
The error message name 'gmtime' is not defined means that
Python doesn’t know anything about the function gmtime, which is
because you haven’t imported it.
If there are a number of functions in a particular module that
you want to use, and you don’t want to refer to them by using the
module name (for example, time.localtime, or time.gmtime), you can
import everything in the module using an asterisk (*), like this:
>>> from time import *
>>> print(localtime())
(2007, 1, 30, 20, 57, 7, 1, 30, 0)
>>> print(gmtime())
(2007, 1, 30, 13, 57, 9, 1, 30, 0)
This form imports everything from the time module, and you
can now refer to the individual functions by name.

------
global
------

The idea of scope in programs is introduced in Chapter 7. Scope
refers to the visibility of a variable. If a variable is defined outside
www.it-ebooks.info
300 Appendix


a function, usually it can be seen (in other words, it’s visible) inside
the function. On the other hand, if the variable is defined inside a
function, usually it can’t be seen outside that function. The global
keyword is one exception to this rule. A variable that is defined as
global can be seen everywhere. Here’s an example:
>>> def test():
global a
a = 1
b = 2
What do you think happens when you call print(a) and then
print(b), after running the function test? The first will work, but
the second will display an error message:
>>> test()
>>> print(a)
1
>>> print(b)
Traceback (most recent call last):
File "<stdin>", line 1, in <module>
NameError: name 'b' is not defined
The variable a has been changed to global inside the function,
so it’s visible, even once the function has completed, but b is still
visible only inside the function. (You must use the global keyword
before setting the value of your variable.)

------
if
------

The if keyword is used to make a decision about something. It
can also be used with the keywords else and elif (else if). An if
statement is a way of saying, “If something is true, then perform
an action of some kind.” Here’s an example:
u if toy_price > 1000:
v print('That toy is overpriced')
w elif toy_price > 100:
x print('That toy is expensive')
y else:
z print('I can afford that toy')
This if statement says that if a toy price is over $1,000 at u,
display a message that it is overpriced at v; otherwise, if the toy
www.it-ebooks.info
Python Keywords 301
price is over $100 as at w, then display a message that it’s expensive
at x. If neither of those conditions is true as at y, it should
display the message “I can afford that toy” at z.

------
import
------

The import keyword is used to tell Python to load a module so it
can be used. For example, the following code tells Python to use
the module sys:
import sys

------
in
------

The in keyword is used in expressions to see if an item is within
a collection of items. For example, can the number 1 be found in a
list (a collection) of numbers?
>>> if 1 in [1,2,3,4]:
>>> print('number is in list')
number is in list
Here’s how to find out if the string 'pants' is in a list of clothing
items:
>>> clothing_list = ['shorts', 'undies', 'boxers', 'long johns',
'knickers']
>>> if 'pants' in clothing_list:
print('pants is in the list')
else:
print('pants is not in the list')
pants is not in the list

------
is
------

The is keyword is a bit like the equal to operator (==), which is
used to tell if two things are equal (for example 10 == 10 is true,
and 10 == 11 is false). However, there is a fundamental difference
between is and ==. If you are comparing two things, == may return
true, while is may not (even if you think the things are the same).
This is an advanced programming concept, and we stick with
using == in this book.
www.it-ebooks.info
302 Appendix

------
lambda
------

The lambda keyword is used to create anonymous, or inline, functions.
This keyword is used in more advanced programs, and we
don’t discuss it in this book.
not
If something is true, the not keyword makes it false. For example,
if we create a variable x and set it to the value True, and then print
the value of this variable using not, we get the following result:
>>> x = True
>>> print(not x)
False
This doesn’t seem very useful, until you start using the keyword
in if statements. For example, to find out whether an item is
not in a list, we could write something like this:
>>> clothing_list = ['shorts', 'undies', 'boxers', 'long johns',
'knickers']
>>> if 'pants' not in clothing_list:
print('You really need to buy some pants')
You really need to buy some pants

------
or
------

The or keyword is 
used to join two conditions together in a statement
(such as an if statement) to say that at least one of the conditions
should be true. Here’s an example:
if dino == 'Tyrannosaurus' or dino == 'Allosaurus':
print('Carnivores')
elif dino == 'Ankylosaurus' or dino == 'Apatosaurus':
print('Herbivores')
In this case, if the variable dino contains Tyrannosaurus
or Allosaurus,
the program prints “Carnivores.” If it contains
Ankylosaurus
or Apatosaurus, the program prints “Herbivores.”
www.it-ebooks.info
Python Keywords 303

------
pass
------

Sometimes when you’re developing a program, you want to write
only small pieces of it, to try things out. The problem with doing
this is that you can’t have an if statement without the block of
code that should be run if the expression in the if statement is
true. You also cannot have a for loop without the block of code that
should be run in the loop. For example, the following code works
just fine:
>>> age = 15
>>> if age > 10:
print('older than 10')
older than 10
But if you don’t fill in the block of code (the body) for the if
statement, you’ll get an error message:
>>> age = 15
>>> if age > 10:
File "<stdin>", line 2
^
IndentationError: expected an indented block
This is the error message Python displays when you should
have a block of code after a statement of some kind (it won’t even
let you type this kind of code if you’re using IDLE). In cases like
these, you can use the pass keyword to write a statement but not
provide the block of code that goes with it.
For example, say you want to create a for loop with an if statement
inside it. Perhaps you haven’t decided what to put in the if
statement yet—maybe you’ll use the print function, put in a break,
or something else. You can use pass, and the code will still work
(even if it doesn’t do exactly what you want yet).
Here’s our if statement again, this time using the pass keyword:
>>> age = 15
>>> if age > 10:
pass
www.it-ebooks.info
304 Appendix


The following code shows another use of the pass keyword:
>>> for x in range(0, 7):
>>> print('x is %s' % x)
>>> if x == 4:
pass
x is 0
x is 1
x is 2
x is 3
x is 4
x is 5
x is 6
Python still checks whether the variable x contains the value
4 every time it executes the block of code in the loop, but it will
do nothing as a consequence, so it will print every number in the
range 0 to 7.
Later, you could add the code in the block for the if statement,
replacing the pass keyword with something else, such as break:

>>> for x in range(1, 7):
print('x is %s' % x)
if x == 5:
break
x is 1
x is 2
x is 3
x is 4
x is 5

The pass keyword is most commonly used when you’re creating
a function but don’t want to write the code for the function yet.

------
raise
------

The raise keyword can be used to cause an error to happen.
That might sound like a strange thing to do, but in advanced
programming, it can actually be quite useful. (We don’t use this
keyword in this book.)
www.it-ebooks.info
Python Keywords 305

------
return
------

The return keyword is used to return a value from a function. For
example, you might create a function to calculate the number of
seconds you’ve been alive up till your last birthday:
def age_in_seconds(age_in_years):
return age_in_years * 365 * 24 * 60 * 60
When you call this function, the returned value can be assigned
to another variable or printed:

>>> seconds = age_in_seconds(9)
>>> print(seconds)
283824000
>>> print(age_in_seconds())
378432000

------
try
------

The try keyword begins a block of code that ends with the except
and finally keywords. Together, these try/except/finally blocks of
code are used to handle errors in a program, such as to make sure
that the program displays a useful message to the user, rather
than an unfriendly Python error. These keywords aren’t used in
this book.

------
while
------

The while keyword is a bit like for, except that a for loop counts
through a range (of numbers), but a while loop keeps on running
while an expression is true. Be careful with while loops because if
the expression is always true, the loop will never end (this is called
an infinite loop). Here’s an example:

>>> x = 1
>>> while x == 1:
    print('hello')

If you run this code, it will loop forever, or at least until you
close the Python shell or press ctrl-C to interrupt it. However, the
following code will print “hello” nine times (each time adding 1 to
the variable x, until x is no longer less than 10).
www.it-ebooks.info
306 Appendix


>>> x = 1
>>> while x < 10:
    print('hello')
    x = x + 1

------
with
------

The with keyword is used with an object to create a block of code in
a similar way to the try and finally keywords. This keyword is not
used in this book.

------
yield
------

The yield keyword is a little bit like return, except that it is used
with a specific class of object called a generator. Generators create
values on the fly (which is another way of saying that they
create values on request), so in that respect, the range function
behaves like a generator. This keyword is not used in this book.
