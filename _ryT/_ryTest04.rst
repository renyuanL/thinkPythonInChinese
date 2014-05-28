====================
Keywords in Python 3 
====================

Python 3 的關鍵字

Python 3 的關鍵字(Keywords)有以下 33 個 (每當 Python 改版時，都會增減一、二個)，
這些關鍵字都扮演了某種語法上的角色，就像英文中的功能字(functional words)一樣，
它們通常都是常見的簡單英文「短字」，單音節居多，我建議當文法知識吸收它們，
每個關鍵字除了定義之外，看一兩個實例。
這些關鍵字在我們的中文程式中，不會被轉成中文詞彙，
一則是因為 Python 3 似乎不允許這樣做 (以我目前的技術而言)，
再則我覺得也不需要，因為它們很短很常見，而且數量有限，
一般學過國中程度英文以上的人士，都很容易就理解並掌握它們。

關鍵字列表如下：

.. sourcecode:: python3
    :linenos:
    
    >>> import keyword
    >>> len(keyword.kwlist)
    33
    >>> keyword.kwlist
    ['False',
     'None',
     'True',
     'and',
     'as',
     'assert',
     'break',
     'class',
     'continue',
     'def',
     'del',
     'elif',
     'else',
     'except',
     'finally',
     'for',
     'from',
     'global',
     'if',
     'import',
     'in',
     'is',
     'lambda',
     'nonlocal',
     'not',
     'or',
     'pass',
     'raise',
     'return',
     'try',
     'while',
     'with',
     'yield']
    
    >>> 

-----------------------------------------------
Description of Keywords in Python with examples
-----------------------------------------------

以實例來描述   Python 關鍵字。

`參考: Description of Keywords in Python with examples <http://www.programiz.com/python-programming/keyword-list>`__


True, False
-----------

中文對應字： **真**, **假**

**True** and **False** are truth values in Python. They are the results of comparison operations or logical (Boolean) operations in Python. For example:


    >>> 1 == 1
    True
    >>> 5 > 3
    True
    >>> True or False
    True
    >>> 10 <= 1
    False
    >>> 3 > 7
    False
    >>> True and False
    False

Here we can see that the first three statements are true so the interpreter returns True and returns False for the remaining three statements. True and False in python is same as 1 and 0. This can be justified with the following example:


    >>> True == 1
    True
    >>> False == 0
    True
    >>> True + True
    2


None
----

中文對應字： **無**

**None** is a special constant in Python that represents the absence of a value or a null value. It is an object of its own datatype, the NoneType. We cannot create multiple None objects but can assign it to variables. These variables will be equal to one another. We must take special care that None does not imply False, 0 or any empty list, dictionary, string etc. For example:


    >>> None == 0
    False
    >>> None == []
    False
    >>> None == False
    False
    >>> x = None
    >>> y = None
    >>> x == y
    True

Void functions that do not return anything will return a None object automatically. None is also returned by functions in which the program flow does not encounter a return statement. For example:

.. sourcecode:: python3
    :linenos:
    
    def a_void_function():
        a = 1
        b = 2
        c = a + b

    x = a_void_function()
    print(x)

    
.. sourcecode:: python3
    :linenos:
    
    def 虛無函數():
        甲 = 1
        乙 = 2
        丙 = 甲 + 乙

    丁 = 虛無函數()
    print(丁)

    
*Output*

.. sourcecode:: pycon

    None

This program has a function that does not return a value, although it does some operations inside. So when we print x, we get None which is returned automatically (implicitly). Similarly, here is another example:

.. sourcecode:: python3
    :linenos:
    
    def improper_return_function(a):
        if (a % 2) == 0:
            return True

    x = improper_return_function(3)
    print(x)

.. sourcecode:: python3
    :linenos:
    
    def 有瑕疵的函數(某數):
        if (某數 % 2) == 0:
            return True

    丁 = 有瑕疵的函數(3)
    print(丁)

*Output*

.. sourcecode:: pycon

    None

Although this function has a return statement, it is not reached in every case. The function will return True only when the input is even. So, if we give the function an odd number, None is returned implicitly.



and, or , not
-------------

中文對應字： **且**, **或**, **非**, 

**and**, **or**, **not** are the logical operators in Python. 

**and** will result into True only if both the operands are True. The truth table for **and** is given below:

Truth table for **and**

======  ======  =======
A	    B	    A and B
======  ======  =======
True	True	True
True	False	False
False	True	False
False	False	False
======  ======  =======

**or** will result into True if any of the operands is True. The truth table for **or** is given below:

Truth table for **or**

======  ======  =======
A	    B	    A or B
======  ======  =======
True	True	True
True	False	True
False	True	True
False	False	False
======  ======  =======

**not** operator is used to invert the truth value. The truth table for **not** is given below:

Truth tabel for **not**

======  ======
A	    not A
======  ======
True	False
False	True
======  ======

some example of their usage are given below


>>> True and False
False
>>> True or False
True
>>> not False
True

as
-------------

中文對應字： **當作**

as is used to create an alias while importing a module. It means giving a different name (user-defined) to a module while importing it. As for example, Python has a standard module called math. Suppose we want to calculate what cosine pi is using an alias. We can do it as follows using as:


>>> import math as myAlias
>>> myAlias.cos(myAlias.pi)
-1.0

>>> import math as 數學
>>> 數學.cos(數學.pi)
-1.0

Here we imported the math module by giving it the name myAlias. Now we can refer to the math module with this name. Using this name we calculated cos(pi) and got -1.0 as the answer.

assert
-------------

中文對應字： **確認**

assert is used for debugging purposes. While programming, sometimes we wish to know the internal state or check if our assumptions are true. assert helps us do this and find bugs more conveniently. assert is followed by a condition. If the condition is true, nothing happens. But if the condition is false, AssertionError is raised. For example:


>>> a = 4
>>> assert a < 5
>>> assert a > 5
Traceback (most recent call last):
  File "<string>", line 301, in runcode
  File "<interactive input>", line 1, in <module>
AssertionError

For our better understanding, we can also provide a message to be printed with the AssertionError.


>>> a = 4
>>> assert a > 5, "The value of a is too small"
Traceback (most recent call last):
  File "<string>", line 301, in runcode
  File "<interactive input>", line 1, in <module>
AssertionError: The value of a is too small

At this point we can note that,

.. sourcecode:: python3
    :linenos:
    
    assert condition, message

.. sourcecode:: python3
    :linenos:
    
    assert 條件成立, 條件不成立的警告訊息

is equivalent to,

.. sourcecode:: python3
    :linenos:

    if not condition:
        raise AssertionError(message)
 
.. sourcecode:: python3
    :linenos:

    if not 條件成立:
        raise AssertionError(條件不成立的警告訊息)
        
break, continue
-------------

中文對應字： **中斷**, **繼續**

break and continue are used inside for and while loops to alter their normal behavior. break will end the smallest loop it is in and control flows to the statement immediately below the loop. continue causes to end the current iteration of the loop, but not the whole loop. This can be illustrated with the following two examples:

.. sourcecode:: python3
    :linenos:
    
    for i in range(1,11):
        if i == 5:
            break
        print(i)

*Output*

.. sourcecode:: pycon

    1
    2
    3
    4

Here, the for loop intends to print numbers from 1 to 10. But the if condition is met when i is equal to 5 and we break from the loop. Thus, only the range 1 to 4 is printed.

.. sourcecode:: python3
    :linenos:
    
    for i in range(1,11):
        if i == 5:
            continue
        print(i)
    
*Output*

.. sourcecode:: pycon

    1
    2
    3
    4
    6
    7
    8
    9
    10

Here we use continue for the same program. So, when the condition is met, that iteration is skipped. But we do not exit the loop. Hence, all the values except 5 is printed out.

class
-------------

中文對應字： **物類**

class is used to define a new user-defined class in Python. Class is a collection of related attributes and methods that try to represent a real world situation. This idea of putting data and functions together in a class is central to the concept of object-oriented programming (OOP). Classes can be defined anywhere in a program. But it is a good practice to define a single class in a module. Following is a sample usage:

.. sourcecode:: python3
    :linenos:
    
    class ExampleClass:
        def function1(parameters):
            …
        def function2(parameters):
            …

.. sourcecode:: python3
    :linenos:
    
    class 甲物類:
        def 乙函數(乙參數群):
            …
        def 丙函數(丙參數群):
            …

def
-------------

中文對應字： **定義**

def is used to define a user-defined function. Function is a block of related statements, which together does some specific task. It helps us organize code into manageable chunks and also to do some repetitive task. The usage of def is shown below:

.. sourcecode:: python3
    :linenos:
    
    def function_name(parameters):
        …

.. sourcecode:: python3
    :linenos:
    
    def 函數名稱(參數群):
        …

del
-------------

中文對應字： **刪除**

del is used to delete the reference to an object. Everything is object in Python. We can delete a variable reference using del


>>> a = b = 5
>>> del a
>>> a
Traceback (most recent call last):
  File "<string>", line 301, in runcode
  File "<interactive input>", line 1, in <module>
NameError: name 'a' is not defined
>>> b
5

Here we can see that the reference of the variable a was deleted. So, it is no longer defined. But b still exists.

del is also used to delete items from a list or a dictionary:


>>> a = ['x','y','z']
>>> del a[1]
>>> a
['x', 'z']

if, else, elif
-------------

中文對應字： **若**, **否則**, **否則又若**

if, else, elif are used for conditional branching or decision making. When we want to test some condition and execute a block only if the condition is true, then we use if and elif. elif is short for else if. else is the block which is executed if the condition is false. This will be clear with the following example:

.. sourcecode:: python3
    :linenos:
    
    def if_example(a):
        if a == 1:
            print('One')
        elif a == 2:
            print('Two')
        else:
            print('Something else')

    if_example(2)
    if_example(4)
    if_example(1)

*Output*

.. sourcecode:: pycon

    Two
    Something else
    One

.. sourcecode:: python3
    :linenos:
    
    def 練習使用if的函數(a):
        if a == 1:
            print('輸入 == 1')
        elif a == 2:
            print('輸入 == 2')
        else:
            print('輸入 不是 1，也不是 2。')

    練習使用if的函數(2)
    練習使用if的函數(4)
    練習使用if的函數(1)

    
*Output*

.. sourcecode:: pycon

    輸入 == 2
    輸入 不是 1，也不是 2。
    輸入 == 1

Here, the function checks the input number and prints the result if it is 1 or 2. Any input other than this will cause the else part of the code to execute.

except, raise, try
-------------

中文對應字： **例外**, **舉發**, **嘗試** 

except, raise, try are used with exceptions in Python. Exceptions are basically errors that suggests something went wrong while executing our program. IOError, ValueError, ZeroDivisionError, ImportError, NameError, TypeError etc. are few examples of exception in Python. try...except blocks are used to catch exceptions in Python. We can raise an exception explicitly with the raise keyword. Following is an example:

.. sourcecode:: python3
    :linenos:
    
    def reciprocal(num):
        try:
            r = 1/num
        except:
            print('Exception caught')
            return
        return r

    print(reciprocal(10))
    print(reciprocal(0))

    
*Output*

.. sourcecode:: pycon

    0.1
    Exception caught
    None


.. sourcecode:: python3
    :linenos:
    
    def 算出倒數(某數):
        try:
            倒數 = 1/某數
        except:
            print('在 算出倒數(某數) 內部，偵測到例外情況！很可能是分母為 0。')
            return
        return 倒數

    print(算出倒數(10))
    print(算出倒數(0))

*Output*

.. sourcecode:: pycon

    0.1
    在 算出倒數(某數) 內部，偵測到例外情況！很可能是分母為 0。
    None

Here, the function reciprocal() returns the reciprocal of the input number. When we enter 10, we get the normal output of 0.1. But when we input 0, a ZeroDivisionError is raised automatically. This is caught by our try…except block and we return None. We could have also raised the ZeroDivisionError explicitly by checking the input and handled it elsewhere as follows:

.. sourcecode:: python3
    :linenos:
    
    if num == 0:
        raise ZeroDivisionError('cannot divide')

.. sourcecode:: python3
    :linenos:
    
    if 某數 == 0:
        raise ZeroDivisionError('某數==0, 不能當分母！')

finally
-------------

中文對應字： **最後**

finally is used with try…except block to close up resources or file streams. Using finally ensures that the block of code inside it gets executed even if there is an unhandled exception. For example:

.. sourcecode:: python3
    :linenos:
    
    try:
        Try-block
    except exception1:
        Exception1-block
    except exception2:
        Exception2-block
    else:
        Else-block
    finally:
        Finally-block

Here if there is an exception in the Try-block, it is handled in the except or else block. But no matter in what order the execution flows, we can rest assured that the Finally-block is executed even if there is an error. This is useful in cleaning up the resources.

for
-------------

中文對應字： **對於每個成員重複**

for is used for looping. Generally we use for when we know the number of times we want to loop. In Python we can use it with any type of sequence like a list or a string. Here is an example in which for is used to traverse through a list of names:

.. sourcecode:: python3
    :linenos:
    
    names = ['John','Monica','Steven','Robin']
    for i in names:
        print('Hello '+i)
        
*Output*

.. sourcecode:: pycon

    Hello John
    Hello Monica
    Hello Steven
    Hello Robin

.. sourcecode:: python3
    :linenos:
    
    名單 = ['可名','可弘','咖之','咖趴']
    for 名字 in 名單:
        print('你好，' + 名字)

*Output*

.. sourcecode:: pycon

    你好，可名
    你好，可弘
    你好，咖之
    你好，咖趴

**for** 的最經典用法如下：

.. sourcecode:: python3
    :linenos:
    
    for i in range(0,10):
        print(i)

*Output*

.. sourcecode:: pycon

    0
    1
    2
    3
    4
    5
    6
    7
    8
    9

特別注意，它從 0 開始，結束在 9，也就是 **不** 包含 最後一個 10。

    
from, import
-------------

中文對應字： **從**, **引入**

import keyword is used to import modules into the current namespace. from…import is used to import specific attributes or functions into the current namespace. For example:

.. sourcecode:: python3
    :linenos:
    
    import math

will import the math module. Now we can use the cos() function inside it as math.cos(). But if we wanted to import just the cos() function, this can done using from as

.. sourcecode:: python3
    :linenos:
    
    from math import cos

now we can use the function simply as cos(), no need to write math.cos().

 

global
-------------

中文對應字： **全區變數**

global is used to declare that a variable inside the function is global (outside the function). If we need to read the value of a global variable, it is not necessary to define it as global. This is understood. But if we need to modify the value of a global variable inside a function, then we must declare it with global. Otherwise a local variable with that name is created. Following example will help us clarify this.

.. sourcecode:: python3
    :linenos:
    
    globvar = 10
    def read1():
        print(globvar)
    def write1():
        global globvar
        globvar = 5
    def write2():
        globvar = 15


    read1()
    write1()
    read1()
    write2()
    read1()

*Output*

.. sourcecode:: pycon

    10
    5
    5

.. sourcecode:: python3
    :linenos:
    
    全區變數甲 = 10
    
    def 讀全區變數():
        print(全區變數甲)
    
    def 寫全區變數1():
        global 全區變數甲
        全區變數甲 = 5
    
    def 寫全區變數2():
        全區變數甲 = 15 # 沒有使用 global，這個「全區變數」變成「本區變數」了


    讀全區變數()
    寫全區變數1()
    讀全區變數()
    寫全區變數2()
    讀全區變數()

*Output*

.. sourcecode:: pycon

    10
    5
    5

Here, the read1() function is just reading the value of globvar. So, we do not need to declare it as global. But the write1() function is modifying the value, so we need to declare the variable as global. We can see in our output that the modification did take place (10 is changed to 5). The write2() also tries to modify this value. But we have not declared it as global. Hence, a new local variable globvar is created which is not visible outside this function. Although we modify this local variable to 15, the global variable remains unchanged. This is clearly visible in our output.

in
-------------

中文對應字： **屬於**

in is used to test if a sequence (list, tuple, string etc.) contains a value. It returns True if the value is present, else it returns False. For example:


>>> a = [1, 2, 3, 4, 5]
>>> 5 in a
True
>>> 10 in a
False

>>> 列表 = [1, 2, 3, 4, 5]
>>> 5 in 列表
True
>>> 10 in 列表
False

The secondary use of in is to traverse through a sequence in a for loop.

.. sourcecode:: python3
    :linenos:
    
    for i in 'hello':
        print(i)
        
*Output*

.. sourcecode:: pycon

    h
    e
    l
    l
    o

.. sourcecode:: python3
    :linenos:
    
    for i in '床前明月光':
        print(i)
        
*Output*

.. sourcecode:: pycon

    床
    前
    明
    月
    光

試試看下面這一段程式碼。

.. sourcecode:: python3
    :linenos:
    
    for i in ['床前明月光', '疑是地上霜','舉頭望明月','低頭吃便當']:
        print(i)
        
*Output*

.. sourcecode:: pycon

    床前明月光
    疑是地上霜
    舉頭望明月
    低頭吃便當    

再試試看下面這一段程式碼。

.. sourcecode:: python3
    :linenos:
    
    for i in ['床前明月光', '疑是地上霜','舉頭望明月','低頭吃便當']:
        for x in i:
            print(x)
        
*Output*

.. sourcecode:: pycon

    床
    前
    明
    月
    光
    疑
    是
    地
    上
    霜
    舉
    頭
    望
    明
    月
    低
    頭
    吃
    便
    當 
    
is
-------------

中文對應字： **是**

*is* is used in Python for testing object *identity*. While the == operator is used to test if two variables are equal or not, *is* is used to test if the two variables refer to the same object. It returns True if the objects are identical and False if not.

*is* 用來偵測兩者「身分」是否完全相同。 
*==* 用來偵測兩者「值」是否相等。

>>> True is True
True
>>> False is False
True
>>> None is None
True

We know that there is only one instance of True, False and None in Python, so they are identical.


>>> [] == []
True
>>> [] is []
False
>>> {} == {}
True
>>> {} is {}
False

An empty list or dictionary is equal to another empty one. But they are not identical objects as they are located separately in memory. This is because list and dictionary are mutable (value can be changed).


>>> '' == ''
True
>>> '' is ''
True
>>> () == ()
True
>>> () is ()
True

Unlike list and dictionary, string and tuple are immutable (value cannot be altered once defined). Hence, two equal string or tuple are identical as well. They refer to the same memory location.

lambda
-------------

中文對應字： **無名函數**

lambda is used to create an anonymous function (function with no name). It is an inline function that does not contain a return statement. It consists of an expression that is evaluated and returned. For example:

.. sourcecode:: python3
    :linenos:
    
    a = lambda x: x*2
    for i in range(1,6):
        print(a(i))

.. sourcecode:: python3
    :linenos:
    
    某種函數 = lambda x: x*2
    for i in range(1,6):
        print(某種函數(i))
        
*Output*

.. sourcecode:: pycon

    2
    4
    6
    8
    10

Here, we have created an inline function that doubles the value, using the lambda statement. We used this to double the values in a list containing 1 to 5.

nonlocal
-------------

中文對應字：**非本區變數**

The use of nonlocal keyword is very much similar to the global keyword. nonlocal is used to declare that a variable inside a nested function (function inside a function) is not local to it, meaning it lies in the outer inclosing function. If we need to modify the value of a non-local variable inside a nested function, then we must declare it with nonlocal. Otherwise a local variable with that name is created inside the nested function. Following example will help us clarify this.

.. sourcecode:: python3
    :linenos:
    
    def outer_funciton():
        a = 5
        def inner_function():
            nonlocal a
            a = 10
            print("Inner function: ",a)
        inner_function()
        print("Outer function: ",a)

    outer_funciton()

*Output*

.. sourcecode:: pycon

    Inner function:  10
    Outer function:  10


    
.. sourcecode:: python3
    :linenos:
    
    def 外面的函數():
        a = 5 #外面的數
        def 裡面的函數():
            nonlocal a # 裡面的數 宣告成 非本區變數，就與外面的數變成代表同一個數了。
            a = 10     # 因此，當改變它時，就改變到外面的數了。
            print("裡面的函數 印 裡面的數: ", a)
        裡面的函數()
        print("外面的函數 印 外面的數: ", a)

    外面的函數()

*Output*

.. sourcecode:: pycon

    裡面的函數 印 裡面的數: 10
    外面的函數 印 外面的數: 10
    
    
Here, the inner_function() is nested within the outer_function. The variable a is in the outer_function(). So, if we want to modify it in the inner_function(), we must declare it as nonlocal. Notice that a is not a global variable. Hence, we see from the output that the variable was successfully modified inside the nested inner_function(). The result of not using the nonlocal keyword is as follows:

.. sourcecode:: python3
    :linenos:
    
    def outer_funciton():
        a = 5
        def inner_function():

            a = 10
            print("Inner function: ",a)
        inner_function()
        print("Outer function: ",a)

    outer_funciton()

*Output*

.. sourcecode:: pycon

    Inner function:  10
    Outer function:  5

.. sourcecode:: python3
    :linenos:
    
    def 外面的函數():
        a = 5 #外面的數
        def 裡面的函數():
            
            a = 10 #裡面的數
            print("裡面的函數 印 裡面的數: ", a)
        裡面的函數()
        print("外面的函數 印 外面的數: ", a)

    外面的函數()

*Output*

.. sourcecode:: pycon

    裡面的函數 印 裡面的數: 10
    外面的函數 印 外面的數: 5
    

Here, we do not declare that the variable a inside the nested function is nonlocal. Hence, a new local variable with the same name is created, but the non-local a is not modified as seen in our output.

pass
-------------

中文對應字： **通過**

pass is a null statement in Python. Nothing happens when it is executed. It is used as a placeholder. Suppose we have a function that is not implemented yet, but we want to implement it in the future. Simply writing,

.. sourcecode:: python3
    :linenos:
    
    def function(args):

>>> 
  File "<module1>", line 1
    def function(args):
                      ^
SyntaxError: unexpected EOF while parsing

in the middle of a program will give us IndentationError. Instead of this, we construct a blank body with the pass statement.

 
.. sourcecode:: python3
    :linenos:

    def function(args):
        pass

.. sourcecode:: python3
    :linenos:

    def 函數(參數群):
        pass
        
We can do the same thing in an empty class as well.

.. sourcecode:: python3
    :linenos:
    
    class example:
        pass

.. sourcecode:: python3
    :linenos:
    
    class 物類:
        pass
        
return
-------------

中文對應字： **回傳**

return statement is used inside a function to exit it and return a value. If we do not return a value explicitly, None is returned automatically. This is verified with the following example.

.. sourcecode:: python3
    :linenos:
    
    def func_return():
        a = 10
        return a

    def no_return():
        a = 10

    print(func_return())
    print(no_return())

*Output*

.. sourcecode:: pycon

    10
    None

.. sourcecode:: python3
    :linenos:
    
    def 有回傳的函數():
        a = 10
        return a

    def 無回傳的函數():
        a = 10

    print(有回傳的函數())
    print(無回傳的函數())

*Output*

.. sourcecode:: pycon

    10
    None

while
-------------

中文對應字： **當條件成立時重複**

while is used for looping in Python. The statements inside a while loop continue to execute until the condition for the while loop evaluates to False or a break statement is encountered. Following program illustrates this.

.. sourcecode:: python3
    :linenos:
    
    i = 5
    while(i >= 1):
        print(i)
        i = i – 1
    
*Output*

.. sourcecode:: pycon

    5
    4
    3
    2
    1

Note that while i == 0, (i>=1) becomes False.

with
-------------

中文對應字： **隨著執行後離開**

with statement is used to wrap the execution of a block of code within methods defined by the context manager. Context manager is a class that implements __enter__ and __exit__ methods. Use of with statement ensures that the __exit__ method is called at the end of the nested block. This concept is similar to the use of try…finally block. Here, is an example.

.. sourcecode:: python3
    :linenos:
    
    with open('example.txt', 'w') as my_file:
        my_file.write('Hello world!')

.. sourcecode:: python3
    :linenos:
    
    開啟檔案= open
    
    with 開啟檔案('一個檔案的檔名', 'w') as 我的檔案:
        我的檔案.write('你好，世界！')
        
This example writes the text Hello world! to the file example.txt. File objects have __enter__ and __exit__ method defined within them, so they act as their own context manager. First the __enter__ method is called, then the code within with statement is executed and finally the __exit__ method is called. __exit__ method is called even if there is an error. It basically closes the file stream.

yield
-------------

中文對應字： **產生**

yield is used inside a function like a return statement. But yield returns a generator. Generator is an iterator that generates one item at a time. A large list of value will take up a lot of memory. Generators are useful in this situation as it generates only one value at a time instead of storing all the values in memory. For example,


>>> g = (2**x for x in range(100))

will create a generator g which generates powers of 2 up to the number two raised to the power 99. We can generate the numbers using the next() function as shown below.

 


>>> next(g)
1
>>> next(g)
2
>>> next(g)
4
>>> next(g)
8
>>> next(g)
16

And so on… This type of generator is returned by the yield statement from a function. Here is an example.

.. sourcecode:: python3
    :linenos:
    
    def generator():
        for i in range(6):
            yield i*i

    g = generator()
    for i in g:
        print(i)
    
*Output*

.. sourcecode:: pycon

    0
    1
    4
    9
    16
    25
    
Here, the function generator() returns a generator that generates square of numbers from 0 to 5. This is printed in the for loop.

