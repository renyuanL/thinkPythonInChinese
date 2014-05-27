﻿..  Copyright (C)  Peter Wentworth, Jeffrey Elkner, Allen B. Downey and Chris Meyers.
    Permission is granted to copy, distribute and/or modify this document
    under the terms of the GNU Free Documentation License, Version 1.3
    or any later version published by the Free Software Foundation;
    with Invariant Sections being Foreword, Preface, and Contributor List, no
    Front-Cover Texts, and no Back-Cover Texts.  A copy of the license is
    included in the section entitled "GNU Free Documentation License".
 
|    
    
.. index:: event, handler    
    
Event-Driven Programming
========================
事件驅動的程式設計

Most programs and devices like a cellphone respond to *events* --- things that happen.
For example, you might move your mouse, and the computer responds.  Or you click a button,
and the program does something interesting.   In this chapter we'll touch very briefly on
how event-driven programming works.

大多數程式和手持裝置，如手機，都會對*事件*有所回應，所謂事件就是指有事情發生了。 
例如，你可能移動你的滑鼠，而電腦對此要有所反應。或者你用滑鼠點擊一個螢幕上的按鈕， 
這時程式也要做一些有趣的事情。在本章中，我們將嘗試一些簡單的事件驅動的程式設計工作。


Keypress events
---------------
**按鍵盤鍵** 事件

Here's a program with some new features.  Copy it into your workspace, run it.  When the 
turtle window opens, press the arrow keys and make tess move about! 


.. sourcecode:: python3
    :linenos:

    import turtle

    turtle.setup(400,500)                # Determine the window size
    wn = turtle.Screen()                 # Get a reference to the window
    wn.title("Handling keypresses!")     # Change the window title
    wn.bgcolor("lightgreen")             # Set the background color
    tess = turtle.Turtle()               # Create our favorite turtle

    # The next four functions are our "event handlers".
    def h1():
       tess.forward(30)

    def h2():
       tess.left(45)

    def h3():
       tess.right(45)

    def h4():
        wn.bye()                        # Close down the turtle window

    # These lines "wire up" keypresses to the handlers we've defined.
    wn.onkey(h1, "Up")
    wn.onkey(h2, "Left")
    wn.onkey(h3, "Right")
    wn.onkey(h4, "q")

    # Now we need to tell the window to start listening for events,  
    # If any of the keys that we're monitoring is pressed, its 
    # handler will be called.
    wn.listen()
    wn.mainloop()    
    
.. sourcecode:: python3
    :linenos:

    import turtle                        # 引入 turtle 模組

    turtle.setup(400,500)                # 設定視窗大小為寬400, 高500
    視窗= turtle.Screen()                # 依此寬高製造視窗
    視窗.title("Handling keypresses!")   # 設定視窗主題名稱
    視窗.bgcolor("lightgreen")           # 設定視窗底色
    特斯龜= turtle.Turtle()              # 製造小烏龜，取名 特斯龜

    #
    # 首先定義幾個「事件處理函數」
    #
    def 前進():
       特斯龜.forward(30)

    def 向左():
       特斯龜.left(45)

    def 向右():
       特斯龜.right(45)

    def 關閉視窗():
        視窗.bye()                    
    #
    # 接下把幾個「事件」和「事件處理函數」連上線。
    # 在此我們選用了鍵盤的方向鍵中的
    #「上」("Up")「左」("Left")「右」("Right")和字母 "q" 等 4 個鍵，
    # 來當作「事件」
    #
    視窗.onkey(前進,    "Up")
    視窗.onkey(向左,    "Left")
    視窗.onkey(向右,    "Right")
    視窗.onkey(關閉視窗,"q")

    #
    # 叫視窗 「開始」傾聽(監控)事件發生與否
    #
    視窗.listen()
    
    #
    # 用主迴圈來不斷取得所監控的事件的資訊，
    # 若發生我們上面所定義的「事件」，
    # 就執行相對應「事件處理函數」
    #
    視窗.mainloop()   
                    
                      
     

Here are some points to note:

* We need the call to the window's ``listen`` method at line 31, otherwise it won't notice our keypresses.
* We named our handler functions ``h1``, ``h2`` and so on, but we can choose better names.  The handlers can be
  arbitrarily complex functions that call other functions, etc. 
* Pressing the ``q`` key on the keyboard calls function ``h4`` (because we `bound` the ``q`` key to ``h4`` on line 26). 
  While executing ``h4``, the window's ``bye`` method (line 24) closes the turtle window, which causes the window's 
  mainloop call (line 31) to end its execution.  Since we did not write any more statements after line 32, this means
  that our program has completed everything, so it too will terminate.  
* We can refer to keys on the keyboard by their character code (as we did in line 26), or by their symbolic names.
  Some of the symbolic names to try are Cancel (the Break key), BackSpace, Tab, Return(the Enter key), 
  Shift_L (any Shift key), Control_L (any Control key), Alt_L (any Alt key), Pause, Caps_Lock, Escape, Prior (Page Up), 
  Next (Page Down), End, Home, Left, Up, Right, Down, Print, Insert, Delete, F1, F2, F3, F4, F5, F6, F7, F8, F9, F10, 
  F11, F12, Num_Lock, and Scroll_Lock.

Mouse events
------------
滑鼠事件
 
A mouse event is a bit different from a keypress event because its handler needs two parameters
to receive x,y coordinate information telling us where the mouse was when the event occurred. 

.. sourcecode:: python3
    :linenos:
   
    import turtle

    turtle.setup(400,500)                    
    wn = turtle.Screen()                   
    wn.title("How to handle mouse clicks on the window!")  
    wn.bgcolor("lightgreen")              

    tess = turtle.Turtle()              
    tess.color("purple")
    tess.pensize(3)
    tess.shape("circle")

    def h1(x, y):
       tess.goto(x, y)

    wn.onclick(h1)  # Wire up a click on the window.
    wn.mainloop()

.. sourcecode:: python3
    :linenos:
   
    import turtle

    turtle.setup(400,500)                    
    視窗= turtle.Screen()                   
    視窗.title("How to handle mouse clicks on the window!")  
    視窗.bgcolor("lightgreen")              

    特斯龜= turtle.Turtle()              
    特斯龜.color("purple")
    特斯龜.pensize(3)
    特斯龜.shape("circle")

    def 特斯龜去滑鼠點的位置(x, y):
       特斯龜.goto(x, y)
    #
    # 把「視窗被滑鼠點擊」這個事件 
    # 和「特斯龜去滑鼠點的位置」這個「事件處理函數」
    # 連結起來。
    #
    視窗.onclick(特斯龜去滑鼠點的位置)  
    
    #
    # 進入視窗主迴圈永遠執行
    #
    視窗.mainloop()
    
There is a new turtle method used at line 14 --- this allows us to move the turtle to an *absolute*
coordinate position.  (Most of the examples that we've seen so far move the turtle *relative* to where
it currently is).   So what this program does is move the turtle (and draw a line) to wherever 
the mouse is clicked.  Try it out! 

If we add this line before line 14, we'll learn a useful debugging trick too::

    wn.title("Got click at coords {0}, {1}".format(x, y))

Because we can easily change the text in the window's title bar, it is a useful place to display
occasional debugging or status information. (Of course, this is not the real purpose of the window
title!) 

    
But there is more! 

Not only can the window receive mouse events: individual turtles can also 
have their own handlers for mouse clicks.  The turtle that 
"receives" the click event will be the one under the mouse.   So we'll create
two turtles.  Each will bind a handler to its own ``onclick`` event.  And the
two handlers can do different things for their turtles. 

.. sourcecode:: python3
    :linenos:
     
    import turtle

    turtle.setup(400,500)              # Determine the window size
    wn = turtle.Screen()               # Get a reference to the window
    wn.title("Handling mouse clicks!") # Change the window title
    wn.bgcolor("lightgreen")           # Set the background color
    tess = turtle.Turtle()             # Create two turtles
    tess.color("purple")
    alex = turtle.Turtle()             # Move them apart
    alex.color("blue")
    alex.forward(100)

    def handler_for_tess(x, y):
        wn.title("Tess clicked at {0}, {1}".format(x, y))
        tess.left(42)
        tess.forward(30)

    def handler_for_alex(x, y):
        wn.title("Alex clicked at {0}, {1}".format(x, y))
        alex.right(84)
        alex.forward(50)

    tess.onclick(handler_for_tess)
    alex.onclick(handler_for_alex)

    wn.mainloop()

  
Run this, click on the turtles, see what happens!


Automatic events from a timer
-----------------------------

Alarm clocks, kitchen timers, and thermonuclear bombs in James Bond movies are set to 
create an "automatic" event after a certain interval. The turtle module in Python has a 
timer that can cause an event when its time is up.

.. sourcecode:: python3
    :linenos:
   
    import turtle

    turtle.setup(400,500)
    wn = turtle.Screen()
    wn.title("Using a timer")
    wn.bgcolor("lightgreen")

    tess = turtle.Turtle()
    tess.color("purple")
    tess.pensize(3)

    def h1():
        tess.forward(100)
        tess.left(56)

    wn.ontimer(h1, 2000)
    wn.mainloop()
    
On line 16 the timer is started and set to explode in 2000 milliseconds (2 seconds). When the event does occur,
the handler is called, and tess springs into action.  

Unfortunately, when one sets a timer, it only goes off once. So a common idiom, or style, is to restart
the timer inside the handler.  In this way the timer will keep on giving new events.  Try this program:

.. sourcecode:: python3
    :linenos:
   
    import turtle

    turtle.setup(400,500)
    wn = turtle.Screen()
    wn.title("Using a timer to get events!")
    wn.bgcolor("lightgreen")

    tess = turtle.Turtle()
    tess.color("purple")

    def h1():
        tess.forward(100)
        tess.left(56)
        wn.ontimer(h1, 60)

    h1()
    wn.mainloop()

An example: state machines
--------------------------

A state machine is a system that can be in one of a few different `states`. We draw a 
state diagram to represent the machine, where each state is drawn as a circle or an ellipse.
Certain events occur which cause the system to leave one state and `transition` into a 
different state.  These `state transitions` are usually drawn as an arrow on the diagram.

This idea is not new: when first turning on a cellphone, it goes into a
state which we could call "Awaiting PIN".  When the correct PIN is entered, it 
transitions into a different state --- say "Ready".  Then we could lock the phone, and it
would enter a "Locked" state, and so on.

A simple state machine that we encounter often is a traffic light.  Here 
is a state diagram which shows that the machine continually cycles through three different
states, which we've numbered 0, 1 and 2.

    .. image::  illustrations/fsm_traffic_lights.png
 
We're going to build a program that uses a turtle to simulate the traffic lights.
There are three lessons here. The first shows off some different ways to use our turtles.
The second demonstrates how we would program a state machine in Python, by using a variable
to keep track of the current state, and a number of different ``if`` statements to 
inspect the current state, and take the actions as we change to a different state.
The third lesson is to use events from the keyboard to trigger the state changes.
  
Copy and run this program.  Make sure you understand what each line does, consulting the 
documentation as you need to.   
   
.. sourcecode:: python3
    :linenos:
  
    import turtle           # Tess becomes a traffic light.

    turtle.setup(400,500)
    wn = turtle.Screen()
    wn.title("Tess becomes a traffic light!")
    wn.bgcolor("lightgreen")
    tess = turtle.Turtle()

    
    def draw_housing():
        """ Draw a nice housing to hold the traffic lights """
        tess.pensize(3)
        tess.color("black", "darkgrey")
        tess.begin_fill()
        tess.forward(80)
        tess.left(90)
        tess.forward(200)
        tess.circle(40, 180)
        tess.forward(200)
        tess.left(90)
        tess.end_fill()

        
    draw_housing()

    tess.penup()
    # Position tess onto the place where the green light should be
    tess.forward(40)
    tess.left(90)
    tess.forward(50)
    # Turn tess into a big green circle
    tess.shape("circle")
    tess.shapesize(3)
    tess.fillcolor("green")

    # A traffic light is a kind of state machine with three states,
    # Green, Orange, Red.  We number these states  0, 1, 2
    # When the machine changes state, we change tess' position and
    # her fillcolor. 

    # This variable holds the current state of the machine
    state_num = 0


    def advance_state_machine():
        global state_num
        if state_num == 0:       # Transition from state 0 to state 1
            tess.forward(70)
            tess.fillcolor("orange")
            state_num = 1
        elif state_num == 1:     # Transition from state 1 to state 2
            tess.forward(70)
            tess.fillcolor("red")
            state_num = 2
        else:                    # Transition from state 2 to state 0
            tess.back(140)
            tess.fillcolor("green")
            state_num = 0

    # Bind the event handler to the space key.
    wn.onkey(advance_state_machine, "space")  

    wn.listen()                      # Listen for events
    wn.mainloop()

The new Python statement is at line 46.  The ``global`` keyword tells Python not to 
create a new local variable for ``state_num`` (in spite of the fact that 
the function assigns to this variable at lines 50, 54, and 58).  Instead, in this function, 
``state_num`` always refers to the variable that was created at line 42.

What the code in ``advance_state_machine`` does is advance from whatever
the current state is, to the next state.  On the state change we move tess 
to her new position, change her color, and, of course, we assign to ``state_num`` 
the number of the new state we've just entered. 

Each time the space bar is pressed, the event handler causes the traffic light
machine to move to its new state.


* 本中文程式需使用改自 turtle 的模組  `烏龜世界 <https://www.dropbox.com/s/wblg8pojtfh0tvu/烏龜世界.py>`__

.. sourcecode:: python3
    :linenos: 

    import 烏龜世界

    螢幕= 烏龜世界.螢幕類()

    螢幕.設立(500,500)
    螢幕.標題("特斯龜 變成紅綠燈！")
    螢幕.背景色("lightblue")

    特斯龜= 烏龜世界.烏龜類()
    特斯龜.形狀("turtle")

    def 龜畫外框():

        特斯龜.筆粗(3)
        特斯龜.顏色("black", "gray")

        特斯龜.開始填色()
        特斯龜.前進(80)
        特斯龜.左轉(90)
        特斯龜.前進(200)
        特斯龜.畫圓(40, 180)
        特斯龜.前進(200)
        特斯龜.左轉(90)
        特斯龜.結束填色()

    def 龜變綠燈():

        特斯龜.形狀("circle")
        特斯龜.形狀尺寸(3)

        特斯龜.提筆()

        特斯龜.前進(40)
        特斯龜.左轉(90)
        特斯龜.前進(50)

        特斯龜.填色("green")


    目前狀態= 0

    def 改變狀態():

        global 目前狀態

        if 目前狀態 == 0:

            特斯龜.前進(70)
            特斯龜.填色("yellow")
            目前狀態= 1

        elif 目前狀態 == 1:

            特斯龜.前進(70)
            特斯龜.填色("red")
            目前狀態= 2

        else:

            特斯龜.後退(140)
            特斯龜.填色("green")
            目前狀態= 0


    龜畫外框()

    龜變綠燈()

    螢幕.當按下鍵盤時(改變狀態)

    螢幕.傾聽()

    螢幕.運轉()





 
    
Glossary
--------

.. glossary::

    bind
        We bind a function (or associate it) with an event, meaning that when the event occurs, the
        function is called to handle it.        

    event
        Something that happens "outside" the normal control flow of our program, usually from some user action.
        Typical events are mouse operations and keypresses.  We've also seen that a timer can be primed 
        to create an event.

    handler
        A function that is called in response to an event.  


Exercises
---------


#. Add some new key bindings to the first sample program:
   
   * Pressing keys R, G or B should change tess' color to Red, Green or Blue.
   * Pressing keys + or - should increase or decrease the width of tess' pen.  
     Ensure that the pen size stays between 1 and 20 (inclusive).  
   * Handle some other keys to change some attributes of tess, or attributes of the window, 
     or to give her new behaviour that can be controlled from the keyboard. 
 
#.  Change the traffic light program so that changes occur automatically, driven by a timer.

#.  In an earlier chapter we saw two turtle methods, ``hideturtle`` and ``showturtle`` that 
    can hide or show a turtle.  This suggests that we could take a different approach to 
    the traffic lights program.  Add to your program above as follows:  draw a second
    housing for another set of traffic lights.  Create three separate 
    turtles to represent each of the green, orange and red lights, and position them appropriately
    within your new housing.  As your state changes occur, just make one of the three turtles visible
    at any time. Once you've made the changes, sit back and ponder some deep thoughts: you've now got
    two different ways to use turtles to simulate the traffic lights, and both seem to work. 
    Is one approach somehow preferable to the other?  Which one more closely resembles reality --- 
    i.e. the traffic lights in your town?    
    
#.  Now that you've got a traffic light program with different turtles for each light, perhaps
    the visibility / invisibility trick wasn't such a great idea. If we watch traffic lights, they 
    turn on and off --- but when they're off they are still there, perhaps just a darker color.
    Modify the program now so that the lights don't disappear: they are either on, or off. But when
    they're off, they're still visible.
    
#.  Your traffic light controller program has been patented, and you're about to 
    become seriously rich.  But your new client needs a change.  They want 
    four states in their state machine: Green, then Green and Orange together, 
    then Orange only, and then Red.  Additionally, they want different
    times spent in each state.  The machine should spend 3 seconds in the Green state, 
    followed by one second in the Green+Orange state, then one second in 
    the Orange state, and then 2 seconds in the Red state.  
    Change the logic in the state machine. 
    
#.  If you don't know how tennis scoring works, ask a friend or consult Wikipedia.  A single
    game in tennis between player A and player B always has a score.  We want to think
    about the "state of the score" as a state machine.   The game starts in state (0, 0), meaning 
    neither player has any score yet.  We'll assume the first element in this pair is the score
    for player A.   If player A wins the first point, the score becomes (15, 0).  
    If B wins the first point, the state becomes (0, 15).  Below are the first 
    few states and transitions for a state diagram. In this diagram, each state 
    has two possible outcomes (A wins the next point, or B does), and the 
    uppermost arrow is always the transition that happens when A wins the point. 
    Complete the diagram, showing all transitions and all states.  
    (Hint: there are twenty states, if you include the duece state, the advantage states, 
    and the "A wins" and "B wins" states in your diagram.)
    
    .. image::  illustrations/fsm_tennis_scores.png
    
