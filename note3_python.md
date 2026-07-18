# 😻 p的python笔记📝

这是p的python笔记😊📖

python不需要头文件（有特例） 不需要语句末尾的`；`变量不需要声明类型

## 😘 print函数

### 1.print("string")

单引号也可以使用，用于区分和配对，比如：  

```bash
printf( " He said "good!" " )
```

是错误的，因为系统会自动认为`第1个引号`和`第2个`配对，而我们希望`第1个引号`和`第4个`配对，此时用单引号和双引号区分可解决这个问题

```bash
print( ' He said "good!" ' )
```

是正确的

也可以使用`\`来完成此功能,`\`的意思是：**后面的那个引号是字符串，你不要识别**

```bash
print( " He said \"Let\'s go!\" " )
```

也是正确的

**补充`\`的用法**：`\`表示转义，即`\`加上任何你不想被识别进去的符号，就可以被正常输出

---

### 2.换行

\n表示**在这里换行**

```bash
print( " Hello! \n Hi!" )
```

还有另种方法，每个print都默认重启一行

还有另另种方法：使用三个引号包裹文字，里面内容可以使用常规换行(enter什么的)

```bash
print(""" Hello
Hi""")
```

---

### 3.`+`和`，`的使用

#### 1. 空格识别规则

* 引号内：原样输出（如 "A B" 变成 A B）。
* 引号外：直接忽略（如 "A"   +   "B" 变成 AB）。
* 逗号 `,`：print 会在输出时自动补一个空格。

#### 2. 加号与逗号的区别

* 加号 +：严丝合缝拼接（如 "Java"+"Script" 变成 JavaScript）**两边必须都是字符串**，常用于拼接网址或将文本存入变量。
* 逗号 `,`：依次独立打印，带自动空格。文字和数字可混写。常用于终端快速查看结果。

#### 3. 推荐：f-string

现代 Python 最推荐的写法，既不用`+`也不用`,`所见即所得：

```bash
name = "小猫"
print(f"你好{name}") 
```

输出：你好小猫

---

## 😊 变量赋值

不需要声明变量类型，所见即所得

变量名由文字、数字、下划线组成，**甚至可以用中文**

  **优秀命名：**

* 下划线命名优先：user_age , user_gender

* 驼峰命名：UserAge , UserGender

**数据类型**：特别的None表示空值（要定义一个变量，但是暂时不知道值）

* type函数可以检查数据类型

```bash
type(不知道的数据)
<class'str'>
<class'int'>
<class'float'>
<class'bool'>
<class'NoneType'>
```

* 字符串索引："Hello"[0]就是H

---

## 🧮 运算

乘方：**

2的3次方：

```bash
2**3
```

**非内置函数需要导入函数库**：`math`

在开头写：

```bash
import math
```

然后就可以这样使用函数功能

```bash
math.函数名(...)
```

比如：

```bash
math.sin(1)
math.log2(8)
math.sqrt(4)
```

还支持很多，记得用变量把结果存起来

---

## 🙌 注释

用＃加内容，只管单行

快捷键：`ctrl`+`\`

## 🤗 一些函数

`len`函数不能用于int

---

## 🙌 Python的交互模式

### 1. 交互模式

* **聊天式运行**：无需新建 `.py` 文件，敲一行代码按回车，Python 就会立刻给出结果。
* **标志特征**：终端中出现三个大于号 `>>>` 即代表进入该模式。
* **退出方式**：输入 `exit()` 回车，或按 `Ctrl + Z`。
* **c/c++没有**

### 2. 核心区别与特点

* **对比文件模式**：命令行模式像写作文（一次性运行并保存），而交互模式像聊天（即时响应但关闭后代码消失）。
* **自动输出**：在交互模式下，输入数学表达式（如 `1+1`）无需写 `print()`，按回车会直接显示结果。

### 3. 什么时候用交互模式

一次性计算等

---

## 🤷‍♀️ input函数

举个例子：

```bash
user_age = input("请输入您的年龄:")
```

💡**注意input一律返回字符串**，但是可以转换类型

⚙️**转换类型**：要转换的类型 (真的可以转换的原数据)

比如：

```bash
int("666")
```

所以可以写：

```bash
int(input("请输入您的年龄："))
```

---

## ✌️ `条件语句`

语法：

```bash
if 条件 :
  执行语句1
  执行语句2
  ...
else:
  执行语句3
  ...
```

python**根据缩进判断每个语句归谁管**，不用写()也不用写{}

**比较运算符**：`==`,`!=`

**条件嵌套语句语法**：

```bash
if 条件 :
  执行语句1

elif 条件2:
  执行语句2

elif 条件3:
  执行语句3
```

注意不是else if是elif

**逻辑运算符**：`not`,`and`,`or`(按照优先级排序，当然括号可以改变优先级)

---

## 😽 数据结构：列表

```bash
shopping_list = ["键盘"，"键帽"]
```

注意列表是方括号

`方法`:和函数类似，这里简单区分调用方式，本质区分单开在下一节

* 函数： `函数名（对象）`

```bash
len(shopping_list)
```

* 方法：`对象.方法名（...）`

```bash
shopping_list.append("显示器")
```

列表和其他类型的区别：**列表是可变的**，举个例子,对于`字符串`：

```bash
s = "Hello"
print(s.upper())
```

首先，**这是方法不是函数**，其次，返回的是新的大写字符串，此时**s字符串没有变**，如果要更新s可以这样：

```bash
s = s.upper()
```

upper是全部元素转换为大写的方法

对于`列表`：

```bash
shopping_list = ["键盘"]
shopping_list.append("显示器")
print(shopping_list)
```

此时链表本身被改变了，append是添加元素的方法

**一些针对列表的内置`函数`**：

* max(某list)
* min(某list)
* sorted(某list)

**一些针对列表的内置`方法`**：

* 某list.append("某元素")
* 某list.remove("某元素")
  
---

## 🤩 函数与方法的本质区别

### 1. 核心定义与归属

* **函数（Function）**：独立存在的代码块。通过函数名直接调用，数据作为参数传入（如 `len(s)`）。
* **方法（Method）**：依赖对象存在的特殊函数。必须通过对象打点调用（如 `s.upper()`），是该对象的专属行为。

### 2. 其他语言的状况

* **Java / C#**：没有独立函数，所有代码必须写在类中，因此**只有方法**。
* **C 语言**：没有类和对象概念，因此**只有函数**。
* **Python / C++ / JS**：两者兼备。独立写的叫函数，写在类/对象内部的叫方法。

😭 其实p还是没有分清楚，先写这么多

---

## 🤩数据结构：字典

和列表一样，**字典也是可变的**，用于储存`键值对`,而`键`是用来查找`值`的，格式如下：

```bash
contacts = {}
```

这是空的字典，**注意字典是花括号表示**

```bash
contacts = {"小1"："18800000000"，
            "小2"："18700000000" }
```

这是存入键值对的字典

```bash
contacts["小1"]
```

这样就可以查到键"小1"的号码是"18800000000"

还需要注意`键`必须是不可变类型，即**`str`，`int`，`float`都可以作为`键`，但是`可变的列表`就不行**

**`元组`**是一个很像列表但不可变的数据结构，它可以作为`键`

```bash
tuple = ("键帽"，"键盘")
```

和`链表`的不同在于，`元组`是小括号,而且`元组`不可变，既然不可变，**增删对元组统统不能操作**

`元组`的好处在于，能作为键：

```bash
contacts = {("小1",23岁)："18800000000"，
            ("小1",22岁)："18700000000" }
```

好处很明显，考虑了多个人叫小1的情况

字典的**增加/更新**元素：

```bash
contacts["小4"] = "1900000000"
```

如果想知道某个键是否已经存在,以下操作会返回一个布尔值：

```bash
"小1" in contacts
```

删除一个键值对操作：

```bash
del contacts["小1"]
```

其他的可用方法：

* 字典名.keys()  **返回所有键**
* 字典名.values()  **返回所有值**
* 字典名.items()  **返回所有键值对**

---

## 🧐 for循环

```bash
for 变量名 in 可迭代对象：
    对每个变量做的事情
    ...
```

for遍历字典时，变量名位置返回键和值组成的元组，需要命两个名，就行下面这样：

```bash
temperature_dict = {"111":36.4, "112":36.6, "113":36.2}

for staff_id, temperature in temperature_dict.items():
    if temperature >= 38:
        print(staff_id)
```

### for循环结合range

#### 第一种

```bash
for i in range(5, 10):
    print(i)
```

i依次被赋值`左开右闭`区间的值

**为什么左开右闭**：因为`左开右闭`可以保证**右-左等于区间长度**

#### 第二种

```bash
for num in range(1, 10, 2):
    print(num)
```

括号内为(起始，结束，步长)

**如果range的括号里只放了一个值**，则默认起始为`0`，放入的是`结束值`

---

## 🤓 while循环

未知结束需要多少次

```bash
while 条件：
      行动
```

## 格式化字符串

### format

用于优雅拼接字符串，替代繁琐的字符串拼接

不用format的拼接(gpa需要转化为字符串保持+前后都是字符串)：

```bash
gpa_dict = {"小明":3.251, "小花":3.869, "小李":2.683,"小张":3.685}

for name, gpa in gpa_dict.items():
    print(name + "你好，你的当前绩点为：" + str(gpa))
```

显然(这里可能不显然)format版更加简洁，并且显然format可以自动转化数据类型拼接，不需要手动转

```bash
gpa_dict = {"小明":3.251, "小花":3.869, "小李":2.683,"小张":3.685}

for name, gpa in gpa_dict.items():
    print("{0}你好，你的当前绩点为：{1}".format(name, gpa))
```

{1},{0}表示打印format里第几位的数据

还可以保留小数：

```bash
gpa = 3.251
# :.2f 保留2位小数
print("绩点：{:.2f}".format(gpa))
# 输出：绩点：3.25
```

### f-string

```bash
gpa_dict = {"小明":3.251, "小花":3.869, "小李":2.683, "小张":3.685}
for name, gpa in gpa_dict.items():
    # f开头，{}内直接写变量，自动类型转换
    print(f"{name}你好，你的当前绩点为：{gpa}")
```

## ⚙️ 函数

```bash
def 函数名(参数1，参数2)：
    操作1
    操作2
    ...
```

注意函数内定义的`局部变量`，出了函数系统都认为它不存在

如果想要存住函数的结果需要return，没有return的函数默认return None

```bash
def 函数名(参数1，参数2)：
    操作1
    操作2
    ...
    return 某
```

此时在外部调用函数并赋值，会得到return的结果

```bash
retult = sum([1,3,5])
```

## 🐾 模块

就是不太常用的函数，也算内置，需要结合类似头文件的东西引入

**引入模块**：

* import语句
  
  ```bash
  import 模块名字
  import statistic
  ```

  调用：

  ```bash
  模块名字.变量名
  statistic.median([19,-5,36])
  ```

* from...import...语句
  
  ```bash
  from statistics import median, mean
  median([19,-5,36])
  mean([19,-5,36])
  ```

  显然第二种在调用时候更简洁

* from...import*
  
  ```bash
  from statistics(模块名) import *

  print(median([19, -5, 36]))
  print(mean([19, -5, 36]))
  ```

  不推荐使用，因为用不到的所有函数和变量都会被引入

除了官方的模块，第三方的模块也可以被引入，同样的引入方法，**引入之前需要先安装**在终端里输入：

```bash
pip install
```

`pypi.org`可以搜素第三方库

---

## 面向对象

面向对象编程 (OOP)，是一种将程序逻辑组织为“对象”的编程范式，核心在于**数据（属性）** 与**逻辑（行为）** 的绑定，简单介绍概念：

### 1. 类 (Class)

有点像结构体

* **定义：** 定义了一类事物共有的属性（数据）和行为（方法）。
* **例子：** 汽车是一个类，它定义了汽车都有品牌、颜色，且都能启动、刹车。

下面是定义属性，第一个参数被占用，用于表示对象自身，约定俗成为self

```bash
class CuteCat:
    def __init__(self, cat_name, cat_age, cat_color):
        self.name = cat_name
        self.age = cat_age
        self.color = cat_color

cat1 = CuteCat("Jojo", 2, "橙色")
print(f"小猫{cat1.name}的年龄是{cat1.age}岁，花色是{cat1.color}")
```

下面是方法：

```bash
class CuteCat:
    def __init__(self, cat_name, cat_age, cat_color):
        self.name = cat_name
        self.age = cat_age
        self.color = cat_color

    def speak(self):
        print("喵" * self.age)

    def think(self, content):
        print(f"小猫{self.name}在思考{content}...")

cat1 = CuteCat("Jojo", 1, "橙色")
cat1.think("现在去抓沙发还是去撕纸箱")
```

spaek方法：小猫的年龄*喵，表现为小猫有多大就会喵几声

上面代码的输出为：

```bash
小猫Jojo在思考现在去抓沙发还是去撕纸箱...
```

在代码末尾加上 cat1.speak()，会输出：

```bash
喵
```

可以总结格式：

```bash
class 类名:
    # 1. 构造方法（初始化函数，必写self）
    def __init__(self, 参数1, 参数2, ...):
        # 绑定实例属性：self.属性名 = 接收的参数
        self.属性1 = 参数1
        self.属性2 = 参数2

    # 2. 自定义实例方法（第一个参数永远是self）
    def 方法名(self, 形参1, 形参2...):
        # 方法内可用 self.属性 访问对象自身数据
        执行语句
```

注意类的规范命名是驼峰命名法

### 2. 封装 (Encapsulation)

* **定义：** 将数据和操作数据的方法捆绑在一起，并**隐藏内部实现细节**，只暴露必要的接口。
* **目的：** 保护数据安全，防止外部随意篡改，降低模块间耦合。
* **核心：** 内部逻辑隐藏，外界只需用接口。

### 3. 继承 (Inheritance)

* **定义：** 允许创建一个新类（子类）来继承已有类（父类）的特征和行为。
* **目的：** 代码复用，建立事物间的层级关系。
* **例子：** “电动汽车”类可以继承“汽车”类，自动拥有品牌和启动行为，并增加“充电”特有功能。

用小猫和人类同属哺乳动物大类举例

```bash
# 父类：哺乳动物 Mammal
class Mammal:
    def __init__(self, name, sex):
        self.name = name
        self.sex = sex
        self.num_eyes = 2

    def breathe(self):
        print(self.name + "在呼吸...")

    def poop(self):
        print(self.name + "在拉屎...")

# 子类：人类 Human，继承 Mammal
class Human(Mammal):
    def __init__(self, name, sex):
        # 调用父类的构造方法
        super().__init__(name, sex)
        self.has_tail = False

    def read(self):
        print(self.name + "在阅读...")

# 子类：猫咪 Cat，继承 Mammal
class Cat(Mammal):
    def __init__(self, name, sex):
        # 调用父类的构造方法
        super().__init__(name, sex)
        self.has_tail = True

    def scratch_sofa(self):
        print(self.name + "在抓沙发...")
```

注意：**优先看子类有没有自己的方法，没有就调用父类**(注意到上面的代码里小猫有自己的拉屎方法)

super表示**继承父类的属性或方法**，继承后也**可以创建自己的**

### 4. 多态 (Polymorphism)

* **定义：** 指“多种形态”。即同一个接口，在不同对象上有不同的实现方式。
* **目的：** 增强代码的灵活性和扩展性。
* **例子：** 无论是“轿车”还是“卡车”，调用“启动”方法时，各自的行为表现不同（轿车轻快启动，卡车轰鸣启动），但外界调用方式完全一致。

---

## 文件

### 1. 路径

#### 1. 核心差异：路径分隔符与根目录

| 特性 | Windows 系统 | Linux / macOS 系统 |
| :--- | :--- | :--- |
| **分隔符** | 反斜杠 `\` | 正斜杠 `/` |
| **根目录** | 驱动器盘符（如 `C:`） | 统一根目录（`/`） |

#### 2. 模拟目录树结构

以跨平台通用的逻辑表示：

* **根 (Root)**
  * **Users**
    * **`Username`**
      * **Documents**
        * `file.txt`

#### 3. 路径表示方法对比

假设我们要访问 `file.txt`，且当前目录为 `Username`。

##### 绝对路径 (完整地址)

* **Windows:** `C:\Users\Username\Documents\file.txt`
* **Linux/macOS:** `/Users/Username/Documents/file.txt`

##### 相对路径 (当前位置出发)

* **Windows:** `(.\)Documents\file.txt`
* **Linux/macOS:** `(./)Documents/file.txt`

##### 特殊符号 (通用)

* `.` ：代表当前目录。
* `..` ：代表上一级目录。
  * *例如，从 `Documents` 目录返回 `Username` 目录：*
    * **Windows:** `..\`
    * **Linux/macOS:** `../`

---

使用 `open()` 函数打开文件，通常编码格式为 `utf-8`

* **语法：** `open("./data.txt", "r", encoding="utf-8")`
  
  r表示只读模式，w表示只写模式，如果没有说明系统默认r

### 2. 读取文件的方法

读取文件主要有三种方法，根据需求选择最合适的一种：

| 方法 | 功能描述 |
| :--- | :--- |
| **read()** | 读取并返回文件的全部内容（字符串形式） |
| **readline()** | 每次读取并返回文件的一行内容（字符串形式） |
| **readlines()** | 读取全部内容，并返回由每行内容组成的列表 |

### 注意事项

* **read()：** 连续调用时，第二次读取会返回空字符串，因为读取指针已经移动到文件末尾
  
```bash
# 以只读模式打开当前目录下的 data.txt 文件，指定编码utf-8
f = open("./data.txt", "r", encoding="utf-8")

# 第一次read：读取文件全部内容
print(f.read())
# 第二次read：文件指针已经到末尾，读取到空字符串
print(f.read())
```

* **read(n)：** 可以传入数字 `n`，表示读取前 `n` 个字节的内容

```bash
f = open("./data.txt", "r", encoding="utf-8")

# 读取前10个字符
print(f.read(10))
# 接着读取接下来的10个字符（第11~20位）
print(f.read(10))
```

* **readline()：** 读取时会包含换行符

```bash
f = open("./data.txt", "r", encoding="utf-8")

# 读取文件第一行内容
print(f.readline())
# 读取文件下一行内容（第二行）
print(f.readline())
```

* **readline()：** 结合`for`循环

```bash
# 打开文件，只读模式，指定utf-8编码
f = open("./data.txt", "r", encoding="utf-8")
# 先读取第一行
line = f.readline()
# 判断是否读到文件末尾（空字符串代表读完）
while line != "":
    print(line)
    # 读取下一行，更新line变量
    line = f.readline()
```

* **readlines()：** 结合`for`循环

```bash
f = open("./data.txt", "r", encoding="utf-8")

# readlines() 读取文件所有行，存入列表，每行作为列表的一个元素
lines = f.readlines()

# 循环遍历列表中的每一行文本
for line in lines:
    print(line)
```

### 3. 关闭文件与资源释放

操作完成后必须关闭文件以释放系统资源

* **传统方式：** 使用 `f.close()` 手动关闭
  
```bash
# 打开文件
f = open("./data.txt")
# 文件操作
print(f.read())
# 手动关闭文件释放资源
f.close()
```

* **推荐方式：** 使用 `with open(...) as f:` 语句。
  * **优点：** 离开 `with` 代码块后，系统会自动帮你关闭文件并释放资源，更加安全便捷。

```bash
# with会自动处理文件打开与关闭，无需手动写close()
with open("./data.txt") as f:
    # 文件操作代码缩进在with内部
    print(f.read())
```

---

### 4. 写入文件的方法

首先把`r`换成`w`，不举例了后面会有，但是要注意如果**用`w`打开一个已经有内容的文件，那个文件里的内容会被清空**，要三思！

**如果不想被清空**可以用`a`表示附加模式，注意对于`w`和和`a`如果传入文件不存在会帮你创建一个新的，而`r`传入文件不存在会报错

但是无论是`w`还是`a`都不支持读入文件，如果想要读入之后再写，可以用`r+`模式

接下来是write操作，注意写的时候(w or a)不支持read：

```bash
# a模式：追加写入，在文件末尾新增内容，文件不存在则自动创建
with open("./data.txt", "a", encoding="utf-8") as f:
    f.write("Hello!\n")
    f.write("Yooooo")
```

不难发现默认不换行，换行符要自己打

---

## 😡 报错处理

报错有很多类型，我们可以捕捉异常，例如

```bash
try:
    user_weight = float(input("请输入您的体重（单位：kg）："))
    user_height = float(input("请输入您的身高（单位：m）："))
    user_BMI = user_weight / user_height ** 2
except ValueError:
    print("输入不为合理数字，请重新运行程序，并输入正确的数字。")
except ZeroDivisionError:
    print("身高不能为零，请重新运行程序，并输入正确的数字。")
except:
    print("发生了未知错误，请重新运行程序。")
else:
    print("您的BMI值为：" + str(user_BMI))
finally:
    print("程序结束运行。")
```

先写有可能产生错误的代码，然后写产生什么错误时运行什么（未知错误类型但是报错了运行什么），还有不产生错误时运行什么，最后finally写的无论前面发生什么都会执行

---

## 代码测试

常用assert断言

```bash
assert 这里写你认为应该为true的表达式
```

一旦你认为应该为true的表达式不为true，停止运行并提示AssertionError断言错误，然后程序直接终止

**测试库**：`unittest`

```bash
import unittest
```

测试代码一般放到独立文件里

假如文件my_calcuilator.py实现代码如下

```bash
def my_adder(x, y):
    return x + y
```

测试文件test_my_calculator.py,假如**测试文件和被测试文件位于同一文件夹下**，语法如下

```bash
# 导入Python内置单元测试框架unittest
import unittest
# 从my_calculator.py文件中导入自定义加法函数my_adder
from my_calculator import my_adder

# 创建测试类，必须继承unittest.TestCase（所有测试用例的父类）
class TestMyAdder(unittest.TestCase):
    # 测试用例方法：方法名必须以test_开头，框架才会自动执行
    # 测试场景：正数 + 正数
    def test_positive_with_positive(self):
        # self.assertEqual(实际结果, 预期结果)：断言方法
        # 作用：判断my_adder(5,3)的返回值是否等于8，不等则测试失败
        self.assertEqual(my_adder(5, 3), 8)

    # 测试用例：负数 + 正数
    def test_negative_with_positive(self):
        # ... 此处省略具体断言代码，可自行补充示例
        # 示例：self.assertEqual(my_adder(-2, 5), 3)
        ...
```

写好测试用例后，在终端输入

```bash
python -m unittest
```

终端会返回运行了几个测试，测试通过终端返回`.`不通过返回`F`

一些测试的方法：

* assertEqual(A, B) 相当于assert A == B
* assertTrue(A) 相当于assert A is True
* assertIn(A, B) 相当于assert A in B
* assertNotEqual(A, B) 相当于assert A != B
* assertFalse(A) 相当于assert A is False
* assertNotIn(A, B) 相当于assert A not in B

assertTrue 是万能方法，但是更具有针对性的方法报错会更具体

Setup方法：不重复创建变量

---

## 🤓 高阶函数

把函数作为参数传入另一个号函数

```bash
# 写法1：传入函数本身（不加括号）✅ 正确用法
calculate_and_print(3, calculate_square)

# 写法2：传入函数调用后的返回值（带括号）❌ 会报错
# calculate_and_print(3, calculate_square())
# 报错原因：calculate_square()缺少必要参数n，程序运行到这一行就先执行函数，无参数直接抛出异常
```

匿名函数：

```bash
# 自定义打印，两侧加竖线
def print_with_vertical_bar(res):
    print(f"|{res}|")

# 接收数值、计算函数、打印函数
def calculate_and_print(n, calc, show):
    res = calc(n)
    show(res)

# 7乘5，再用竖线格式打印
calculate_and_print(7, lambda num: num * 5, print_with_vertical_bar)
```

也可以定义好被直接调用

```bash
# 双参数lambda直接传2和3求和
(lambda num1, num2: num1 + num2)(2, 3)
```

匿名函数适合一次性调用，但是只能写一行操作，不支持写多行

---

完了！
