==================
大家都來學習寫程式
==================

林口國中資優班程式教學

`教青少年寫程式.pdf <https://www.dropbox.com/s/qfj3vkz127q4xda/%E6%95%99%E9%9D%92%E5%B0%91%E5%B9%B4%E5%AF%AB%E7%A8%8B%E5%BC%8F.pdf>`__


======
小烏龜00
======

.. sourcecode:: python3
    :linenos:

    import time
    from turtle import *

    setworldcoordinates(-240,-180,240,180)
    delay(0)

    goto(0, 0)
    setheading(0)
    shape('turtle')
    color('red')

    pendown()

    write('Hello world! 我是 Python 小烏龜。')
    time.sleep(2) # 2 sec
    clear()

    for i in range(100):
        forward(200)
        left(170)
        time.sleep(0.1) # sec

    penup()

    done()

======
小烏龜01
======

.. sourcecode:: python3
    :linenos:

    """       turtle-example-suite:

                tdemo_yinyang.py

    Another drawing suitable as a beginner's
    programming example.

    The small circles are drawn by the circle
    command.

    """

    from turtle import *

    def yin(radius, color1, color2):
        width(3)
        color("black", color1)
        begin_fill()
        circle(radius/2., 180)
        circle(radius, 180)
        left(180)
        circle(-radius/2., 180)
        end_fill()
        left(90)
        up()
        forward(radius*0.35)
        right(90)
        down()
        color(color1, color2)
        begin_fill()
        circle(radius*0.15)
        end_fill()
        left(90)
        up()
        backward(radius*0.35)
        down()
        left(90)

    def main():
        reset()
        yin(200, "black", "white")
        yin(200, "white", "black")
        ht()
        return "Done!"

    if __name__ == '__main__':
        main()
        mainloop()

======
小烏龜02
======

.. sourcecode:: python3
    :linenos:

    """         turtle-example-suite:

                  tdemo_teddy.py

    A drawing sent in by a reader of
    "Python fuer Kids", just after she had
    read chapter 2, which introduces
    turtle graphics.
    """
    from turtle import *

    def main():
        mode("logo")
        speed(10)
        shape("arrow")
        pensize(3)
        circle(66)
        rt(180)
        circle(66)
        pu()
        lt(90)
        fd(33)
        rt(90)
        fd(34)
        pd()
        fillcolor("blue")
        begin_fill()
        circle(33)
        end_fill()
        pu()
        fd(15)
        lt(90)
        fd(4)
        rt(90)
        pd()
        fillcolor("black")
        begin_fill()
        circle(11)
        end_fill()
        pu()
        home()
        lt(90)
        fd(33)
        lt(90)
        fd(34)
        lt(180)
        pd()
        fillcolor("blue")
        begin_fill()
        circle(33)
        end_fill()
        pu()
        bk(15)
        rt(90)
        bk(4)
        lt(90)
        pd()
        fillcolor("black")
        begin_fill()
        circle(11)
        end_fill()
        pu()
        home()
        lt(180)
        fd(70)
        pd()
        fd(30)
        circle(30, 180)
        pu()
        rt(180)
        circle(-30, -180)
        lt(180)
        pd()
        circle(-30, 180)
        rt(180)
        circle(30, 90)
        rt(90)
        fillcolor("red")
        begin_fill()
        circle(30, 180)
        end_fill()
        pu()
        home()
        fd(80)
        rt(90)
        fd(100)
        fillcolor("brown")
        pd()
        lt(50)
        circle(-70, 200)
        pu()
        home()
        fd(80)
        lt(90)
        fd(100)
        pd()
        rt(50)
        circle(70, 200)
        pu()
        home()
        lt(90)
        fd(190)
        lt(90)
        fd(40)
        pd()
        circle(190, 180)
        pu()
        home()
        fd(80)
        pd()
        circle(50, 60)
        rt(180)
        circle(-50, 60)
        rt(180)
        circle(-60, 60)
        lt(180)
        circle(60, 60)
        lt(180)
        circle(-30, 60)
        pu()
        home()
        bk(110)
        lt(90)
        fd(20)
        pd()
        fd(1)
        pu()
        fd(19)
        pd()
        fd(1)
        pu()
        rt(180)
        fd(60)
        pd()
        fd(1)
        pu()
        fd(19)
        pd()
        fd(1)
        pu()
        rt(90)
        fd(10)
        rt(90)
        fd(10)
        pd()
        fd(1)
        pu()
        fd(60)
        pd()
        fd(1)
        pu()
        home()
        ht()
        return "DONE!"

    if __name__ == "__main__":
        msg = main()
        print(msg)
        mainloop()


======
小烏龜03
======
`傳統漢字龜模組 <https://www.dropbox.com/s/enatm4yh3fxk3dq/turtle_tc.py>`__

.. sourcecode:: python3
    :linenos:

    '''

    用漢字來做程式設計
    ==================
    呂仁園
    -------
    2014/04/24

    傳統漢字(traditional Chinese)
    龜模組(turtle module)
    下載處：

    https://www.dropbox.com/s/enatm4yh3fxk3dq/turtle_tc.py

    '''
    from turtle_tc import  *

    def 畫Teddy():

        模式(角度從北開始順時針)

        速度(10)
        形狀(龜形)

        筆大小(3)
        筆色(黑)
        下筆()
        畫圓(66)

        右轉(180)
        畫圓(66)

        提筆()
        左轉(90)
        前進(33)
        右轉(90)
        前進(34)
        下筆()
        填色(藍)

        開始填色()
        畫圓(33)
        結束填色()

        提筆()
        前進(15)
        左轉(90)
        前進(4)
        右轉(90)
        下筆()
        填色(黑)

        開始填色()
        畫圓(11)
        結束填色()

        提筆()
        回家()
        左轉(90)
        前進(33)
        左轉(90)
        前進(34)
        左轉(180)
        下筆()
        填色(藍)

        開始填色()
        畫圓(33)
        結束填色()

        提筆()
        後退(15)
        右轉(90)
        後退(4)
        左轉(90)
        下筆()
        填色(黑)

        開始填色()
        畫圓(11)
        結束填色()

        提筆()
        回家()
        左轉(180)
        前進(70)
        下筆()
        前進(30)
        畫圓(30, 180)

        提筆()
        右轉(180)
        畫圓(-30, -180)

        左轉(180)
        下筆()
        畫圓(-30, 180)

        右轉(180)
        畫圓(30, 90)

        右轉(90)
        填色(紅)

        開始填色()
        畫圓(30, 180)
        結束填色()

        提筆()
        回家()
        前進(80)
        右轉(90)
        前進(100)
        填色(黃)
        下筆()
        左轉(50)
        畫圓(-70, 200)

        提筆()
        回家()
        前進(80)
        左轉(90)
        前進(100)
        下筆()
        右轉(50)
        畫圓(70, 200)

        提筆()
        回家()
        左轉(90)
        前進(190)
        左轉(90)
        前進(40)
        下筆()
        畫圓(190, 180)

        提筆()
        回家()
        前進(80)
        下筆()
        畫圓(50, 60)

        右轉(180)
        畫圓(-50, 60)

        右轉(180)
        畫圓(-60, 60)

        左轉(180)
        畫圓(60, 60)

        左轉(180)
        畫圓(-30, 60)

        提筆()
        回家()
        後退(110)
        左轉(90)
        前進(20)
        下筆()
        前進(1)

        提筆()
        前進(19)
        下筆()
        前進(1)

        提筆()
        右轉(180)
        前進(60)
        下筆()
        前進(1)

        提筆()
        前進(19)

        下筆()
        前進(1)
        提筆()
        右轉(90)
        前進(10)

        右轉(90)
        前進(10)

        下筆()
        前進(1)

        提筆()
        前進(60)

        下筆()
        前進(1)

        提筆()
        回家()
        隱藏()

        前往(0,-200)
        筆色(紫)
        寫('大家好，我是 Teddy。')

        進入主迴圈()


    if __name__ == "__main__":

        畫Teddy()


======
小烏龜04
======

.. sourcecode:: python3
    :linenos:

    #!/usr/bin/python
    """       turtle-example-suite:

             tdemo_minimal_hanoi.py

    A minimal 'Towers of Hanoi' animation:
    A tower of 6 discs is transferred from the
    left to the right peg.

    An imho quite elegant and concise
    implementation using a tower class, which
    is derived from the built-in type list.

    Discs are turtles with shape "square", but
    stretched to rectangles by shapesize()
     ---------------------------------------
           To exit press STOP button
     ---------------------------------------
    """
    from turtle import *

    class Disc(Turtle):
        def __init__(self, n):
            Turtle.__init__(self, shape="square", visible=False)
            self.pu()
            self.shapesize(1.5, n*1.5, 2) # square-->rectangle
            self.fillcolor(n/6., 0, 1-n/6.)
            self.st()

    class Tower(list):
        "Hanoi tower, a subclass of built-in type list"
        def __init__(self, x):
            "create an empty tower. x is x-position of peg"
            self.x = x
        def push(self, d):
            d.setx(self.x)
            d.sety(-150+34*len(self))
            self.append(d)
        def pop(self):
            d = list.pop(self)
            d.sety(150)
            return d

    def hanoi(n, from_, with_, to_):
        if n > 0:
            hanoi(n-1, from_, to_, with_)
            to_.push(from_.pop())
            hanoi(n-1, with_, from_, to_)

    def play():
        onkey(None,"space")
        clear()
        hanoi(6, t1, t2, t3)
        write("press STOP button to exit",
              align="center", font=("Courier", 16, "bold"))

    def main():
        global t1, t2, t3
        ht(); penup(); goto(0, -225)   # writer turtle
        t1 = Tower(-250)
        t2 = Tower(0)
        t3 = Tower(250)
        # make tower of 6 discs
        for i in range(6,0,-1):
            t1.push(Disc(i))
        # prepare spartanic user interface ;-)
        write("press spacebar to start game",
              align="center", font=("Courier", 16, "bold"))
        onkey(play, "space")
        listen()
        return "EVENTLOOP"

    if __name__=="__main__":
        msg = main()
        print(msg)
        mainloop()

    
======
小烏龜05
======

.. sourcecode:: python3
    :linenos:
    
    '''
    ======
    河內塔
    ======

    `Tower_of_Hanoi <http://en.wikipedia.org/wiki/Tower_of_Hanoi>`__

    '''

    #from turtle import *

    from turtle_tc import *


    層數= 6

    class 盤類(龜類):

        def __init__(盤自己, n):



            龜類.__init__(盤自己, shape= 龜形, visible= False)

            盤自己.提筆()
            盤自己.形狀大小(1, n)
            盤自己.填色(n/層數, 0, 1-n/層數)
            盤自己.顯龜()

    class 塔類(list):

        def __init__(塔自己, 座標x, 塔色= 紅):

            塔自己.座標x = 座標x
            塔自己.色= 塔色

            顯龜()
            筆色(塔色)
            筆大小(5)
            提筆(); 前往(座標x, -150)
            下筆(); 前往(座標x, +150)
            提筆()
            藏龜()

        def 壓(塔自己, 盤):

            if 盤 is not None:
                盤.設座標x(塔自己.座標x)
                盤.設座標y(-150 + 30*len(塔自己))

                塔自己+= [盤]

        def 彈(塔自己):

            if len(塔自己)>0:
                盤= list.pop(塔自己)
                盤.設座標y(150)
                return 盤

    def 搬多盤(n, 來塔, 去塔, 暫塔):

        def 搬1盤(來塔, 去塔):
            盤= 來塔.彈()
            印(' '*n+'%d'%(n))
            去塔.壓(盤)

        if n == 1:
            搬1盤(來塔, 去塔)
        elif n>1:
            搬多盤(n-1, 來塔,  暫塔, 去塔)
            搬1盤(來塔, 去塔)
            搬多盤(n-1, 暫塔, 去塔, 來塔)
        else:
            pass
        return

    def 玩(x,y):

        搬多盤(層數, a塔, b塔, c塔)

        寫('點擊 X 結束。')

    def 主函數():

        global a塔, b塔, c塔

        開幕()
        標題('河內塔之龜。')

        藏龜(); 提筆(); 前往(0, -225)

        a塔= 塔類(-250,   紅)
        b塔= 塔類(   0,   綠)
        c塔= 塔類(+250,   藍)

        for n in 範圍(層數,0,-1):
            盤= 盤類(n)
            a塔.壓(盤)

        寫('在點擊幕時 玩。')

        在點擊幕時(玩)

        閉幕()

    if __name__=="__main__":

        主函數()

    