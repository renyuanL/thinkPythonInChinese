=================================================================
Overview of available Turtle and Screen methods, 龜、幕 方法 概觀
=================================================================

Turtle methods, 龜方法
----------------------

Turtle motion, 龜動作

   Move and draw, 移動 和 畫圖
   
      | :func:`前進` | :func:`forward` | :func:`fd`    
      | :func:`後退` | :func:`backward` | :func:`bk` | :func:`back` 
      | :func:`右轉` | :func:`right` | :func:`rt`  
      | :func:`左轉` | :func:`left` | :func:`lt`  
      | :func:`前往` | :func:`goto` | :func:`setpos` | :func:`setposition`
      | :func:`設座標x` | :func:`setx`
      | :func:`設座標y` | :func:`sety`
      | :func:`設頭向`  | :func:`setheading` | :func:`seth`
      | :func:`回家` | :func:`home`
      | :func:`圓`   | :func:`畫圓` | :func:`circle`
      | :func:`點`   | :func:`畫點` | :func:`dot`
      | :func:`蓋章` | :func:`stamp`
      | :func:`清除蓋章`    |:func:`clearstamp`
      | :func:`清除蓋章群`  |:func:`clearstamps`
      | :func:`回復` | :func:`undo`
      | :func:`速度` | :func:`speed`

   Tell Turtle's state, 告知 龜狀態
   
      | :func:`位置`  | :func:`position` | :func:`pos`
      | :func:`朝向`  | :func:`towards`
      | :func:`座標x` | :func:`xcor`
      | :func:`座標y` | :func:`ycor`
      | :func:`頭向`  | :func:`heading`
      | :func:`距離`  | :func:`distance`

   Setting and measurement
   
      | :func:`角度` | :func:`degrees`
      | :func:`弧度` | :func:`radians`

Pen control, 筆控制

   Drawing state, 畫圖狀態
   
      | :func:`下筆` | :func:`pendown` | :func:`pd` | :func:`down`
      | :func:`提筆` | :func:`penup`   | :func:`pu` | :func:`up`
      | :func:`筆大小` | :func:`pensize` | :func:`width`
      | :func:`筆` | :func:`pen`
      | :func:`是下筆狀態` | :func:`isdown`

   Color control, 顏色控制
   
      | :func:`顏色` | :func:`color`
      | :func:`筆色` | :func:`pencolor`
      | :func:`填色` | :func:`fillcolor`

   Filling, 填色
   
      | :func:`正在填色狀態` | :func:`filling`
      | :func:`開始填色` | :func:`begin_fill`
      | :func:`結束填色` | :func:`end_fill`

   More drawing control, 更多畫圖控制
   
      | :func:`重設` | :func:`reset`
      | :func:`清除` | :func:`clear`
      | :func:`寫` | :func:`write`

Turtle state, 龜狀態

   Visibility, 可見狀態
   
      | :func:`顯龜` | :func:`顯示` | :func:`showturtle` | :func:`st`
      | :func:`藏龜` | :func:`隱藏` | :func:`hideturtle` | :func:`ht`
      | :func:`是可見狀態` | :func:`isvisible`

   Appearance, 外表
   
      | :func:`形狀` | :func:`shape`
      | :func:`重設大小模式` | :func:`resizemode`
      | :func:`形狀大小` | :func:`龜大小` | :func:`shapesize` | :func:`turtlesize`
      | :func:`扭曲因子` | :func:`shearfactor`
      | :func:`設傾斜角`  | :func:`settiltangle`
      | :func:`傾斜角`  | :func:`tiltangle`
      | :func:`傾斜`  | :func:`tilt`
      | :func:`形狀轉換`  | :func:`shapetransform`
      | :func:`取形狀多邊形` | :func:`get_shapepoly`

Using events, 運用 事件

   | :func:`在點擊時` | :func:`onclick`
   | :func:`在釋放時` | :func:`onrelease`
   | :func:`在拖曳時` | :func:`ondrag`

Special Turtle methods, 特殊 龜方法

   | :func:`開始多邊形` | :func:`begin_poly`
   | :func:`結束多邊形` | :func:`end_poly`
   | :func:`取多邊形` | :func:`get_poly`
   | :func:`複製` | :func:`clone`
   | :func:`取龜` | :func:`取筆` | :func:`getturtle` | :func:`getpen`
   | :func:`取幕` | :func:`getscreen`
   | :func:`設回復暫存` | :func:`setundobuffer`
   | :func:`回復暫存項目個數`


Methods of TurtleScreen/Screen, 龜幕/幕 方法
--------------------------------------------

Window control, 視窗控制

   | :func:`背景色`  | :func:`bgcolor`
   | :func:`背景圖`  | :func:`bgpic`
   | :func:`清除` | :func:`清除幕` | :func:`clear` | :func:`clearscreen`
   | :func:`重設` | :func:`重設幕` | :func:`reset` | :func:`resetscreen`
   | :func:`幕大小` | :func:`screensize`
   | :func:`設座標系統` | :func:`setworldcoordinates`

Animation control, 動畫控制

   | :func:`延遲` | :func:`delay`
   | :func:`追蹤` | :func:`tracer`
   | :func:`更新` | :func:`update`

Using screen events, 運用 幕 事件

   | :func:`聽` | :func:`聽鍵盤` | :func:`listen`
   | :func:`在按鍵時` | :func:`onkey` | :func:`onkeyrelease`
   | :func:`在按著鍵時` | :func:`onkeypress`
   | :func:`在點擊時` | :func:`在幕點擊時` | :func:`在點擊幕時` | :func:`onclick` | :func:`onscreenclick`
   | :func:`在計時後` | :func:`ontimer`
   | :func:`主迴圈` | :func:`進入主迴圈` | :func:`做完了` | :func:`mainloop` | :func:`done`

Settings and special methods, 設定 和 特殊方法

   | :func:`模式` | :func:`mode`
   | :func:`顏色模式` | :func:`colormode` 
   | :func:`取畫布` | :func:`getcanvas`
   | :func:`取形狀` | :func:`getshapes`
   | :func:`註冊形狀` | :func:`加形狀` | :func:`register_shape` | :func:`addshape`
   | :func:`龜群` | :func:`turtles`
   | :func:`幕高` | :func:`視窗高` | :func:`window_height`
   | :func:`幕寬` | :func:`視窗寬` | :func:`window_width`

Input methods, 輸入方法

   | :func:`文字輸入` | :func:`textinput`
   | :func:`數字輸入` | :func:`numinput`

Methods specific to Screen, 幕 特有 方法

   | :func:`再見` | :func:`bye`
   | :func:`在點擊時離開` | :func:`離開在點擊時` | :func:`exitonclick`
   | :func:`設立` | :func:`setup`
   | :func:`標題`  | :func:`title`
