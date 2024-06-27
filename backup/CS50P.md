# 重续兴趣之烈火
## 梦开始的地方
  结束了懵懂的大一，不出意外的上学期的目标接着拖入了下学期，但至少一身轻，在暑假也以更稳定的目标所提升自己。在平时零碎的信息洪流中，我通过琐细的视频与文章等窥探着计算机科学大厦的全貌。在一次偶然的机会中，我在GitHub上了解到了《《CS自学指南》》，自此我犹如获得新生，宛如行走的孤舟有了指引的灯塔，开始踏入CS的大厦。伴随着哈佛，伯克利，斯坦福等顶尖学府的课程，那些Project，那些Discussion，让我真正的见识到了代码，编程并不是如书本教材上般死寂，而是一个个灵动跳跃的字符。当然在此之中我也遇到重重困难，配置环境，语言难理解等，还有一部分是我自己的心贪，经常学着一门课又因为相关知识的欠缺亦或者为了学习跟学校课程本身所同步，而跑过去学另一门课程，最终因时间不够而又放弃。最终导致的结果就是，是的，我什么也没学成。但伴着这一年的相关踩坑和总结，我的这些烦恼，我觉得可以真正的烟消云散了。而写这篇博客的目的也是希望能为其他在自学路上的大家，贡献自己的一份绵薄之力。经历过C++与数据结构的毒打，我还是想遵循我内心开始的想法，从引起我注意的Python所开始，启程我的梦想旅途。如果你当下也是处在茫然的状态中，那不妨从哈佛大学的**CS50P**所开始，从Python来开启新的征程！
###  CS50P 0(计算机人独有的计数方式）
  由于课程教学中有很多终端页面操作(也就是CLI),而且作为计算机学子，学一些常见命令也是特别有必要的，比如以后所使用的Linux系统等。
  常见的为：
|Abbreviation  | Function |
|-----:|-----------|
| ls  | list all files(列出所有文件)|
|  cp| copy(复制)    |
|    mv| move file(移动),当然也可用于改名       |
| rm  | remove (移除）|
|  mkdir| make a director (创建文件夹)    |
|   cd| change director(创建文件夹)     |
| rmdir |remove director(删除文件夹)  |
| clear|清除屏幕(为了美观)     |


在课程的教学中，运用的 VS Code 云平台，以下为上述操作的一些举例：
`比如 **code hello.py** 即可创建一个python文件，**python hello.py**即可执行此文件。(当然，电脑中已有的文件也不用每次繁琐的输入名字，输入前几个字母按下TAB键，系统也会自动为我们补齐。
 此外也可创建文件夹如： cd folder/  复制文件：cp hello.py  goodbye.py 移动文件: mv goodbye.py  farewell.py  
进入文件夹后如：folder/$ mv farewell.py ..(移动到上一父文件夹)  folder/$ cd ..(返回主目录)，也可以就一个cd，文件夹的斜线\也可以不带`
  **下面正式开始python之旅**
首先
也是从我们耳熟能详的hello word开始
```python
#第一个学习的函数为print
print("hello world")
#（习惯了敲C++的同学可能会因为没有分号而感到不习惯）
#python中行注释的做法为，在所注释的行之前携带一个井号#，多行注释则为```(书写内容)```.
```
而如果我们就想打出双引号本身的话,可以用类似转义字符的方法如：
```python
print("hello \"friend\")
#亦或者单引号实现
print('hello "friend"')
```
既然有了输出，接下来介绍输入函数
```python
#input 函数
input("What`s your name?")
#当然我们也可以创造变量来储存我们的输入
name=input("What`s your name?")
print("hello,",name)#在这注意到print函数会自动给输入一个空格，因此,我们不用本身再额外敲击空格。
```
> [!NOTE]
> 上述空格问题，我们查阅python官方文档可得知print函数的参数列表为
print(*objects,sep=' ',end='\n')#实际单双引号均可
因此print函数会输出完自动加入空格与换行！
因此上述代码我们也可换这种方式所书写
```python
name=input("What`s your name?")
print("hello,",end="")#我们覆盖了end的原有值，令其为空.
print(name)#name不用加双引号，否则将会单单的输出'name'这个单词
#我们也可以用另一种方式来输出
print(f"hello,{name}")
```
```python
name=input("What`s your name?")
print("hello,",name,sep="???")#如果这样子更改，那么逗号和名字则会以一种丑陋的方式所隔开
```
接下来，让我们了解一些关于字符串的常见函数(方法）
```python
name=name.strip()#用‘’.“来调用，作用为去除字符串中的空格
name=name.capitalize()#作用为第一个首字母大写
name=name.title()#作用为标题大写，即每个词的首字母大写
#上述函数python也是支持嵌套调用的
name=name.strip().capitalize()
#自此我们可将代码缩短到一行
name=input("What`s your name?").strip().capitalize()
#现在我们可将所学结合起来，比如别人输入fullname，我们可单单获取输出firstname
first,last=name.split()#split该函数默认以空格为分隔符，将字符串进行分割
print(f"hello,{first}")
```
现在我们有了初步的了解后，我们来实现一个简易的计算器
```python
x=input("What`s x?")
y=input("What`s y?")
z=x+y
print(z)
```
> [!WARNING]
> 大家如果自己亲手实现则会发现一个问题，就是比如我输入1+2，则最后会输出12.这是因为什么呢？是因为python将这些默认为字符串，用加号简单的拼接起来了，我们接下啦介绍的int 整数类型就会让你恍然大悟！
我们来重新改写上述代码
```python
x=input("What`s x?")
y=input("What`s y?")
z=(int)x+(int)y
print(z)
#亦或者
x=int(input("What`s x?"))
y=int(input("What`s y?"))
print(x+y)
#当然python也是支持不断地嵌套，只是代码会变得不美观，影响阅读，比如：
print(int(input("What`s x?"))+int(input("What`s y?")))
```
我们在加减法中经常遇到小数的加减法，因此接下来我们将学习的数据类型为浮点型float
以及一个新的函数round作用为对结果进行四舍五入
python文档中的原型为：round(number[,ndigits])
官方文档方括号里边的通常是可选项，round中的则为四舍五入后保留几位小数.
```python
x=float(input("What`s your name?")
y=float(input("What`s your name?")
z=round(x+y)
print(z)
```当然，当数字越来越大的时候，我们也可以以三位为单位，像英语数字表示一样分割，只需修改print为：print(f"{z:,}") ,例如输入1000，则输出1,000```
#我们也可保留两位小数的形式来输出：
z=round(x/y,2)
print(f"{z:.2f}")
```
引用了那么多函数，你也对自己创造一个函数而跃跃欲试吧？接下来我们来学习定义函数
```python
def hello(to):        #在这，我们见到了新面孔 def 来定义属于我们自己的函数
                             #函数参数也可以自带默认值
····print("hello,",to)

name=input("What`s your name?")
hello(name)
#当然，函数里面也是可以嵌套调用函数的 如：
def main():
  x=int(input("What`s x?"))
  print("x square is",square(x))

def square(n):
    return n*n    #也可以用n**2来表示平方

main()
#我们也可以用python自带的函数来实现
def square(n):
    return pow(n,2)
```
最后我们在云平台上写完代码每次得手动运行，我们也可以在终端界面输入python来启动代码交互模式
会出现 >>> 这样的符号，即可实时交互 

感谢认真看到这里的你，这只是Python编程世界的一小部分。在接下来的文章中，我们将探索更多的主题和技巧，一起在编程海洋里面遨游！
