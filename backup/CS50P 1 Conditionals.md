**Conditionals**
 - 今天我们来学习条件语句，通过条件语句我们可以让程序在根据某些条件来实现选择.
 - Python内置了一些提出数学问题的"运算符".
 - \>和< 符号对于我们来说比较熟悉.
 - \>=表示"大于或等于"，初次看到这种表示形式你可能会诧异，但由于我们无法直接在键盘上打出一整个符号，所以得分开表示
 - \>= 表示“大于或等于”。
 - \<= 表示“小于或等于”。
 - == 表示“等于，但请注意双等号！单个等号将分配一个值。双等号用于比较变量。
 - != 表示“不等于”。
 **IF 语句**
 ```python
 x=int(input("What`s x ?"))
 y=int(input("What`s y ?"))
 if x>y:
       print("x`s greater than y")
```
- if语句的会根据布尔值（Bool）来决定是否执行，即为True 或 False，如果是True 则执行该条件下的代码
> [!WARNING]
> Python的特性之一，要注意代码的缩进，否则代码无法正常运行！
接着我们来进一步补全上述代码，令其功能完整
```python 
x=int(input("What`s x?"))
y=int(input(What`s y?"))
if x<y:
      print("x is less than y")
if x>y:
      print("x is greater than y")
if x==y:
      print("x is equal to y")
```
  我们注意到这一系列if语句，首先，对第一条if语句进行评估。然后，第二个if语句进行其计算以此类推，这种决策流称为“控制流”
  - 我们也可以用一种更直观的图表的方法来表示上述代码：
![图片1](https://github.com/KKKadk/AD-forever.github.io/assets/162538427/44da6c6a-33c1-49b9-89c3-90d98c0d8341)
当然，你或许觉得这个问题并不需要问三个问题而得出答案，很棒的思考！我们可以引进新的关键词"elif"来进一步的改进上面的代码：
```python 
 x = int(input("What's x? "))
 y = int(input("What's y? "))

if x < y:
    print("x is less than y")
elif x<y:
    print("x is greater than y")
elif x==y:
    print("x is equal to y")
```
这样，我们的流程图就可以简化为：
<img width="529" alt="屏幕截图 2024-07-01 174613" src="https://github.com/KKKadk/AD-forever.github.io/assets/162538427/7aa38ab3-449b-49c9-bc42-b063022f1efe">
可能你会觉得我们的计算机不会因为这一个细小的修订而存在运行速度上的差异，但正如David老师在课程中所讲：
- >**但请考虑每天运行数十亿或数万亿次此类计算的在线服务器肯定会受到如此小的编码决策的影响** 


最后，我们可对我们的代码进行最后的改进，逻辑上“elif x==y"不是要运行判断的代码，因为如果当前面的条件都不满足时，则x必定会等于y.因此我们可以修改代码如下：
```python 
x = int(input("What's x? "))
y = int(input("What's y? "))

if x < y:
    print("x is less than y")
elif x > y:
    print("x is greater than y")
else:
    print("x is equal to y")
```
最终，流程图可表示如下:
<img width="479" alt="屏幕截图 2024-07-01 175531" src="https://github.com/KKKadk/AD-forever.github.io/assets/162538427/d16161f6-41e9-456f-acfe-1ca17112e3bd">
- 接下来我们学习一个新的关键字 **or**
- 使用**or**我们可在一个或多个备选方案中做出决定：
```python 
x=int(input(What`s x?"))
y=int(input(What`s y?"))

 if x>y or x<y:
     print("x is not equal to y")
 else:
     print("x is equal to y")
```

当然我们也可以进一步的改进此代码：
```python 
x=int(input(What`s x?"))
y=int(input(What`s y?"))

 if x==y:#请注意双等于号和单个等于号的区别！
     print("x is  equal to y")
 else:
     print("x is not equal to y")
```
这样，我们的代码流程图可如下图所示：
<img width="263" alt="屏幕截图 2024-07-01 230705" src="https://github.com/KKKadk/AD-forever.github.io/assets/162538427/92a9066d-1a21-45a0-ac9e-4f3a5402ee1c">

**and**
- 与"or"类似，and也可以在条件语句中使用,比如下列代码，我们想输出不同分段学生所获得的等级：
```python
score=int(input("Score::")

if(score>=90 and score<=100
    print("Grade:A")
elif score>=80 and score<90
   print(Grade:B")
elif score >=70 and score < 80:
    print("Grade: C")
elif score >=60 and score < 70:
    print("Grade: D")
else:
    print("Grade: F")
```


- 当然我们也可以用一个python所独有的方式来改写上段代码：

```python 
score = int(input("Score: "))

  if 90 <= score <= 100:
      print("Grade: A")
  elif 80 <= score < 90:
      print("Grade: B")
  elif 70 <= score < 80:
      print("Grade: C")
  elif 60<=score<70:
      print(Grade: D")
   else:
    print("Grade:F")
```
我们可以继续进一步的改进我们的程序：
```python
score = int(input("Score: "))
#我们去除了边界限制条件是因为，程序从上往下执行，因此除第一个外某一个条件满足，则说明其前一个条件必不满足.
if score >= 90:
    print("Grade: A")
elif score >= 80:
    print("Grade: B")
elif score >= 70:
    print("Grade: C")
elif score >= 60:
    print("Grade: D")
else:
    print("Grade: F")
```
> [!TIP]
> 我们在一步步的思考如何通过减少问题来改进程序，这使得我们的程序也更加的易于阅读，并且未来也更好的去维护.(好的习惯都是从平时的点点滴滴所形成！)


**紧接着,我们来学习%（模）运算**
用代码来演示最直观明了，因此我们简单的来编写一个判断数字奇偶性的程序：
```python
x = int(input("What's x? "))

if x % 2 == 0:#模 % 运算符允作用为显示两个数字是整除除法还是带有余数.
    print("Even")
else:
    print("Odd")
```
- 我们也可直接写一个函数来封装，可以运用我们的Bool值：
```python 
def main():
    x=int(input("What`s x?"))
   if is_even(x):
       print("Even")
   else:
    print("Odd")

def is_even(x):
    if n%2==0:
     return True 
    else:
     return False
```
 **在编程世界中，有些类型的编程本质上被称为“Pythonic”。也就是说，有些编程方法有时只在 Python 编程中看到**
- 我们可以改写上述代码为：
```python
def main():
     x = int(input("What's x? "))
    if is_even(x):
        print("Even")
    else:
        print("Odd")

def is_even(n):
    return True if n%2==0 else False

main()
```
- 我们代码中的这个 return 语句几乎就像英语中的句子。这是一种仅在 Python 中看到的独特编码方式.(习惯了写c++，看到这个当时真的眼前一亮）

 **我们将学习的最后一个关键字为“match”**
如果我们有以下一段程序：
```python
name = input("What's your name? ")

  if name == "Ankar":
      print("HNU")
  elif name == "Erpan":
      print("NWAFU")
  elif name == "Dilnur": 
      print("NNU")
  elif name == "Nurbiya":
      print("XISU")
  elif name=="bakere":
      print("SCUT")
  else:
      print("Who?")
```
我们可以使用“match”来改写上述代码：
```python
match name:
      case "Ankar":
          print("HNU")
      case "Erpan":
          print("NWAFU")
      case "Dilnur":
          print("NNU")
      case "Nurbiya":
          print("XISU")
      case "bakere":
          print("SCUT")
      case _:
          print("Who?")
```
- 请注意，在最后一种情况下使用符号“_",这将与任何输入匹配，从而产生与“else”语句类似的行为.
- match 语句将 “match”关键字后面的每个值进行比较，如果找到匹配项，则执行相应代码，程序停止往下运行.
- 我们也可以在同一个"case"语句中检查多个值：

```python
   name = input("What's your name? ")

  match name: 
      case "Ankar" | "Dilnur" | "Erpan"|"Nurbiya":
          print("Beggar`s Room")
      case "bakere":
          print("I don`t know")
      case _:
          print("Who?")
```
**今天的内容到此结束啦~希望这些概念能帮助你更好的理解和使用Python进行编程，也希望你多多动手实现！**
