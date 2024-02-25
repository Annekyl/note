[TOC]

# 库的使用

## 1. turtle库指令大全

[](https://docs.python.org/zh-cn/3/library/turtle.html#window-control)

## 2.openpyxl模块使用方法

[Python 读取 Excel 详解（openyxl）_python读取excel文件-CSDN博客](https://blog.csdn.net/qq_34745941/article/details/106492488?ops_request_misc=%7B%22request%5Fid%22%3A%22170607044316800226512159%22%2C%22scm%22%3A%2220140713.130102334..%22%7D&request_id=170607044316800226512159&biz_id=0&utm_medium=distribute.pc_search_result.none-task-blog-2~all~sobaiduend~default-1-106492488-null-null.142^v99^pc_search_result_base8&utm_term=python读取excel数据openpyxl&spm=1018.2226.3001.4187)

## 3.PriorityQueue优先级队列

[Python 优先级队列PriorityQueue 用法示例_python priorityqueue-CSDN博客⁤](https://blog.csdn.net/u013288190/article/details/128810536)

# 扩展

## 比较方法

在Python中，比较方法是指那些定义了对象之间如何进行比较操作的特殊方法（或称为魔术方法、双下方法）。这些方法允许自定义对象支持比较运算符（如`<`、`>`、`==`等），从而可以根据开发者定义的规则进行比较。这些方法在实现排序算法、将对象放入支持排序的数据结构（如`PriorityQueue`、排序列表等）时非常有用。

以下是一些常用的比较方法及其对应的运算符：

- `__lt__(self, other)`：定义小于 (`<`) 的行为。
- `__le__(self, other)`：定义小于等于 (`<=`) 的行为。
- `__eq__(self, other)`：定义等于 (`==`) 的行为。
- `__ne__(self, other)`：定义不等于 (`!=`) 的行为。
- `__gt__(self, other)`：定义大于 (`>`) 的行为。
- `__ge__(self, other)`：定义大于等于 (`>=`) 的行为。

### 示例：使用比较方法

假设我们有一个简单的`Person`类，我们想根据年龄来比较不同的`Person`实例：

```
class Person:
    def __init__(self, name, age):
        self.name = name
        self.age = age

    def __lt__(self, other):
        return self.age < other.age

    def __eq__(self, other):
        return self.age == other.age
```

在这个例子中，`__lt__`方法使得我们可以使用小于运算符 (`<`) 来比较两个`Person`实例的年龄，而`__eq__`方法则用于判断两个实例是否拥有相同的年龄。

### 使用场景

比较方法在Python中的应用非常广泛，特别是在需要对自定义对象进行排序或比较的场合。例如：

- 在使用`sort()`方法或`sorted()`函数对列表进行排序时，可以根据对象的某个属性进行排序。
- 在将对象插入到`PriorityQueue`等需要根据某种优先级排序的数据结构时，可以定义优先级的比较逻辑。
- 在实现一些需要元素比较的算法时，比如搜索、排序算法等。

通过定义这些方法，你可以让自定义的类更加灵活和强大，使其能够适应各种需要比较操作的场景。

# 第01课 文字游戏

## 1. 输入输出函数

==input==函数 输入内容 接收到的都是**字符串**

==print==函数 输出内容

==int==函数 转换为整型

## 2. 循环语句

==while==语句 **死循环**

==for==语句 常用于**循环遍历**

​		均与**continue**和**break**配套使用，其中，continue作用为结束当前循环开始下一次循环，break为退出循环。

## 3.代码案例

```python
#print("请输入收款人姓名：")
\#a=input()
a=input("请输入收款人姓名")
print("请输入性别")
b=input()
\#c=int(b)


print("\n\n   微信收款凭证\n")
print("金额:",b)
print("收款人",a)

if(b=="男"):
    print("大款在你眼前，推VIP")
    print("加油勇士")
else:
    print("正常女客户")


print("Hero,你已经来到了地狱门口")
point=1

while(1):       #循环
    if(print==1):
        t=input("请选择：1左边3教   2中间1教  3右边2教")
        if(t=="1"):
            print("你选择了左边3教")
            point==3
        if(t=="2"):
            print("你选择了中间1教")
            point=0
        if(t=="3"):
            print("你选择了右边2教")
            point=2
        
    if(print==2):
        t=input("请选择：1向前6教   2返回大门")
        if(t=="1"):
            print("你选择了6教")
            point=6
        if(t=="2"):
            print("你回到了大门口")
            point=1
```

***



# 第02课 windows LOGO

## 1. turtle库基本使用

==penup()== 抬起画笔

==pendown()== 放下画笔

==goto(x,y)== 去(x,y)位置处

==forward(x)== 前进x

==backward(x)== 后退x

==right/left(x)== 左右转

==color(x,y)== x为画笔颜色，y为填充颜色，填充时需要搭配begin_fill()和end_fill() 



## 2. 代码案例

### 画五星红旗

```python
import turtle

turtle.pensize(1)

turtle.speed(0)

turtle.color("red", "red")
turtle.begin_fill()
turtle.penup()
turtle.goto(-300, 200)
turtle.pendown()
\# 国旗旗帜
turtle.forward(600)
turtle.right(90)
turtle.forward(400)
turtle.right(90)
turtle.forward(600)
turtle.right(90)
turtle.forward(400)
turtle.end_fill()
\# 大五角星
turtle.color("yellow", "yellow")
turtle.begin_fill()
turtle.penup()
turtle.goto(-260, 120)
turtle.pendown()
turtle.right(90)
turtle.forward(120)
turtle.right(144)
turtle.forward(120)
turtle.right(144)
turtle.forward(120)
turtle.right(144)
turtle.forward(120)
turtle.right(144)
turtle.forward(120)
turtle.end_fill()
\# 小五角星1
turtle.color("yellow", "yellow")
turtle.begin_fill()
turtle.penup()
turtle.goto(-80, 160)
turtle.left(6)
turtle.pendown()
turtle.forward(40)
turtle.left(144)
turtle.forward(40)
turtle.left(144)
turtle.forward(40)
turtle.left(144)
turtle.forward(40)
turtle.left(144)
turtle.forward(40)
turtle.end_fill()
\# 小五角星2
turtle.color("yellow", "yellow")
turtle.begin_fill()
turtle.penup()
turtle.goto(-80, 120)
turtle.pendown()
turtle.left(6)
turtle.forward(40)
turtle.right(144)
turtle.forward(40)
turtle.right(144)
turtle.forward(40)
turtle.right(144)
turtle.forward(40)
turtle.right(144)
turtle.forward(40)
turtle.end_fill()
\# 小五角星3
turtle.color("yellow", "yellow")
turtle.begin_fill()
turtle.penup()
turtle.goto(-80, 65)
turtle.pendown()
turtle.left(205)
turtle.forward(40)
turtle.right(144)
turtle.forward(40)
turtle.right(144)
turtle.forward(40)
turtle.right(144)
turtle.forward(40)
turtle.right(144)
turtle.forward(40)
turtle.end_fill()
\# 小五角星4
turtle.color("yellow", "yellow")
turtle.begin_fill()
turtle.penup()
turtle.goto(-80, 20)
turtle.pendown()
turtle.left(10)
turtle.forward(40)
turtle.left(144)
turtle.forward(40)
turtle.left(144)
turtle.forward(40)
turtle.left(144)
turtle.forward(40)
turtle.left(144)
turtle.forward(40)
turtle.end_fill()
turtle.right(12)
turtle.forward(100)
```

***



# 第03课 肥胖计算器

## 1. 数据类型

==int(x)== 转换为**整数**

==float(x)== 转换为**浮点数**

==str(x)== 转换为**字符串**

## 2. 定义子函数

==def== 定义函数  作用：减少代码的重复

## 3. turtle库的使用

==pensize（x）== 画笔粗细

==speed（x）== 画笔速度

==hideturtle（）==隐藏画笔箭头

==tracer（True/Forse）== 是否隐藏绘画过程

## 4. 代码案例

### 4.1 模块法画五星红旗

```python
# ——————载入库————————
import turtle as t

t.pensize(1)
t.speed(0)
t.hideturtle()


# ——————模块——————
# 画旗帜，x为横坐标，y为纵坐标
def flag(x, y):
    t.penup()
    t.goto(x, y)
    t.pendown()
    t.color("red", "red")
    t.begin_fill()
    t.forward(300)
    t.right(90)
    t.forward(200)
    t.right(90)
    t.forward(300)
    t.right(90)
    t.forward(200)
    t.end_fill()


# 大星星
def big_star(a, b):
    t.color("yellow", "yellow")
    t.begin_fill()
    t.penup()
    t.goto(a, b)
    t.pendown()
    t.right(90)
    t.forward(60)
    t.right(144)
    t.forward(60)
    t.right(144)
    t.forward(60)
    t.right(144)
    t.forward(60)
    t.right(144)
    t.forward(60)
    t.end_fill()


# 小星星(左)
def star_left(m, n, k):  # m为横坐标，n为纵坐标，k为画笔左转角度
    t.color("yellow", "yellow")
    t.begin_fill()
    t.penup()
    t.goto(m, n)
    t.pendown()
    t.left(k)
    t.forward(20)
    t.left(144)
    t.forward(20)
    t.left(144)
    t.forward(20)
    t.left(144)
    t.forward(20)
    t.left(144)
    t.forward(20)
    t.end_fill()


# 小星星(右)
def star_right(m, n, k):  # m为横坐标，n为纵坐标，k为画笔左转角度
    t.color("yellow", "yellow")
    t.begin_fill()
    t.penup()
    t.goto(m, n)
    t.pendown()
    t.left(k)
    t.forward(20)
    t.right(144)
    t.forward(20)
    t.right(144)
    t.forward(20)
    t.right(144)
    t.forward(20)
    t.right(144)
    t.forward(20)
    t.end_fill()


# 画整个国旗
def draw(x, y):  # (x,y)为整面国旗的左上角位置
    flag(x, y)
    big_star(x + 20, y - 40)
    star_left(x + 110, y - 20, 6)
    star_right(x + 110, y - 40, 6)
    star_right(x + 110, y - 67.5, 205)
    star_left(x + 110, y - 90, 10)


# ——————主程序——————
draw(-400, 300)
t.right(11)
draw(100, 300)
t.right(11)
draw(-400, -100)
t.right(11)
draw(100, -100)
t.mainloop()

```

### 4.2 绩点计算器&肥胖计算器

```python
# 选择计算机
b = "1"
while b == "1":
    a = input("请您选择 1：肥胖计算器 2：绩点计算器\n")
    # 肥胖计算器
    if a == "1":
        print("欢迎使用肥胖计算器")
        height = float(input("请输入身高：(单位:米)"))
        weight = float(input("请输入体重："))
        bmi = (weight / (height ** 2))
        print("肥胖指数为%.2f" % bmi)

    # 绩点计算器
    if a == "2":
        print("欢迎使用绩点计算器\n")
        m = float(input("请输入高数成绩\n"))
        e1 = float(input("请输入英语读写成绩：\n"))
        e2 = float(input("请输入英语听说成绩：\n"))
        c = float(input("请输入计算机导论成绩：\n"))
        # 计算数学单科绩点
        if m >= 60:
            math = float((m - 50) / 10 * 4)
        if m < 60:
            math = float(0)
        # 计算英语读写单科绩点
        if e1 >= 60:
            english1 = float((e1 - 50) / 10 * 5)
        if e1 < 60:
            english1 = float(0)
        # 计算英语听说单科绩点
        if e2 >= 60:
            english2 = float((e2 - 50) / 10 * 2)
        if e2 < 60:
            english2 = float(0)
        # 计算计算机导论单科绩点
        if c >= 60:
            computer = float((c - 50) / 10 * 2)
        if c < 60:
            computer = float(0)
        # 计算总绩点
        print("您的总绩点为:")
        GPA = ((math + english1 + english2 + computer) / 13)
        print("您的绩点为%.2f" % GPA)

    print("请重新选择：\n")
    b = input("1:继续 2：结束\n")
    if b == "2":
        print("感谢使用，下次再见")

```



# 第04课 表情包

## 1. turtle库使用

==circle（x, y）== x为**正**数，圆心在**左侧**，x为**负**数，圆心在**右侧**，x的绝对值为**圆的大小**；y为**正**，**顺**时针画，y为**负**，**逆**时针画，y的绝对值表示所画**弧的度数大小**，省略y即为画整个圆

==sethheading（x）== 设置画笔**绝对方向**

==mainloop（）== 画布停留

## 2. 代码案例

###  2.1 四个表情同框

```python
#  ---------------载入库---------------
import turtle as t

t.speed(0)
t.hideturtle()


# ---------------模块---------------
def move(x, y):
    t.penup()
    t.goto(x, y)
    t.pendown()


def face(x, y):  # 脸部
    t.pensize(3)
    t.seth(0)
    t.color("orange", "yellow")
    t.begin_fill()
    t.penup()
    t.goto(x, y)
    t.pendown()
    t.circle(150)
    t.end_fill()


def eye1(x, y):  # 大眼
    t.pensize(2)
    t.color("orange", "white")
    t.begin_fill()
    t.penup()
    t.goto(x, y)
    t.pendown()
    t.circle(30)
    t.end_fill()


def eye2(x, y):  # 小眼
    t.pensize(1)
    t.color("black", "black")
    t.begin_fill()
    t.penup()
    t.goto(x, y)
    t.pendown()
    t.circle(18)
    t.end_fill()


def smile(x, y, z):  # 弧度
    t.pensize(3)
    t.color("orange")
    t.penup()
    t.goto(x, y)
    t.pendown()
    t.circle(80, z)


def rectangle1(x, y):
    t.pensize(3)
    t.penup()
    t.goto(x, y)
    t.pendown()
    t.color("orange", "white")
    t.begin_fill()
    t.forward(90)
    t.circle(-5, 90)
    t.forward(20)
    t.circle(-5, 90)
    t.forward(90)
    t.circle(-5, 90)
    t.forward(20)
    t.circle(-5, 90)
    t.end_fill()


def rectangle2(x, y):
    t.pensize(3)
    t.penup()
    t.goto(x, y)
    t.pendown()
    t.color("red", "white")
    t.begin_fill()
    t.forward(85)
    t.circle(-5, 90)
    t.forward(35)
    t.circle(-5, 90)
    t.forward(85)
    t.circle(-5, 90)
    t.forward(35)
    t.circle(-5, 90)
    t.end_fill()


def black(x, y):
    t.penup()
    t.goto(x, y)
    t.pendown()
    t.color("black", "black")
    t.begin_fill()
    t.circle(-17, 360)
    t.end_fill()


def half_circle(x, y):
    move(x, y)
    t.seth(-90)
    t.color("black", "black")
    t.begin_fill()
    t.circle(20, 180)
    t.end_fill()


# ---------------主程序---------------
# 左上笑脸
face(-200, 100)
eye1(-250, 300)  # 左眼大
eye2(-250, 300)  # 左眼小
eye1(-150, 300)  # 右眼大
eye2(-150, 300)  # 右眼小
t.seth(75)  # 设置绝对方向
smile(-120, 200, -150)  # 画微笑

# 右上哭脸
face(100, 100)
eye1(50, 300)  # 左眼大
eye2(50, 300)  # 左眼小
eye1(150, 300)  # 右眼大
eye2(150, 300)  # 右眼小
t.seth(103)  # 设置绝对方向
smile(180, 170, 150)  # 画哭泣

# 左下表情
face(-250, -300)  # 脸部
rectangle1(-365, -90)  # 左眼
half_circle(-340, -90)
t.seth(0)
rectangle1(-210, -90)  # 右眼
half_circle(-195, -90)
t.seth(0)
t.color("orange")
move(-270, -150)  # 嘴
t.forward(50)

# 右下表情
face(150, -300)  # 脸部
rectangle2(35, -90)  # 左眼
black(80, -95)
rectangle2(180, -90)  # 右眼
black(220, -95)
t.seth(-30)  # 微笑
smile(110, -200, 60)

t.mainloop()

```

### 2.2 模块法画国旗

```python
# --------------载入库---------------
import turtle as t

t.speed(0)
t.hideturtle()


# --------------模块-----------------
def roundness(a, b):  # 圆
    t.color("white", a)
    t.begin_fill()
    t.circle(b)
    t.end_fill()


def move(x, y):  # 画笔移动到（x,y）位置处
    t.penup()
    t.goto(x, y)
    t.pendown()


def star():  # 五角星
    t.color("white", "white")
    t.begin_fill()
    t.forward(110)
    t.right(144)
    t.forward(110)
    t.right(144)
    t.forward(110)
    t.right(144)
    t.forward(110)
    t.right(144)
    t.forward(110)
    t.end_fill()


# ----------------主程序---------------
# 画左侧美国队长标志
move(-200, -100)
roundness("red", 150)  # 最大的红色圆圈
move(-200, -70)
roundness("white", 120)  # 第二个白色圆圈
move(-200, -40)
roundness("red", 90)  # 第三个红色圆圈
move(-200, -10)
roundness("blue", 60)  # 最后一个蓝色圆圈
move(-255, 68)
star()  # 画五角星
# 画右侧搞笑美国队长标志
t.seth(0)
move(200, -100)
roundness("red", 150)  # 最大的红色圆圈
move(200, -70)
roundness("white", 120)  # 第二个白色圆圈
move(200, -40)
roundness("red", 90)  # 第三个红色圆圈
move(200, -10)
roundness("blue", 60)  # 最后一个蓝色圆圈
move(145, 68)
star()  # 画五角星
# 搞笑元素
move(215, 75)  # 黄色圆圈
roundness("yellow", 25)
move(192, 65)  # 左眼大
roundness("white", 6)
move(192, 62)  # 左眼小
roundness("black", 4)
move(215, 65)  # 右眼大
roundness("white", 6)
move(215, 62)  # 右眼小
roundness("black", 4)

t.color("black")
t.pensize(2)

t.seth(160)  # 左眉毛
move(195, 65)
t.forward(10)
t.seth(20)  # 右眉毛
move(208, 65)
t.forward(10)
t.seth(0)  # 嘴
move(200, 40)
roundness("gray", 5)
t.mainloop()

```



# 第05课 九九表&脱单计算器

## 1. 运算符

// 取整除

% 取余

** 指数

## 2. 字符串拼接

+ **% 占位符** 

**%s**字符串占位

 **%d**整数占位 

**%f**浮点数占位

## 3.精度控制

**m.n** 

​	m控制宽度，小于数字自身时无效

​	.n控制小数点精度 会***四舍五入*** 

​	f"内容{变量}" 快速格式化

## 4. 比较运算符

== 是否相等 != 是否不相等

## 5. 条件判断语句

if，elif，else语句	其中else不需要条件

## 6. 代码案例

### 6.1 判断素数方法1

```python
a = 0  # 计算素数个数的变量
for i in range(2, 1001):  # 循环遍历1到1000所有的数
    j = 2
    for j in range(2, i):  # 判断是否有除了1和自身的因子
        if i % j == 0:  # 条件成立时证明有因子，不是素数
            break  # 直接结束循环
    else:  # 在此之前没有结束循环，此数为素数
        print(i, end=',')  # 输出该数并且不换行
        a += 1  # 素数个数加1
print(f"1到1000共有{a}个素数")

```

### 6.2 判断素数方法2

```python
# ------------模块设计---------------
def judge(a):  # 通过布尔类型判断是否为素数并将结果返回给子函数
    if a < 2:  # 1不是素数
        return False
    if a < 4:  # 2和3都是素数
        return True
    if a % 2 == 0:  # 能被2整除的数都不是素数
        return False
    for i in range(3, int(a ** 0.5) + 1, 2):  # 若为合数且为奇数，必定有一个比所给数开根号小的因子
        if a % i == 0:
            return False
    else:
        return True


# -------------主程序------------
x = 0  # 素数的个数
list = []
for num in range(1, 1001):  # 循环遍历从1到1000的数判断是否为素数
    if judge(num):  # 结果为True，输入该数并给x加1
        list.append(num)
        x += 1
print(list)
print(f"\n1到1000共有{x}个素数")  # 输出从1到1000共有多少素数

```

### 6.3 九九表(四种)

```python
#  正九九乘法表
for i in range(1, 10):  # 从1取到9
    j = 1  # 重新赋值j等于1
    while j <= i:  # 第一个数字从1到i乘以i
        print(f"{j}*{i}={j * i}\t", end="")  # \t制表符，end起不换行的作用
        j += 1  # 将j加1后重新赋值给i
    print()  # 起到换行的作用
    i += 1  # 每次循环将后一个数字加1
print()  # 换行作用

print()

#  倒九九乘法表
j = 9
for number in range(9):  # 循环9次
    i = 1  # 每次循环都把i重新赋值为1
    while i <= j:
        print(f"{i}*{j}={i * j}\t", end='')
        i += 1  # 将i加1后重新赋值给i
    print()  # 换行
    j -= 1

print()

for i in range(1, 10):
    for j in range(1, i + 1):
        print(f"{j}*{i}={j * i}\t", end='')
    print()

print()

j = 9
for number in range(9):
    i = 0
    for a in range(j):
        i += 1
        print(f"{i}*{j}={i * j}\t", end='')
    j -= 1
    print()

```



# 第06课 纸飞机&直方图

## 1.列表的使用

列表=[]

列表.**index**（元素）查下标

列表.**insert**（下标元素）在指定位置插入元素

列表.**append**（元素）追加元素

列表.**extend**（其他数据容器）追加一批元素

删除元素：

​	方法1：**del** 列表[下标]

​	方法2：列表.**pop**（下标）	此方法可以将删除的元素作为**返回值**用变量接收

​	方法3：列表.**remove**（元素）如果有重复的相同元素，**只会删除第一个**

## 2. 代码案例

### 2.1 纸飞机

```python
# 载入库
import turtle as t

t.tracer(False)  # 隐藏作图轨迹


# 定义函数
def cir():  # 太阳
    t.color('red', 'red')
    t.begin_fill()
    t.penup()
    t.goto(250, 200)
    t.pendown()
    t.circle(50)
    t.end_fill()


def line(x1, y1, x2, y2, x3, y3):  # 飞机
    t.color('black', 'blue')
    t.pensize(3)
    t.penup()
    t.goto(x1, y1)
    t.pendown()
    t.begin_fill()
    t.goto(x2, y2)
    t.goto(x3, y3)
    t.goto(x1, y1)
    t.end_fill()


def line2(x1, y1, x2, y2):  # 线条
    t.penup()
    t.pensize(4)
    t.goto(x1, y1)
    t.pendown()
    t.goto(x2, y2)


# 主程序
my_list = [[0, 0], [100, 50], [-300, 150], [-300, 150], [-50, -50], [-125, -125], [-50, -50],
           [-85, -85], [-30, -125]]  # 飞机参数
my_list2 = [[75, 25], [200, 0], [50, -5], [250, -30], [10, -80],
            [100, -150], [-80, -125], [120, -200]]  # 线条参数
cir()  # 画太阳
# 画飞机
line(my_list[0][0], my_list[0][1], my_list[1][0], my_list[1][1], my_list[2][0], my_list[2][1])
line(my_list[3][0], my_list[3][1], my_list[4][0], my_list[4][1], my_list[5][0], my_list[5][1])
line(my_list[6][0], my_list[6][1], my_list[7][0], my_list[7][1], my_list[8][0], my_list[8][1])
# 画线条
line2(my_list2[0][0], my_list2[0][1], my_list2[1][0], my_list2[1][1])
line2(my_list2[2][0], my_list2[2][1], my_list2[3][0], my_list2[3][1])
line2(my_list2[4][0], my_list2[4][1], my_list2[5][0], my_list2[5][1])
line2(my_list2[6][0], my_list2[6][1], my_list2[7][0], my_list2[7][1])
line2(-80, -125, 120, -200)
line2(0, 0, -30, -125)
line2(0, 0, -30, -125)
t.mainloop()

```

### 2.2 填充法画直方图

```python
# 载入库
import turtle as t

t.pensize(1)
t.speed(0)
t.hideturtle()


# 定义子函数
def block(a, b, x, y):
    t.color("black", "black")
    t.penup()
    t.goto(a, b)
    t.pendown()
    t.begin_fill()
    t.left(90)
    t.forward(x)
    t.left(90)
    t.forward(y)
    t.left(90)
    t.forward(x)
    t.left(90)
    t.forward(y)
    t.end_fill()


# 主程序
my_list = [[69, 15], [292, 10], [33, 8], [131, 10], [61, 5], [254, 10], [100, 15], [80, 25]]  # 数据参数
# 画框架
t3 = t.Turtle()
t3.penup()
t3.goto(-400, -200)
t3.pendown()
t2 = t3.clone()
t2.pensize(3)
t3.pensize(3)
t3.forward(800)
t2.seth(90)
t2.forward(400)

m = -350  # 定义初始横坐标
n = -200  # 定义初始纵坐标
for i in range(len(my_list)):  # 循环遍历(列表数量-1)次
    if i < len(my_list) - 1:  # 填充法绘制柱状图
        block(m, n, my_list[i][0], my_list[i][1])
        m += 50 + my_list[i + 1][1]  # 控制每个柱形的间距相等
    else:
        block(m, n, my_list[i][0], my_list[i][1])  #

t.mainloop()

```

### 2.3 描线法画直方图

```python
# 载入库
import turtle as t

t.pensize(1)
t.speed(0)


# 定义子函数
def line(x, y, length):  # 线条 (x,y)为线条的起点，length为线条的长度
    t.penup()
    t.goto(x, y)
    t.pendown()
    t.seth(90)
    t.forward(length)


# 主程序
my_list = [[69, 15], [292, 10], [33, 8], [131, 10], [61, 5], [254, 10], [100, 15], [80, 25]]  # 数据参数
# 框架
t3 = t.Turtle()
t3.penup()
t3.goto(-400, -200)
t3.pendown()
t2 = t3.clone()
t2.pensize(3)
t3.pensize(3)
t3.forward(800)
t2.seth(90)
t2.forward(400)
x = -350  # 初始横坐标
for num in range(len(my_list)):  # 循环柱状次数
    for i in range(my_list[num][1]):  # 每条柱的宽度
        line(x, -200, my_list[num][0])
        x += 1
    x += 50  # 控制每个柱之间的距离相等
t.mainloop()

```



# 第07课 排序算法

## 1. 选择排序

```python
# 选择排序
ls = [12, 40, 10, 9, 8, -1, 21, -6]
ls2 = []
print(ls)
# 普通方法
n = 0  # 交换次数
for j in range(len(ls) - 1):
    for i in range(len(ls) - 1 - j):
        if ls[j] > ls[i + j + 1]:
            ls[j], ls[i + j + 1] = ls[i + j + 1], ls[j]
            n += 1
            '''
            tmp = ls[0]
            ls[0] = ls[i + 1]
            ls[i + 1] = tmp
            '''
print(ls)
print(f"普通方法交换次数为{n}次")

# 改进方法
ls = [12, 40, 10, 9, 8, -1, 21, -6]
n = 0
for j in range(len(ls) - 1):
    f = j
    for i in range(len(ls) - 1 - j):
        if ls[f] > ls[j + i + 1]:
            f = j + i + 1
    ls[j], ls[f] = ls[f], ls[j]
    n += 1
print(ls)
print(f"优化方法交换次数为{n}次")

# 最优方法
ls = [12, 40, 10, 9, 8, -1, 21, -6]
n = 0
for j in range(len(ls) - 1):
    f = j
    for i in range(len(ls) - 1 - j):
        if ls[f] > ls[j + i + 1]:
            f = j + i + 1
    if f != j:
        ls[j], ls[f] = ls[f], ls[j]
        n += 1
print(ls)
print(f"最优方法交换次数为{n}次")

```

## 2. 冒泡排序

```python
# 冒泡排序
ls = [12, 40, 10, 9, 8, -1, 21, -6]
m = 0
for a in range(len(ls) - 1):
    for i in range(len(ls) - a - 1):
        if ls[i] > ls[i + 1]:
            ls[i], ls[i + 1] = ls[i + 1], ls[i]
            m += 1
print(ls)
print(f"共交换{m}次")

```



# 第08课 斗地主自动发牌机

## 1. random随机数库

==random.dandint（x，y）==随机整数

==random.random（）==随机小数

## 2. turtle库用法

==write（字符串，font=(”微软雅黑“，50，"normal")）==

## 3. 代码案例

### 3.1 斗地主发牌机文字版

```python
import random

pk = ["红心A", "红心2", '红心3', '红心4', '红心5', '红心6', '红心7', '红心8', '红心9', '红心10',
      '红心J', '红心Q', '红心K', '方块A',  '方块2', '方块3', '方块4', '方块5', '方块6',
      '方块7', '方块8', '方块9', '方块10', '方块J', '方块Q', '方块K', '黑桃A',  '黑桃2',
      '黑桃3', '黑桃4', '黑桃5', '黑桃6', '黑桃7', '黑桃8', '黑桃9', '黑桃10', '黑桃J', '黑桃Q',
      '黑桃K', '梅花A', '梅花2', '梅花3', '梅花4', '梅花5', '梅花6', '梅花7', '梅花8', '梅花9',
      '梅花10', '梅花J', '梅花Q', '梅花K', '大王', '小王']
people1 = []
people2 = []
people3 = []
# 每人先发出17张牌
for piece in range(17):
    list_num = random.randint(0, 53 - piece)  #
    people1.append(pk[list_num])  # 追加给人
    del pk[list_num]  # 删除牌库中对应的牌

for piece in range(17):  # 每人先发17张
    list_num = random.randint(0, 53 - piece - 17)  #
    people2.append(pk[list_num])  # 追加给人
    del pk[list_num]  # 删除牌库中对应的牌

for piece in range(17):  # 每人先发17张
    list_num = random.randint(0, 53 - piece - 17 - 17)  #
    people3.append(pk[list_num])  # 追加给人
    del pk[list_num]  # 删除牌库中对应的牌

# 选出地主并发牌
select = random.randint(1, 3)
if select == 1:
    people1.extend(pk)
    print(f"people1为地主，他拥有的牌是：{people1}\n")
    print(f"people2为农民，他拥有的牌为：{people2}\n")
    print(f"people3为农民，他拥有的牌为：{people3}")

if select == 2:
    people2.extend(pk)
    print(f"people1为农民，他拥有的牌是：{people1}\n")
    print(f"people2为地主，他拥有的牌为：{people2}\n")
    print(f"people3为农民，他拥有的牌为：{people3}")

if select == 3:
    people3.extend(pk)
    print(f"people1为农民，他拥有的牌是：{people1}\n")
    print(f"people2为农民，他拥有的牌为：{people2}\n")
    print(f"people3为地主，他拥有的牌为：{people3}")

```

### 3.2 斗地主发牌机图形版

```python
# 载入库
import turtle as t
import random

t.screensize(bg="gray")
t.tracer(False)
t.hideturtle()
ch1 = '\u2665'  # 红心
ch2 = '\u2660'  # 黑桃
ch3 = '\u2666'  # 方块
ch4 = '\u2663'  # 梅花


def move(x, y, z):
    t.penup()
    t.goto(x, y)
    t.pendown()
    t.seth(z)


def block(x, y):
    move(x, y, 0)
    t.color("black", "white")
    t.begin_fill()
    t.forward(45.6)
    t.right(90)
    t.forward(70.4)
    t.right(90)
    t.forward(45.6)
    t.right(90)
    t.forward(70.4)
    t.end_fill()


def draw(x1, y1, x2, y2, x3, y3, x4, y4, num, little_flower, big_flower, pencolor):
    move(x1, y1, -90)
    t.write(num, font=("微软雅黑", 12, "normal"))
    move(x2, y2, -90)
    t.color(pencolor)
    t.write(little_flower, font=("微软雅黑", 12, "normal"))
    move(x3, y3, 0)
    t.write(big_flower, font=("微软雅黑", 30, "normal"))
    move(x4, y4, 0)


pk = ["A", "2", '3', '4', '5', '6', '7', '8', '9', '10', 'J', 'Q', 'K',
      "A", "2", '3', '4', '5', '6', '7', '8', '9', '10', 'J', 'Q', 'K',
      "A", "2", '3', '4', '5', '6', '7', '8', '9', '10', 'J', 'Q', 'K',
      "A", "2", '3', '4', '5', '6', '7', '8', '9', '10', 'J', 'Q', 'K',
      "J\nO\nK\nE\nR.", "J\nO\nK\nE\nR"]
color = [ch1, ch1, ch1, ch1, ch1, ch1, ch1, ch1, ch1, ch1, ch1, ch1, ch1,
         ch2, ch2, ch2, ch2, ch2, ch2, ch2, ch2, ch2, ch2, ch2, ch2, ch2,
         ch3, ch3, ch3, ch3, ch3, ch3, ch3, ch3, ch3, ch3, ch3, ch3, ch3,
         ch4, ch4, ch4, ch4, ch4, ch4, ch4, ch4, ch4, ch4, ch4, ch4, ch4,
         "", ""]
pen_color = ["red", "red", "red", "red", "red", "red", "red", "red", "red", "red", "red", "red", "red",
             "black", "black", "black", "black", "black", "black", "black", "black", "black", "black", "black", "black",
             "black",
             "red", "red", "red", "red", "red", "red", "red", "red", "red", "red", "red", "red", "red",
             "black", "black", "black", "black", "black", "black", "black", "black", "black", "black", "black", "black",
             "black", "red", "black"]

total = 54
x = -400
y = 200

for j in range(2):
    for i in range(17):
        send = random.randint(0, total - 1 - i)
        if pk[send] == "J\nO\nK\nE\nR.":
            block(x, y)
            move(x + 5, y - 70, 0)
            t.color("red")
            t.write(pk[send], font=("微软雅黑", 7, "normal"))
            x += 20
            del pk[send]
            del color[send]
        elif pk[send] == "J\nO\nK\nE\nR":
            block(x, y)
            move(x + 5, y - 70, 0)
            t.color("black")
            t.write(pk[send], font=("微软雅黑", 7, "normal"))
            x += 20
            del pk[send]
            del color[send]
        else:
            block(x, y)
            draw(x + 5, y - 20, x + 3, y - 35, x + 10, y - 60, x, y, pk[send], color[send], color[send],
                 pen_color[send])
            x += 20
            del pk[send]
            del color[send]
    x = 100
    total -= 17
x = -200
y = -100
for i in range(20):
    send = random.randint(0, total - 1 - i)
    if pk[send] == "J\nO\nK\nE\nR.":
        block(x, y)
        move(x + 5, y - 70, 0)
        t.color("red")
        t.write(pk[send], font=("微软雅黑", 7, "normal"))
        x += 20
        del pk[send]
        del color[send]
    elif pk[send] == "J\nO\nK\nE\nR":
        block(x, y)
        move(x + 5, y - 70, 0)
        t.color("black")
        t.write(pk[send], font=("微软雅黑", 7, "normal"))
        x += 20
        del pk[send]
        del color[send]
    else:
        block(x, y)
        draw(x + 5, y - 20, x + 3, y - 35, x + 10, y - 60, x, y, pk[send], color[send], color[send],
             pen_color[send])
        x += 20
        del pk[send]
        del color[send]
t.tracer(True)
t.mainloop()

```



# 第09课 猴子吃桃

## 1. format控制符具体用法

![image-20231025113403383](D:\Typora笔记\python笔记.assets\image-20231025113403383-16982048477121.png)

## 2. 运算

==and==与运算 ==or==或运算 ==not== 非运算

## 3. 代码案例

### 3.1 猴子吃桃

```python
# 猴子吃桃问题
num = 1
for i in range(1, 10):
    num = (num + 1) * 2
    print(f"第{10-i}天猴子有{num}个桃")

```

### 3.2 逢三过

```python
# 逢三过
print("欢迎使用逢三过作弊器")
total = int(input("请输入游戏总人数"))
location = int(input("请输入你位于第几位："))
num1 = location  # 数字
speak = 1
while 1:
    if num1 % 3 == 0 or '3' in str(num1):
        input(f"第{speak}次不需要报数")
        num1 += total
        speak += 1
    elif num1 % 3 != 0:
        input(f"第{speak}次你要说的数字是：{num1}")
        num1 += total
        speak += 1

```

### 3.3 闰年计算器

```python
# 求闰年数量
print("欢迎使用闰年计算器\n")
while 1:
    start = int(input("请输入起始年份:\n"))
    end = int(input("请输入结束年份:\n"))
    all_years = []
    num = 0
    print("闰年有：", end='')
    for year in range(start, end + 1):
        if year % 100 == 0:
            if year % 400 == 0:
                print(year, end=',')
                num += 1
                continue
        elif year % 100 != 0 and year % 4 == 0:
            print(year, end=',')
            num += 1
        else:
            pass
    print(f"在{start}和{end}之间共有{num}个闰年")
    a = input("您还要再玩一次吗？ 1:继续 2.不玩了")
    if a == '2':
        print("\n闰年计算器已关闭")
        break

```



# 第10课 凯撒密码&斯诺克台球

## 1. ASCII码表

==ord（）==转换为ascii字符

==chr（）==转换回原内容

![](D:\Typora笔记\python笔记.assets\image-20231025114030753-16982052339642.png)

## 2. turtle库使用

==turtle.xcor（）==获取x轴位置，需要用变量接收

==turtle.ycor（）==获取y轴位置 ，需要用变量接收

## 3. 代码案例

### 3.1 凯撒密码

```python
print("欢迎使用凯撒法加密与解密器")

while 1:
    a = int(input("\n请选择：1.加密 2.解密 "))

    if a == 1:
        write = input("请输入你要加密的内容：")

        print("加密后的内容为：")
        for i in write:
            num1 = ord(i) + 3
            re_write = chr(num1)
            print(re_write, end='')

    if a == 2:
        write = input("请输入你要解密的内容：")

        print("解密后的内容为：")
        for i in write:
            num1 = ord(i) - 3
            re_write = chr(num1)
            print(re_write, end='')

    b = int(input("\n你还要继续使用吗？ 1.继续 2.结束"))
    if b == 1:
        continue
    if b == 2:
        break

```

### 3.2 斯诺克台球

```python
# ---------------------------初始化-------------------------
import turtle as t
import time

t.hideturtle()
t.speed(0)
t2 = t.Turtle()
t2.hideturtle()


# --------------------------子函数------------------------------
def move(x, y):
    t.penup()
    t.goto(x, y)
    t.pendown()
    t.seth(0)


def block(x, y, length1, length2, color):
    move(x, y)
    t.color(color, color)
    t.begin_fill()
    t.forward(length1)
    t.right(90)
    t.forward(length2)
    t.right(90)
    t.forward(length1)
    t.right(90)
    t.forward(length2)
    t.end_fill()


def circle(x, y, size, color):
    move(x, y)
    t.color(color, color)
    t.begin_fill()
    t.circle(size)
    t.end_fill()


# --------------------数据列表-----------------------

# 桌面数据
desk_data = [[-400, 220, 800, 440, "darkgrey"], [-350, 175, 700, 350, "green"], [-330, 220, 660, 45, "rosybrown"],
             [-330, -175, 660, 45, "rosybrown"], [-400, 150, 50, 300, "rosybrown"], [350, 150, 50, 300, "rosybrown"]]
desk_data2 = [[-200, 175, "black", -90, 350], [-200, 70, "black", 180, 70, 180]]
# 台球数据
billiards_data = [[-200, 55, 10, "olive"], [-200, -10, 10, "khaki"], [-200, -75, 10, "yellow"],
                  [-270, -10, 10, "white"], [-50, -10, 10, "blue"], [80, -10, 10, "khaki"],
                  [300, -10, 10, "black"]]

# -------------------------主程序---------------------------

# 桌面
block(desk_data[0][0], desk_data[0][1], desk_data[0][2], desk_data[0][3], desk_data[0][4])
block(desk_data[1][0], desk_data[1][1], desk_data[1][2], desk_data[1][3], desk_data[1][4])
block(desk_data[2][0], desk_data[2][1], desk_data[2][2], desk_data[2][3], desk_data[2][4])
block(desk_data[3][0], desk_data[3][1], desk_data[3][2], desk_data[3][3], desk_data[3][4])
block(desk_data[4][0], desk_data[4][1], desk_data[4][2], desk_data[4][3], desk_data[4][4])
block(desk_data[5][0], desk_data[5][1], desk_data[5][2], desk_data[5][3], desk_data[5][4])

# 球袋
n = 140
for i in range(2):
    m = -350
    for j in range(3):
        circle(m, n, 30, "gray")
        m += 350
    n -= 330

# 线条
move(desk_data2[0][0], desk_data2[0][1])
t.color(desk_data2[0][2])
t.seth(desk_data2[0][3])
t.forward(desk_data2[0][4])
move(desk_data2[1][0], desk_data2[1][1])
t.color(desk_data2[1][2])
t.seth(desk_data2[1][3])
t.circle(desk_data2[1][4], desk_data2[1][5])

# 台球
draw = 5
p = 250
q = 30
for i in range(5):
    for j in range(draw):
        circle(p, q, 10, "darkred")
        q -= 20
    p -= 20
    q += 20 * (draw - 1) + 10
    draw -= 1

circle(billiards_data[0][0], billiards_data[0][1], billiards_data[0][2], billiards_data[0][3])
circle(billiards_data[1][0], billiards_data[1][1], billiards_data[1][2], billiards_data[1][3])
circle(billiards_data[2][0], billiards_data[2][1], billiards_data[2][2], billiards_data[2][3])
circle(billiards_data[4][0], billiards_data[4][1], billiards_data[4][2], billiards_data[4][3])
circle(billiards_data[5][0], billiards_data[5][1], billiards_data[5][2], billiards_data[5][3])
circle(billiards_data[6][0], billiards_data[6][1], billiards_data[6][2], billiards_data[6][3])

t2.penup()
t2.goto(-270, -10)
t2.pendown()
sleep = 0.01
for i in range(80):
    t.tracer(False)
    t2.seth(25)
    t2.color("white", "white")
    t2.begin_fill()
    t2.circle(10)
    t2.end_fill()
    t.update()
    time.sleep(sleep)
    t2.clear()
    t2.penup()
    t2.forward(5)
    t2.pendown()
    sleep += 0.001

x1 = t2.xcor()
y1 = t2.ycor()
for j in range(50):
    t.tracer(False)
    t2.seth(-25)
    t2.color("white", "white")
    t2.begin_fill()
    t2.circle(10)
    t2.end_fill()
    t.update()
    time.sleep(sleep)
    t2.clear()
    t2.penup()
    t2.forward(5)
    t2.pendown()
    sleep += 0.001

x2 = t2.xcor()
y2 = t2.ycor()
circle(x2, y2, 10, "white")

t.mainloop()

```



# 第11课 烧脑的递归

## 1. 递归

for循环中return**返回值**

## 2. 代码案例

### 2.1 猴子吃桃

```python
# 任务1：求年龄
def age(n):
    if n == 5:
        return 10
    else:
        return age(n + 1) + 2


t = age(1)
print(f"第1个人的年龄为：{t}")


# 任务2：猴子吃桃
def num(n):
    if n == 10:
        return 1
    else:
        return (num(n + 1) + 1) * 2


a = num(1)
print(a)


# 任务3：求阶乘
def jc(i):
    if i == 1:
        return 1
    else:
        return jc(i - 1) * i


b = jc(5)
print(b)


# 任务4：斐波那契数列
def fbnq(i):
    if i == 1:
        return 1
    if i == 2:
        return 1
    else:
        return fbnq(i - 2) + fbnq(i - 1)


c = fbnq(15)
print(c)


# 任务5：求值并保留小数点后四位
def add(i):
    if i == 1:
        return 1
    else:
        return add(i - 2) + 1 / i


d = add(11)
print("{:.4f}".format(d))


# 任务6：正负整数相加
def jiajian1(i):
    if i == 1:
        return 1
    else:
        return jiajian1(i - 1) + (i * 2 - 1) * (-1) ** (i - 1)


print(jiajian1(8))


# 任务7：正负分数相加并保留四位小数
def jiajian2(i):
    if i == 1:
        return 1
    else:
        return jiajian2(i - 1) + (-1) ** (i - 1) * (1 / (i * 2 - 1))


print("{:.4f}".format(jiajian2(7)))

```

### 2.2 斐波那契前n个数字之和

```python
# 求斐波那契数列前n个数字之和
def add(i):
    if i == 1:
        return 1
    if i == 2:
        return 1
    else:
        return add(i - 1) + add(i - 2)


num = int(input("请输入你要求和到第几位"))
total = 0
for a in range(1, num + 1):
    total += add(a)
print(f"结果为：{total}")

```

### 2.3 汉诺塔文字版

```python
def hannuota(i, A, B, C):  # i为汉诺塔层数，参数A为起始柱子，参数B为中转柱子，参数C为目标柱子
    if i == 1:
        print(A, "移动到", C)  # 将盘子从传入的第一个塔移动到第三个塔
    else:
        hannuota(i - 1, A, C, B)  # 如果不是最下面的盘子，调换目标位置为中转柱子
        print(A, "移动到", C)  # 此时塔1上已经只剩下一个盘子，移到目标柱子
        hannuota(i - 1, B, A, C)  # 将剩下的盘子通过起始柱子移到目标柱子


num = int(input("请输入层数"))
hannuota(num, "塔1", "塔2", "塔3")

```



### 2.4 汉诺塔图形版

```python
# --------------载入库---------------
import turtle
import time

#  ---------------初始化画笔--------------------
t1 = turtle.Pen()
t2 = turtle.Pen()
t1.pensize(15)
t2.pensize(15)
t2.color("pink")
t1.speed(0)
t1.hideturtle()
t2.hideturtle()
# ---------------------数据准备---------------------
tower_data = [[-350, -100], [-100, -100], [150, -100]]
plate_data = [[-320, -80], [-50, -80], [180, -80]]
a = [3, 2, 1]
b = []
c = []


def tower(x, y):
    t1.seth(0)
    t1.pu()
    t1.goto(x, y)
    t1.pd()
    t1.forward(150)
    t1.seth(180)
    t1.forward(75)
    t1.seth(90)
    t1.forward(200)


def plates(x, y, my_list):
    t2.pu()
    t2.goto(x, y)
    t2.pd()
    t2.seth(0)
    for i in range(len(my_list)):
        t2.forward(my_list[i] * 30)
        x += 15
        y += 20
        t2.penup()
        t2.goto(x, y)
        t2.pendown()


def total_plates():
    t2.clear()
    turtle.tracer(False)
    plates(plate_data[0][0], plate_data[0][1], a)
    plates(plate_data[1][0], plate_data[1][1], b)
    plates(plate_data[2][0], plate_data[2][1], c)
    turtle.tracer(True)
    time.sleep(2)


def hannuota(i, a, b, c):
    if i == 1:
        c.append(a[len(a) - 1])
        del a[len(a) - 1]
        print(a, b, c)
        total_plates()
    else:
        hannuota(i - 1, a, c, b)
        c.append(a[len(a) - 1])
        del a[len(a) - 1]
        print(a, b, c)
        total_plates()
        hannuota(i - 1, b, a, c)


for m in range(len(tower_data)):
    tower(tower_data[m][0], tower_data[m][1])
total_plates()
hannuota(3, a, b, c)
turtle.mainloop()

```



# 第12课 计算圆周率

## 1. math库使用

==fabs（x）==返回绝对值

## 2. 代码案例

### 2.1 计算圆周率

```python
from math import fabs
import random

while 1:
    sel = int(input("请选择计算Π的方法 1.BBP公式 2.公式法2 3.概率法"))

    if sel == 1:
        pai = 0
        for i in range(100):
            pai += 1 / pow(16, i) * ((4 / (8 * i + 1)) - 2 / (8 * i + 4) - 1 / (8 * i + 5) - 1 / (8 * i + 6))
        print("Π的值为：{:.10f}".format(pai))

    if sel == 2:
        pai = 1
        up = 1
        down = 3
        n = 1
        a = 1
        while fabs(a) >= 1e-6:
            a = (up / down) * (-1) ** n
            pai += a
            n += 1
            down += 2
        print("Π的值为：{:.10f}".format(pai * 4))

    if sel == 3:
        total = 1000000
        cir = 0
        for i in range(total):
            x = random.random()
            y = random.random()
            long = (x ** 2 + y ** 2) ** 0.5
            if long <= 1:
                cir += 1
        pai = (cir / total) * 4
        print(f"Π的值为：{pai}")

    sel2 = input("还要继续吗 1.继续 2.结束")
    if sel2 == "1":
        continue
    if sel2 == "2":
        break

```



# 第13课 神奇的读心术

## 1. 全局变量与屏幕点击检测函数

```python
def click(x, y):
    global k
    k = 1


k = 0
t.onscreenclick(click)

```

其中click（x，y）的x和y**不可省略**，当点击屏幕后x和y会被赋值

==**global**==用于声明子函数中的变量为全局变量

## 2. 代码案例

### 2.1    9的倍数图案

```python
import random
import turtle

turtle.bgcolor("pink")
t1 = turtle.Pen()  # 写字
t1.color('black')
t2 = turtle.Pen()  # 画图案
t2.color("violet")
t3 = turtle.Pen()  # 画球
t4 = turtle.Pen()

t1.hideturtle()
t2.hideturtle()
t3.hideturtle()
t4.hideturtle()
symbol = [
    #   1         2         3         4         5         6         7         8         9         10
    '\u264B', '\u2648', '\u2649', '\u264F', '\u264E', '\u264A', '\u264D', '\u2653', '\u264C', '\u264F',  # 1

    '\u2653', '\u264F', '\u264B', '\u2648', '\u2649', '\u264F', '\u264E', '\u264C', '\u264E', '\u264A',  # 2

    '\u2648', '\u2649', '\u264F', '\u2653', '\u264B', '\u264E', '\u264C', '\u264A', '\u2652', '\u264B',  # 3

    '\u264D', '\u2650', '\u2652', '\u264B', '\u2649', '\u264C', '\u2648', '\u264F', '\u264A', '\u264F',  # 4

    '\u264A', '\u2649', '\u264B', '\u2652', '\u264C', '\u264F', '\u2653', '\u2648', '\u2653', '\u2649',  # 5

    '\u2649', '\u264D', '\u264F', '\u264C', '\u2648', '\u2650', '\u264E', '\u2651', '\u264E', '\u264C',  # 6

    '\u2652', '\u2649', '\u264C', '\u2648', '\u264B', '\u264A', '\u2650', '\u264F', '\u264E', '\u264D',  # 7

    '\u264E', '\u264C', '\u2648', '\u2649', '\u264F', '\u264B', '\u264F', '\u2653', '\u264D', '\u264E',  # 8

    '\u264C', '\u264F', '\u264E', '\u264D', '\u2648', '\u2649', '\u264B', '\u2652', '\u264F', '\u264C',  # 9

    '\u264D', '\u2650', '\u2652', '\u264B', '\u2649', '\u264C', '\u2648', '\u264F', '\u2653', '\u264A'  # 10
]


def p(x, y):
    global k
    k = 1


def write1(x, y):
    t1.penup()
    t1.goto(x, y)
    t1.pendown()
    t1.write("想一个一百以内的数字\n将该数字减去个位数字和十位数字\n准备好后请点击屏幕",
             font=('华文仿宋', 30, "normal"))


def write2(x, y):
    t1.penup()
    t1.goto(x, y)
    t1.pendown()
    t1.write("是否是下面的图案", font=('华文仿宋', 30, "normal"))


def qiu(x, y):
    t3.penup()
    t3.goto(x, y)
    t3.pendown()
    t3.color("purple", "purple")
    t3.begin_fill()
    t3.circle(200)
    t3.end_fill()


num = random.randint(0, 99)
turtle.tracer(False)
y = 300
shuzi = 1
for i in range(10):
    x = 0
    for j in range(1, 11):
        t2.penup()
        t2.goto(x, y)
        t2.pd()
        num2 = random.randint(0, 99)
        if (j + 10 * i) % 9 == 0:
            t2.write(symbol[num], font=('华文仿宋', 40, "normal"))
            t2.penup()
            t2.goto(x + 10, y - 20)
            t2.pendown()
            t2.write(shuzi, font=('华文仿宋', 20, "normal"))
            shuzi += 1
        else:
            t2.write(symbol[num2], font=('华文仿宋', 40, "normal"))
            t2.penup()
            t2.goto(x + 10, y - 20)
            t2.pendown()
            t2.write(shuzi, font=('华文仿宋', 20, "normal"))
            shuzi += 1
        x += 65
    y -= 80
k = 0
turtle.onscreenclick(p)
qiu(-400, -300)
while 1:
    write1(-600, 300)
    if k == 1:
        t1.clear()
        write2(-600, 300)
        t4.pu()
        t4.goto(-530, -250)
        t4.pd()
        t4.color("blue")
        t4.write(symbol[num], font=('华文仿宋', 200, "normal"))
        break
    else:
        continue
turtle.mainloop()

```



# 第14课 枚举算法

## 1 . 条件表达式 

a=int(input("请输入a值："))

 b=int(input("请输入b值："))

 **c=a if a>b else b** 

print("a,b中的大数为：{}".format(c))

 print("a,b中的小数为：{}".format(a if a>b else b)

## 2. for表达式

my_list1 = [x for x in range(5)]
print(my_list1)

## 3. for表达式+条件表达式

ls2=[x for x in range(5) if x > 2]  # for 表达式 + 简版条件表达式

print（ls2）

## 4. turtle库使用

画笔形状可以使用图片（gif），语法如下：

​	print(turtle.getshapes())

​	turtle.register_shape("名称.gif")

​	turtle.shape("名称.gif")

​	print(turtle.shape())

## 5. 代码案例

### 5.1 自幂数

```python
point = 1
while point == 1:
    a = int(input("请选择你要求的水仙花数的位数"))
    for num in range(10 ** (a - 1), 10 ** a):
        num_str = str(num)
        num_sum = 0
        for i in num_str:
            num_sum += int(i) ** a
        if num_sum == num:
            print(num)
    point = int(input("你还要继续吗？1.继续 2.结束"))

```

### 5.2 狼羊菜渡河文字版

```python
def judge(position):  # 用于判断移动后是否符合要求
    if position[1] == position[2] and position[0] != position[1]:  # 狼和羊在同一边并且人不在
        # print("狼吃羊")
        return False
    elif position[2] == position[3] and position[0] != position[2]:  # 羊和菜在同一边并且人不在
        # print("羊吃菜")
        return False
    else:
        return True


def search_all_next_position(position):  # 找到下一步移动的全部情况
    next_position_list = []  # 将情况统计在同一个列表中
    for i in range(0, 4):  # 循环遍历全部方法
        if position[0] != position[i]:  # 位置不同，不能带走，跳过当前循环
            continue
        next_position = [not position[0], position[1], position[2], position[3]]  # 反转船的位置
        if i != 0:  # 如果船带走一样物品，物品也需要反转
            next_position[i] = next_position[0]
        if judge(next_position):  # 判断是否符合要求
            next_position_list.append(next_position)  # 追加到总情况中
    return next_position_list  # 返回全部情况


def show_position(position, bull):
    """
    将物品分到两岸
    :param position:全部物体的位置
    :param bull: 通过布尔类型来分开
    :return: 返回分开后的结果
    """
    result = ""
    for i in range(4):
        if position[i] == bull:
            if len(result) != 0:
                result += ","
            result += name[i]

    return '[' + result + ']'


def print_all_position(all_position):  # 输出过河的全过程
    for position in all_position:
        print(show_position(position, False), '=====', show_position(position, True))


def is_finish(position):  # 用于判断是否完成目的
    return position[0] and position[1] and position[2] and position[3]


def search(all_position):
    global num
    current_position = all_position[len(all_position) - 1]
    next_position_list = search_all_next_position(current_position)
    # print(f"下一步共有{len(next_position_list)}种情况:", next_position_list)
    for next_position in next_position_list:  # 循环遍历所有可能的步骤
        if next_position in all_position:  # 将重复的跳过
            continue
        # print(show_position(next_position, False), '=====', show_position(next_position, True))

        all_position.append(next_position)  # 将本次的位置加入位置过程统计列表中

        if is_finish(next_position):  # 判断是否已经完成目的
            num += 1
            print(f"第{num}种方法开始：")
            print_all_position(all_position)
            print(f"第{num}种方法结束")
        else:
            search(all_position)
            # 后退一个位置进行另外步骤的尝试
            del all_position[len(all_position) - 1]



num = 0
name = ['猎人', '狼', '羊', '菜']
position = [False, False, False, False]  # False表示在河岸左边，True表示在河岸右边
all_position = [position]  # 统计全过程
search(all_position)
print(f"共找到{num}种情况")

```

### 5.3 狼羊菜渡河图形版

```python
import turtle

wolf = turtle.Turtle()  # 狼
sheep = turtle.Turtle()  # 羊
food = turtle.Turtle()  # 菜
t4 = turtle.Turtle()  # 画河流
ship = turtle.Turtle()  # 画船
turtle.hideturtle()
print(turtle.getshapes())
turtle.register_shape("狼.gif")
turtle.register_shape("羊.gif")
turtle.register_shape("菜.gif")
turtle.register_shape("船.gif")
wolf.shape("狼.gif")
sheep.shape("羊.gif")
food.shape("菜.gif")
ship.shape("船.gif")
print(turtle.shape())


def river(x, y):
    t4.penup()
    t4.goto(x, y)
    t4.pendown()
    t4.color('lightskyblue', 'lightskyblue')
    t4.begin_fill()
    t4.forward(300)
    t4.right(90)
    t4.forward(1000)
    t4.right(90)
    t4.forward(300)
    t4.right(90)
    t4.forward(1000)
    t4.end_fill()


# def move():


position = [[-600, 350], [-600, 0], [-600, -350], [600, 350], [600, 0], [600, -350]]
turtle.tracer(False)
river(-200, 500)
wolf.pu()
sheep.pu()
food.pu()
wolf.goto(position[0][0], position[0][1])
sheep.goto(position[1][0], position[1][1])
food.goto(position[2][0], position[2][1])

turtle.tracer(True)
wolf.goto(position[3][0], position[3][1])

turtle.mainloop()

```

# 第15课 走迷宫

## 1. turtle库使用

### 1.1 创建新窗口

```python
game = turtle.Screen()  # 创建窗体
game.title("走迷宫")  # 给窗体命名
game.bgcolor("pink")  # 设置背景颜色
game.setup(800, 600)  # 设置窗体大小
```

### 1.2 创建物体

['arrow', 'blank', 'circle', 'classic', 'square', 'triangle', 'turtle']

​    箭头     空白        圆      经典样式    方形       三角形    乌龟

==turtlesize(x)==  改变画笔大小

```python
ball = turtle.Pen()
ball.color("purple")
ball.shape("turtle")
ball.penup()
ball.turtlesize(3)
```

### 1.3 让球动起来

ball.goto(ball.xcor()+1,ball.ycor()+1)

## 2.代码案例

```python
import turtle as t
import time

# 窗口设置
game = t.Screen()
game.title("走迷宫")
game.bgcolor("pink")
game.setup(800, 600)

# 物体
ball = t.Pen()
ball.color("purple")
ball.shape("circle")
ball.penup()
ball.goto(-300, 0)

# 迷宫初始化
t2 = t.Pen()
t2.color("yellow")
t2.hideturtle()
t2.pensize(15)
t2.speed(0)
t2.penup()
t2.goto(-200, 0)
t2.pendown()
lost_data = [[-300, 200], [300, 200], [-300, -200], [300, -200], [-200, 200], [-200, -100], [-100, 100], [-100, -200],
             [0, 200], [0, -100], [100, 100], [100, -200], [200, 200], [200, -100], [-300, 200], [-300, 50],
             [-300, -50], [-300, -200], [300, 200], [300, 50], [300, -50], [300, -200]]

# 计时器
t3 = t.Pen()
t3.penup()
t3.color("black")
t3.pensize(10)


def judge():
    x = ball.xcor()
    y = ball.ycor()
    if y == 200 or y == -200:
        return True
    if x == -300 and not -50 < y < 50:
        return True
    if x == 300 and not -50 < y < 50:
        return True
    for i in range(4, len(lost_data) - 1, 2):
        if lost_data[i][0] == x and lost_data[i][1] > y > lost_data[i + 1][1]:
            return True
    else:
        return False


def move_up():
    if judge():
        ball.clear()
        t2.clear()
        t3.clear()
        t2.goto(-200, 0)
        t2.write("游戏失败", font=("华文仿宋", 80, "normal"))

    else:
        ball.sety(ball.ycor() + 5)


def move_down():
    if judge():
        ball.clear()
        t2.clear()
        t3.clear()
        t2.goto(-200, 0)
        t2.write("游戏失败", font=("华文仿宋", 80, "normal"))
    else:
        ball.sety(ball.ycor() - 5)


def move_right():
    if judge():
        ball.clear()
        t2.clear()
        t3.clear()
        t2.goto(-200, 0)
        t2.write("游戏失败", font=("华文仿宋", 80, "normal"))
    else:
        ball.setx(ball.xcor() + 5)


def move_left():
    if judge():
        ball.clear()
        t2.clear()
        t3.clear()
        t2.goto(-200, 0)
        t2.write("游戏失败", font=("华文仿宋", 80, "normal"))
    else:
        ball.setx(ball.ycor() - 5)


def draw_lost():
    num = 0
    for i in range(11):
        t2.penup()
        t2.goto(lost_data[num][0], lost_data[num][1])
        t2.pendown()
        t2.goto(lost_data[num + 1][0], lost_data[num + 1][1])
        num += 2


def success_way():
    t2.penup()
    t2.goto(300, -20)
    t2.pendown()
    t2.color("green", "green")
    t2.begin_fill()
    t2.circle(20)
    t2.end_fill()


def is_success():
    x = ball.xcor()
    y = ball.ycor()
    if x == 300 and y == -20:
        ball.clear()
        t2.clear()
        t2.write("游戏成功", font=("华文仿宋", 80, "normal"))
        return True


# 键盘监测
game.listen()
game.onkeypress(move_up, 'Up')
game.onkeypress(move_down, 'Down')
game.onkeypress(move_right, 'Right')
game.onkeypress(move_left, 'Left')

# 绘制迷宫
draw_lost()

# 设置计时器和终点
success_way()
t3.penup()
t3.goto(-120, 220)
t3.pendown()
now_time = 0
while 1:
    t3.pu()
    now_time += 0.1
    t3.write("{:.1f}".format(now_time), font=("微软雅黑", 30, "normal"))
    time.sleep(0.1)
    t3.clear()
    if is_success():
        is_success()

```

# 第16课 扫码枪的应用

## 1.序列的切片操作

==序列[起始下标 ：结束下标 ：步长 ]==  不会影响序列本身，而是**得到一个新序列**，需要用新变量来接收

切片是不包含结束下标，如果要取到最后一位，则结束下标处不需要写数字



## 2.列表的操作( 整合 )

1.定义列表			变量名称=[]

2.查下标			==列表.index(元素)==

3.追加元素到列表最后			==列表.append(元素)==

4.追加一批元素			==列表.extend(其他数据容器)==

5.删除列表中的元素			==del 列表[下标]==	默认删除最后一个

​											  ==列表.pop(下标)==	删除指定下标元素	同时删除的元素可作为**返回值**用变量接收

​											   ==列表.remove(元素)==	若元素重复出现，只会**删除**列表中靠前的**第一个**

6.清空列表			==列表.clear()==

7.统计列表中的同一元素数量			==列表.count(元素)==

8.统计列表中的元素的全部数量			==len(列表)==

9.取出列表中的元素			==列表[下标]==



## 3.元组的操作(整合)

元组=（）		只有一个元素时后面要加逗号，元组具有不可修改的特性

1.取元素			==元组[下标]==

2.查下标			==元组.index(元素)==

3.统计元组中全部元素数量			==len(元组)==

4.统计同一元素的数量			==元组。count(元素)==



## 4. 字典的操作(整合)

字典名称={x:	;   y:	;   z:	}			键值对

1.定义空字典			==my_dict={}==

2.查Value(**Key不可为字典**)			==字典[key]==

3.增加或更新元素			==字典[key]=value==

4.获得value，删除元素			==变量=字典.pop(key)==

5.清空字典			==字典.clear()==

6.获取全部的key			==变量=字典.keys()==

7.统计字典元素数量			==len(字典)==



## 5.集合的操作(整合)

集合		{x，y，z}			元素具有不可重复性

1.定义空集合			==变量.set()==

2.添加元素			==集合.add(元素)==

3.移除元素			==集合.remove（元素）==

4.随机删除一个元素			==集合.pop()==

？？？对于是字典和字符转换的集合是随机删除元素的。当集合是由列表和元组组成时、set.pop() 是从左边删除元素

5.清空集合			==集合.clear()==

6.取差集（集合1有而集合2没有），得到新集合			==变量=集合1.difference（集合2）==

7.在集合1中删除与集合2相同的元素		==集合1.difference_update(集合2)==

8.将集合1和集合2组成新集合			==变量=集合1.union(集合2)==

9.统计集合中的元素数量			==len(集合)==



## 6.字符串的操作(整合)

==变量=字符串.replace(x,y)==			替换字符串(x变成y)

==字符串.split(x)==			按照x分割字符串为列表

==变量=字符串.strip(x)==			无参数时去除前后空格和换行符，有参数时去除参数，需要用新变量接收

==字符串.count(元素)==			统计元素出现的次数

==len(字符串)==			统计字符串长度



## 7. 代码案例

### 7.1 超市商品系统

```python
# win+R进入命令提示符，输入pip install tabulate 下载模块后程序方可运行
from tabulate import tabulate
from random import randint

print("--------------超市商品录入与查询系统----------------")
m = input("请输入员工码")
n = input("请输入密码")
lock = randint(1000, 9999)
q = int(input(f"请输入验证码{lock}"))
point = 0
if m == "1" and n == "1" and q == lock:
    point = 1
else:
    print("验证失败！")
data = {"id": ['9787572218194', '9787544653114', '9787544654166', '9787530217610', '9787530221099'],
        "name": ['四级词汇书', '听力练习上册', '听力练习下册', '《兄弟》', "《文城》"],
        "price": [48.00, 40.00, 40.00, 68.00, 59.00],
        "number": [40, 56, 30, 14, 37]}
while point == 1:
    a = int(input("----------主菜单----------\n1.查询超市全部商品\n2.商品录入\n3.单个商品查询\n4.收银\n5.退出\n"))
    if a == 1:
        table = tabulate(data, headers="keys", showindex=True, tablefmt='simple', numalign='left')
        print(table)
    if a == 2:
        new_id = input("请扫描商品条形码")
        data["id"].append(new_id)
        new_name = input("请输入商品名称")
        data["name"].append(new_name)
        new_price = float(input("请输入商品价格"))
        data["price"].append(new_price)
        new_number = int(input("请输入商品数量"))
        data["number"].append(new_number)
        print("商品已录入成功")
    if a == 3:
        choose = int(input("请选择:1.通过条形码查询 2.通过商品名查询"))
        if choose == 1:
            now_id = input("请扫描条形码")
            num = data["id"].index(now_id)
            print("商品id为:", data["id"][num])
            print("商品名称为:", data["name"][num])
            print("商品价格为：{:.2f}元".format(data['price'][num]))
        if choose == 2:
            now_name = input("请输入商品名")
            num = data["name"].index(now_name)
            print("商品id为:", data["id"][num])
            print("商品名称为:", data["name"][num])
            print("商品价格为：{:.2f}元".format(data['price'][num]))
    if a == 4:
        judge = 1  # 判断是否重复收银
        total_price = 0
        now_data = {"id": [], "name": [], "price": [], "number": []}
        while judge == 1:
            now_id = input("请扫描商品条形码")
            num = data["id"].index(now_id)
            total_price += data["price"][num]
            data["number"][num] = data["number"][num] - 1  # 商品数量减1
            # 是否同一个商品购买多次
            for i in now_data["id"]:
                if i == now_id:
                    v = now_data["id"].index(i)
                    now_data["number"][v] = now_data["number"][v] + 1
                    break
            else:
                now_data["id"].append(data["id"][num])
                now_data["name"].append(data["name"][num])
                now_data["price"].append(data["price"][num])
                now_data["number"].append(1)
            judge = int(input("是否继续 1.继续 2.结束扫码"))

        receive = input("请扫描收款码")
        is_correct = receive[0:2:1]
        is_correct = int(is_correct)
        if is_correct == 10 or is_correct == 11 or is_correct == 12 or is_correct == 13 \
                or is_correct == 14 or is_correct == 15:
            if len(receive) == 18:
                print("付款成功，谢谢惠顾！")
                table = tabulate(now_data, headers="keys", showindex=True, tablefmt='simple', numalign='center')
                print(table)
                print("总金额为{:.2f}元".format(total_price))
            else:
                print("付款失败！")
        else:
            print("付款失败！")
    if a == 5:
        print("超市商品录入与查询系统已退出")
        break

```

# 第17课 超市商品管理系统

## 1.python写txt文件

f=open(文件名，“ r / w / a ” ，encodint="UTF-8")		读文件

f.flush()			内容写入文件

f.close()			关闭文件

f.readlines()			读取全部内容

f.readline()			读取一行内容

f.write(x)			写入内容

## 2. python 写excel文件

import  openpyxl			载入openpyxl库

f=openpyxl.load_workbook(excel文件名)			打开文件

f.save(文件名)			载入数据

f.close()			关闭文件

sheet=f[表名]			打开excel中的指定表格

变量=sheet[x]			获取指定列内容，得到的是列表

列名[x].value		获取列中指定下标的值

表名.cell(x,y).value=???			x为行，y为列,添加数据

## 3. 代码案例

### 3.1超市管理系统（txt版本）



```python
from random import randint
import turtle as t

t.hideturtle()
t.penup()
x = -200
y = 100
print("--------------超市商品录入与查询系统----------------")
point = 0
while point == 0:
    sel = input("1.登录 2.注册 3.退出")
    if sel == "2":
        f = open('超市系统登陆账户.txt', "a", encoding="UTF-8")
        m = input("请输入员工码")
        f.write("\n" + m + "\t")
        n = input("请输入密码")
        f.write(n)
        f.close()
    if sel == "1":
        f = open('超市系统登陆账户.txt', "r", encoding="UTF-8")
        m = input("请输入员工码")
        n = input("请输入密码")
        lock = randint(1000, 9999)
        q = int(input(f"请输入验证码{lock}"))
        total_users = f.readlines()
        for i in total_users:
            i = i.strip()
            if i == m + "\t" + n:
                print("登录成功！")
                point = 1
                break
        else:
            print("登录失败！")
    if sel == "3":
        break
while point == 1:
    a = int(input(
        "----------主菜单----------\n1.查询超市全部商品\n2.商品录入\n3.单个商品查询\n4.收银\n5.查看销售情况 6.退出\n"))
    if a == 1:
        f = open('商品统计.txt', "r", encoding="UTF-8")
        total_data = f.readlines()
        for i in total_data:  # 按行打印
            i = i.strip()  # 去除前后空格和换行符
            print(i)
        f.close()
    if a == 2:
        f = open('商品统计.txt', "a", encoding="UTF-8")
        new_id = input("请扫描商品条形码")

        f.write("\n" + new_id)
        new_name = input("请输入商品名称")
        f.write("\t" + new_name)
        new_price = input("请输入商品价格")
        f.write("\t" + new_price)
        new_number = input("请输入商品数量")
        f.write("\t" + new_number)
        print("商品已录入成功")
        f.close()
    if a == 3:
        select_id = input("请扫描商品的条形码")
        if select_id != "":
            f = open('商品统计.txt', "r", encoding="UTF-8")
            total_data = f.readlines()
            for i in total_data:
                now_i = i[0:13:1]
                if select_id == now_i:
                    print(i)
                    break
            else:
                print("商品不存在！")
            f.close()
    if a == 4:
        while 1:
            sale = input("请扫描商品条形码")
            if sale != "":
                f = open("商品统计.txt", "r", encoding="UTF-8")
                total_data = f.readlines()
                my_list = total_data
                f.close()
                for i in my_list:
                    i = i.strip()
                    is_sale = i[0:13:1]
                    if is_sale == sale:
                        print(i)
                        print("出库成功！")
                        f = open("销售额统计.txt", "a", encoding="UTF-8")
                        for line in f:
                            if is_sale == line[0:13:1]:
                                f
                        f.close()
                        t.goto(x, y)
                        t.write(i)
                        y -= 15
            else:
                break
    if a == 5:
        f = open("销售额统计.txt", "r", encoding="UTF-8")
        total_sale = f.readlines()
        for i in total_sale:
            i = i.strip()
            print(i)
        f.close()
    if a == 6:
        print("超市商品录入与查询系统已退出")
        break

```

### 3.2 超市管理系统(excel版本)

```python
# win+R输入cmd进入命令提示符，输入pip install tabulate下载模块
from random import randint
import openpyxl

print("--------------超市商品录入与查询系统----------------")
system = openpyxl.load_workbook(u"超市管理系统.xlsx")
sheet1 = system["账户"]
sheet2 = system["商品统计"]
sheet3 = system["销售额"]
point = 0
while point == 0:
    sel = input("1.登录 2.注册 3.退出")
    if sel == "1":
        user = int(input("请输入员工码"))
        password = int(input("请输入密码"))
        cheek = randint(1000, 9999)
        is_cheek = int(input(f"请输入验证码{cheek}"))
        sheet1_line_2 = sheet1["B"]
        sheet1_line_3 = sheet1["C"]
        num = len(sheet1_line_2)
        for i in range(num):
            is_user = sheet1_line_2[i].value
            is_password = sheet1_line_3[i].value
            if user == is_user and password == is_password and cheek == is_cheek:
                print("登录成功！")
                point = 1
                break
        else:
            print("登录失败！")
    if sel == "2":
        user = int(input("请输入员工码"))
        password = int(input("请输入密码"))
        cheek = randint(1000, 9999)
        is_cheek = int(input(f"请输入验证码{cheek}"))
        sheet1_line_2 = sheet1["B"]
        sheet1_line_3 = sheet1["C"]
        num = len(sheet1_line_2)
        if is_cheek == cheek:
            sheet1.cell(num + 1, 1).value = num
            sheet1.cell(num + 1, 2).value = user
            sheet1.cell(num + 1, 3).value = password
            system.save(u"超市管理系统.xlsx")
            print("注册成功！")
        else:
            print("注册失败！")
    if sel == "3":
        break
while point == 1:
    a = int(input(
        "----------主菜单----------\n1.查询超市全部商品\n2.商品录入\n3.单个商品查询\n4.收银\n5.查看销售额 6.退出\n"))
    if a == 1:
        sheet2_line_1 = sheet2["A"]
        sheet2_line_2 = sheet2["B"]
        sheet2_line_3 = sheet2["C"]
        sheet2_line_4 = sheet2["D"]
        sheet2_line_5 = sheet2["E"]
        num = len(sheet2_line_1)
        for i in range(num):
            print(sheet2_line_1[i].value, end="\t")
            print(sheet2_line_2[i].value, end="\t")
            print(sheet2_line_3[i].value, end="\t")
            print(sheet2_line_4[i].value, end="\t")
            print(sheet2_line_5[i].value)
    if a == 2:
        new_id = int(input("请扫描商品条形码"))
        new_name = input("请输入商品名称")
        new_price = float(input("请输入商品价格"))
        new_number = int(input("请输入商品数量"))
        print("商品已录入成功")
        sheet2_line_1 = sheet2["A"]
        num = len(sheet2_line_1)
        sheet2.cell(num + 1, 1).value = num
        sheet2.cell(num + 1, 2).value = new_id
        sheet2.cell(num + 1, 3).value = new_name
        sheet2.cell(num + 1, 4).value = new_price
        sheet2.cell(num + 1, 5).value = new_number
        system.save(u"超市管理系统.xlsx")
    if a == 3:
        cheek_id = int(input("请扫描商品条形码"))
        sheet2_line_1 = sheet2["A"]
        sheet2_line_2 = sheet2["B"]
        sheet2_line_3 = sheet2["C"]
        sheet2_line_4 = sheet2["D"]
        sheet2_line_5 = sheet2["E"]
        num = len(sheet2_line_1)
        for i in range(num):
            if cheek_id == sheet2_line_2[i].value:
                print(sheet2_line_1[i].value, end="\t")
                print(sheet2_line_2[i].value, end="\t")
                print(sheet2_line_3[i].value, end="\t")
                print(sheet2_line_4[i].value, end="\t")
                print(sheet2_line_5[i].value)
                break
        else:
            print("商品不存在！")
    if a == 4:
        is_sale = 1
        while is_sale == 1:
            sheet2_line_1 = sheet2["A"]
            sheet2_line_2 = sheet2["B"]
            sheet2_line_3 = sheet2["C"]
            sheet2_line_4 = sheet2["D"]
            sheet2_line_5 = sheet2["E"]
            sheet2_num = len(sheet2_line_1)
            sheet3_line_1 = sheet3["A"]
            sheet3_line_2 = sheet3["B"]
            sheet3_line_3 = sheet3["C"]
            sheet3_line_4 = sheet3["D"]
            sheet3_line_5 = sheet3["E"]
            sheet3_num = len(sheet3_line_1)
            sale_id = int(input("请扫描商品条形码"))
            for i in range(sheet2_num):  # 查找商品信息
                if sheet2_line_2[i].value == sale_id:  # 存在商品信息
                    sheet2.cell(i + 1, 5).value -= 1
                    for j in range(sheet3_num):  # 查找是否卖过同类商品
                        if sheet3_line_2[j] == sale_id:  # 如果存在，销售数量加1
                            sheet3.cell(j, 5).value += 1  # 销售数量加1
                            system.save(u"超市管理系统.xlsx")
                            print("出库成功")
                            break
                    else:  # 如果不存在，追加到sheet3
                        num = 0
                        for i in range(sheet2_num):
                            num += 1
                            if sheet2_line_2[i] == sale_id:
                                break
                        sheet3.cell(sheet3_num + 1, 1).value = sheet2.cell(num, 1).value
                        sheet3.cell(sheet3_num + 1, 2).value = sheet2.cell(num, 2).value
                        sheet3.cell(sheet3_num + 1, 3).value = sheet2.cell(num, 3).value
                        sheet3.cell(sheet3_num + 1, 4).value = sheet2.cell(num, 4).value
                        sheet3.cell(sheet3_num + 1, 5).value = 1
                        system.save(u"超市管理系统.xlsx")
                        print("出库成功")
                        break
            else:
                print("商品不存在，请先录入商品")
            is_sale = int(input("请选择 1.继续扫描 2.结束收银"))

        receive = input("请扫描收款码")
        is_correct = receive[0:2:1]
        is_correct = int(is_correct)
        if is_correct == 10 or is_correct == 11 or is_correct == 12 or is_correct == 13 \
                or is_correct == 14 or is_correct == 15:
            if len(receive) == 18:
                print("付款成功，谢谢惠顾！")
            else:
                print("付款失败！")
        else:
            print("付款失败！")
    if a == 5:
        sheet3_line_1 = sheet3["A"]
        sheet3_line_2 = sheet3["B"]
        sheet3_line_3 = sheet3["C"]
        sheet3_line_4 = sheet3["D"]
        sheet3_line_5 = sheet3["E"]
        num = len(sheet3_line_1)
        for i in range(num):
            print(sheet3_line_1[i].value, end="\t")
            print(sheet3_line_2[i].value, end="\t")
            print(sheet3_line_3[i].value, end="\t")
            print(sheet3_line_4[i].value, end="\t")
            print(sheet3_line_5[i].value)
    if a == 6:
        print("超市商品录入与查询系统已退出！")
        break
system.save(u"超市管理系统.xlsx")
system.close()

```



# 第18课综合应用

## 1. 昵称计分器

```python
# -----------------载入库--------------------
import openpyxl
import re

# ------------------准备数据---------------------
total_name = openpyxl.load_workbook(u"QQ群昵称总表.xlsx")
total_score = openpyxl.load_workbook(u"班级名单.xlsx")

name_dl682006 = total_name["导论682006"]
name_dl655694 = total_name["导论655694"]
name_dl655686 = total_name["导论655686"]
name_dl655687 = total_name["导论655687"]
name_dl = total_name["导论重修群"]

score_dl682006 = total_score["导论682006"]
score_dl655694 = total_score["导论655694"]
score_dl655686 = total_score["导论655686"]
score_dl655687 = total_score["导论655687"]
name_list = [name_dl682006, name_dl655694, name_dl655686, name_dl655687, name_dl]
score_list = [score_dl682006, score_dl655694, score_dl655686, score_dl655687]
check_all = r'(^[0-9]{10}[\u4E00-\u9FFF]+$)'
check_id = r'([0-9]{10})'
check_name = r'[\u4e00-\u9fa5]+'
# ------------------主程序-------------------------
# 读取数据
for i in range(4):
    sheet1_line = name_list[i]["D"]  # 将数据存放到列表中
    sheet2_line = score_list[i]["B"]
    sheet2_line2 = score_list[i]["C"]
    sheet2_line3 = score_list[i]["F"]
    num1 = len(sheet1_line)  # 数据的总数
    num2 = len(sheet2_line)
    for j in range(num1):  # 遍历全部的数据并进行赋分操作
        result = re.search(check_all, str(sheet1_line[j].value))
        result_id = re.search(check_id, str(sheet1_line[j].value))
        result_name = re.search(check_name, str(sheet1_line[j].value))
        if result is not None:
            result_id = int(result.group()[0:10:1])
            for k in range(num2):
                if sheet2_line[k].value == result_id:
                    score_list[i].cell(k + 1, 6).value = 100
        elif result_name is not None and result_id is not None:
            result_id = int(result_id.group())
            for k in range(num2):
                if sheet2_line[k].value == result_id:
                    score_list[i].cell(k + 1, 6).value = 90
        elif result_name is not None:
            for k in range(num2):
                if sheet2_line2[k].value == result_id:
                    score_list[i].cell(k + 1, 6).value = 80
        elif 1:
            for m in range(num2):
                if score_list[i].cell(m + 1, 6).value != 80 or score_list[i].cell(m + 1, 6).value != 90 or score_list[
                    i].cell(m + 1, 6).value != 100:
                    score_list[i].cell(m + 1, 6).value = 0

sheet = name_list[4]["D"]
for i in range(4):
    sheet2_line = score_list[i]["B"]
    sheet2_line2 = score_list[i]["C"]
    sheet2_line3 = score_list[i]["F"]
    num1 = len(sheet)  # 数据的总数
    num2 = len(sheet2_line)
    for j in range(num1):  # 遍历全部的数据并进行赋分操作
        result = re.search(check_all, str(sheet[j].value))
        result_id = re.search(check_id, str(sheet[j].value))
        result_name = re.search(check_name, str(sheet[j].value))
        if result is not None:
            result_id = int(result.group()[0:10:1])
            for k in range(num2):
                if sheet2_line[k].value == result_id:
                    score_list[i].cell(k + 1, 6).value = 100
        elif result_name is not None and result_id is not None:
            result_id = int(result_id.group())
            for k in range(num2):
                if sheet2_line[k].value == result_id:
                    score_list[i].cell(k + 1, 6).value = 90
        elif result_name is not None:
            for k in range(num2):
                if sheet2_line2[k].value == result_id:
                    score_list[i].cell(k + 1, 6).value = 80
        # elif 1:
        #     for m in range(num2):
        #         if score_list[i].cell(m + 1, 6).value != 80 or score_list[i].cell(m + 1, 6).value != 90 or score_list[
        #             i].cell(m + 1, 6).value != 100:
        #             score_list[i].cell(m + 1, 6).value = 0
total_score.save(u"班级名单.xlsx")
total_name.close()
total_score.close()

```

## 2. 会议迟到缺课统计

```python
import openpyxl
from datetime import datetime
import warnings

warnings.filterwarnings('ignore')

word = [u'01课.xlsx', u'02课.xlsx', u'03课.xlsx']
record = []  # 用于记录缺课数据

f = open("实验室名单.txt", "r", encoding="UTF-8")
total_name = f.readlines()
for i in range(len(total_name)):
    total_name[i] = total_name[i].strip()
f.close()
# print(total_name)

data = openpyxl.load_workbook(word[0])
sheet = data['成员参会概况']
name_line = sheet["A"]  # 参会人
time_line = sheet["B"]  # 入会时间
num = len(name_line)  # 用于控制循环次数
target_time = '2023-09-23 19:31:00'
format_pattern = '%Y-%m-%d %H:%M:%S'
for j in range(10, num + 1):
    attend_time = str(time_line[j - 1].value)
    time1 = datetime.strptime(target_time, format_pattern)
    time2 = datetime.strptime(attend_time, format_pattern)
    if time1 > time2:
        record.append(name_line[j - 1].value + "\n")

f = open("上课情况统计.txt", "a", encoding="UTF-8")
for i in record:
    f.write(i)
f.close()
data = openpyxl.load_workbook(word[1])
sheet = data['成员参会概况']
name_line = sheet["A"]  # 参会人
time_line = sheet["B"]  # 入会时间
num = len(name_line)  # 用于控制循环次数
target_time = '2023-09-23 19:31:00'
format_pattern = '%Y-%m-%d %H:%M:%S'
for j in range(10, num + 1):
    attend_time = str(time_line[j - 1].value)
    time1 = datetime.strptime(target_time, format_pattern)
    time2 = datetime.strptime(attend_time, format_pattern)
    if time1 > time2:
        record.append(name_line[j - 1].value + "\n")

f = open("上课情况统计.txt", "a", encoding="UTF-8")
for i in record:
    f.write(i)
f.close()
data = openpyxl.load_workbook(word[2])
sheet = data['成员参会概况']
name_line = sheet["A"]  # 参会人
time_line = sheet["B"]  # 入会时间
num = len(name_line)  # 用于控制循环次数
target_time = '2023-09-23 19:31:00'
format_pattern = '%Y-%m-%d %H:%M:%S'
for j in range(10, num + 1):
    attend_time = str(time_line[j - 1].value)
    time1 = datetime.strptime(target_time, format_pattern)
    time2 = datetime.strptime(attend_time, format_pattern)
    if time1 > time2:
        record.append(name_line[j - 1].value + "\n")

f = open("上课情况统计.txt", "a", encoding="UTF-8")
for i in record:
    f.write(i)
f.close()

```



## 3. 刷分登记

```python
import openpyxl
import re

# 打开excel文件
data1 = openpyxl.load_workbook('导论考试01--进制转换2.xlsx')
sheet1 = data1["Sheet1"]
data2 = openpyxl.load_workbook('导论考试01--进制转换2.xlsx')
sheet2 = data2["Sheet1"]
data3 = openpyxl.load_workbook('导论考试01--进制转换3.xlsx')
sheet3 = data3["Sheet1"]
data4 = openpyxl.load_workbook('导论考试01--进制转换4.xlsx')
sheet4 = data4["Sheet1"]
data5 = openpyxl.load_workbook('导论考试01--进制转换5.xlsx')
sheet5 = data5["Sheet1"]
score_data = openpyxl.load_workbook('班级名单.xlsx')
sheet_a = score_data['导论682006']
sheet_b = score_data['导论655694']
sheet_c = score_data['导论655686']
sheet_d = score_data['导论655687']
score_sheet = [sheet_a, sheet_b, sheet_c, sheet_d]
# 将表对象存到列表中，用于循环
total_data = [sheet1, sheet2, sheet3, sheet4, sheet5]
# 循环全部表对象
for i in range(len(total_data)):
    # 第一步：读取表中的数据
    total_id = total_data[i]["I"]  # 读取全部学号
    total_score = total_data[i]["H"]  # 读取全部分数
    total_time = total_data[i]["D"]  # 读取答题分数
    # 计算一共有多少组数据
    num = len(total_id)
    # 依次处理数据
    for j in range(num):
        # 读取学号，答题分数，时间
        now_id = total_id[j].value
        now_score = total_score[j].value
        now_time = total_time[j].value
        now_time = re.search(r'[0-9]+', now_time)
        now_time = int(now_time)
        # 第二步：给出总分
        if now_time <= 180:
            pass
        if now_time > 180:
            add = (total_score - 180) // 2
            now_score -= add + 1
        # 第三步：写入数据到表中
        # 循环四个表格，通过读取学号来配对并填入分数
        for sheet in total_data:
            sheet_id = sheet["B"]  # 读取学号得到列表
            # sheet["G"]  用于填写分数的表格
            # 循环遍历所有的学号并判断
            for is_id in sheet_id:
                # 得到下标
                low = sheet_id.index(is_id)
                if is_id == now_id:
                    sheet.cell(low + 1, 7).value = now_score

# 将数据载入excel
score_data.save('班级名单.xlsx')
# 关闭excel文件
data1.close()
data2.close()
data3.close()
data4.close()
data5.close()
score_data.close()

```



## 4. 缺作业统计

```python
import os

f = open("实验室名单.txt", "r", encoding="UTF-8")
total_person2 = f.readlines()
total_person = []  # 实验室人员名单
for people in total_person2:  # 去除换行符和空格后追加到人员名单中
    people = people.strip()
    total_person.append(people)
# print(total_person)
f.close()


def get_all_files_in_folder(folder_path):
    """
    获取指定文件夹下的所有文件名

    :param folder_path: 文件夹路径
    :return: 包含所有文件名的列表
    """
    file_names = []
    for root, dirs, files in os.walk(folder_path):
        for file in files:
            file_names.append(os.path.join(root, file))
    return file_names


folder_path = "第15课走迷宫"  # 查找的文件夹的路径
file_names = get_all_files_in_folder(folder_path)

# 打印所有文件名
# for file_name in file_names:
#     file_name = file_name[8::1]
#     print(file_name)
total_file = ["第15课走迷宫", '第16课扫码枪的应用作业']
f = open(r"缺课统计.txt", 'a')
toji = []
for now_file in total_file:
    for i in os.listdir(now_file):  # os.listdir(x)获取包含指定目录中的所有文件和子目录，返回的是列表
        toji.append(i)
    for j in range(len(total_person)):
        person = total_person[j].strip()  # 将换行符去掉
        n = 0
        if now_file == "第15课走迷宫":
            n = 6
        if now_file == "第16课扫码枪的应用作业":
            n = 3
        for i in range(len(toji)):
            if person in toji[i]:
                n -= 1
        if n > 0:
            f.write(f"{person}欠{n} \n")
f.close()

```



# 第19课词频统计

## 1. jieba库(分词库)

（1）精确模式：试图将句子最精确地切开，适合文本分析。精确分词模式对应的方法是==jieba.cut==，该方法接受四个输入参数: 需要分词的字符串；cut_all 参数用来控制是否采用全模式，值为==False==时表示采用精确分词模式；HMM 参数用来控制是否使用 HMM 模型。

（2）全模式：把句子中所有的可以成词的词语都扫描出来，速度非常快，但是不能解决歧义。全模式同样是调用==jieba.cut==方法实现，不过cut_all参数值设置为==True==。

（3）搜索引擎模式：在精确模式的基础上，对长词再词切分，提高召回率，适合用于搜索引擎分词。搜索引擎模式对应的方法是==jieba.cut_for_search==。该方法接受两个参数：需要分词的字符串；是否使用 HMM 模型。该方法适合用于搜索引擎构建倒排索引的分词，粒度比较细。

## 2.pyecharts库（可视化）

### 2.1 柱状图

![img](D:\Typora笔记\python笔记.assets\27a87123ac4cf29078172b665c74a565.png)

[](https://blog.csdn.net/itmsn/article/details/120885327)

### 2.2 饼状图

[](https://blog.csdn.net/weixin_44940488/article/details/117465337)

## 3.代码案例

### 3.1政府工作报告

```python
# -----------------载入库-------------------
import jieba
import pyecharts

# ------------------数据准备------------------
with open("政府工作报告2021.txt", "r", encoding="UTF-8") as f:
    all_content1 = f.readlines()
with open("政府工作报告2022.txt", "r", encoding="UTF-8") as f:
    all_content2 = f.readlines()


# --------------------------定义函数-------------------
def all_cut(content):
    my_dict = {}
    for i in content:
        cut = jieba.cut(i)
        for word in cut:
            if len(word) == 2:
                my_dict[word] = my_dict.get(word, 0) + 1
    return my_dict


# -------------------主程序------------------
my_dict1 = all_cut(all_content1)
my_list1 = list(my_dict1.items())
my_list1.sort(key=lambda x: x[1], reverse=True)

my_dict2 = all_cut(all_content2)
my_list2 = list(my_dict2.items())
my_list2.sort(key=lambda x: x[1], reverse=True)
print("2021年政府工作报告二字高频词汇为：")
for i in range(20):
    print(my_list1[i][0], ":", my_list1[i][1])
print("2022年政府工作报告二字高频词汇为：")
for i in range(20):
    print(my_list2[i][0], ":", my_list2[i][1])
x_list1 = list(my_dict1.keys())
x_list1 = x_list1[0:20:1]
y_list1 = list(my_dict1.values())
y_list1 = y_list1[0:20:1]
x_list2 = list(my_dict2.keys())
x_list2 = x_list2[0:20:1]
y_list2 = list(my_dict2.values())
y_list2 = y_list2[0:20:1]
for i in range(20):
    x_list1.append(my_dict1)
picture1 = pyecharts.charts.Bar()\
    .add_xaxis(x_list1)\
    .add_yaxis("出现次数", y_list1)\
    .render("2021年政府报告高频二字词汇.html")
picture2 = pyecharts.charts.Bar()\
    .add_xaxis(x_list2)\
    .add_yaxis("出现次数", y_list2)\
    .render("2022年政府报告高频二字词汇.html")

```

### 3.2 政府工作报告综合

```python
# -----------------载入库-------------------
import jieba
from pyecharts import options as opts
from pyecharts.charts import Pie

# ------------------数据准备------------------
with open("政府工作报告2021.txt", "r", encoding="UTF-8") as f:
    all_content1 = f.readlines()
with open("政府工作报告2022.txt", "r", encoding="UTF-8") as f:
    all_content2 = f.readlines()


# --------------------------定义函数-------------------
def all_cut(content):
    my_dict = {}
    for i in content:
        cut = jieba.cut(i)
        for word in cut:
            if len(word) == 2:
                my_dict[word] = my_dict.get(word, 0) + 1
    return my_dict


# -------------------主程序------------------
my_dict1 = all_cut(all_content1)
my_list1 = list(my_dict1.items())
my_list1.sort(key=lambda x: x[1], reverse=True)

my_dict2 = all_cut(all_content2)
my_list2 = list(my_dict2.items())
my_list2.sort(key=lambda x: x[1], reverse=True)
print("2021年政府工作报告二字高频词汇为：")
for i in range(20):
    print(my_list1[i][0], ":", my_list1[i][1])
print("2022年政府工作报告二字高频词汇为：")
for i in range(20):
    print(my_list2[i][0], ":", my_list2[i][1])
x_list1 = list(my_dict1.keys())
y_list1 = list(my_dict1.values())
x_list2 = list(my_dict2.keys())
y_list2 = list(my_dict2.values())

same_list_x = []
same_list_y = []
difference_list1_x = []
difference_list1_y = []

for x1 in x_list1:
    for x2 in x_list2:
        if x1 == x2:  # 共同的高频词
            if len(same_list_x) <= 10:  # 前十个
                same_list_x.append(x1)
                same_list_y.append(my_dict1[x1])
                break
        else:
            if len(difference_list1_x) <= 5:
                difference_list1_x.append(x1)
                difference_list1_y.append(my_dict1[x1])
pie1 = Pie()
pie2 = Pie()
data1 = []
data2 = []
for i in range(len(same_list_x)):
    data1.append((same_list_x[i], same_list_y[i]))
for i in range(len(difference_list1_x)):
    data2.append((difference_list1_x[i], difference_list1_y[i]))
pie1.add('', data1)
pie1.set_global_opts(title_opts=opts.TitleOpts(title='2021年政府报告高频二字词汇统计'))
pie2.add('', data2)
pie2.set_global_opts(title_opts=opts.TitleOpts(title='2022年政府报告高频二字词汇统计'))
pie1.render("比较.html")
pie2.render("比较.html")

```

### 3.3 论语提纯

```python
f1 = open("论语解读版本.txt", "r", encoding="UTF-8")
f2 = open("论语.txt", "w", encoding="utf-8")
data = ''  # 用于储存要写入的数据
a = 0  # 用于判断行是否需要写入
for line in f1:  # 遍历每一行
    line = line.strip()  # 去除前后空格和换行符

    if line.count("【原文】") != 0:  # 原文下面的内容要写
        a = 1
    if line.count("【注释】") != 0:  # 注释下面的内容不写
        a = 0
    if a == 1 and line.count("【原文】") == 0 and line.count("【注释】") == 0 and len(line) != 0:
        data += line + "\n"

data = data.replace("(", "")  # 去掉左括号
data = data.replace(")", "")  # 去掉右括号
for i in range(10):  # 去掉数字
    data = data.replace(f"{i}", "")
f2.write(data)  # 将数据写入文件中
f1.close()  # 关闭读取文件
f2.close()  # 关闭写入文件

```

### 3.4网页数据大学学院统计

```python
import re
from pyecharts.charts import Bar

total_dx = []  # 统计大学
total_xy = []  # 统计学院
f = open("慕课MOOC.txt", "r", encoding="UTF-8")
for line in f:
    if "alt=" in line:
        name = re.findall(r'[\u4e00-\u9fa5]+', line)
        name = name[0]
        check = name[-2::1]
        if check == "大学":
            total_dx.append(name)
        if check == "学院":
            total_xy.append(name)
print(f"大学共有{len(total_dx)}所")
for i in total_dx:
    print(i, end='\t')
print(f"\n学院共有{len(total_xy)}所")
for i in total_xy:
    print(i, end='\t')
my_list1 = ['大学', "学院"]
my_list2 = [len(total_dx), len(total_xy)]
Bar().add_xaxis(my_list1).add_yaxis("统计", my_list2).render("统计图.html")

```



# 第20课三国演义之谁是话痨

## 1.操作文件指针

==f.tell()==			指针位置

==seek(offset[, whence])==

​	**offset**--偏移量，可以是负值，代表从后向前移动

​	**whence**--偏移相对位置，分别为：os.SEEK_SET(相对文件**起始**位置，也可用“0”表示)；os.SEEK_CUR(相对文件**当前**位置，也可以用“1”表示)；os.SEEK_END(相对文件**结尾**位置，也可用"2"表示)

==read(size)==

​	从文件指针**当前位置**起读取size个字节（包括换行符）

## 2.openpyxl使用

f.merge_cells(x:y)			x,y为需要合并的左上角和右下角单元格坐标

## 3. threading库(多线程)  (考试03任务2弹幕)

1.import threading			导包

2.将需要执行的任务包装成子函数，便于线程的添加

3.创建线程

​		线程名===threading.Thread(target=task,args=(arg1,arg2))==

​			task:代表任务的子函数

​			args:代表变量（子函数）

4.运行进程

​		==进程名.start()==

​	多进程时依次start即可

## 4.正则表达式

### 4.1基础语法

==import re== 载入模块

==变量=re.match(匹配规则，被匹配字符串)==	从头开始匹配

==变量.span()==	字符串下标

==变量.group()==	字符串的值

			该函数默认传参为0，传入参数0（默认值）将返回整个匹配的子串，而传入参数1将返回第一个匹配的捕获组（即正则表达式中用括号括起来的部分）。

当正则表达式中包含分组时，group方法可以用于返回指定分组的匹配结果。每个分组都可以通过小括号括起来，用于将匹配结果分成多个组，可以通过在group方法中指定分组编号来获取指定分组的匹配结果。

==search(规则，被匹配字符串)==	搜索整个字符串，找到一个就停止

==findall(规则，被匹配字符串)==	找到所有匹配项

### 4.2匹配规则

#### 单字符匹配

.	任意字符（除了换行符），匹配.时需要在前面加\

[]	匹配[]中列举的字符

\d	匹配数字

\D	匹配非数字		字符串前面加r表示转义字符无效

\s	匹配空白，即空格，tab键

\S	匹配非空白

\w	单词字符（0-9，a-z，A-Z，下划线_）

\W	非单词字符

#### 数量匹配

*出现0到无穷

+出现1到无穷

？出现0或者1

{m}出现m次

{m，}出现最少m次

{m,n}出现m到n次

#### 边界匹配

^从开头匹配

$从结尾匹配

\b匹配一个单词的边界

\B匹配非单词边界

#### 分组匹配

|匹配左右任意一个表达式

()将括号中的字符作为一个分组

## 5.代码案例

### 1.文件操作

```python
# ----------------载入库---------------
import openpyxl

# ---------------主程序--------------------
fr = open("任务1.txt", "r", encoding="UTF-8")
fw = openpyxl.load_workbook("任务1.xlsx")
sheet = fw["Sheet1"]
num = 1  # 序号
cell_row = 1  # 单元格的行
cell_line = 1  # 单元格的列
begin = "A"
for line in fr:  # 依次读取每一列
    for i in line:  # 依次读取每一个字符
        a = ord(i)  # UTF-8编码
        hebing = chr(ord(begin) + len(i.encode("UTF-8")))
        # 填序号
        sheet.cell(cell_row, cell_line).value = num
        sheet.merge_cells(f"{begin}{cell_row}:{hebing}{cell_row}")
        # 合并单元格并填入原内容
        sheet.cell(cell_row + 1, cell_line).value = i
        sheet.merge_cells(f"{begin}{cell_row + 1}:{hebing}{cell_row + 1}")
        # 合并单元格并填入UTF-8编码
        sheet.cell(cell_row + 2, cell_line).value = a
        sheet.merge_cells(f"{begin}{cell_row + 2}:{hebing}{cell_row + 2}")
        sheet.cell(cell_row + 3, cell_line).value = bytes(i, "UTF-8").hex()
        sheet.merge_cells(f"{begin}{cell_row + 3}:{hebing}{cell_row + 3}")
        # 为下次循环做准备
        num += 1
        cell_line += len(i.encode("UTF-8")) + 1
    cell_row += 4
    cell_line = 1
    begin = "A"
# 关闭文件
fr.close()
fw.save("任务1.xlsx")
fw.close()

```

### 2.三国

```python
import re
from collections import Counter

# 读取《三国演义》文本文件
with open('sg（原文）.txt', 'r', encoding='utf-8') as file:  # 读取文件
    text = file.read()

# 通过正则表达式提取人物对话
dialogues = re.findall(r'[\u4e00-\u9fa5]{2,5}：“.*?”', text)  # 通过正则表达式找到人说的话
print(dialogues)
# 统计每个人物的说话字数
word_count = Counter()  # 类似于字典，键值对中的值用来计数

for dialogue in dialogues:
    # 提取人物名称
    match = re.match(r'([\u4e00-\u9fa5]{2,5})：“.*?”', dialogue)  # 将说话前的内容加括号用group显示
    if match:
        character = match.group(1)  # 说话前的字
        # 统计字数
        words = re.findall(r'[^\u4e00-\u9fa5\s]', dialogue)
        word_count[character] += len(words)

# 打印人物说话字数统计结果
for character, count in word_count.most_common():
    print(f'{character}: {count}字 ')
# m=word_count["大惊曰"]
# print(m)
a = {}
a["诸葛亮"] = word_count["孔明曰"] + word_count["孔明笑曰"] + word_count["孔明答曰"] + word_count["孔明暗思"] \
              + word_count["孔明厉声曰"] + word_count["孔明又曰"] + word_count["明仰面笑曰"] + \
              word_count["孔明亦谢曰"] + word_count["孔明喜曰"] + word_count["孔明大惊曰"]
a["周瑜"] = word_count["瑜曰"] + word_count["瑾曰"] + word_count["瑜笑曰"] + word_count["瑜执干手曰"] \
            + word_count["瑜令众将曰"] + word_count["周瑜曰"] + word_count["瑜怒曰"] + word_count["瑜懊悔曰"] + \
            word_count["周瑜笑曰"] + word_count["瑜思曰"] + word_count["瑜告众官曰"] + word_count["周瑜大喜曰"] + \
            word_count["瑜惊曰"] + \
            word_count["瑜喝"] + word_count[""] + word_count["瑜又问"]
a["孙权"] = word_count["权曰"] + word_count["权抚瑜背曰"] + word_count["权矍然起曰"] + word_count["权叹曰"] \
            + word_count["权大悦曰"] + word_count["瑜问"] + word_count["孙权曰"]
a["鲁肃"] = word_count["肃曰"] + word_count["鲁肃愕然曰"] + word_count["鲁肃入见曰"] + word_count["肃责孔明曰"] \
            + word_count["肃先问瑜曰"] + word_count["肃密谓瑜曰"] + word_count["鲁肃曰"] + word_count["肃问瑜曰"] + \
            word_count["鲁肃入问曰"] + word_count[
                "肃谓孔明曰"] + word_count["鲁肃看毕曰"] + word_count["鲁肃看毕曰"] + word_count["肃手而言曰"] + \
            word_count["鲁肃大怒曰"]
a["刘备"] = word_count["玄德曰"] + word_count["玄德聚众曰"] + word_count["玄德愕然曰"]
a["曹操"] = word_count["操曰"] + word_count["操怒曰"] + word_count["操问"] + word_count["操问众将曰"] + word_count[
    "操问曰"] + word_count["操大怒曰"] + word_count["操方省悟曰"]
print(a)

```

# 第21课 时钟

## 1.datatime模块

```python
import datetime
# %Y——获取年份
datetime.datetime.now().strftime("%Y")
'2020'
# %H——获取24小时制时间
datetime.datetime.now().strftime("%H")
'22'
# 获取年月日_时分秒
In [4]: datetime.datetime.now().strftime("%Y-%m-%d_%H:%M:%S")
'2020-12-01_22:41:46'
# 获取字符串表示
 str(datetime.datetime.now())
'2020-12-01 22:41:46.384800'

```

## 2. turtle库

turtle.reset()

	重置画笔位置：将 Turtle 实例的位置恢复到初始位置，即坐标原点。
	重置画笔方向：将 Turtle 实例的当前方向恢复到初始方向，即向东。
	重置画笔速度：将 Turtle 实例的速度恢复到初始速度，即中等速度。
	重置画笔颜色：将 Turtle 实例的当前颜色恢复为初始颜色，即黑色
## 3.代码案例

```python
import datetime as dt
import turtle as t

hour_time = dt.datetime.now().strftime("%H")  # 时
minute_time = dt.datetime.now().strftime("%M")  # 分
second_time = dt.datetime.now().strftime("%S")  # 秒
t.ht()
t1 = t.Pen()  # 写当前时间，时分秒
t1.penup()
t1.ht()
t4 = t.Pen()
t4.pensize(3)


def draw_clock():
    for i in range(60):
        t.tracer(0)
        if i % 5 == 0:
            t4.color("red")
        else:
            t4.color("black")
        t4.penup()
        t4.seth(i * 6)
        t4.fd(100)
        t4.pendown()
        t4.fd(15)
        t4.penup()
        t4.goto(0, 0)


class Clock(t.Turtle):
    def __init__(self):
        t.Turtle.__init__(self)

    def creat_pointer(self, length, width, name):
        t.reset()  # 清除t画笔已画的全部内容
        t.penup()
        t.begin_poly()  # 记录多边形
        t.forward(length * 1.1)
        t.end_poly()  # 停止记录
        t.register_shape(name, t.get_poly())  # 给多边形定义一个名字
        hand = t.Turtle()
        hand.shape(name)
        hand.shapesize(1, 1, width)
        return hand

    def anto_renew(self):
        global an0
        t1.clear()
        t1.goto(0, -300)
        tm = dt.datetime.now().strftime("%H:%M:%S")  # 时分秒
        t.tracer(False)  # 防止时间闪烁
        t1.write(tm, align='center', font=('Courier', 14, 'bold'))
        t.update()
        t1.goto(0, -350)
        second.seth(an0)  # 设置箭头朝向
        an0 -= 6
        t.ontimer(Clock().anto_renew, 1000)  # 定时器，500毫秒后启动

    def anto_minute(self):
        global an1
        minute.seth(an1)
        an1 -= 6
        t.ontimer(Clock().anto_minute, 1000 * 60)

    def anto_hour(self):
        global an2
        hour.seth(an2)
        an2 -= 30
        t.ontimer(Clock().anto_hour, 1000 * 60 * 60)


# 画表盘
draw_clock()
# 画针
second = Clock().creat_pointer(90, 6, 'second')  # 秒针
an0 = 175 - int(second_time) * 6
minute = Clock().creat_pointer(70, 8, "minute")  # 分针
an1 = 175 - int(minute_time) * 6
hour = Clock().creat_pointer(50, 10, "hour")  # 时针
an2 = 175 - int(hour_time) * 30
Clock().anto_renew()
Clock().anto_minute()
Clock().anto_hour()
t.mainloop()

```

# 第22课扫雷文字版(面向对象)

## 类的定义

class函数定义类

## 代码案例

```python
import random


# ------------------定义雷块的类--------------------
class Mine:
    def __init__(self, x, y):
        self.x = x  # 横坐标
        self.y = y  # 纵坐标
        self.txt = '■'  # 文本显示
        self.stat = False  # 是否为雷
        self.mine_count = 0  # 附近的雷的数量
        self.blank = 0  # 成片空雷划分，初始值为0表示不属于任何区

    def __str__(self):  # 显示内容
        return "mine%d%d" % (self.x, self.y)

    def click(self):  # 选择雷块
        global Game
        if self.stat:  # 选择到雷块,结束游戏
            Game = 1
            return
        if self.mine_count != 0:  # 周围有雷
            self.txt = str(self.mine_count)
        else:  # 周围没有雷
            self.txt = "□"


# -----------------------定义子函数-----------------
# 画扫雷游戏界面
def draw_map():
    print("扫雷游戏")
    print("", end='  ')
    for i in range(10):
        print(i, end=' ')
    print()
    for i in range(10):
        print(i, end=' ')
        for j in range(10):
            print(mines[i][j].txt, end=' ')
        print()


def scan_mines():  # 每个雷块的附近的雷的数量
    for i in range(10):
        for j in range(10):
            if not mines[i][j].stat:  # 此处不是雷
                n = 0  # 统计周围的雷的数量
                for k in range(i - 1, i + 2):
                    for l in range(j - 1, j + 2):
                        if 9 >= k >= 0 and 9 >= l >= 0:
                            if mines[k][l].stat:  # 此处是雷
                                n += 1
                                mines[i][j].mine_count = n
            elif mines[i][j].stat:  # 此处是雷
                mines[i][j].mine_count = '*'


def near_mines_map():  # 作图显示附近的雷的数量
    scan_mines()  # 扫描附近雷的数量
    print("调试界面")
    print("", end='  ')
    for i in range(10):
        print(i, end=' ')
    print()
    for i in range(10):
        print(i, end=' ')
        for j in range(10):
            print(mines[i][j].mine_count, end=' ')
        print()


def find_blank(n, x, y):
    """
    找到成片的空雷并划分区号
    :param n: 区号
    :param x: 横坐标
    :param y: 纵坐标
    :return:
    """
    global flag, area  # 判断此处是否已经划分好了空雷区
    if mines[x][y].mine_count == 0 and mines[x][y].blank == 0:
        mines[x][y].blank = n
        flag = 1
        if y + 1 < 10:
            find_blank(n, x, y + 1)
        if x + 1 < 10:
            find_blank(n, x + 1, y)
        if y - 1 >= 0:
            find_blank(n, x, y - 1)
        if x - 1 >= 0:
            find_blank(n, x - 1, y)


def click_total(x, y):
    global Game
    global count  # 统计雷块数量
    my_list = [(x, y)]  # 存储待点击的雷块坐标
    while my_list:  # 只要不是空的，就进入循环
        x, y = my_list.pop()  # 删除列表中的最后一个元素并得到返回值
        mines[x][y].click()
        if not mines[x][y].stat:  # 不是雷块
            count += 1
        if mines[x][y].mine_count == 0:
            for i in range(x - 1, x + 2):
                for j in range(y - 1, y + 2):
                    if 0 <= i <= 9 and 0 <= j <= 9 and mines[i][j].txt == '■':
                        mines[i][j].click()
                        my_list.append((i, j))
        if count == 90:
            Game = 2
            return


# --------------------初始化-----------------------
# 10*10的扫雷方阵
mines = [[0 for _ in range(10)] for _ in range(10)]
for i in range(10):
    for j in range(10):
        mines[i][j] = Mine(i, j)
# print(mines)
# 随机生成10个雷
total = 0
while total < 10:
    p, q = random.randint(0, 9), random.randint(0, 9)
    if not mines[p][q].stat:
        mines[p][q].stat = True
        total += 1
# -----------------------主程序------------------------
Game = 0  # 用于判断是否点击到雷
count = 0
while Game == 0:
    draw_map()  # 扫雷界面
    near_mines_map()  # 调试界面
    # 选择雷块
    try:  # 输入的数字可能会超出范围
        xcor = int(input("请输入横坐标"))
        ycor = int(input("请输入纵坐标"))
        if xcor < 0 or xcor > 9 or ycor < 0 or ycor > 9:
            raise ValueError("坐标数值必须在0-9之间")  # ValueError数值错误
    except ValueError as e:  # 捕获异常并处理
        print("输入错误", e)
        xcor = int(input("请输入横坐标"))
        ycor = int(input("请输入纵坐标"))
    click_total(xcor, ycor)
    if Game == 1:
        print("游戏失败")
    if Game == 2:
        print("游戏成功")

```

# 第23课扫雷图形版

## 代码案例

```

```

# 第24课mirror游戏

## 检测鼠标位置

```python
import turtle


def motion(event):
    x, y = event.x, event.y
    print(f"鼠标位置：{x}, {y}")


screen = turtle.Screen()
canvas = screen.getcanvas()
canvas.bind('<Motion>', motion)  # <Motion> 是 Tkinter 中用于表示鼠标移动的事件类型的标准字符串,将鼠标移动事件（<Motion>）与一个名为 motion 的函数绑定在一起

screen.mainloop()

```

# 第25课走迷宫

## pygame的使用

### 01游戏最小系统

```python
import pygame

# 1. 初始化操作
pygame.init()

# 2. 创建游戏窗口

# 窗口大小：set_mode
window = pygame.display.set_mode((400, 600))
# 设置游戏标题
pygame.display.set_caption('走迷宫(杨山峰)')

# 3.让游戏保持一直运行的状态
# game loop(游戏循环)
while True:
    # 4.检测事件
    for event in pygame.event.get():
        # 检测关闭按钮被点击的事件
        if event.type == pygame.QUIT:
            # 退出
            exit()  # 结束线程

```



### 02显示图片

```python
import pygame

pygame.init()
window = pygame.display.set_mode((400, 600))
pygame.display.set_caption("显示图片")
# 设置背景颜色
window.fill((255, 255, 255))

# -----------游戏启动页面静态效果----------------
# 1.加载图片
image1 = pygame.image.load('../files/背景.jpg')

# 2.渲染图片
# blit(渲染对象，坐标)
window.blit(image1, (0, 0))

# 操作图片
# 1）获取图片大小
w, h = image1.get_size()
# print(w,h)
window.blit(image1, (400 - w, 600 - h))

# 2)旋转和缩放
# scale(缩放对象， 目标大小)     可能会发生形变
new1 = pygame.transform.scale(image1, (100, 100))
window.blit(new1, (210, 0))

# rotozoom(缩放/旋转对象， 旋转角度(逆时针旋转)，缩放比例)
new2 = pygame.transform.rotozoom(image1, 90, 0.5)
window.blit(new2, (0, 200))
# 3. 刷新显示页面
# pygame.display.flip()   第一次刷新
# pygame.display.update()   以后的刷新
pygame.display.flip()

while True:
    # -------------游戏帧的刷新-----------------
    for event in pygame.event.get():
        if event.type == pygame.QUIT:
            exit()

```



### 03显示文字

```python
import pygame

pygame.init()
window = pygame.display.set_mode((400, 600))
pygame.display.set_caption("显示文字")
# 设置背景颜色
window.fill((255, 255, 255))

# ===================显示文字=====================
# 1.创建字体对象
# Font(字体文件路径，字体大小)
font = pygame.font.Font('../files/字体.ttf', 30)

# 2. 创建文字对象
# render(文字内容，True, 文字颜色， 背景颜色(可以不设置))
text = font.render("你好", True, (255, 0, 0), (255, 255, 0))

# 3.渲染到窗口上
window.blit(text, (0, 0))

# 4.操作文字对象
# 1)获取文字大小
w, h = text.get_size()
window.blit(text, (400 - w, 600 - h))

# 2)缩放和旋转
new_t1 = pygame.transform.scale(text, (400, 50))
window.blit(new_t1, (0, 60))

new_t2 = pygame.transform.rotozoom(text, 0, 2)

# 刷新
pygame.display.flip()

while True:
    # -------------游戏帧的刷新-----------------
    for event in pygame.event.get():
        if event.type == pygame.QUIT:
            exit()

```



### 04显示图形

```python
import pygame
from math import pi

pygame.init()
window = pygame.display.set_mode((400, 600))
pygame.display.set_caption("显示图形")
# 设置背景颜色
window.fill((255, 255, 255))

# ==================显示图形=================
# 1.画直线
# line(画在哪儿，线的颜色，线的起点，线的终点,线宽（默认为1）)
pygame.draw.line(window, (255, 0, 0), (10, 20), (200, 20))

# 2.画折线
# lines(画在哪儿，线的颜色，是否闭合，点列表，线宽（默认为1）)
points = [(10, 300), (100, 160), (180, 260), (300, 100)]
pygame.draw.lines(window, (0, 255, 0), False, points)

# 3.画圆
# circle(画在哪儿，线的颜色，圆心坐标，半径，线宽（默认为0,即填充整个圆）)
pygame.draw.circle(window, (0, 0, 255), (200, 250), 100, 1)

# 4.画矩形
# rect(画在哪儿，线的颜色，矩形范围(横坐标，纵坐标，长度，宽度)，线宽（默认为0）)
pygame.draw.rect(window, (120, 20, 60), (100, 70, 100, 200), 3)

# 5.画椭圆
# ellipse(画在哪儿，线的颜色，矩形范围(横坐标，纵坐标，长度，宽度)，线宽（默认为0）)
pygame.draw.ellipse(window, (255, 20, 60), (100, 70, 100, 200), 3)

# 6.画弧线
# arc(画在哪儿，线的颜色，矩形范围，起始弧度，终止弧度，线宽（默认为1）)
pygame.draw.arc(window, (0, 0, 0), (100, 70, 100, 200), 0, pi, 3)

# 刷新界面
pygame.display.flip()

while True:
    for event in pygame.event.get():
        if event.type == pygame.QUIT:
            exit()

```



## pygame的动画和事件

### 01动画原理

```python
import pygame

WIN_WIDTH = 400  # 窗口宽度
WIN_HEIGHT = 600  # 窗口高度

# 初始化游戏
pygame.init()

# 创建窗口
window = pygame.display.set_mode((WIN_WIDTH, WIN_HEIGHT))
pygame.display.set_caption("动画原理")
window.fill((255, 255, 255))
pygame.display.flip()

# 1.显示静态球
y = 100
r = 30
pygame.draw.circle(window, (255, 0, 0), (100, y), r)
pygame.display.update()

# 游戏循环
num = 1
while True:
    num += 1
    if num % 10000 == 0:

        # # 移动动画
        # pygame.draw.circle(window, (255, 255, 255), (100, y), 50)
        # y += 1
        # pygame.draw.circle(window, (255, 0, 0), (100, y), 50)
        # pygame.display.update()

        # 缩放动画
        pygame.draw.circle(window, (255, 255, 255), (100, y), r)
        r += 1
        pygame.draw.circle(window, (255, 0, 0), (100, y), r)
        pygame.display.update()

    # 检测事件
    for event in pygame.event.get():
        if event.type == pygame.QUIT:
            exit()

```



### 02动画的应用

```python
import pygame

WIN_WIDTH = 400  # 窗口宽度
WIN_HEIGHT = 600  # 窗口高度

# 初始化游戏
pygame.init()

# 创建窗口
window = pygame.display.set_mode((WIN_WIDTH, WIN_HEIGHT))
pygame.display.set_caption("动画的应用")
window.fill((255, 255, 255))
pygame.display.flip()

# 1.静态球
x, y = 200, 50  # 圆心坐标
r = 50  # 半径
y_speed = 1
pygame.draw.circle(window, (0, 255, 0), (x, y), r)
pygame.display.update()

num = 0
while True:
    num += 1
    if num % 10000 == 0:
        window.fill((255, 255, 255))
        # 修改y坐标
        y += y_speed
        if y >= WIN_HEIGHT - r:
            y_speed = -1
        if y <= r:
            y_speed = 1
        pygame.draw.circle(window, (0, 255, 0), (x, y), r)
        pygame.display.update()
    # 检测事件
    for event in pygame.event.get():
        if event.type == pygame.QUIT:
            exit()

```



### 03事件检测

```python
import pygame
import random

WIN_WIDTH = 400  # 窗口宽度
WIN_HEIGHT = 600  # 窗口高度

# 初始化游戏
pygame.init()

# 创建窗口
window = pygame.display.set_mode((WIN_WIDTH, WIN_HEIGHT))
pygame.display.set_caption("事件检测")
window.fill((255, 255, 255))
pygame.display.flip()

font = pygame.font.Font(r"D:\编程学习\实验室\python\课程\pygame游戏开发\files\字体.ttf", 30)

count = 0  # 统计事件发生的次数
while True:
    # 检测事件
    for event in pygame.event.get():
        count += 1
        print(event)
        print(count)

        # event的type属性是用来区分不同类型的事件
        """
        QUIT    点击关闭按钮对应的事件
        
        1.鼠标事件
        MOUSEBUTTONDOWN     鼠标按下
        MOUSEBUTTONUP       鼠标弹起
        MOUSEMOTION         鼠标移动
        
        鼠标位置属性(点在哪儿)  pos
        
        2.键盘事件
        KEYDOWN     按键按下
        KEYUP       按键弹起
        
        按键值属性(哪个键被按下了)  key
        """
        if event.type == pygame.QUIT:
            # 退出
            exit()
        # ===============鼠标事件===================
        if event.type == pygame.MOUSEBUTTONDOWN:
            print("鼠标按下", event.pos)
            mx, my = event.pos  # 取出鼠标的x坐标和y坐标
            pygame.draw.circle(window, (255, 255, 0), (mx, my), 50)
            pygame.display.update()

        if event.type == pygame.MOUSEBUTTONUP:
            print("鼠标弹起")

        if event.type == pygame.MOUSEMOTION:
            print('鼠标移动')
            r = random.randint(0, 255)
            g = random.randint(0, 255)
            b = random.randint(0, 255)
            mx, my = event.pos  # 取出鼠标的x坐标和y坐标
            pygame.draw.circle(window, (r, g, b), (mx, my), 50)
            pygame.display.update()

        if event.type == pygame.KEYDOWN:
            print("按键按下", event.key, chr(event.key))

            if chr(event.key) == "f":
                print("闪现")

            text = font.render(chr(event.key), True, (255, 0, 0))
            window.fill((255, 255, 255))
            window.blit(text, (0, 300))
            pygame.display.update()

        if event.type == pygame.KEYUP:
            print("按键弹起")

```



### 04按钮点击

```python
import pygame

WIN_WIDTH = 400  # 窗口宽度
WIN_HEIGHT = 600  # 窗口高度

# 初始化游戏
pygame.init()

# 创建窗口
window = pygame.display.set_mode((WIN_WIDTH, WIN_HEIGHT))
pygame.display.set_caption("按钮点击")
window.fill((255, 255, 255))
pygame.display.flip()

# 创建字体对象
font = pygame.font.Font(r"D:\编程学习\实验室\python\课程\pygame游戏开发\files\字体.ttf", 30)

# 1.确定按钮
bx1, by1, bw1, bh1 = 30, 100, 100, 50
pygame.draw.rect(window, (255, 0, 0), (bx1, by1, bw1, bh1))
text1 = font.render("确定", True, (255, 255, 255))

tw1, th1 = text1.get_size()
tx1 = bx1 + bw1 / 2 - tw1 / 2
ty1 = by1 + bh1 / 2 - th1 / 2

window.blit(text1, (tx1, ty1))

# 2.取消按钮
bx2, by2, bw2, bh2 = 30, 200, 100, 50
pygame.draw.rect(window, (0, 255, 0), (bx2, by2, bw2, bh2))
text2 = font.render("取消", True, (255, 255, 255))

tw2, th2 = text2.get_size()
tx2 = bx2 + bw2 / 2 - tw2 / 2
ty2 = by2 + bh2 / 2 - th2 / 2
window.blit(text2, (tx2, ty2))

pygame.display.update()

while True:
    # 检测事件
    for event in pygame.event.get():
        if event.type == pygame.QUIT:
            # 退出
            exit()
        if event.type == pygame.MOUSEBUTTONDOWN:
            mx, my = event.pos
            # 是否点击了确定按钮
            if bx1 <= mx <= bx1 + bw1 and by1 <= my <= by1 + bh1:
                # 按钮点击的反应
                pygame.draw.rect(window, (200, 200, 200), (bx1, by1, bw1, bh1))
                window.blit(text1, (tx1, ty1))
                pygame.display.update()

                print("确定按钮被点击")

            # 是否点击的取消按钮
            if bx2 <= mx <= bx2 + bw2 and by2 <= my <= by2 + bh2:
                print("取消按钮被点击")
                # 按钮点击的反应
                pygame.draw.rect(window, (200, 200, 200), (bx2, by2, bw2, bh2))
                window.blit(text2, (tx2, ty2))
                pygame.display.update()

        if event.type == pygame.MOUSEBUTTONUP:
            # 确定按钮恢复
            pygame.draw.rect(window, (255, 0, 0), (bx1, by1, bw1, bh1))
            window.blit(text1, (tx1, ty1))
            # 取消按钮恢复
            pygame.draw.rect(window, (0, 255, 0), (bx2, by2, bw2, bh2))
            window.blit(text2, (tx2, ty2))

            pygame.display.update()

```



### 05 按住不放

```python
import pygame

WIN_WIDTH = 400  # 窗口宽度
WIN_HEIGHT = 600  # 窗口高度

# 初始化游戏
pygame.init()

# 创建窗口
window = pygame.display.set_mode((WIN_WIDTH, WIN_HEIGHT))
pygame.display.set_caption("按钮点击")
window.fill((255, 255, 255))
pygame.display.flip()

# 放坦克
tank_up = pygame.image.load(r"D:\编程学习\实验室\python\课程\pygame游戏开发\files\人物.gif")  # 向上的坦克
tank_x, tank_y = 200, 450

window.blit(tank_up, (tank_x, tank_y))
pygame.display.update()
is_move = False  # 是否移动
x_speed = 0
y_speed = 0

while True:
    if is_move:
        window.fill((255, 255, 255))  # 填充白色
        tank_x += x_speed
        tank_y += y_speed
        window.blit(tank_up, (tank_x, tank_y))
        pygame.display.update()

    # 检测事件
    for event in pygame.event.get():
        if event.type == pygame.QUIT:
            # 退出
            exit()
        if event.type == pygame.KEYDOWN:
            char = chr(event.key)

            # 往上
            if char == 'w':
                x_speed = 0
                y_speed = -0.01
                is_move = True

            # 往左
            if char == 'a':
                x_speed = -0.01
                y_speed = 0
                is_move = True

            # 往下
            if char == 's':
                x_speed = 0
                y_speed = 0.01
                is_move = True

            # 往右
            if char == 'd':
                x_speed = 0.01
                y_speed = 0
                is_move = True

        if event.type == pygame.KEYUP:
            x_speed = 0
            y_speed = 0
            is_move = False

```

## 走迷宫游戏案例

### 一层走迷宫

```python
# ================载入模块=================
import pygame

# ==================数据==================
# 设置窗口大小
WINDOW_SIZE = (600, 400)
# 字体大小
FONT_SIZE = 30
# 设置颜色
BLACK = (0, 0, 0)
WHITE = (255, 255, 255)
BLUE = (0, 0, 255)
GREEN = (0, 255, 0)
YELLOW = (255, 255, 0)
# 对象初始位置
PLAYER_POSITION = (0, 0)

# ================准备==================
# 初始化
pygame.init()
# 创建窗口
window = pygame.display.set_mode(WINDOW_SIZE)
# 窗口命名
pygame.display.set_caption("走迷宫")
# 创建字体
font = pygame.font.Font('字体.ttf', FONT_SIZE)
# 背景音乐
pygame.mixer.music.load('青睐 - 贩卖人间黄昏.mp3')  # 载入音乐文件
pygame.mixer.music.play(-1)  # -1 表示循环播放


# =================类==================
class Player:
    def __init__(self, x, y, map_obj):
        self.x = x
        self.y = y
        self.player = pygame.image.load("人物.gif")
        window.blit(self.player, (self.x, self.y))
        pygame.display.update()
        self.map = map_obj  # 保存地图对象
        self.rect = self.player.get_rect()  # 创建Rect对象，用于进行碰撞检测
        self.rect.x = self.x
        self.rect.y = self.y

    def move(self, dx, dy):
        # 移动前先备份Rect对象的位置
        prev_x = self.rect.x
        prev_y = self.rect.y

        self.x = dx
        self.y = dy
        # window.blit(self.player, (self.x, self.y))
        # pygame.display.update()
        self.rect.x = self.x  # 更新Rect对象的位置
        self.rect.y = self.y

        # 检测是否与墙壁碰撞
        for row in range(self.map.maze_height):
            for col in range(self.map.maze_width):
                if self.map.maze_map[row][col] == 0:  # 墙壁
                    wall_rect = pygame.Rect(col * self.map.rect_width, row * self.map.rect_height, self.map.rect_width,
                                            self.map.rect_height)  # 墙壁的Rect对象
                    if self.rect.colliderect(wall_rect):  # 两个Rect对象重叠
                        # 与墙壁碰撞，撤回移动
                        self.x = prev_x
                        self.y = prev_y
                        window.blit(self.player, (self.x, self.y))
                        pygame.display.update()
                        self.rect.x = self.x
                        self.rect.y = self.y
                        return
        # 绘制玩家角色
        window.blit(self.player, (self.x, self.y))
        pygame.display.update()


class Map:
    def __init__(self):
        # 迷宫
        self.maze_map = [
            [1, 1, 1, 0, 1, 1, 0, 1, 1, 0],
            [1, 0, 1, 1, 1, 0, 0, 1, 0, 0],
            [1, 1, 0, 0, 1, 1, 1, 1, 1, 0],
            [1, 0, 1, 0, 0, 0, 0, 0, 1, 1],
            [1, 1, 1, 1, 1, 1, 1, 1, 0, 0],
            [1, 1, 0, 0, 0, 1, 0, 1, 0, 0],
            [0, 1, 1, 1, 1, 0, 1, 1, 1, 1],
            [0, 0, 0, 0, 1, 1, 1, 0, 0, 1]
        ]  # 二维列表创建10*8的迷宫,1为路，0为墙壁
        # 计算迷宫的大小
        self.maze_width = len(self.maze_map[0])  # 长为10
        self.maze_height = len(self.maze_map)  # 宽为8

        # 定义墙壁和路径的宽和高
        self.rect_width = WINDOW_SIZE[0] / self.maze_width
        self.rect_height = WINDOW_SIZE[1] / self.maze_height

    def draw(self):
        """画迷宫"""
        for row in range(self.maze_height):
            for col in range(self.maze_width):
                x = col * self.rect_width
                y = row * self.rect_height
                if self.maze_map[row][col] == 1:  # 路
                    pygame.draw.rect(window, WHITE, (x, y, self.rect_width, self.rect_width), 0)
                else:  # 墙壁
                    pygame.draw.rect(window, BLACK, (x, y, self.rect_width, self.rect_width), 0)
        pygame.display.update()


class Game:
    def __init__(self):
        # 初始化
        pygame.init()
        # 创建窗口
        self.window = pygame.display.set_mode(WINDOW_SIZE)
        # 窗口命名
        pygame.display.set_caption("走迷宫")
        # 创建字体
        self.font = pygame.font.Font('字体.ttf', FONT_SIZE)
        # 创建对象
        self.x = PLAYER_POSITION[0]
        self.y = PLAYER_POSITION[1]
        self.map1 = Map()
        self.player = Player(PLAYER_POSITION[0], PLAYER_POSITION[1], self.map1)
        # 游戏帧率
        self.clock = pygame.time.Clock()
        # 移动速度
        self.x_speed = 1
        self.y_speed = 1
        # 是否移动
        self.is_move = None

    def run(self):
        running = True
        while running:
            self.clock.tick(60)
            if self.is_move:
                window.fill(BLACK)
                self.map1.draw()
                self.x += self.x_speed
                self.y += self.y_speed
                self.player.move(self.x, self.y)
            # 检测事件
            for event in pygame.event.get():
                if event.type == pygame.QUIT:
                    # 退出
                    running = False
                if event.type == pygame.KEYDOWN:
                    char = chr(event.key)  # 敲击的按钮
                    # 往上
                    if char == 'w':
                        self.x_speed = 0
                        self.y_speed = -1
                        self.is_move = True
                    # 往左
                    if char == 'a':
                        self.x_speed = -1
                        self.y_speed = 0
                        self.is_move = True
                    # 往下
                    if char == 's':
                        self.x_speed = 0
                        self.y_speed = 1
                        self.is_move = True
                    # 往右
                    if char == 'd':
                        self.x_speed = 1
                        self.y_speed = 0
                        self.is_move = True

                if event.type == pygame.KEYUP:
                    self.x_speed = 0
                    self.y_speed = 0
                    self.is_move = False

        pygame.mixer.music.stop()  # 停止背景音乐
        pygame.quit()  # 退出pygame


if __name__ == "__main__":
    game = Game()
    game.run()

```

### 走迷宫（完整版）

#### 地图

```
import pygame

# 设置颜色
BLACK = (0, 0, 0)
WHITE = (255, 255, 255)
BLUE = (0, 0, 255)
GREEN = (0, 255, 0)
YELLOW = (255, 255, 0)


def read_txt_file(file_path):
    """
    读取txt文件转换成二维列表
    :param file_path: 迷宫的文本文件
    :return: 迷宫的二维列表
    """
    data = []
    with open(file_path, 'r') as file:
        for line in file:
            line = line.strip()  # 去除行尾的换行符和空格
            lines = []
            for i in line:
                lines.append(int(i))
            data.append(lines)
    return data


class Map:
    def __init__(self, window, window_size, maze_map):
        """
        地图设计
        :param window:显示的界面
        :param window_size:界面的宽和高
        :param maze_map:地图设计
        """
        self.maze_map = maze_map
        # 计算迷宫的大小
        self.maze_width = len(self.maze_map[0])  # 长为10
        self.maze_height = len(self.maze_map)  # 宽为8

        # 定义墙壁和路径的宽和高
        self.rect_width = window_size[0] / self.maze_width
        self.rect_height = window_size[1] / self.maze_height
        self.window = window

    def draw(self):
        """画迷宫"""
        for row in range(self.maze_height):
            for col in range(self.maze_width):
                x = col * self.rect_width
                y = row * self.rect_height
                if self.maze_map[row][col] == 1:  # 路
                    pygame.draw.rect(self.window, WHITE, (x, y, self.rect_width, self.rect_width), 0)
                else:  # 墙壁
                    pygame.draw.rect(self.window, BLACK, (x, y, self.rect_width, self.rect_width), 0)
        pygame.display.update()

```



#### 玩家

```
import pygame


class Player:
    def __init__(self, window, x, y, map_obj, player_fill):
        """
        初始化
        :param window: 显示窗口
        :param x: 玩家初始横坐标
        :param y: 玩家初始纵坐标
        :param map_obj: 迷宫二维列表
        :param player_fill:玩家图片文件
        """
        self.x = x
        self.y = y
        self.player = pygame.image.load(player_fill)
        window.blit(self.player, (self.x, self.y))
        pygame.display.update()
        self.map = map_obj  # 保存地图对象
        self.rect = self.player.get_rect()  # 创建Rect对象，用于进行碰撞检测
        self.rect.x = self.x
        self.rect.y = self.y
        self.window = window

    def move(self, dx, dy):
        # 移动前先备份Rect对象的位置
        prev_x = self.rect.x
        prev_y = self.rect.y
        self.x = dx
        self.y = dy
        self.rect.x = self.x  # 更新Rect对象的位置
        self.rect.y = self.y

        # 检测是否与墙壁碰撞
        for row in range(self.map.maze_height):
            for col in range(self.map.maze_width):
                if self.map.maze_map[row][col] == 0:  # 墙壁
                    wall_rect = pygame.Rect(col * self.map.rect_width, row * self.map.rect_height, self.map.rect_width,
                                            self.map.rect_height)  # 墙壁的Rect对象
                    if self.rect.colliderect(wall_rect):  # 两个Rect对象重叠
                        # 与墙壁碰撞，撤回移动
                        self.x = prev_x
                        self.y = prev_y
                        self.window.blit(self.player, (self.x, self.y))
                        pygame.display.update()
                        self.rect.x = self.x
                        self.rect.y = self.y
                        return
        # 绘制玩家角色
        self.window.blit(self.player, (self.x, self.y))
        pygame.display.update()

```



#### 游戏类

```
from map import *
from player import Player

BLACK = (0, 0, 0)


class SimpleGame:
    def __init__(self, window, player_position, file, player_fill):
        """
        游戏模式
        :param window: 窗口界面
        :param player_position:玩家位置
        :param file:迷宫文件
        :param player_fill: Z玩家图片文件
        """
        # 初始化
        pygame.init()
        self.PLAYER_POSITION = player_position
        # 创建窗口
        self.window = window
        window_size = self.window.get_size()  # 获取窗口大小

        # 窗口命名
        pygame.display.set_caption("走迷宫")
        # 迷宫地图
        self.maze_map = read_txt_file(file)
        # 创建对象
        self.x = self.PLAYER_POSITION[0]
        self.y = self.PLAYER_POSITION[1]
        self.map1 = Map(self.window, window_size, self.maze_map)
        self.player = Player(self.window, self.PLAYER_POSITION[0], self.PLAYER_POSITION[1], self.map1, player_fill)
        # 游戏帧率
        self.clock = pygame.time.Clock()
        # 移动速度
        self.x_speed = 1
        self.y_speed = 1
        # 是否移动
        self.is_move = None

    def run(self):
        running = True
        while running:
            self.clock.tick(60)
            if self.is_move:
                self.window.fill(BLACK)
                self.map1.draw()
                self.x += self.x_speed
                self.y += self.y_speed
                self.player.move(self.x, self.y)
            # 检测事件
            for event in pygame.event.get():
                if event.type == pygame.QUIT:
                    # 退出
                    running = False
                if event.type == pygame.KEYDOWN:
                    char = chr(event.key)  # 敲击的按钮
                    # 往上
                    if char == 'w':
                        self.x_speed = 0
                        self.y_speed = -1
                        self.is_move = True
                    # 往左
                    if char == 'a':
                        self.x_speed = -1
                        self.y_speed = 0
                        self.is_move = True
                    # 往下
                    if char == 's':
                        self.x_speed = 0
                        self.y_speed = 1
                        self.is_move = True
                    # 往右
                    if char == 'd':
                        self.x_speed = 1
                        self.y_speed = 0
                        self.is_move = True

                if event.type == pygame.KEYUP:
                    self.x_speed = 0
                    self.y_speed = 0
                    self.is_move = False

        pygame.quit()  # 退出pygame

```



#### 完整版本

```
import pygame
from game import SimpleGame

# =================数据准备=====================
# 窗口大小
WINDOW_SIZE = (600, 400)
# 定义颜色
BLACK = (0, 0, 0)
WHITE = (255, 255, 255)
RED = (255, 0, 0)
GREEN = (0, 255, 0)
YELLOW = (255, 255, 0)
BLUE = (0, 0, 255)


class TwoGame:
    def __init__(self):
        # =================初始化====================
        # 初始化pygame
        pygame.init()
        # 初始化mixer模块
        pygame.mixer.init()
        # 创建游戏窗口
        self.window = pygame.display.set_mode(WINDOW_SIZE)
        # 设置标题
        pygame.display.set_caption('走迷宫')
        # 加载字体
        self.font = pygame.font.Font('字体.ttf', 20)
        # 绘制界面
        self.window.fill(WHITE)
        text1 = self.font.render("简单模式", True, BLACK)
        pygame.draw.rect(self.window, RED, (50, 50, 150, 50))
        self.window.blit(text1, (85, 60))
        text2 = self.font.render("困难模式", True, BLACK)
        pygame.draw.rect(self.window, GREEN, (350, 50, 150, 50))
        self.window.blit(text2, (385, 60))
        text3 = self.font.render("噩梦模式", True, BLACK)
        pygame.draw.rect(self.window, YELLOW, (50, 200, 150, 50))
        self.window.blit(text3, (85, 210))
        text4 = self.font.render("自定义", True, BLACK)
        pygame.draw.rect(self.window, BLUE, (350, 200, 150, 50))
        self.window.blit(text4, (395, 210))

        pygame.display.flip()
        # 选择的游戏模式
        self.point = 0
        # 背景音乐
        pygame.mixer.music.load('青睐 - 贩卖人间黄昏.mp3')  # 载入音乐文件
        pygame.mixer.music.play(-1)  # -1 表示循环播放

    def run(self):
        running = True
        while running:
            for event in pygame.event.get():
                if event.type == pygame.QUIT:  # 退出游戏
                    running = False
                if event.type == pygame.MOUSEBUTTONDOWN:
                    x, y = event.pos
                    if 50 <= x <= 200 and 50 <= y <= 100:  # 点击了简单模式按钮
                        print("选择了简单模式")
                        # 设置游戏为简单模式
                        self.point = 1
                        running = False
                    if 350 <= x <= 500 and 50 <= y <= 100:  # 点击了困难模式按钮
                        print("选择了困难模式")
                        # 设置游戏为困难模式
                        self.point = 2
                        running = False
                    if 50 <= x <= 200 <= y <= 250:  # 点击了噩梦模式按钮
                        print("选择了噩梦模式")
                        # 设置游戏为困难模式
                        self.point = 3
                        running = False
                    if 350 <= x <= 500 and 200 <= y <= 250:  # 点击了自定义模式按钮
                        print("选择了自定义模式")
                        # 设置游戏为困难模式
                        self.point = 4
                        running = False

        if self.point == 1:
            self.window.fill(BLACK)
            run_game = SimpleGame(self.window, (0, 0), '简单模式迷宫.txt', '人物.gif')
            run_game.run()
        if self.point == 2:
            self.window.fill(BLACK)
            run_game = SimpleGame(self.window, (0, 0), '困难模式迷宫.txt', '人物.gif')
            run_game.run()
        if self.point == 3:
            self.window.fill(BLACK)
            run_game = SimpleGame(self.window, (0, 0), '噩梦模式迷宫.txt', '人物(小).gif')
            run_game.run()
        if self.point == 4:
            self.window.fill(BLACK)
            run_game = SimpleGame(self.window, (0, 0), '自定义迷宫.txt', '人物.gif')
            run_game.run()
        pygame.quit()  # 退出pygame


if __name__ == "__main__":
    game = TwoGame()
    game.run()

```

