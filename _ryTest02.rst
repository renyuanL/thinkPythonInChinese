
========================
ryDSP004_即時語音頻譜.py
========================

`Demo it on youTube <https://www.youtube.com/watch?v=tZ9ElWcyV5c&feature=youtu.be>`__

to run this program, you also need the following module
`ryaudio.py <https://www.dropbox.com/s/w60t2z9as4inrmm/ryaudio.py>`__

.. sourcecode:: python3
    :linenos:
    

    #
    # ryDSP004_即時語音頻譜.py
    #


    # 用 hsla 選顏色，比較有直覺。
    # ---

    def chooseColor():

        pg.init()

        N=10
        aSurf= pg.display.set_mode([N*N,N*N])

        c=pg.Color('red')

        for i in range(N):
            for j in range(N):

                c.hsla=(360*(i*N+j)/N/N%360,100,50,50) # 就像這樣可以計算

                color= (c.r, c.g, c.b, c.a)
                x,y= j*N, i*N
                pg.draw.rect(aSurf, color, (x,y,N,N))

        pg.display.update()
        time.sleep(10)
        pg.quit()


    import time

    import random    as rd
    import pylab     as pl
    import pygame    as pg

    from  rylab.ryaudio import RyAudio

    #import pyaudio   as pa
    #import threading as th


    def main():

        aRyAudio= RyAudio()
        aRyAudio.startGet()
        aRyAudio.startPlay()
        

        pg.init()

        aSurf= pg.display.set_mode([1024,512])

        #
        # for specgram, 頻譜
        #
        c= pg.Color('red')
        '''
        x= 100
        c.hsla=(x%360,100,50,50)
        color= (c.r, c.g, c.b, c.a)
        '''
        
        bSurf= pg.Surface(aRyAudio.specgram.shape ,depth=8) # for specgram
        cSurf= pg.Surface(aRyAudio.xBuf.shape ,depth=8) # for speech buf, xBuf

        bPal= []#[(x, x, 0) for x in range(256)]
        for x in range(256):
            c.hsla=(int(x*360/256)%360,100,50,50)
            color= (c.r, c.g, c.b)#, c.a)
            bPal.append(color)

        cPal= []#[(x, x, 0) for x in range(256)]
        for x in range(256):
            c.hsla=(x*360/256,x*100/256,x*100/256,50)
            color= (c.r, c.g, c.b)#, c.a)
            cPal.append(color)
        
        bSurf.set_palette(bPal)
        cSurf.set_palette(cPal)
        #

        aRect= pg.draw.rect(aSurf, pg.Color('red'), (0,0,5,5))
        pg.display.update()

        bRect= pg.draw.rect(aSurf, pg.Color('red'), (0,0,10,10))
        pg.display.update()

        maxT= 10
        t0= time.time()
        runningWhileLoop= True
        mouseButtonDown= False
        #while (time.time()-t0<= maxT) and (runningWhileLoop is True):
        mouseX= mouseY= 0


        while (runningWhileLoop is True):

            eL= pg.event.get() ## 主要靠這行取得訊號。滑鼠及鍵盤。 語音不能靠 pygame，要靠 pyaudio

            #print('eL= ', eL)

            for e in eL:

                if e.type in [pg.QUIT]: # 先學會「安全降落」。
                    #print('e.type, e.dict= ', e.type, e.dict)
                    runningWhileLoop= False
                    break

                if e.type in [pg.MOUSEBUTTONDOWN]:
                    #print('e.type, e.dict= ', e.type, e.dict)
                    mouseButtonDown= True
                    x,y= e.pos
                    mouseX= x

                if e.type in [pg.MOUSEBUTTONUP]:
                    #print('e.type, e.dict= ', e.type, e.dict)
                    mouseButtonDown= False

                if e.type in [pg.MOUSEMOTION]:
                    #print('e.type, e.dict= ', e.type, e.dict)
                    if (mouseButtonDown is True):
                        x,y= e.pos
                        zRect= aRect.move(x,y)
                        pg.draw.ellipse(aSurf, pg.Color('gray'), zRect)

                        mouseX= x
                        mouseY= y

                if e.type in [pg.KEYDOWN]:
                    #print('e.type, e.dict= ', e.type, e.dict)
                    pass

            #
            # 開始要取聲音訊號了！！！
            #

            t=  aRyAudio.t   # 時間 (sec)
            en= aRyAudio.en  # 能量 (energy, en)
            f0= aRyAudio.f0  # 基本頻率 (fundamental frequency, f0)
            fm= aRyAudio.fm  #
            fv= aRyAudio.fv  #
            fs= aRyAudio.fs  #
            enP=  aRyAudio.enP
            enPL= aRyAudio.enPL
            enPH= aRyAudio.enPH
            entropy= aRyAudio.entropy

            w= aSurf.get_width()
            h= aSurf.get_height()
            x= (t*100)%w
            
            #
            # for specgram, 頻譜
            #
            fft= aRyAudio.fft
            specgram= aRyAudio.specgram #pl.random([100,512])*100 #aRyPaEvent.specgram
            specgram= specgram[:,-1::-1]  # up_down flip, 頻譜上下對調，讓低頻在下，高頻在上，比較符合直覺。
            specgram= (pl.log(specgram)+10)*10  # 這個大小要如何自動調整才能恰當的呈現在螢幕上，還有待研究一下。

            pg.surfarray.blit_array(bSurf, specgram.astype('int')) #for speec raw data
            b1Surf= pg.transform.scale(bSurf,(w,h//4))     
            aSurf.blit(b1Surf, (0,0))
            #

            #
            # for xBuf, 語音暫存
            #
            xBuf= aRyAudio.xBuf
            xBuf = xBuf/256
            xBuf= xBuf.astype('int')

            pg.surfarray.blit_array(cSurf, xBuf) #for speec raw data
            c1Surf= pg.transform.scale(cSurf,(w,h//8))
            aSurf.blit(c1Surf, (0,h//4))
            #
            


            #'''
            if (mouseButtonDown is True):
                #x= mouseX
                r= (en ** 0.5) *0.1
                pg.draw.ellipse(aSurf, pg.Color('white'), (mouseX-r/2,mouseY-r/2,r,r))

            #'''


            y1= h- (en ** 0.5)   *0.01      # *0.1 是經驗值
            y2= h- f0 *h *2        # *2 也是經驗值
            y3= h- fm *h *2        # *2 也是經驗值
            y4= h- fs *h *2        # *2 也是經驗值
            y5= h- (enP ** 0.5)  *0.002
            y6= h- (enP ** 0.5)  *0.002
            y7= h- (enP ** 0.5)  *0.002
            y8= h- entropy*100

            yL=[]
            #y1Rect= bRect.move(x,y1); yL.append(y1Rect)
            y2Rect= aRect.move(x,y2); yL.append(y2Rect)
            y3Rect= aRect.move(x,y3); yL.append(y3Rect)
            y4Rect= aRect.move(x,y4); yL.append(y4Rect)
            #y5Rect= bRect.move(x,y5); yL.append(y5Rect)
            y6Rect= bRect.move(x,y6); yL.append(y6Rect)
            y7Rect= bRect.move(x,y7); yL.append(y7Rect)

            #y8Rect= bRect.move(x,y8); yL.append(y8Rect)

            #color=(rd.randint(0,255), rd.randint(0,255), rd.randint(0,255))
            #yL= [y1Rect, y2Rect, y3Rect, y4Rect, y5Rect, y6Rect, y7Rect]

            c=pg.Color('red')
            cL=[]
            for i in range(len(yL)):
                c.hsla=(360*i/len(yL),100,50,90)
                color= (c.r, c.g, c.b, c.a)
                cL.append(color)

            for i in range(len(yL)):
                pg.draw.rect(aSurf, cL[i], yL[i])


            pg.display.update()


            time.sleep(0.01) # this is so called 'sampling period'

            #aSurf.fill(pg.Color('black'))
            if x > w-10:
            #if(int(x)%10==0):
                aSurf.fill(pg.Color('black'))

        print('time.time()-t0= ', time.time()-t0)


        pg.quit()
        aRyAudio.stop()

    if __name__=='__main__':
        main()






==========================
Tutorial2014_003_敲磚塊.py
==========================

本程式需要 2 個音效檔
---------------------

`rySound01.wav <https://www.dropbox.com/s/mmudp3asw3dzfta/rySound01.wav>`__

`rySound02.wav <https://www.dropbox.com/s/pjs4ox2890cgqn7/rySound02.wav>`__

.. sourcecode:: python3
    :linenos:
    

    '''
    Tutorial2014_003_敲磚塊.py

    這支程式實現了我童年時期，最愛在電動玩具店玩的遊戲，
    敲磚塊，
    音效採用舌頭點出來的聲音(wav)，一高一低，
    rySound01.wav
    rySound02.wav

    還有我最喜歡的「卡農」曲之8個音符(midi)。

    2014/02/08

    '''

    import math
    import time

    import random as rd

    import pygame as pg
    import pygame.midi as pgMidi

    class RyColor:

        黑= black= (0,0,0)
        灰= grey= gray= (128,128,128)
        白= white= (255,255,255)
        紅= red=   (255,0,0)
        藍= blue=  (0,0,255)
        綠= green= (0,255,0)
        黃= yellow=(255,255,0)
        青= cyan=  (0,255,255)
        紫= magenta=(255,0,255)

    class Block(pg.sprite.Sprite):

        # Constructor. Pass in the color of the block, and its x and y position
        def __init__(self,color=(255,0,0),x=0,y=0, width=100, height=20):
            # Call the parent class (Sprite) constructor
            pg.sprite.Sprite.__init__(self)

            self.width= width #20#23
            self.height=height #15

            # Create the image of the block of appropriate size
            # The width and height are sent as a list for the first parameter.
            self.image= pg.Surface([width, height])

            # Fill the image with the appropriate color
            self.image.fill(color)

            # Fetch the rectangle object that has the dimensions of the image
            self.rect= self.image.get_rect()

            # Move the top left of the rectangle to x,y.
            # This is where our block will appear..
            self.rect.x= x
            self.rect.y= y

    class Ball(pg.sprite.Sprite):

        # Speed in pixels per cycle
        #speed= 10.0

        # Floating point representation of where the ball is
        #x= 200 #0.0
        #y= 200 #180.0

        # Direction of ball (in degrees)
        #direction= 180 #200

        width= 10
        height=10

        # Constructor. Pass in the color of the block, and its x and y position
        def __init__(self):
            # Call the parent class (Sprite) constructor
            pg.sprite.Sprite.__init__(self)

            # Create the image of the ball
            self.image= pg.Surface([self.width, self.height])

            # Color the ball
            #self.image.fill(yellow)

            # Get a rectangle object that shows where our image is
            aRect= self.image.get_rect()

            self.rect= pg.draw.ellipse(self.image, RyColor.黃, aRect )

            # Get attributes for the height/width of the aSurface
            self.screenheight= pg.display.get_surface().get_height()
            self.screenwidth=  pg.display.get_surface().get_width()

            self.x, self.y= self.screenwidth//2, self.screenheight//2
            
            #
            # 以下有點「物理」
            #
            self.speed= 10
            self.direction= rd.randint(0,360)
            theta= math.radians(self.direction)
            self.dx= self.speed * math.sin(theta)
            self.dy= -self.speed * math.cos(theta)

            self.sound = pg.mixer.Sound("rySound02.wav") # 舌頭音效

        # This function will bounce the ball off a horizontal surface diff=0
        # To bounce off a vertical surface set diff= 180

        def bounce(self, diff= 0):

            self.direction= (180-self.direction)%360
            self.direction -= diff

            # Sine and Cosine work in degrees, so we have to convert them
            theta= math.radians(self.direction)

            # Change the position (x and y) according to the speed and direction
            self.dx =  self.speed * math.sin(theta)
            self.dy =  -self.speed * math.cos(theta)

            self.sound.play()


        # Update the position of the ball
        def update(self):

            self.x += self.dx
            self.y += self.dy

            # Move the image to where our x and y are
            self.rect.x= self.x
            self.rect.y= self.y

            # Do we bounce off the top or bottom of the screen?
            if (self.y <= 0) or (self.y > self.screenheight-self.height):
                self.bounce(0)

            # Do we bounce off the left or right of the screen?
            if (self.x <= 0) or(self.x > self.screenwidth-self.width):
                self.bounce(180) 

    class Player(pg.sprite.Sprite):

        # Constructor function
        def __init__(self):
            # Call the parent's constructor
            pg.sprite.Sprite.__init__(self)

            self.width=  80 #75
            self.height= 10  #15
            self.image= pg.Surface([self.width, self.height])
            self.image.fill(RyColor.紫)

            # Make our top-left corner the passed-in location.
            self.rect= self.image.get_rect()
            self.screenheight= pg.display.get_surface().get_height()
            self.screenwidth= pg.display.get_surface().get_width()

            self.rect.x= 0
            self.rect.y= self.screenheight-self.height

            self.sound= pg.mixer.Sound("rySound01.wav")
            self.paddleSpeed= 10
            self.useMouse= False

        # Update the player
        def update(self):

            # Get where the mouse is
            mouseX, mouseY= pos= pg.mouse.get_pos()

            # Make sure we don't push the player paddle off the right side of the screen
            '''
            if self.rect.x > self.screenwidth - self.width:
                self.rect.x= self.screenwidth - self.width
            '''
            #
            # 以下是鍵盤方向鍵控制球拍
            #


            aKey= pg.key.get_pressed()
            if 1 in aKey:
               asciiCode= aKey.index(1)
               #print('aKey.index(1)=', asciiCode, chr(asciiCode))
               if asciiCode==pg.K_UP:
                  self.rect.y -= self.paddleSpeed
                  pass
               elif asciiCode==pg.K_DOWN:
                  self.rect.y += self.paddleSpeed
                  pass
               elif asciiCode==pg.K_LEFT:
                  self.rect.x -= self.paddleSpeed
                  pass
               elif asciiCode==pg.K_RIGHT:
                  self.rect.x += self.paddleSpeed
                  pass
               elif asciiCode==pg.K_a: # 球拍加速
                  self.paddleSpeed +=1
                  pass
               elif asciiCode==pg.K_d: # 球拍減速
                  self.paddleSpeed -=1
                  pass
               elif asciiCode==pg.K_m: # 球拍由滑鼠控制
                  #self.rect.x= mouseX
                  #self.rect.y= mouseY
                  self.useMouse= True
                  pass
               elif asciiCode==pg.K_n: # 球拍不由滑鼠控制
                  #self.rect.x= mouseX
                  #self.rect.y= mouseY
                  self.useMouse= False
                  pass
               else:
                  pass

            if self.useMouse==True:
                self.rect.x= mouseX
                self.rect.y= mouseY


    class RyMidi:
          def __init__(self):
          
                pgMidi.init()
                
                self.output= pgMidi.Output(0)
                
                self.output.set_instrument(1,1)

                self.song= [72,67,69,64,65,60,65,67]
                #
                # 這行是卡農 8 音符
                #
                
                #
                # self.song= [60,60,67,67,69,69,67,67,65,65,64,64,62,62,60,60]
                # 這行是小星星。
                #

          def play(self,  note= 60, duration= 0.2):

                self.output.note_on(note, 100,1)
                time.sleep(duration)
                self.output.note_off(note,100,1)

          def playSong(self, song= None, duration= 0.2):
                if song==None:
                    song= self.song
                else:
                    self.song= song

                [self.play(note, duration) for note in song]


    class RyApp:
        def __init__(self):

            aPg= pg.init()

            aRyMidi= RyMidi()

            # Create an 800x600 sized Surface
            aSurface= pg.display.set_mode([800, 600])

            # This is a aFont we use to draw text on the aSurface (size 36)
            aFont= pg.font.SysFont('kaiti',36) #pg.font.Font(None, 36)

            # Create another surface we can draw on # why? 不能直接畫在 aSurface 上就好嗎？
            bSurface= aSurface #pg.Surface(aSurface.get_size())

            # Create sprite lists
            blockG=  pg.sprite.Group()
            ballG=   pg.sprite.Group()
            spriteG= pg.sprite.Group()

            # Create the aPlayer paddle object
            aPlayer= Player()
            spriteG.add(aPlayer)

            # Create the ball
            aBall= Ball()
            ballG.add(aBall)
            spriteG.add(aBall)

            self.aSurface     =aSurface
            self.bSurface     =bSurface
            self.aFont        =aFont
            self.aPlayer      =aPlayer
            self.aBall        =aBall
            self.ballG        =ballG
            self.spriteG      =spriteG
            self.aRyMidi      =aRyMidi
            self.blockG       =blockG

        def 建立磚牆(self, nRows= 1):
            blockG, spriteG, bSurface= self.blockG, self.spriteG, self.bSurface

            # Number of blockG to create
            aBlock= Block()
            blockcount= bSurface.get_width()//aBlock.width# 32
            top= bSurface.get_height()*rd.randint(1,6)//8 #80

            #nRows= 1
            for row in range(nRows):
                # 32 columns of blockG
                for column in range(0,blockcount):
                    # Create a block (color,x,y)
                    color=(rd.randint(0,255), rd.randint(0,255), rd.randint(0,255))

                    b= Block(color,column*aBlock.width,top)
                    blockG.add(b)
                    spriteG.add(b)
                # Move the top of the next row down
                top += aBlock.height

        def run(self):
            aSurface= self.aSurface
            bSurface= self.bSurface
            aFont=    self.aFont
            aPlayer=  self.aPlayer
            aBall=    self.aBall
            ballG=    self.ballG
            spriteG=  self.spriteG
            aRyMidi=  self.aRyMidi
            blockG=   self.blockG


            self.建立磚牆(nRows= 1)

            # Clock to limit speed
            aClock= pg.time.Clock()

            # Is the game over?
            game_over=      False

            # Exit the program?
            exit_program=   False

            #
            # 主迴圈由此開始 -------------------------------
            #
            # Main program loop
            aCount=0
            while exit_program != True:

                # Process the events in the game
                eL= pg.event.get()
                for e in eL:
                    if e.type == pg.QUIT: # 使用者滑鼠按下X
                        exit_program= True

                if exit_program==True:
                    break # 跳出主迴圈，準備結束。

                # Limit to 30 fps
                aClock.tick(30)

                # Clear the aSurface
                aSurface.fill(RyColor.灰)

                # Book keeping the aCount on the Surface
                t= aFont.render("aCount= %d"%aCount, True, RyColor.綠)
                p= t.get_rect(centerx= bSurface.get_width()/2)
                p.top= 0
                aSurface.blit(t, p)

                # If we are done, print game over
                if game_over==True:
                    t=aFont.render("Game Over, Restart. 遊戲結束，重新開始", True, RyColor.白)
                    p= t.get_rect(centerx= bSurface.get_width()/2)
                    p.top= bSurface.get_height()/2
                    aSurface.blit(t, p)

                    time.sleep(1)

                    # 重新玩
                    self.建立磚牆(nRows= rd.randint(1,3))
                    game_over= False

                # Update the player and ball positions
                aPlayer.update()
                aBall.update()


                # See if the ball hits the player paddle
                if pg.sprite.spritecollide(aPlayer, ballG, False):

                    aPlayer.sound.play()

                    # The 'diff' lets you try to bounce the ball left or right depending where on the paddle you hit it
                    diff= (aPlayer.rect.x +aPlayer.width/2) - (aBall.rect.x +aBall.width/2)

                    # Set the ball's y position in case we hit the ball on the edge of the paddle
                    #aBall.rect.y= aSurface.get_height() - aPlayer.rect.height - aBall.rect.height -1
                    aBall.bounce(diff)

                # Check for collisions between the ball and the blockG
                deadblocks= pg.sprite.spritecollide(aBall, blockG, True)

                # If we actually hit a block, bounce the ball
                if len(deadblocks) > 0:
                    aBall.bounce(0)
                    #aRyMidi.play(rd.randint(60,72), 0.05)
                    note= aRyMidi.song[aCount%len(aRyMidi.song)]
                    aRyMidi.play(note, 0.05)
                    aCount +=1

                    # Game ends if all the blockG are gone
                    if len(blockG) == 0:
                        game_over= True

                # Draw Everything
                spriteG.draw(aSurface)

                # Flip the aSurface and show what we've drawn
                pg.display.flip()

                #
                # 主迴圈到此結束，有點長了，該縮短了。
                #--------------------------------------

            pgMidi.quit()
            pg.quit()

    if __name__=='__main__':

        aRyApp= RyApp()
        aRyApp.run()



