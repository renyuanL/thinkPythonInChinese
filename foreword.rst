Foreword
========
前言

By David Beazley

中文翻譯： `呂仁園 <http://renyuan.iTaiwanese.org>`__

As an educator, researcher, and book author, I am delighted to see the
completion of this book. Python is a fun and extremely easy-to-use programming
language that has steadily gained in popularity over the last few years.
Developed over ten years ago by Guido van Rossum, Python's simple syntax and
overall feel is largely derived from ABC, a teaching language that was
developed in the 1980's. However, Python was also created to solve real
problems and it borrows a wide variety of features from programming languages
such as C++, Java, Modula-3, and Scheme. Because of this, one of Python's most
remarkable features is its broad appeal to professional software developers,
scientists, researchers, artists, and educators.


作為一個教育工作者、研究人員以及寫書的作家，
我很高興看到這本書的完成。 
Python 是一個暨有趣又極端容易使用的程式語言。
它在過去幾年中漸漸普及起來。
Python 最初是由 `Guido van Rossum <http://www.python.org/~guido/>`__ 所開發。
它那簡單的語法和整體的感覺主要源自於 ABC 程式語言，
那是一種教學語言，開發於 1980 年代。
然而，Python 也被用來解決實際問題，
並廣泛借用了各種特性的程式語言 
如 C++、Java、Modula-3 以及Scheme。
正因為如此，Python 的一個最顯著特點是其廣泛吸引了各種專業人士，
包括：軟體開發人員、科學家、研究人員、藝術家以及教育家。


Despite Python's appeal to many different communities, you may still wonder why
Python? or why teach programming with Python? Answering these questions is no
simple task---especially when popular opinion is on the side of more
masochistic alternatives such as C++ and Java.  However, I think the most
direct answer is that programming in Python is simply a lot of fun and more
productive.

儘管 Python 吸引了 各種不同的社群，你可能仍然不知道為什麼 要用 Python？
或者為什麼要教 Python 編程？ 回答這些問題沒那麼簡單 --- 
尤其是主流觀點傾向 較為自虐的替代品，如 C++ 和 Java。
不過，我覺得最 直接的回答是，
用 Python 來編程就只是很有趣，且更有 生產力。

When I teach computer science courses, I want to cover important concepts in
addition to making the material interesting and engaging to students.
Unfortunately, there is a tendency for introductory programming courses to
focus far too much attention on mathematical abstraction and for students to
become frustrated with annoying problems related to low-level details of
syntax, compilation, and the enforcement of seemingly arcane rules. Although
such abstraction and formalism is important to professional software engineers
and students who plan to continue their study of computer science, taking such
an approach in an introductory course mostly succeeds in making computer
science boring. When I teach a course, I don't want to have a room of
uninspired students. I would much rather see them trying to solve interesting
problems by exploring different ideas, taking unconventional approaches,
breaking the rules, and learning from their mistakes. In doing so, I don't want
to waste half of the semester trying to sort out obscure syntax problems,
unintelligible compiler error messages, or the several hundred ways that a
program might generate a general protection fault.

當我教計算機科學的課程時，
除了使材料有趣的以吸引學生之外，
我還想涵蓋一些重要概念。


  不幸的是，對於編程入門課程的傾向
  集中了太多的注意力放在數學抽象和學生
  變得沮喪與相關的低層次的細節惱人的問題
  語法，編譯和看似神秘的規則的實施。
  
  雖然
  這種抽象和形式主義是非常重要的專業軟件工程師
  和學生誰打算繼續計算機科學的研究，採取這種
  在入門課程的做法大多是成功的電腦製作
  科學無聊。
  
  當我教一門課程，我不希望有一個房間
  平庸的學生。
  
  我寧願看到他們試圖解決有趣
  通過探索不同的想法，採取非常規的方法問題，
  打破規則，並從他們的錯誤中學習。
  
  在這樣做時，我不希望
  浪費半學期試圖理清晦澀的語法問題，
  難以理解的編譯器錯誤消息，或者幾百方法，一個
  程序可能會生成一般保護性錯誤。


One of the reasons why I like Python is that it provides a really nice balance
between the practical and the conceptual. Since Python is interpreted,
beginners can pick up the language and start doing neat things almost
immediately without getting lost in the problems of compilation and linking.
Furthermore, Python comes with a large library of modules that can be used to
do all sorts of tasks ranging from web-programming to graphics. Having such a
practical focus is a great way to engage students and it allows them to
complete significant projects. However, Python can also serve as an excellent
foundation for introducing important computer science concepts. Since Python
fully supports procedures and classes, students can be gradually introduced to
topics such as procedural abstraction, data structures, and object-oriented
programming --- all of which are applicable to later courses on Java or C++.
Python even borrows a number of features from functional programming languages
and can be used to introduce concepts that would be covered in more detail in
courses on Scheme and Lisp.

我喜歡 Python 的眾多原因之一是，
它在實務和概念之間提供了一個非常好的平衡。

  因為Python解釋，
  初學者可以拿起的語言，並開始做整潔的事物幾乎
  立即而不迷失在編譯和鏈接的問題。
  
  此外， Python提供了模塊的大庫，可用於
  做各種任務，從網絡編程圖形。
  
  具有這種
  切合實際的重點是一個偉大的方式來吸引學生，並讓他們
  完成顯著的項目。
  
  然而， Python也可以作為一個很好的
  基礎引入重要的計算機科學概念。
  
  因為Python
  完全支持程序和類，學生可逐步引入到
  主題，如過程抽象，數據結構和面向對象
  編程---
  所有這些都適用於基於Java或C + +以後的課程。
  
  蟒蛇甚至借用了一些功能從函數式編程語言
  並且可以用來引入，將被覆蓋了更詳細的概念
  課程計劃和Lisp 。


In reading Jeffrey's preface, I am struck by his comments that Python allowed
him to see a higher level of success and a lower level of frustration and that
he was able to move faster with better results.  Although these comments refer
to his introductory course, I sometimes use Python for these exact same reasons
in advanced graduate level computer science courses at the University of
Chicago. In these courses, I am constantly faced with the daunting task of
covering a lot of difficult course material in a blistering nine week quarter.
Although it is certainly possible for me to inflict a lot of pain and suffering
by using a language like C++, I have often found this approach to be
counterproductive---especially when the course is about a topic unrelated to
just programming. I find that using Python allows me to better focus on the
actual topic at hand while allowing students to complete substantial class
projects.

在閱讀 Jeffrey 的序言時，我被他的評論感動了， Python 允許 
他看到更高層次的成功和較低水平的挫折，而 
他能夠有更佳的成果向前邁進。 

  儘管這些評論指 
  他的入門課程，我有時會使用Python這些完全相同的原因 
  在先進的研究生水平的計算機科學課程的大學 
  芝加哥。 
  
  在這些課程，我不斷地面臨著艱鉅的任務 
  涵蓋了很多困難當然材料的起泡9週季度。 
  
  雖然這是絕對有可能為我造成了很多痛苦和苦難 
  通過使用像C + +語言，我經常發現這種方法是 
  適得其反---尤其是當過程大約是無關的話題 
  只是編程。 
  
  我發現使用Python可以讓我更好地專注於 
  手頭同時讓學生完成大量的類實際話題 
  項目。

Although Python is still a young and evolving language, I believe that it has a
bright future in education. This book is an important step in that direction.

雖然 Python 仍然是一個年輕且不斷發展中的語言，我相信，至少在教育層面，它有一個 
明亮的未來。這本書是在這一方向邁出了重要一步。

David Beazley, 
University of Chicago Author of the *Python Essential Reference*
