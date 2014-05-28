

================
繁體中文程式集錦
================

`你可在此找到最新例子 more examples at GitHub <https://github.com/renyuanL/pythonTurtleInChinese>`__

.. sourcecode:: python3
    :linenos:

    '''
    ryByteDesign.py
     
    呂仁園 中文程式翻譯
     
    2014/05/19
     
    翻譯原則:
         python keyword 不翻
         單字母變數     不翻
    '''
    #!/usr/bin/env python3
    """      turtle-example-suite:
     
            tdemo_bytedesign.py
     
    An example adapted from the example-suite
    of PythonCard's turtle graphics.
     
    It's based on an article in BYTE magazine
    Problem Solving with Logo: Using Turtle
    Graphics to Redraw a Design
    November 1982, p. 118 - 134
     
    """
     
    #from turtle import Turtle, mainloop
    from turtle_tc import *
     
    from time import clock as 鐘
     
     
    class 設計師類(龜類):
     
        def 設計(我, 家位置, 尺度):
     
            我.提筆()
            for i in 範圍(5):
                我.前進(64.65 * 尺度)
                我.下筆()
                我.輪子(我.位置(), 尺度)
                我.提筆()
                我.後退(64.65 * 尺度)
                我.右轉(72)
     
            我.提筆()
            我.前往(家位置)
            我.右轉(36)
            我.前進(24.5 * 尺度)
            我.右轉(198)
            我.下筆()
            我.中角(46 * 尺度, 143.4, 尺度)
            我.取幕().追蹤器(True)
     
        def 輪子(我, 初始位置, 尺度):
     
            我.右轉(54)
            for i in 範圍(4):
                我.五角(初始位置, 尺度)
            我.下筆()
            我.左轉(36)
            for i in 範圍(5):
                我.三角(初始位置, 尺度)
            我.左轉(36)
            for i in 範圍(5):
                我.下筆()
                我.右轉(72)
                我.前進(28 * 尺度)
                我.提筆()
                我.後退(28 * 尺度)
            我.左轉(54)
            我.取幕().更新()
     
        def 三角(我, 初始位置, 尺度):
     
            舊頭向= 我.頭向()
            我.下筆()
            我.後退(2.5 * 尺度)
            我.三角向右(31.5 * 尺度, 尺度)
            我.提筆()
            我.前往(初始位置)
            我.設頭向(舊頭向)
            我.下筆()
            我.後退(2.5 * 尺度)
            我.三角向左(31.5 * 尺度, 尺度)
            我.提筆()
            我.前往(初始位置)
            我.設頭向(舊頭向)
            我.左轉(72)
            我.取幕().更新()
     
        def 五角(我, 初始位置, 尺度):
     
            舊頭向= 我.頭向()
            我.提筆()
            我.前進(29 * 尺度)
            我.下筆()
            for i in 範圍(5):
                我.前進(18 * 尺度)
                我.右轉(72)
            我.五角向右(18 * 尺度, 75, 尺度)
     
            我.提筆()
            我.前往(初始位置)
            我.設頭向(舊頭向)
            我.前進(29 * 尺度)
            我.下筆()
            for i in 範圍(5):
                我.前進(18 * 尺度)
                我.右轉(72)
            我.五角向左(18 * 尺度, 75, 尺度)
     
            我.提筆()
            我.前往(初始位置)
            我.設頭向(舊頭向)
            我.左轉(72)
            我.取幕().更新()
     
        def 五角向左(我, 邊長, 角度, 尺度):
     
            if 邊長 < (2 * 尺度): return
            我.前進(邊長)
            我.左轉(角度)
            我.五角向左(邊長 - (.38 * 尺度), 角度, 尺度)
     
        def 五角向右(我, 邊長, 角度, 尺度):
     
            if 邊長 < (2 * 尺度): return
     
            我.前進(邊長)
            我.右轉(角度)
            我.五角向右(邊長 - (.38 * 尺度), 角度, 尺度)
     
        def 三角向右(我, 邊長, 尺度):
     
            if 邊長 < (4 * 尺度): return
     
            我.前進(邊長)
            我.右轉(111)
            我.前進(邊長 / 1.78)
            我.右轉(111)
            我.前進(邊長 / 1.3)
            我.右轉(146)
            我.三角向右(邊長 * .75, 尺度)
     
        def 三角向左(我, 邊長, 尺度):
     
            if 邊長 < (4 * 尺度): return
     
            我.前進(邊長)
            我.左轉(111)
            我.前進(邊長 / 1.78)
            我.左轉(111)
            我.前進(邊長 / 1.3)
            我.左轉(146)
            我.三角向左(邊長 * .75, 尺度)
     
        def 中角(我, 邊長, 角度, 尺度):
     
            我.前進(邊長); 我.左轉(角度)
            if 邊長 < (7.5 * 尺度):
                return
            我.中角(邊長 - (1.2 * 尺度), 角度, 尺度)
     
    def 主函數():
     
        設計師= 設計師類()
     
        設計師.速度(0)
        設計師.藏龜()
        設計師.取幕().延遲(0)
        設計師.取幕().追蹤器(0)
     
        t0= 鐘()
     
        設計師.設計(設計師.位置(), 2)
     
        t1= 鐘()
     
        return "執行時間: %.2f 秒。" % (t1-t0)
     
    if __name__ == '__main__':
     
        m= 主函數()
        印(m)
        進入主迴圈()   

.. sourcecode:: python3
    :linenos:
    '''
    ryChaos.py
     
    呂仁園 中文程式翻譯
     
    2014/05/19
     
    '''
    # File: tdemo_chaos.py
    # Author: Gregor Lingl
    # Date: 2009-06-24
     
    # A demonstration of chaos
     
    #from turtle import *
    from turtle_tc import *
     
    N= 80
     
    def f(x):
        f= 3.9*x*(1-x)
        return f
     
    def g(x):
        g= 3.9*(x-x**2)
        return g
     
    def h(x):
        h= 3.9*x-3.9*x*x
        return h
     
    def 跳到(x, y):
     
        提筆(); 前往(x,y)
     
    def 直線(x1, y1, x2, y2):
     
        跳到(x1, y1)
        下筆()
        前往(x2, y2)
     
    def 畫座標軸():
     
        直線(-1, 0, N+1, 0)
        直線(0, -0.1, 0, 1.1)
     
    def 畫(函數, 起點, 色):
     
        筆色(色)
        x= 起點
        跳到(0, x)
        下筆()
        點(5)
        for i in 範圍(N):
            x= 函數(x)
            前往(i+1,x)
            點(5)
     
    def 主函數():
     
        重設()
        設座標系統(-1.0,-0.1, N+1, 1.1)
        速度(0)
        藏龜()
     
        畫座標軸()
        畫(f, 0.35, 藍)
        畫(g, 0.35, 綠)
        畫(h, 0.35, 紅)
     
        # Now zoom in:
        for s in 範圍(100):
            設座標系統(0.5*s,-0.1, N+1, 1.1)
     
        return "完成!"
     
    if __name__ == "__main__":
     
        主函數()
     
        進入主迴圈()
    
    
.. sourcecode:: python3
    :linenos:

    '''
    ryClock.py
     
    呂仁園 中文程式翻譯
     
    2014/05/19
     
    '''
    #!/usr/bin/env python3
    # -*- coding: cp1252 -*-
    """       turtle-example-suite:
     
                 tdemo_clock.py
     
    Enhanced clock-program, showing date
    and time
      ------------------------------------
       Press STOP to exit the program!
      ------------------------------------
    """
    #from turtle import *
     
    from turtle_tc import *
     
    from datetime import datetime as 日期時間
     
    #模式("logo")
     
    def 跳(距離, 角度=0):
     
        提筆()
        右轉(角度)
        前進(距離)
        左轉(角度)
        下筆()
     
    def 指針(長度, 針尖尺寸):
     
        前進(長度*1.15)
        右轉(90)
        前進(針尖尺寸/2.0)
        左轉(120)
        前進(針尖尺寸)
        左轉(120)
        前進(針尖尺寸)
        左轉(120)
        前進(針尖尺寸/2.0)
     
    def 做指針形狀(名, 長度, 針尖尺寸):
     
        重設()
        跳(-長度*0.15)
        開始多邊形()
        指針(長度, 針尖尺寸)
        結束多邊形()
        指針形狀= 取多邊形()
        登記形狀(名, 指針形狀)
     
     
    def 鐘面(半徑):
     
        重設()
        筆大小(7)
        for i in 範圍(60):
            跳(半徑)
            if i % 5 == 0:
                前進(25)
                跳(-半徑-25)
            else:
                畫點(3)
                跳(-半徑)
            右轉(6)
     
    def 設立():
     
        global 秒針, 分針, 時針, 寫手
     
        模式("logo")
     
        做指針形狀("秒針",  125, 25)
        做指針形狀("分針",  130, 25)
        做指針形狀("時針",  90, 25)
        鐘面(160)
     
        秒針= 龜類()
        秒針.形狀("秒針")
        秒針.顏色("gray20", "gray80")
     
        分針= 龜類()
        分針.形狀("分針")
        分針.顏色("blue1", "red1")
     
        時針= 龜類()
        時針.形狀("時針")
        時針.顏色("blue3", "red3")
     
        for 指針 in 秒針, 分針, 時針:
            指針.重設大小模式("user")
            指針.形狀大小(1, 1, 3)
            指針.速度(0)
     
        藏龜()
     
        寫手= 龜類()
        #寫手.模式("logo")
        寫手.藏龜()
        寫手.提筆()
        寫手.後退(85)
     
     
    def 星期(現在時刻):
     
        星期 = ["拜一", "拜二", "拜三", "拜四", "拜五", "拜六", "拜日"]
     
        return 星期[現在時刻.weekday()]
     
    def 日期(現在時刻):
     
        月份= ['正', '二', '三','四','五','六',
               '七','八','九','十','十一','十二']
     
        年= 現在時刻.year
        月= 月份[現在時刻.month - 1]
        日= 現在時刻.day
     
        return "%d 年 %s 月 %d 日" % (年, 月, 日)
     
    def 滴答():
     
        global 寫手
     
        現在時刻= 日期時間.today()
     
        秒= 現在時刻.second
        分= 現在時刻.minute + 秒/60.0
        時= 現在時刻.hour   + 分/60.0
     
        追蹤更新畫面(False)
     
        寫手.清除()
        寫手.回家()
        寫手.前進(65)
        寫手.寫(星期(現在時刻))
        寫手.後退(150)
        寫手.寫(日期(現在時刻))
        寫手.前進(85)
     
        追蹤更新畫面(True)
     
        秒針.設頭向(6*秒)
        分針.設頭向(6*分)
        時針.設頭向(30*時)
     
        追蹤更新畫面(True)
     
        在計時後(滴答, 100)
     
    def 主函數():
     
        追蹤更新畫面(False)
        設立()
        追蹤更新畫面(True)
        滴答()
        return "進入主迴圈"
     
    if __name__ == "__main__":
     
        m= 主函數()
        印(m)
        進入主迴圈()
    
.. sourcecode:: python3
    :linenos:

    '''
    ryColormixer.py

    呂仁園 中文程式翻譯

    2014/05/20
    '''


    from turtle_tc import * # 幕類, 龜類, 主迴圈

    class 色龜類(龜類):

        def __init__(我, x, y):

            龜類.__init__(我)

            我.形狀(龜形)
            我.重設大小模式("user")
            我.形狀大小(3,3,5)
            我.筆粗(10)

            我._顏色= [0,0,0]
            我.x= x

            我._顏色[x] = y
            我.顏色(我._顏色)
            我.速度(0)
            我.左轉(90)
            我.提筆()
            我.前往(x,0)
            我.下筆()
            我.設y座標(1)
            我.提筆()
            我.設y座標(y)
            我.筆色("gray25")
            我.在拖曳時(我.移動)

        def 移動(我, x, y):

            我.設y座標(max(0,min(y,1)))
            我._顏色[我.x] = 我.y座標()
            我.填色(我._顏色)
            設背景色()

    def 設背景色():

        幕.背景色(紅龜.y座標(), 綠龜.y座標(), 藍龜.y座標())

    def 主函數():

        global 幕, 紅龜, 綠龜, 藍龜

        幕= 幕類()
        幕.延遲(0)
        幕.設座標系統(-1, -0.3, 3, 1.3)

        紅龜= 色龜類(0, .5)
        綠龜= 色龜類(1, .5)
        藍龜= 色龜類(2, .5)

        設背景色()

        寫字龜= 龜類()
        寫字龜.藏龜()
        寫字龜.提筆()
        寫字龜.前往(1,1.15)

        寫字龜.寫("色龜混色!")

        return "EVENTLOOP"

    if __name__ == "__main__":

        msg = 主函數()
        印(msg)
        主迴圈()
    
.. sourcecode:: python3
    :linenos:

    '''
    ======
    河內塔
    ======

    呂仁園 中文程式翻譯

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


    
    
.. sourcecode:: python3
    :linenos:

    '''

    用漢字來做程式設計
    ==================
    呂仁園
    -------
    2014/04/24

    傳統漢字(traditional Chinese)
    龜模組(tirtle module)
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

        
    
    
.. sourcecode:: python3
    :linenos:

    '''
    ryYinyang.py

    用 中文龜模組 ryTurtle
    示範龜畫陰陽太極圖。

    by 呂仁園
    2014/03/24

    '''


    #from  turtle import *

    from  turtle_tc import *

    def 陰陽(半徑, 色01, 色02):

        筆大小(3)
        顏色(黑, 色01)
        開始填色()
        畫圓(半徑/2, 180)
        畫圓(半徑, 180)
        左轉(180)
        畫圓(-半徑/2, 180)
        結束填色()
        左轉(90)
        提筆()
        前進(半徑*0.35)
        右轉(90)
        下筆()
        顏色(色01, 色02)
        開始填色()
        畫圓(半徑*0.15)
        結束填色()
        左轉(90)
        提筆()
        後退(半徑*0.35)
        下筆()
        左轉(90)

    def 主函數():

        重設()
        陰陽(200,  黑, 白)
        陰陽(200,  白, 黑)
        藏龜()

        進入主迴圈()

        return "完成!"

    if __name__ == '__main__':

        主函數()
        
.. youtube:: 36QJsF1anhw
    :width:  320
    :height: 240
    
.. sourcecode:: python3
    :linenos:

    '''
    ryTurtleEx01.py
    ===============

    運用 中文龜模組 turtle_tc.py
    ------------------------

    1. 無名龜 自己畫圖
    2. 跟隨滑鼠
    3. 聽候鍵盤



    by 呂仁園
    2014/03/24


    '''



    from  turtle_tc import *
    #
    # 程式由此開始
    # ------------

    def 主函數():

        開幕()

        W= 幕寬= 100
        設座標系統(0,0,W,W)
        背景色 (灰)
        標題('小烏龜會畫圖。')

        生一隻龜()

        形狀(龜形)
        顏色(紅)

        速度(0)       # 0 是最快的; 1 ~ 10 最慢 ~ 很快
        提筆()
        回家()

        def 畫格子點():

            N= 10
            for x in 範圍(N+1):
                提筆(); 前往(W/N*x, 0)
                下筆(); 前往(W/N*x, W)

            for y in 範圍(N+1):
                提筆(); 前往(0, W/N*y)
                下筆(); 前往(W, W/N*y)

        畫格子點()

        提筆();前往(W/2, W/2)

        def 畫星狀圖():

            下筆();
            for i in 範圍(100):
                前進(W/4)
                左轉(170)
                顏色(隨機數(),隨機數(),隨機數())

        畫星狀圖()

        def 畫多個星狀圖(K=2):

            for i in 範圍(K):
                前往(隨機數()*W,隨機數()*W)

                蓋章()
                寫('(%.1f, %.1f)'%(座標x(), 座標y()))

                畫星狀圖()

                睡(1)

        畫多個星狀圖(K=2)

        現在時間= 看時間()
        寫('現在時間= %s'%現在時間)

        回家()

        睡(1)


        def 叫烏龜前往且算距離(x,y):

            前一點座標x, 前一點座標y= 座標x(), 座標y()

            前往(x,y)
            到前一點的距離= 距離(前一點座標x, 前一點座標y)

            寫('(%.1f, %.1f) 距離= %.1f'%(座標x(), 座標y(), 到前一點的距離 ))


        在滑鼠鍵點擊幕時(叫烏龜前往且算距離)

        #在鍵盤鍵壓下時(清除幕)
        在按鍵時(清除幕,空白鍵)


        聽鍵盤()

        筆色(藍)
        寫('''
        在滑鼠鍵點擊幕時(叫烏龜前往)
        在鍵盤鍵壓下時(清除幕)
        點擊 X 結束。
        ''')

        閉幕()

    if __name__=='__main__':
        主函數()
        
    
.. sourcecode:: python3
    :linenos:

    '''
    ryTurtleEx02.py
    ===============

    運用 中文龜模組 turtle_tc.py
    ------------------------

    1. 無名龜 自己畫圖
    2. 跟隨滑鼠
    3. 聽候鍵盤



    by 呂仁園
    2014/03/24

    '''

    from  turtle_tc import *
    #
    # 程式由此開始
    # ------------


    def 主函數():

        開幕()

        W= 100

        座標系統(-W, -W, W, W)

        形狀(龜形)

        顏色(紅)

        寫('我是無名龜')

        速度(100)

        def 畫格子線(N=20):

            w= 格子寬= (2*W)/N

            線集=  [ ((-W+w*n,-W),        (-W+w*n, +W))       for n in range(N)]
            線集+= [ ((-W,    -W+w*n),    (+W,     -W+w*n))   for n in range(N)]

            for 線 in 線集:
                起點, 終點= 線
                提筆(); 前往(起點)
                下筆(); 前往(終點)

            提筆();
            筆色(藍);
            前往(0,0); 寫(位置())
            前往(w*N/4,0); 寫(位置())
            前往(0,w*N/4); 寫(位置())

            回家()
            pass

        畫格子線(20)

        多邊形= [(0,0),(50,0),(50,50),(0,50)]

        開始多邊形()

        [前往(x) for x in 多邊形]

        結束多邊形()

        在點擊幕時(前往)

        在按著鍵時(清除)

        聽鍵盤()

        閉幕()

    if __name__=='__main__':

        主函數()


.. sourcecode:: python3
    :linenos:

    '''
    turtle_tc.py

    開始超朝向自動翻譯方向前進。

    先做出中英對照表。

    2014/04/19




    turtle_tc.py
    ============================
    用 Python 3，學中文程式設計。
    ============================

    繁體中文龜
    ----------

    使用這個模組，可以讓你使用繁體中文來控制龜畫圖。

    作者：呂仁園。
    -------------

    受了 MIT Scratch project 的啟發，
    讓 programming language 能夠以程式員的母語來表達，
    將是讓更多人(特別是非英語為母語的小孩)能夠來寫程式的一個關鍵要素。

    Python 3.0 以後， 變數、函數、以及物類名稱都使用  Utf-8 編碼，
    允許 程式員 運用 其母語來寫作程式，
    只要我們鑽進眾多模組內部，為每個物類的函數名稱給個母語別名，
    再把相應的 doc 文件說明也轉成母語，
    這個基本工程將建立起母語寫作程式的基礎環境，
    程式教育就有可能向下紮根，到達高中，甚至是國中的階段。

    本程式模組就是在這個想法之下的首次嘗試，
    我們把 Python 中， 一個頗負盛名的模組，turtle.py，
    為其提供一個繁體中文 (traditional Chinese) 的附加模組，
    命名為 turtle_tc.py，

    使用者只要把本程式模組放在 python環境下，模組的搜尋路徑內，
    一般為當前程式碼的目錄 (current dir)或是 C:/Python3.x/Lib/，
    那麼，你就可以用
    import turtle_tc
    來取代
    import turtle

    進而，運用中文來寫基於 龜 的作圖程式，就成為可能。


    ryTurtle02.py ---> turtle_tc.py # for traditional chinese
    ============================
    用 Python 3，學中文程式設計，
    ============================

    小龜的世界。
    ============
    作者：呂仁園。
    -------------

    ryTurtle02.py

    2014/03/27

    turtle_tc.py

    Inspired by the MIT Scratch project, 
    a program language capable of supporting programmers' native language ,
    will allow more people ( particularly non-English-speaking kids ) able to write the program more fluently.

    Starting from Python version 3.0 ,  names of variables, functions, and classes  are encoded in utf-8 ,
    that is to say, programmers can write programs in their mother languages. 
    I think this will be a key point to make Python overspread even broader and broader.

    As long as we can get into many python's modules, provide a set of name aliases for each class, method, and import global variables, then kids or naive people can also write their own programs. Kids include those from K to 12 in non-English-speaking countries, who are not fluent nor possess enough vocabulary in English. 

    This program/module implementing the idea is one of the few first tries,
    it is an appendix to the Python built-in modules turtle.py, 
    which is majorly a bunch of traditional Chinese alias of English name.

    This file is named as turtle_tc.py, to emphasize it is majorly in traditional Chinese.

    Similar modification can be made to make it suitable in any non-English language. 

    This file can be run by itself, 
    it can also be put in the path of Python library, 
    and be imported by the other application of turtle programs

    To use Chinese names could not only make the program more readable for local Chinese speaking programmers, 
    it could also make the program more compact, dense and beautiful.

    Renyuan Lyu
    2014/05/24

    renyuan.lyu@gmail.com
    google.com/+RenyuanLyu    

    '''

    import math
    import time
    import random


    #'''
    #import turtle as tt
    from turtle import *
    from turtle import _CFG, _Screen, _Root, TK, _TurtleImage, Tbuffer, TurtleGraphicsError
    from turtle import TurtleScreenBase, TurtleScreen, TNavigator, TPen, RawTurtle, Canvas #, Turtle, Screen
    #'''

    '''
    #import ryTurtle as tt
    from ryTurtle import *
    from ryTurtle import _CFG, _Screen, _Root, TK, _TurtleImage, Tbuffer, TurtleGraphicsError
    from ryTurtle import TurtleScreenBase, TurtleScreen, TNavigator, TPen, RawTurtle, Turtle, Screen
    '''


    import inspect as ip


    import math
    import random as rd

    '''
    隨機數= rd.random
    隨機整數= rd.randint
    時間= time.time
    睡= time.sleep
    '''

    #
    # 物類內別名，(Inside-class alias)
    #


    cListTurtleScreenBase=[
    ('TurtleScreenBase', '龜幕基類', '烏龜螢幕地基類', 'guimujilei'),
    ('mainloop'  ,   '主迴圈', '進入主迴圈', '做完了', '點擊X結束', '等待閉幕', '閉幕',  'zhuhuiquan'),
    ('numinput'  ,   '輸入數字',    'shurushuzi'),
    ('textinput' ,   '輸入文字',    'shuruwenzi'),
    ]



    cListTurtleScreen=[
    ('TurtleScreen',                '龜幕類', '烏龜螢幕類', 'guimulei'),

    ('addshape',                    '加形狀',  'jiaxingzhuang'),
    ('bgcolor',                     '背景色',  'beijingse'),
    ('bgpic',                       '背景圖',  'beijingtu'),
    ('clear',                       '清除',   'cingchu'),
    ('clearscreen',                 '清除幕'),
    ('colormode',                   '色模式'),
    ('delay',                       '延遲'),
    ('getcanvas',                   '取畫布'),
    ('getshapes',                   '取形', '取形狀'),
    ('listen',                      '聽', '聽鍵盤'),
    ('mode',                        '模式'),

    ('onclick',                     '在點擊時','在點擊龜時'),
    ('onclick',                     '在滑鼠鍵點擊時'),
    ('onkey',                       '在按鍵時', '在按鍵鬆開時'),

    ('onkeypress',                  '在按著鍵時', '在按下鍵時'),
    ('onkeyrelease',                '在按鍵鬆開時'),
    ('onscreenclick',               '在點擊幕時', '在幕點擊時', '在滑鼠鍵點擊幕時' ),
    ('ontimer',                     '在計時後', '在計時器若干毫秒之後'),

    ('register_shape',              '登記形狀','註冊形狀'),
    ('reset',                       '重設', '重設所有龜'),
    ('resetscreen',                 '重設幕'),
    ('screensize',                  '幕大小', '重設幕寬高', '重設幕大小'),
    ('setworldcoordinates',         '設座標系統', '座標系統'),
    ('tracer',                      '追蹤','追蹤更新畫面', '追蹤器'),
    ('turtles',                     '龜群', '取龜列表', '龜列表'),
    ('update',                      '更新', '更新畫面'),
    ('window_height',               '取幕高', '幕高','窗高'),
    ('window_width',                '取幕寬', '幕寬','窗寬')
    ]



    cListTNavigator= [
    ('TNavigator', '龜行類', '烏龜航行類','guixinglei'),

    ('reset',                       '重設','chongshe'),
    ('forward',                     '前進','qianjin'),
    ('back',                        '後退','houtui'),
    ('right',                       '右轉','youzhuan'),
    ('left',                        '左轉','zuozhuan'),
    ('pos',                         '位置','weizhi'),
    ('goto',                        '前往', '設位置', '去到','qianwang'),
    ('setheading',                  '設頭向','shetouxiang'),
    ('home',                        '回家','huijia'),

    ('circle',                      '畫圓', '圓','huayuan'),
    ('speed',                       '速度','sudu'),

    ('degrees',                     '角度','設角為度', '設圓為360度', '設角的單位為角度'),
    ('radians',                     '弳度', '弧度' ,'半徑數', '設角為弧', '設角的單位為半徑數', '設圓為2pi弧'),

    ('xcor',                        'x座標','座標x'),
    ('ycor',                        'y座標','座標y'),
    ('setx',                        '設x座標','設座標x'),
    ('sety',                        '設y座標','設座標y'),
    ('distance',                    '距離'),
    ('heading',                     '頭向'),
    ('towards',                     '朝向', '朝向xy' ),


    ('setpos',                      '設位置'),
    ('setposition',                 '設位置')

    ]



    cListTPen= [
    ('TPen', '龜筆類', '烏龜畫筆類'),

    ('pensize',                     '筆粗', '筆粗細', '筆大小'),
    ('width',                       '筆寬', '寬'),
    ('penup',                       '提筆'),
    ('pendown',                     '下筆'),
    ('showturtle',                  '顯龜','顯示','顯'),
    ('hideturtle',                  '藏龜','隱藏','藏'),
    ('color',                       '顏色'),
    ('pencolor',                    '筆色'),
    ('speed',                       '速度'),
    ('pen',                         '筆', '筆屬性'),
    ('fillcolor',                   '填色'),

    ('isdown',                      '下筆嗎', '是否下筆', '下筆狀態'),
    ('isvisible',                   '顯龜嗎', '是否可見', '可見狀態'),

    ('pendown',                     '下筆'),
    ('fillcolor',                   '填色'),
    ('penup',                       '提筆'),



    ('resizemode',                  '重設大小模式', '設成可伸縮模式')


    ]



    cListRawTurtle=[
    ('RawTurtle',                       '原龜類', '粗龜類', '原生龜類'),

    ('shapesize',                       '形狀大小', '大小', '龜大小'),
    ('shape',                           '形狀'),
    ('write',                           '寫'),
    ('begin_fill',                      '開始填', '開始填色'),
    ('end_fill',                        '結束填', '結束填色'),
    ('begin_poly',                      '開始多邊形'),
    ('clear',                           '清除'),
    ('clearstamp',                      '清除蓋章'),
    ('clearstamps',                     '清除蓋章群'),
    ('clone',                           '複製'),
    ('dot',                             '點', '畫點'),
    ('end_poly',                        '結束多邊形'),
    ('filling',                         '是否正在填色', '正在填色', '填色狀態'),
    ('get_poly',                        '取多邊形'),
    ('get_shapepoly',                   '取形狀多邊形'),
    ('getpen',                          '取筆'),
    ('getscreen',                       '取幕'),
    ('getturtle',                       '取龜'),

    ('onclick',                         '在點擊時', '在滑鼠點擊龜時'),
    ('ondrag',                          '在拖曳時', '在滑鼠拖曳龜時'),
    ('onrelease',                       '在鬆開時', '在滑鼠鬆開龜時', '在釋放時', '在滑鼠釋放龜時'),

    ('reset',                           '重設'),

    #('screens',                         '幕群', '幕列表'),

    ('settiltangle',                    '設傾角', '設傾斜角度'),
    ('setundobuffer',                   '設回復暫存區'),
    ('shapetransform',                  '形狀轉換'),
    ('shearfactor',                     '扭曲因子', '設取扭曲因子'),
    ('stamp',                           '蓋章', '蓋印', '戳印'),
    ('tilt',                            '傾斜'),
    ('tiltangle',                       '傾斜角度'),
    ('turtlesize',                      '龜大小'), # 是否為 shapesize 的別名。
    ('undo',                            '回復'),
    ('undobufferentries',               '回復暫存區的個數', '回復暫存區的長度', '取回復暫存區的長度' ),
    ('write',                           '寫')

    ]


    cList_Screen= [
    ('_Screen',     '_幕類','_螢幕類'),
    ('setup',       '設立'),
    ('title',       '設標題', '標題'),
    ('bye',         '再見'),
    ('exitonclick', '在點擊時離開', '離開在點擊時')
    ]


    cListTurtle=[
    ('Turtle', '龜類', '烏龜類','生一隻龜'),
    #('None', '無')
    ]

    cListScreen=[
    ('Screen', '幕類', '螢幕類', '開幕'),
    #('None', '無')
    ]

    classBeChanged= ['TurtleScreenBase', 'TurtleScreen', 'TNavigator', 'TPen', 'RawTurtle', '_Screen',  'Screen', 'Turtle']

    #
    # 印出 物類內 別名表，可供 程式員 參考，以及作為 自動翻譯 的依據
    #
    for y in classBeChanged:
        cList= 'cList'+y
        ec= eval(cList)

        print('\n'+'-'*20)
        print('class ', y)
        print('-'*20+'\n')

        for x in ec:
            print(x)

    print('='*60+'\n')




    aClassL=[]
    bClassL=[]
    cClassL=[]
    for y in classBeChanged: #= 'TurtleScreenBase'

        ey= eval(y)
        aClass= ip.getsource(ey)
        aClassL+= [aClass]

        #classTurtleScreenBase=''

        cList= 'cList'+y
        ec= eval(cList)
        #bClassL=[]
        for x in ec[1:]:
            for n in range(1,len(x)):
                bClass= ' '*4 + x[n] +'= '  + x[0] +'\n'
                #
                # 物類 內， 有 4 個空白
                #
                aClass+= bClass
                bClassL+= [bClass]

        x= ec[0]
        #cClassL=[]
        for n in range(1,len(x)):
            cClass= x[n] +'= '  + x[0] +'\n'
            #
            # 物類 外， 無 4 個空白。
            #
            aClass+= cClass
            cClassL+= [cClass]

        #print(aClass)

        exec(aClass)




    #
    # 全區別名，(global  alias)
    #


    字串別名表= [
     ('"Delete"',   '清除鍵'),
     ('"Down"',     '向下鍵'),
     ('"Home"',     '回家鍵'),
     ('"Left"',     '向左鍵'),
     ('"Right"',    '向右鍵'),
     ('"Up"',       '向上鍵'),
     ('"space"',    '空白鍵'),
     ('"Escape"',   '脫離鍵'),
     ('"black"',    '黑','黑色'),
     ('"blue"',     '藍','藍色'),
     ('"cyan"',     '青','青色'),
     ('"gray"',     '灰','灰色'),
     ('"green"',    '綠','綠色'),
     ('"magenta"',  '紫','紫色'),
     ('"orange"',   '橙','橙色'),
     ('"red"',      '紅','紅色'),
     ('"white"',    '白','白色'),
     ('"yellow"',   '黃','黃色'),
     ('"turtle"',   '龜形','烏龜形狀'),
     ('"square"',   '方形'),
     ('"logo"',     '角度從北開始順時針')
     ]


    #
    # 常用的就把它加在這裡
    #

    函數別名表= [
     ('None',               '無'),
     ('True',               '真'),
     ('False',              '假'),

     ('print',              '印'),
     ('range',              '範圍'),

     ('random.random',      '隨機數', '亂數'),
     ('random.choice',      '隨機選', '亂選'),
     ('random.randint',     '隨機整數', '亂整數'),
     ('random.sample',      '隨機取樣', '亂取樣'),

     #("['red','orange','yellow','green','cyan','blue','magenta']", '彩虹', '彩虹色群'),

     ('time.ctime', '看時間', '取時間'),
     ('time.sleep', '睡', '等時間'),
     ('time.time',  '時間'),

     ('Turtle', '龜類', '生龜','生一隻龜'),
     ('Screen', '幕類', '開幕'),

     ('Pen',                '筆類'),
     ('RawPen',             '原生筆類'),
     ('RawTurtle',          '原生龜類'),
     ('ScrolledCanvas',     '可捲畫布類'),
     ('Shape',              '形狀類'),
     ('TurtleScreen',       '龜幕類'),
     ('Vec2D',              '向量2D類', '二維向量類')

    ]


    #
    # 這一行是「別名」的關鍵語句
    #

    #'''

    別名表 = 字串別名表 + 函數別名表

    aCmd=''
    for e in 別名表:
        #exec(e[1] + '=' + e[0] )
        for n in range(1,len(e)):
            aCmd += e[n] + '='+ e[0] + '\n'


    #print(aCmd)

    exec(aCmd)




    中英對照表=[
        cListTurtleScreenBase,
        cListTurtleScreen,
        cListTNavigator,
        cListTPen,
        cListRawTurtle,
        cList_Screen,
        cListTurtle,
        cListScreen,
        字串別名表,
        函數別名表
        ]

    print('-'*20)
    print('中英對照表')
    print('-'*20)

    i= 0
    for x in 中英對照表:
        for y in x:
            print(i,y)
            i+=1



    #
    #
    #


    #'''
    #
    # 設法來寫 help ...
    #

    def read_docstrings(lang=''):
        """Read in docstrings from lang-specific docstring dictionary.

        Transfer docstrings, translated to lang, from a dictionary-file
        to the methods of classes Screen and Turtle and - in revised form -
        to the corresponding functions.
        """

        #modname = "turtle_docstringdict_%(language)s" % {'language':lang.lower()}
        modname = "turtle_docstringdict_tc"
        #
        # turtle_docstringdict_tc.py
        #
        # 這是繁體中文說明文件，還在翻譯當中，先有個版本來寫程式。
        # 2014/03/22
        #

        bMsg= '''這是繁體中文說明文件，
        還在翻譯當中，尚未完成，先行請您試閱並包容錯誤，
        一切仍以英文說明為主。 2014/03/22
        '''
        aMsg='中文說明'

        module = __import__(modname)

        docsdict = module.docsdict

        i= 0
        for key in docsdict:
            try:
                 #eval(key).im_func.__doc__ = docsdict[key] # 這行本來就 被原作者 mark 掉。

                 #
                 # 原作者用這行。
                 #
                 #eval(key).__doc__ =  docsdict[key]   # original version

                 #
                 # 我把它改成如下。
                 #

                 #eval(key).__doc__ += '\n\n'+ docsdict[key]  # renyuan make it += from =

                 eval(key).__doc__ = '『%04d  '%(i)+ aMsg + '』\n'+ docsdict[key] + '\n\n' + eval(key).__doc__ # 出現次序調一下。
                 #
                 # 從原始 turtle.py 挖出這行程式碼，很珍貴。把 = 改成 += 就可把中文 help 黏進去
                 #
                 i+= 1

            except:
                print('''%s 說明文件輸入有誤，檢查： %s
                '''% (modname, key))

    #'''
    讀入繁體中文說明文件= read_docstrings
    try:
        讀入繁體中文說明文件()
    except:
        print('讀入繁體中文說明文件()， 失敗，跳過。' )
    #'''



    '''


    for methodname in _tg_screen_functions:
        pl1, pl2 = getmethparlist(eval('_Screen.' + methodname))
        if pl1 == "":
            print(">>>>>>", pl1, pl2)
            continue
        defstr = ("def %(key)s%(pl1)s: return _getscreen().%(key)s%(pl2)s" %
                                       {'key':methodname, 'pl1':pl1, 'pl2':pl2})
        exec(defstr)
        eval(methodname).__doc__ = _screen_docrevise(eval('_Screen.'+methodname).__doc__)

    '''

    #
    # 把類別內 函數 釋放到 類別外
    #
    #
    # 從 turtle.py 學來的，還沒消化。
    #

    #
    # 主要是把 物類內函數 的 (self, ...) 變成  (...)
    #

    from turtle import __all__, getmethparlist #, _getpen, _getscreen, _turtle_docrevise, _screen_docrevise #, _Screen, Turtle

    '''
    _龜= 龜類()
    _幕= 幕類()
    '''
    def _取筆():
        """Create the 'anonymous' turtle if not already present."""

        if 龜類._pen is None:
            龜類._pen= 龜類()

        return 龜類._pen

    def _取幕():
        """Create a TurtleScreen if not already present."""
        if 龜類._screen is None:
            龜類._screen = _幕類()  ###### 會不會就是這行搞鬼？？ 有無底線之分！

        return 龜類._screen

    memberOfTurtle= ip.getmembers(龜類)

    memberOfScreen= ip.getmembers(_幕類)

    methodPutToMain=[]

    cmdString=''
    for mem in memberOfTurtle:

        m, mid= mem
        methodname= m

        #
        # 暴力 debug
        #
        if methodname == 'screens':
            continue

        if ord(m[0])>= ord('a'): #128: # 這一行是為了 僅要 中文 部分，英文部分原作者已經有，不需我多寫。
            '''
            cmd= m + '= ' + 'Turtle.' + m + '\n'
            cmdString += cmd
            '''

            methodPutToMain += [m]

            try:

                pl1, pl2 = getmethparlist(eval('龜類.' + methodname))
                if pl1 == "":
                    print(">>>>>>", pl1, pl2)
                    continue
                defstr = ("def %(key)s%(pl1)s: return _取筆().%(key)s%(pl2)s" %
                                               {'key':methodname, 'pl1':pl1, 'pl2':pl2})
                cmdString += defstr +'\n\n'

                exec(defstr)
                eval(methodname).__doc__ = eval('龜類.'+methodname).__doc__ # _turtle_docrevise(eval('龜類.'+methodname).__doc__)

            except:
                print('龜類.' + methodname +' No put to main')

    for mem in memberOfScreen:

        m, mid= mem
        methodname= m

        #
        # 暴力 debug
        #
        if methodname == 'screens':
            continue

        if ord(m[0])>= ord('a'): #128:
            '''
            cmd= m + '= ' + 'Turtle.' + m + '\n'
            cmdString += cmd
            '''

            methodPutToMain += [m]

            try:

                pl1, pl2 = getmethparlist(eval('_幕類.' + methodname))
                if pl1 == "":
                    print(">>>>>>", pl1, pl2)
                    continue
                defstr = ("def %(key)s%(pl1)s: return _取幕().%(key)s%(pl2)s" %
                                               {'key':methodname, 'pl1':pl1, 'pl2':pl2})
                cmdString += defstr +'\n\n'

                exec(defstr)
                eval(methodname).__doc__ = eval('_幕類.'+methodname).__doc__# _screen_docrevise(eval('_幕類.'+methodname).__doc__)
            except:
                print('_幕類.' + methodname +' No put to main')

    #print(cmdString)
    #exec(cmdString)

    __all__ += methodPutToMain


    for x in 別名表:
        for y in x[1:]:
            __all__ +=  [y]


    __all__ += ['中英對照表']

    #'''
    print('-'*10)
    print('可用的詞彙別名表')
    print('-'*10)
    print('__all__= ',sorted(__all__))
    #'''

    #
    # 模組到此結束。以下為測試。
    #
    #################################################################

    def 展示00_程序性程式設計():

        開幕()

        標題('「無名」小烏龜。')

        W= 100

        設座標系統(-W,-W,W,W)


        形狀(龜形)
        顏色(紅)

        速度(10)

        寫('大家好，我是「無名」小烏龜。')

        for i in range(10):
            前進(100)
            左轉(170)
            顏色(隨機數(), 隨機數(), 隨機數())
            畫點 ()

        回家()
        清除()
        畫圓(50)
        寫('''
        我做完了，
        幕進入主迴圈等你吩咐，
        你可以點擊 X 結束。
        ''')

        #在點擊時離開()  # 會再開出新螢幕，不知為何？？
        閉幕()



    def 展示01_物件導向程式設計():


        幕= 螢幕類()
        幕.標題('一群小烏龜。')

        W= 100
        幕.設座標系統(-W,-W,W,W)

        for i in 範圍(7):

            龜= 烏龜類()

            龜.形狀(龜形)
            龜.顏色(彩虹[i%7])
            睡(1)

            龜.速度(10)

            龜.寫('大家好，我是小烏龜 %d 。'%(i))
            龜.提筆()
            龜.前往((隨機數()-.5)*W/2, (隨機數()-.5)*W/2)
            龜.下筆()

            for i in range(10):
                龜.前進(100)
                龜.左轉(170)
                #龜.顏色(隨機數(), 隨機數(), 隨機數())
                龜.畫點 ()

            #龜.回家()
            #龜.清除()
            龜.畫圓(10)

        龜.寫('''
        我做完了，
        幕進入主迴圈等你吩咐，
        你可以點擊 X 結束。
        ''')

        幕.主迴圈()

    def 展示02():
        '''
        星形
        '''

        for N in 範圍(5,9):
            for k in 範圍(1,6):

                清除()
                下筆()
                寫('(N,k)= (%d, %d)'%(N, k))

                for i in 範圍(N):
                    前進(100)
                    左轉(k*360/N)

                回家()

        主迴圈()


    if __name__ == "__main__":

        #展示00_程序性程式設計()
        #展示01_物件導向程式設計()

        展示02()

        pass


        
    