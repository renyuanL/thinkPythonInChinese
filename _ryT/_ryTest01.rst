==================
大家都來學習寫程式
==================

林口國中資優班程式教學
----------------------

+ 學生作品展示

    + `ryTemp2014_001 <http://scratch.mit.edu/users/ryTemp2014_001>`__

    + `lyukehong12 <http://scratch.mit.edu/users/lyukehong12>`__

+ 我的簡報

    + `教青少年寫程式.pptx <https://www.dropbox.com/s/yu8q65hm53a9we6/教青少年寫程式.pptx>`__

    + `教青少年寫程式.pdf <https://www.dropbox.com/s/qfj3vkz127q4xda/教青少年寫程式.pdf>`__

+ 程式範例

    + `教青少年寫程式ex001.py <https://www.dropbox.com/s/yxk299gvcuao6au/教青少年寫程式ex001.py>`__

    + `教青少年寫程式ex002_解方程式.py <https://www.dropbox.com/s/uswb9cxmwl7uab6/教青少年寫程式ex002_解方程式.py>`__

    + `教青少年寫程式ex002_解方程式01.py <https://www.dropbox.com/s/e40hadlc5u3cjkx/教青少年寫程式ex002_解方程式01.py>`__

+ 方便印成紙本

    + `教青少年寫程式ex001.pdf <https://www.dropbox.com/s/epvwgxmz5oj0idx/教青少年寫程式ex001.pdf>`__

    + `教青少年寫程式ex002_解方程式.pdf <https://www.dropbox.com/s/584oa7bexdrbqzt/教青少年寫程式ex002_解方程式.pdf>`__

    + `教青少年寫程式ex002_解方程式01.pdf <https://www.dropbox.com/s/osb3bhpbu9celnr/教青少年寫程式ex002_解方程式01.pdf>`__

+ 一組有趣的小烏龜程式

    + `ryTdemo20140409.zip <https://www.dropbox.com/s/uwa273vl0ubjni3/ryTdemo20140409.zip>`__

==============
Python程式語言很簡單
==============
.. sourcecode:: python3
    :linenos:

    '''
    ryPython程式語言很簡單001.py
    '''

    #
    # 變數 x, y, z
    # 指定 =
    # 運算 +, -, *, /, **, //, %, ( )
    #

    x= 10
    y= 20
    x+y
    z= x+y

    u= (x+y)*z/(x**2//3%4)

    #
    # print, 印, 中文別名
    #

    print(u)

    印= print
    印(u)

    #
    # if 條件 :
    #

    x= 10
    if x<100:
       印(x)

    #
    # 條件， <, <=, >, >=, !=, ==
    # 真假值  (True/False)
    # 運算 and, or, not
    #

    if (x>=10) and (y<20):
       印(x,y)
    elif (x != 3):
         印(z)
    else:
         印(u)

    #
    # 函數 def f():
    #

    def f():
        x= 10
        y= 20
        x+y
        z= x+y

        u= (x+y)*z/(x**2//3%4)

        print(u)

        印= print
        印(u)

    f()

    函數= f

    函數()

    #
    # 迴圈 for ~ :
    #

    for i in range(10):
        印(i)

    範圍= range

    for i in 範圍(10):
        印(i)

    #
    # 迴圈 while ~ :
    #

    x= 10
    while x<100:
          印(x)
          x= x+10

    #
    # 物類 class 名稱為 C， 「慣例」是以 大寫字母為開頭。
    #

    class C:
          '''
          這是一個物類，名稱為 C
          '''
          def __init__(self, x=100):
              '''
              函數名: __init__
              參數: x
              '''
              self.x= x

          def printme(self):
              '''
              函數名: printme | 印我
              參數:
              '''
              print(self, self.x)
          #
          # class 內部方法(也是一種函數) 的中文別名
          #
          印我= printme

    #
    # class 的中文別名
    #

    物類= C

    #
    # class 的使用
    #
    c= C(1000)
    c.printme()

    物件= 物類(2000)
    物件.印我()

        

==============
列出 99 乘法表
==============

.. sourcecode:: python3
    :linenos:

    '''
    ryTutor2014_99乘法表.py

    列出 99 乘法表

    計算數字累加

    看看電腦多快

    '''

    #
    # 翻譯成中文函數名稱
    #

    印=      print

    #
    # 程式由此開始
    #

    for x in [1,2,3,4,5,6,7,8,9]:

        印(x,'-------------------')

        for y in [1,2,3,4,5,6,7,8,9]:

            印(x,' * ',y,' = ',x*y)


    #
    # 列出 0 ~ 100 的數字
    #
    for x in [0,1,2,3,4,5,6,7,8,9,10,11,12,13,14,15,16,17,18,19,20,100]:
        印(x)
    #
    # 列表太長，寫不完，怎麼辦？
    #
    數字列表0到100= list(range(0,101))
    
    for x in 數字列表0到100:
        印(x)

    #
    # 翻譯成中文函數名稱
    #
    範圍= range

    for x in 範圍(0,101):
        印(x)

    #
    # 計算 0 ~ 100 加起來的總和
    #

    s= 0
    for x in 範圍(0,101):
        s= s + x
    印('計算 0 ~ 100 加起來的總和= ',s)

    #
    # 計算 0 ~ 100 個別平方加起來的總和
    #

    s= 0
    for x in 範圍(0,101):
        s= s + x**2
    印('計算 0 ~ 100 個別平方加起來的總和= ',s)

    #
    # 看看電腦有多快？
    #

    #
    # 引入 他人寫的「程式模組」， time
    #
    #

    import time

    #
    # 在 time 程式模組中，有個函數叫做 time(), 全名就叫做 time.time()
    # 把它翻譯成中文函數名稱
    #
    取現在時間= time.time


    N=1000000 # 1,000,000 = 1 million (百萬)

    開始時間= 取現在時間()

    s= 0
    for x in 範圍(0,N+1):
        s= s + x**2

    結束時間= 取現在時間()

    所花時間= 結束時間- 開始時間

    印('計算 0 ~ N 個別平方加起來的總和= ', s)
    印('所花時間 (秒數)== ', 所花時間)


===================    
列出 100 以內的質數
===================    

.. sourcecode:: python3
    :linenos:

    '''
    ryTutor2014_isPrime.py
    列出 100 以內的質數
    '''

    #
    # 翻譯中文函數名稱
    #

    印=      print
    範圍=    range

    def 判斷是否為質數(x):

        它是質數嗎= True

        for n in 範圍(2, x):

            r= x % n     # x 除以 n 取餘數 r

            if r == 0:
               它是質數嗎= False
               break

        答案= 它是質數嗎

        return 答案

    質數列= []

    for x in 範圍(2,101):

        答案= 判斷是否為質數(x)

        if 答案 == True:
           質數列= 質數列 + [x]

    印(質數列)

======
小烏龜
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

==========================================
小烏龜，懂一點數學函數圖形，和隨機變數了。
==========================================

.. sourcecode:: python3
    :linenos:

    '''
    ryEx00 -- demo how to use

    math
    random
    turtle

    http://docs.python.org/3.3/library/math.html
    http://docs.python.org/3.3/library/random.html#module-random
    http://docs.python.org/3.3/library/turtle.html#module-turtle
    '''


    import math
    import random
    import turtle

    '''
    dir(math)
    dir(random)
    dir(turtle)

    help(math)
    help(random)
    help(turtle)
    '''

    from math import *
    from random import *
    from turtle import *

    W= 100
    setworldcoordinates(-W,-W,+W,+W)

    goto(-W,-W)
    write('我是小烏龜，我會畫圖，而且我懂數學，')

    home()
    clear()
    goto(-W,-W)
    write('sin(x)*10')
    for t in range(-W,W+1):
        x= t/pi/2
        y= sin(x)*10
        goto(x,y)

    home()
    clear()
    goto(-W,-W)
    write('random()*W')
    for t in range(-W,W+1):
        x= random()*W
        y= random()*W
        goto(x,y)

    home()
    clear()
    goto(-W,-W)
    write('uniform(-W,W)')
    for t in range(-W,W+1):
        x= uniform(-W,W)
        y= uniform(-W,W)
        goto(x,y)

    home()
    clear()
    goto(-W,-W)
    write('normalvariate(0,30)')
    for t in range(-W,W+1):
        x= normalvariate(0,30)
        y= normalvariate(0,30)
        goto(x,y)

    home()
    clear()
    shape('turtle')
    color('red')

    write('''
    我是小烏龜，我會畫圖，而且我懂數學，
    我用隨機顏色，用高斯隨機變數畫點。
    color(random(),random(),random())
    gauss(0,30)
    ''')

    for t in range(-W,W+1):
        x= gauss(0,30)
        y= gauss(0,30)
        penup()
        goto(x,y)
        color(random(),random(),random())
        dot()

    done()


    
=======================
艾力龜環遊烏龜世界100天
=======================

你要下載 `turtle_tc.py <https://www.dropbox.com/s/enatm4yh3fxk3dq/turtle_tc.py>`__，


把它與 艾力龜環遊烏龜世界100天.py 放在同個目錄。
或放在 C:\\Python33\\Lib\\ 這個 python 的標準模組庫中

.. sourcecode:: python3
    :linenos:
    
    #
    # 艾力龜環遊烏龜世界100天.py
    #

    import turtle_tc as 烏龜世界
    from random import random as 隨機數0到1

    #
    # 艾力龜誕生於烏龜世界，屬於烏龜類。
    #
    艾力龜= 烏龜世界.烏龜類()

    #
    # 艾力龜可以自由選擇形狀和顏色
    #
    艾力龜.形狀('turtle')
    艾力龜.顏色(1,0,0) # 1,0,0 是紅色；0,1,0 是綠色；0,0,1 是藍色；

    #
    # 艾力龜會寫(文字和數字)
    #
    艾力龜.寫('大家好，我是艾力龜，我要去環遊烏龜世界。')

    #
    # 艾力龜要去環遊烏龜世界 100 天，日子從 0 開始。
    #

    i= 0

    while i<100: # 每天一直玩，直到第 100 天時，不再遊玩，直接回家。

        #
        # 每天，艾力龜都隨意改變自己的顏色
        #
        x= 隨機數0到1()
        y= 隨機數0到1()
        z= 隨機數0到1()

        艾力龜.顏色(x,y,z) # 顏色分「紅綠藍」，各數值隨意從 0 到 1。

        #
        # 他也寫下到了第幾天。
        #
        艾力龜.寫(i)

        #
        # 然後，它隨意決定要前進幾步、畫多大的圓，左轉幾度。
        #
        艾力龜.前進(x*100)
        艾力龜.畫圓(y*10)
        艾力龜.左轉(z*360)

        #
        # 然後太陽下山，日字又過了 1 天。
        #
        i= i+1
    #
    # 到了 100 天之後，艾力龜終於必須要回家了。
    #
    艾力龜.回家()

    #
    # 回到家之後，艾力龜畫了一個大大的圓。
    #
    艾力龜.畫圓(100)

    #
    # 最後寫下一句感言。
    #
    艾力龜.寫('我回家了，艾力龜環遊世界 100 天。')

    #
    # 烏龜世界 繼續 不斷 運轉著。
    #
    烏龜世界.主迴圈()

    #
    # 除非你按下毀滅之鍵。(在烏龜世界視窗右上角那個 X)
    #





====================
求二元一次方程式的解
====================

* `參考 Wikipedia <http://en.wikipedia.org/wiki/Cramer%27s_rule>`__

.. image:: http://upload.wikimedia.org/math/0/2/2/022647cdad8949b0bca936f79556ce61.png
-----

.. image:: http://upload.wikimedia.org/math/0/a/0/0a024897bdd245a3bfcafdbcf22ffa10.png
-----

.. image:: http://upload.wikimedia.org/math/b/6/2/b628451a72054ca40c6ca96c57029697.png
-----

.. sourcecode:: python3
    :linenos:    
    
    #
    #
    # ryCramerRule.py
    #
    # 求二元一次方程式的解，
    #
    # 運用 克拉瑪 公式 (Cramer's rule)
    #
    # http://en.wikipedia.org/wiki/Cramer%27s_rule
    #


    說明='''

    解二元一次方程式：

    a x + b y = e
    c x + d y = f

    請輸入
    a, b, e
    c, d, f

    '''

    print(說明)

    #
    # 首先要取得使用者輸入，
    # 目前沒有預防措施，
    # 也就是使用者要與本程式合作，
    # 照我們所說來輸入。
    #
    # 否則，本程式會當掉！
    # 不好意思。
    #

    輸入字串= input('a, b, e, c, d, f= ? (以空白隔開 6 個數字) ')
    輸入列表= 輸入字串.split()
    a, b, e, c, d, f= [float(x) for x in 輸入列表]

    #
    # 數學公式由此開始
    #
    行列式=  a*d - b*c
    行列式x= e*d - b*f
    行列式y= a*f - e*c

    if 行列式 != 0:

       解x= 行列式x / 行列式
       解y= 行列式y / 行列式

    if 行列式 == 0:

       if 行列式x == 0 and 行列式y == 0:
          解x= 解y= '任意數'
       else:
            解x= 解y= '無解'

    結果='''

    二元一次方程式

    %f x + %f y = %f
    %f x + %f y = %f

    其解如下：

    x = %s
    y = %s

    '''%(a,b,e,c,d,f, str(解x),str(解y))

    print(結果)

    
    #
    #  ex01
    # 請寫一段程式碼來驗算答案。
    #
    
    #
    #  ex02
    # 能否推廣到 三元一次方程式。
    #
    # a x + b y + c z = j
    # d x + e y + f z = k
    # g x + h y + i z = l
    #

    #
    #  ex03
    # 檢查使用者的輸入是否合法，阻擋不合法的輸入。
    #
    # 比如說我們叫他輸入 6 個數字，用空白隔開，
    #
    # 他有沒有照做？
    #
    # 他如果輸入 7 個 或 5 個 怎麼辦？
    # 我們叫他用空白隔開，萬一他用別的符號，比如說逗點，怎麼辦？
    # 我們叫他輸入數字，萬一他打錯，輸入一些 abcd，怎麼辦？
    #
    # 其實我們很難百分之百預測使用者會如何「整」我們的程式，
    #
    # 所以，程式設計其實是一項藝術，永遠可以更好，永無止境。
    #    

====================
井字棋， Tic-Tac-Toe
====================
`參考 <http://zh.wikipedia.org/wiki/井字棋>`__

.. image:: http://upload.wikimedia.org/wikipedia/commons/thumb/1/1b/Tic-tac-toe-game-1.svg/479px-Tic-tac-toe-game-1.svg.png


.. sourcecode:: python3
    :linenos:
            
    '''
    ry2014_Tictactoe_c05.py

    井字棋， Tic-Tac-Toe

    運用人工智慧，教電腦下井字棋。
    然後叫他與玩家走棋。

    這據說是Bill Gates 13 歲時，
    用 BASIC 寫過的第一支遊戲程式。

    adapted from tictactoe.py
    This code can be downloaded
    from http://inventwithpython.com/tictactoe.py
    '''
    import random

    class 井字棋:

        def __init__(它, 電腦棋力= 0):

            它.棋盤=[' ']*10
            #
            #
            # 運用數字1-9形成井字，當作棋盤，
            # 並運用數字鍵盤1-9來輸入。
            #
            # [7,8,9]
            # [4,5,6]
            # [1,2,3]
            #
            # [0] 不用
            #
            #
            它.玩家='O'
            它.電腦='X'

            它.電腦棋力= 電腦棋力 # 幼稚園=0,小學=1,國中=2,高中=3

            它.玩家得分= 0
            它.電腦得分= 0
            它.和棋次數= 0

            它.玩家棋步=[]
            它.電腦棋步=[]

        def 更新棋盤(它):

            它.棋盤=[' ']*10

            它.玩家棋步=[]
            它.電腦棋步=[]

        def 畫出棋盤(它):

            n= 10 -它.棋盤.count(' ')
            print('第',n,'步 ','='*10)

            print(它.棋盤[7:10])
            print(它.棋盤[4:7])
            print(它.棋盤[1:4])

        def 決定走棋者(它):

            誰= [它.玩家,它.電腦][random.randint(0,1)] # 隨機決定
            它.說(誰, '先走！')
            return 誰

        def 更換走棋者(它, 誰):

            if 誰==它.玩家:
                return 它.電腦
            else:
                return 它.玩家

        def 走棋(它, 誰, 位置):

            #它.說(誰,' 走棋在 ',位置)
            它.棋盤[位置]= 誰

        def 紀錄棋步(它, 誰, 位置):

            if 誰== 它.玩家:
                它.玩家棋步.append(位置)
            elif 誰== 它.電腦:
                它.電腦棋步.append(位置)
            else:
                pass

        def 印出棋步(它):

            print('玩家棋步= ', 它.玩家棋步)
            print('電腦棋步= ', 它.電腦棋步)

        def 判斷是否有人贏了(它, 誰):

            贏棋位置= [ (1,2,3),
                        (4,5,6),
                        (7,8,9),
                        (1,4,7),
                        (2,5,8),
                        (3,6,9),
                        (1,5,9),
                        (3,5,7)]

            ans= any([all([(它.棋盤[y]==誰) for y in x]) for x in 贏棋位置])

            return ans

        def 對贏者加分(它, 誰):

            if 誰==它.玩家:
                它.玩家得分 += 1
            elif 誰==它.電腦:
                它.電腦得分 += 1
            else:
                pass

        def 判斷是否和棋(它):

            ans= (它.棋盤.count(' ')<=1)
            return ans

        def 判斷是否此位置可走(它,位置):

            ans= (位置 in range(1,10)) and (它.棋盤[位置]==' ')
            return ans

        def 取得玩家走棋位置(它):

            def 取得數字按鍵1到9的數字():
                x= input('請玩家 %s 輸入走棋位置(1-9)'%它.玩家)
                while x not in ['1','2','3','4','5','6','7','8','9']:
                    x= input('請玩家 %s 輸入走棋位置(1-9)'%它.玩家)
                x= int(x)
                return x

            x= 取得數字按鍵1到9的數字()
            while 它.判斷是否此位置可走(x)==False:
                x= 取得數字按鍵1到9的數字()

            return x

        def 算出電腦走棋位置00(它):  # 幼稚園大班程度
            '''
            要知道哪裡能走，人家或自己走過的就不能再走了。
            '''
            x= random.randint(1,9)
            while 它.判斷是否此位置可走(x)==False:
                x= random.randint(1,9)
            return x

        def 算出電腦走棋位置01(它):  # 小學程度
            '''
            要知道人家走哪裡會贏，要去堵他。
            '''

            #
            # 複製棋盤來模擬
            #
            # 其實是保留 它.棋盤 的複製品「原始比賽棋盤」放在一旁，
            # 然後在 它.棋盤 上沙盤推演。
            # 最後在回復 它.棋盤 為 「原始比賽棋盤」
            #

            原始比賽棋盤= 它.棋盤[:]

            #算出玩家會贏的位置
            誰=  它.玩家
            ans= False
            x= 0
            for y in range(1,10):
                if 它.判斷是否此位置可走(y)==True:
                    它.走棋(誰, y)  # 假裝自己是玩家來走棋
                    ans= 它.判斷是否有人贏了(誰)
                    它.棋盤[y]= ' ' # 擦掉自己假裝的走棋
                    if ans==True:
                        x= y
                        break
            # 回復棋盤
            它.棋盤= 原始比賽棋盤[:]

            if x==0: # 這次玩家不會贏
                x= random.randint(1,9)
                while 它.判斷是否此位置可走(x)==False:
                    x= random.randint(1,9)
            return x
            pass

        def 算出電腦走棋位置02(它): # 國中程度
            '''
            1. 優先走自己會贏的位置
            2. 其次堵對方會贏的位置
            3. 走中間 [5]
            4. 走角位 [1,3,7,9]
            5. 走邊位 [2,4,6,8]
            6. 走沒人走過的地方
            '''
            #
            # 複製棋盤來模擬
            #
            # 其實是保留 它.棋盤 的複製品「原始比賽棋盤」放在一旁，
            # 然後在 它.棋盤 上沙盤推演。
            # 最後在回復 它.棋盤 為 「原始比賽棋盤」
            #
            原始比賽棋盤= 它.棋盤[:]

            #算出電腦自己會贏的位置
            誰=  它.電腦
            ans= False
            x= 0
            for y in range(1,10):
                if 它.判斷是否此位置可走(y)==True:
                    它.走棋(誰, y)  # 假裝自己是電腦來走棋
                    ans= 它.判斷是否有人贏了(誰)
                    它.棋盤[y]= ' ' # 擦掉自己假裝的走棋
                    if ans==True:
                        x= y
                        break

            if ans==True: # 這步電腦會贏
                # 回復棋盤
                它.棋盤= 原始比賽棋盤[:]
                return x  # 就走這步了

            # 這步電腦不會贏

            #算出玩家會贏的位置
            誰=  它.玩家
            ans= False
            x= 0
            for y in range(1,10):
                if 它.判斷是否此位置可走(y)==True:
                    它.走棋(誰, y)  # 假裝自己是玩家來走棋
                    ans= 它.判斷是否有人贏了(誰)
                    它.棋盤[y]= ' ' # 擦掉自己假裝的走棋
                    if ans==True:
                        x= y
                        break
            if ans==True: # 這步玩家會贏
                # 回復棋盤
                它.棋盤= 原始比賽棋盤[:]
                return x  # 就走這步了

            # 這步玩家不會贏

            # 回復棋盤
            它.棋盤= 原始比賽棋盤[:]

            # 優先下中間 [5]
            # 其次 [1,3,7,9]
            # 最後 [2,4,6,8]
            y=5
            if 它.判斷是否此位置可走(y)==True:
                x=y
                return x  # 就走這步了
            for y in [1,3,7,9]:
                if 它.判斷是否此位置可走(y)==True:
                    x=y
                    return x  # 就走這步了
                    #break
            for y in [2,4,6,8]:
                if 它.判斷是否此位置可走(y)==True:
                    x=y
                    return x  # 就走這步了
                    #break


            if x==0: # 預防措施，上面都沒考慮到的，就隨便走一步。
                x= random.randint(1,9)
                while 它.判斷是否此位置可走(x)==False:
                    x= random.randint(1,9)
            return x  # 就走這步了

        def 算出電腦走棋位置03(它): # 高中程度
            '''
            增加「雙殺」的能力
            當電腦自己走中間[5]，
            而玩家走邊位[2,4,6,8]時，
            電腦應走[(1,3), (1,7), (3,9), (7,9)]
            則必贏。
            '''
            # 還沒完成

            # 先引入國中程度

            '''
            1. 優先走自己會贏的位置
            2. 其次堵對方會贏的位置
            3. 走中間 [5]
            4. 走角位 [1,3,7,9]
            5. 走邊位 [2,4,6,8]
            6. 走沒人走過的地方
            '''
            #
            # 複製棋盤來模擬
            #
            # 其實是保留 它.棋盤 的複製品「原始比賽棋盤」放在一旁，
            # 然後在 它.棋盤 上沙盤推演。
            # 最後在回復 它.棋盤 為 「原始比賽棋盤」
            #
            原始比賽棋盤= 它.棋盤[:]

            #算出電腦自己會贏的位置
            誰=  它.電腦
            ans= False
            x= 0
            for y in range(1,10):
                if 它.判斷是否此位置可走(y)==True:
                    它.走棋(誰, y)  # 假裝自己是電腦來走棋
                    ans= 它.判斷是否有人贏了(誰)
                    它.棋盤[y]= ' ' # 擦掉自己假裝的走棋
                    if ans==True:
                        x= y
                        break

            if ans==True: # 這步電腦會贏
                # 回復棋盤
                它.棋盤= 原始比賽棋盤[:]
                return x  # 就走這步了

            # 這步電腦不會贏

            #算出玩家會贏的位置
            誰=  它.玩家
            ans= False
            x= 0
            for y in range(1,10):
                if 它.判斷是否此位置可走(y)==True:
                    它.走棋(誰, y)  # 假裝自己是玩家來走棋
                    ans= 它.判斷是否有人贏了(誰)
                    它.棋盤[y]= ' ' # 擦掉自己假裝的走棋
                    if ans==True:
                        x= y
                        break
            if ans==True: # 這步玩家會贏
                # 回復棋盤
                它.棋盤= 原始比賽棋盤[:]
                return x  # 就走這步了

            # 這步玩家不會贏

            # 回復棋盤
            它.棋盤= 原始比賽棋盤[:]

            # 優先下中間 [5]
            # 其次 [1,3,7,9]
            # 最後 [2,4,6,8]
            y=5
            if 它.判斷是否此位置可走(y)==True:
                x=y
                return x  # 就走這步了

            #
            # 在此接入高中智商
            #
            # 雙殺必勝，在第 3 步時執行 (11-3=8)
            #
            if (它.棋盤[5]== 它.電腦) and (它.棋盤.count(' ')==8):
                if 它.棋盤[2]== 它.玩家:
                    for y in [1,3]:
                        if 它.判斷是否此位置可走(y)==True:
                            x=y
                            return x
                if 它.棋盤[4]== 它.玩家:
                    for y in [1,7]:
                        if 它.判斷是否此位置可走(y)==True:
                            x=y
                            return x
                if 它.棋盤[6]== 它.玩家:
                    for y in [3,9]:
                        if 它.判斷是否此位置可走(y)==True:
                            x=y
                            return x
                if 它.棋盤[8]== 它.玩家:
                    for y in [7,9]:
                        if 它.判斷是否此位置可走(y)==True:
                            x=y
                            return x
            #
            # 被呂可名看出某破綻，對付一下。
            #
            # 在第4步時 (11-4=7)，如果電腦在中間 [5] 被玩家用 2角位[1,9] [3,7]包夾，千萬不能再走角位，
            # 必須走邊位 [2,4,6,8]
            #
            死步= 0

            if (它.棋盤[5]== 它.電腦) and (它.棋盤.count(' ')==7):

                if(    (它.棋盤[1]== 它.玩家 and 它.棋盤[9]== 它.玩家)
                    or (它.棋盤[3]== 它.玩家 and 它.棋盤[7]== 它.玩家)):
                    邊位= [2,4,6,8]
                    random.shuffle(邊位)
                    for y in 邊位:
                        if 它.判斷是否此位置可走(y)==True:
                            x=y
                            return x

                if(它.棋盤[2]== 它.玩家 and 它.棋盤[7]== 它.玩家):
                    死步= 9
                elif(它.棋盤[2]== 它.玩家 and 它.棋盤[9]== 它.玩家):
                    死步= 7
                elif(它.棋盤[4]== 它.玩家 and 它.棋盤[3]== 它.玩家):
                    死步= 9
                elif(它.棋盤[4]== 它.玩家 and 它.棋盤[9]== 它.玩家):
                    死步= 3
                elif(它.棋盤[6]== 它.玩家 and 它.棋盤[1]== 它.玩家):
                    死步= 7
                elif(它.棋盤[6]== 它.玩家 and 它.棋盤[7]== 它.玩家):
                    死步= 1
                elif(它.棋盤[8]== 它.玩家 and 它.棋盤[1]== 它.玩家):
                    死步= 3
                elif(它.棋盤[8]== 它.玩家 and 它.棋盤[3]== 它.玩家):
                    死步= 1
                else:
                    pass
            #
            # 加了上述規則，防了一部份漏洞，
            # 但仍然被呂可名破，可見還有更複雜的邏輯需要思考，先暫停一下。
            #

            #
            # 回到國中程度，但加上 random.shuffle()
            #
            #
            邊位= [2,4,6,8]
            角位= [1,3,7,9]
            random.shuffle(角位)
            random.shuffle(邊位)
            for y in 角位:
                if 它.判斷是否此位置可走(y)==True and y!=死步:
                    x=y
                    return x  # 就走這步了
                    #break
            for y in 邊位:
                if 它.判斷是否此位置可走(y)==True and y!=死步:
                    x=y
                    return x  # 就走這步了
                    #break


            if x==0: # 預防措施，上面都沒考慮到的，就隨便走一步。
                x= random.randint(1,9)
                while 它.判斷是否此位置可走(x)==False:
                    x= random.randint(1,9)
            return x  # 就走這步了
            pass

        def 算出電腦走棋位置(它, 棋力= None):
            '''
            這是主要人工智慧所在，
            分階段來呈現。
            算出電腦走棋位置00(它):  # 幼稚園程度
            算出電腦走棋位置01(它):  # 小學程度
            算出電腦走棋位置02(它):  # 國中程度
            算出電腦走棋位置03(它):  # 高中程度
            '''
            if 棋力== None:
                棋力= 它.電腦棋力

            if 棋力==0:
                x= 它.算出電腦走棋位置00()
            elif 棋力==1:
                x= 它.算出電腦走棋位置01()
            elif 棋力==2:
                x= 它.算出電腦走棋位置02()
            elif 棋力==3:
                x= 它.算出電腦走棋位置03()
            else:
                x= 它.算出電腦走棋位置00()
            return x

        def 詢問是否再玩一次(它):

            ans= input('是否再玩一次? (y/n)')
            if ans in ['y','Y']:
                return True
            else:
                return False

        def 說(它,*話):

            print(*話)
            # 那個 * 允許多個參數一起丟進來，
            # 像是 說(x1, x2, x3,...),
            # 若沒有那個 *, 則只能 說(x1)

        def 玩(它):
            '''
            這是主遊戲控制流程。
            '''

            再玩一次= 它.詢問是否再玩一次()

            while 再玩一次:

                它.更新棋盤()
                它.畫出棋盤()
                誰= 它.決定走棋者()

                遊戲還在玩= True
                while 遊戲還在玩:

                    if 誰==它.玩家:
                        位置= 它.取得玩家走棋位置()
                    else:
                        位置= 它.算出電腦走棋位置()

                    它.走棋(誰, 位置)

                    它.說(誰,' 走棋在 ',位置)

                    它.畫出棋盤()

                    它.紀錄棋步(誰, 位置)


                    有人贏了= 它.判斷是否有人贏了(誰)
                    和棋=     它.判斷是否和棋()

                    if 有人贏了:
                        它.說('恭喜「',誰,'」贏了。')
                        它.對贏者加分(誰)
                        遊戲還在玩= False
                    elif 和棋:
                        它.說('和棋，平分秋色。')
                        它.和棋次數 += 1
                        遊戲還在玩= False
                    else:
                        誰= 它.更換走棋者(誰)
                        遊戲還在玩= True # 本行多餘，但增進了解。



                它.印出棋步()

                它.說('玩家得分 : 電腦得分 : 和棋次數= %d : %d : %d'
                        %(它.玩家得分, 它.電腦得分, 它.和棋次數))


                再玩一次= 它.詢問是否再玩一次()

            它.說('不玩了，再見！')

    #
    # 主程式開始
    #

    a井字棋= 井字棋(電腦棋力=0)

    a井字棋.玩()

====
能寫一個五子棋的程式嗎？
====


五子棋，五目並べ（ごもくならべ），Gomoku
----------------------------------------

`參考 <http://zh.wikipedia.org/wiki/五子棋>`__


.. image:: http://upload.wikimedia.org/wikipedia/commons/thumb/6/69/Renju.jpg/220px-Renju.jpg
