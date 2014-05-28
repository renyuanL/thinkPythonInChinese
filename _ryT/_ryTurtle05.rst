===========================
繁體中文程式 之 學生作品
===========================
開始有學生跟上了
----------------

.. sourcecode:: python3
    :linenos:
    
    '''
    b0129033_曹祐_HW06
    '''
    #--------------# code #-------------------


    #first iteration.#

    class 寵物:

        def __init__(自己, 名字, 年齡):
            自己.名字 = 名字
            自己.年齡 = 年齡


    class 貓(寵物):

        def __init__(自己, 名字, 年齡):
            寵物.__init__(自己, 名字, 年齡) # You can run and super class method like this.


    def Main():

        這個動物 = 寵物("寵物", 1)
        傑斯 = 貓("傑斯", 3)

        print ("傑斯是一隻貓?" + str(isinstance(傑斯, 貓)))
        print ("傑斯是一隻寵物?" + str(isinstance(傑斯, 寵物)))
        print ("這個動物是貓?" + str(isinstance(這個動物, 貓)))
        print ("這個動物是寵物?" + str(isinstance(這個動物, 寵物)))
        
        print (傑斯.名字)

    if __name__ == '__main__':
        Main()


    #second iteration. (polymorphism)#

    class 寵物:

        def __init__(自己, 名字, 年齡):
            自己.名字 = 名字
            自己.年齡 = 年齡

        def 叫(自己):
            pass
            #raise NotImplementedError("Subclass must implement abstract method")

    class 貓(寵物):

        def __init__(自己, 名字, 年齡):
            寵物.__init__(自己, 名字, 年齡)

        def 叫(自己):
            return "喵"

    class 狗(寵物):

        def __init__(自己, 名字, 年齡):
            寵物.__init__(自己, 名字, 年齡)

        def 叫(自己):
            return "汪"

    def Main():

        寵物們 = [貓("傑斯",3), 狗("傑克", 2), 貓("fred", 7), 寵物("這個動物", 5)]

        for 每隻 in 寵物們:
            print ("名字:" + 每隻.名字 + ", 年齡:" + str(每隻.年齡) + ", 說:" + str(每隻.叫()))
        
    if __name__ == '__main__':
        Main()



    #-----------------# extra code #-------------------------

    class 人():
     def 付錢(自己):
       raise NotImplementedError

    class 有錢人(人):
     def 付錢(自己):
       print ("錢在這裡，不用找錢！")

    class 窮學生(人):
     def 付錢(自己):
       print ("能否先欠著，或我留下來洗盤子抵帳？")

    def Main():

        人們 = [有錢人(), 窮學生()]

        for 每個人 in 人們:
            每個人.付錢()
        
    if __name__ == '__main__':
        Main()

.. sourcecode:: python3
    :linenos:

    '''
    b0129033_曹祐_HW06
    '''
    import math

    class 二維向量:

        def __init__(自己, 橫座標, 縱座標):
            自己.橫座標 = 橫座標
            自己.縱座標 = 縱座標

        def __add__(自己, 其他):
            return 二維向量(自己.橫座標 + 其他.橫座標, 自己.縱座標 + 其他.縱座標)

        def __iadd__(自己, 其他):
            自己.橫座標 += 其他.橫座標
            自己.縱座標 += 其他.縱座標
            return 自己

        def __sub__(自己, 其他):
            return 二維向量(自己.橫座標 - 其他.橫座標, 自己.縱座標 - 其他.縱座標)

        def __isub__(自己, 其他):
            自己.橫座標 -= 其他.橫座標
            自己.縱座標 -= 其他.縱座標
            return 自己

        def __mul__(自己, 其他):
            return 二維向量(自己.橫座標 * 其他.橫座標, 自己.縱座標 * 其他.縱座標)

        def __imul__(自己, 其他):
            自己.橫座標 *= 其他.橫座標
            自己.縱座標 *= 其他.縱座標
            return 自己

        def __div__(自己, 其他):
            return 二維向量(自己.橫座標/float(其他.橫座標), 自己.縱座標/float(其他.縱座標))

        def __idiv__(自己, 其他):
            自己.橫座標 /= 其他.橫座標
            自己.縱座標 /= 其他.縱座標
            return 自己

        def 向量長度(自己):
            return math.sqrt(自己.橫座標**2 + 自己.縱座標**2)

        def 正規化(自己):
            length = 自己.向量長度()
            if length != 0:
                return 二維向量(自己.橫座標/float(length), 自己.縱座標/float(length))
            return 二維向量(自己)

        def 取得角度(自己):
            return math.degrees(math.atan2(自己.縱座標, 自己.橫座標))

        def __str__(自己):
            return "橫座標:" + str(自己.橫座標) + ",縱座標:" + str(自己.縱座標)

    def Main():
        向量 = 二維向量(5,6)
        向量2 = 二維向量(2,3)
        print (向量)
        print (向量2)

        暫時方法 = 向量.取得角度
        
        向量 = 向量 + 向量2
        print (向量)

        向量 += 向量2
        print (向量)

        向量 *= 二維向量(2,2)
        print (向量)

        print (向量.正規化())
        print (向量.取得角度())

        print (暫時方法())
        
    if __name__ == '__main__':
        Main()


