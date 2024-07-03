### Loops(循环）
- 今天，我们来学习循环语句，简单来说就是一遍又一遍的做某一件事.
比如如果我们想在屏幕上打印出三个猫叫的语句，我们可如下代码所示实现：
```python 
print("meow")
print("meow")
print("meow")
```
_这是在次数少的情况下，如果我们想不停的输出几百次甚至几万次，那我们还要手动去敲击实现吗？(那可真是个灾难!)_
- 而循环恰恰就能为我们实现重复一遍又一遍实现的代码块

1. While 循环
```python 
i=3
while i!=0
     print("meow")
```
我们运行上述代码会发现，这似乎是个永无止境的死循环？因此我们要在代码块中加入能改变循环条件的代码
```python 
i=3
while i!=0
     print("meow")
     i=i-1#当然，我们也可以"偷懒"写为i-=1
```
- 现在我们的代码可以正常执行，每次通过循环的“迭代”都会减少 i .

- 也由于我们编程习惯用0开始计数，因此上述代码通常写为： 
```python 
i = 0
while i < 3:
    print("meow")
    i += 1
```
此时的代码流程如下图所示：
<img width="463" alt="屏幕截图 2024-07-02 183352" src="https://github.com/KKKadk/AD-forever.github.io/assets/162538427/17353dbb-cf60-47e0-93a8-3b5f8249dbfb">
- 接下来我们来学习"大名鼎鼎"的for循环
为了更好的理解for循环，我们先来学习python中的列表list，就好像我们生活中的其他领域一样，我们可以有一个购物清单，一个代办事项等.
我们可通过for循环来遍历list中的个体：
```python
for i in [0,1,2]:#i依次取值为0，1，2
     print("meow")
```
但又如开头提到的问题，当我们的循环次数越来越多时，我们不可能一个个的手动输入列表里的所有内容，因此我们可以改进代码为：
```python 
    for i in range(3):
      print("meow")
```
- 你可能注意到了，我们不在代码中显式的用到变量“i”，只用来存储循环的迭代次数，不用于其他任何目的.类似的,在Python中，如果这样的变量在我们的代码中没有任何其他意义，我们可以简单的将这个变量表示为单个下划线“_"因此，我们可以如下修改代码：
```python 
   for _ in range(3):
     print("meow")
```
为了更深入的了解python，我们可以进一步改写上述代码：
```python 
print("meow"*3)#是的，你没有看错，这就会连续输出三次meow
```
但你会注意到程序会产生"meowmeowmeow"的结果，这并不是我们所想要的效果，回想一下我们刚开始学习print函数时的参数列表，我们可以按如下方式所改写：
```python 
print("meow\n"*3,end="")
```
- 现在我们可以用循环语句引导用户进行正确的输入了！顺便引出我们的两个新的关键字"continue"和“break”
```python
while True：
     n=int(input(What`s n?")
     if  n<0:
       continue#当不满足我们想要的结果时，一直迭代下去
     else:
        break #退出循环，执行程序剩下的部分
```
- 现在我们可以运用这些知识，用函数来改进上述代码：
```python
def main():
      meow(get_number())#我们可以用一个函数的返回值作为另一个函数的参数值

def get_number():
    while True:
       n=int(input(What`s n?")
      if n>0：
         return n

def meow(n):
   for _ in range(n):
     print("meow")
  
main()
```
-接下来的主题来重点来引申介绍**list**
```python
students= ["Hermonie","Harry","Ron"]

print(students[0])
print(student[1])
print(student[2])
#我们也可以用 for 循环来改写上述代码
students= ["Hermonie","Harry","Ron"]
 for student in students:
    print(student)
```
> [!NOTE]
>请注意，对于students列表中的每个student，你可能会提出疑问，为什么我们没有使用前面讨论的“_"来代替student，因为student在我们的代码中显式使用了它.

- 我们可以使用“len”函数来获得list的长度
我们用代码来输出学生姓名与列表中的位置：
```python 
students=["Hermonie","Harry","Ron"]

for i in range(len(studens)):
    print(i+1,students[i])
```
- 最后，我们来学习Dictionaries（dict，一种数据结构，允许我们将键与值相关联）
- list 是多个值的列表，而dict 将键与值相关联
<img width="529" alt="屏幕截图 2024-07-02 235008" src="https://github.com/KKKadk/AD-forever.github.io/assets/162538427/1b940593-ccba-4ad3-83e8-587e24ac60d6">



如这样一个表格，我们可以用list来实现：
```python 
students = ["Hermoine", "Harry", "Ron", "Draco"]
houses = ["Gryffindor", "Gryffindor", "Griffindor", "Slytherin"]
```

- 请注意，我们可以保证我们将始终保持这些列表的顺序。第一个位置 students 的个人与 houses 列表第一个位置的房子相关联，依此类推。但是，随着我们列表的增加，这可能会变得非常麻烦！
因此，我们可以用dict来改进我们的代码
```python
student={
    “Hermonie”：“Gryffindor”，
    "Harry": "Gryffindor",
    "Ron": "Gryffindor",
    "Draco": "Slytherin",
}
print(students["Hermoine"])
print(students["Harry"])
print(students["Ron"])
print(students["Draco"])
```
- 我们也可用如下方式改进我们的代码，同时打印键和值：
```python 
students={
     "Hermonie": "Gryffindor"
     "Harry": "Gryffindor",
    "Ron": "Gryffindor",
    "Draco": "Slytherin",
}
for student in students:
  print(student,students[student],sep=",")#用逗号隔开，更加的美观
```
- 但如果我们有更多关于学生的信息的话，我们如何将其联系起来？
<img width="545" alt="image" src="https://github.com/KKKadk/AD-forever.github.io/assets/162538427/71fac320-369e-46d5-90ce-2cdc5b22a23a">


我们可将多个值与键相匹配，如：
```python 
     students= [
     {"name":"Hermonie","house":"Gryffindor","patrouns":"Otter"},
{"name":"Harry","house":"Gryffindor","patrpus":"Stag”},
{"name": "Ron", "house": "Gryffindor", "patronus": "Jack Russell terrier"},
    {"name": "Draco", "house": "Slytherin", "patronus": None},
]
```

- 我们创建了关于"dict"的"list",并且我们可注意到"None"关键字表明，无值与键所对应.
现在，我们可以联系起所有数据去改进我们代码为：
```python 
students = [
    {"name": "Hermoine", "house": "Gryffindor", "patronus": "Otter"},
    {"name": "Harry", "house": "Gryffindor", "patronus": "Stag"},
    {"name": "Ron", "house": "Gryffindor", "patronus": "Jack Russell terrier"},
    {"name": "Draco", "house": "Slytherin", "patronus": None},
]

for student in students:
    print(student["name"], student["house"], student["patronus"], sep=", ")
```
接下来让我们以一个小的练习来首尾：
![image](https://github.com/KKKadk/AD-forever.github.io/assets/162538427/8debbe0a-7284-49fd-a0ef-ae2277f30d2f)

-如果我们想在屏幕上打印出类似超级马里奥这样的砖块，我们可写代码为：

```python
def main(3)
    print_square(3)

def print_square(size)
    #打印出每一行
   for i in range(size):
    #打印出每一列
       for j in range(size):
    #打印出砖块
          print("#",end="") 
     #打印空白行
     print()#参数为空时，打印空白行

main()
```
- 整体代码逻辑就是：一个外循环，用于正方形中的每一行。然后，我们有一个内部循环，在每列中打印一块砖。最后，我们有一个打印空行 print 的语句。
-当然，我们也可以换种方式来改写：
```python 
def main():
    print_square(3)


def print_square(size):
    for i in range(size):
        print_row(size)


def print_row(width):
    print("#" * width)


main()
```
**啊哈！我们又在Python大陆上解锁了又一种能力，让我们在接下来的日子里继续带着热情去探索！**