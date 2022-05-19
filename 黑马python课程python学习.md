# 黑马python课程python学习

## ubuntu16.04 安装中文输入法 谷歌拼音

```shell
sudo apt-get install language-pack-zh-hans
sudo apt-get install fcitx-googlepinyin 
```

打开设置中的语言设置，将键盘输入法改为**fcitx**，如图所示：

![image-20220502142227895](C:\Users\28647\AppData\Roaming\Typora\typora-user-images\image-20220502142227895.png)

重启ubuntu

打开终端，输入：

```shell
fcitx-configtool 
```

点加号找到谷歌拼音，如图所示：

![image-20220502142419461](C:\Users\28647\AppData\Roaming\Typora\typora-user-images\image-20220502142419461.png)

安装后通过 **CTRL + 空格**切换中英文输入法

## pycharm使用技巧

- 关闭除当前文件的其他文件：点击当前文件界面右键选择**close other tabs**

![image-20220501163352260](C:\Users\28647\AppData\Roaming\Typora\typora-user-images\image-20220501163352260.png)

- 调试快捷键 **shift + f9**   单步执行 **f8**
- 运行快捷键 **ctrl+shift+f10**
- **tab**增加缩进，**shift+tab**取消缩进
- **ins**切换鼠标光标
- **ctrl+/**注释与解除注释
- **F8 step over 可以单步执行代码。会把函数调用看作是一行代码执行**
- **F7 step into 可以单步执行代码，如果是函数，会进入函数内部**
- 在**函数调用位置**，使用快捷键 `ctrl+q`可以查看函数的说明信息
- 在函数没有注释的前提下 给函数添加注释的快捷操作：**点击函数名后点击黄色小灯泡，后点击 `insert a documentation string stub`**
- **在#后面跟上 TODO，用于标记需要做的工作，虽然也是注释，但是高亮显示，并且可以快速跳转**
- 一次性修改某变量在程序中的名字：**选中该变量右键->Refactor->Rename->Rename code occurrences。快捷键：shift f6 修改后回车**

## python理论学习

**计算机不能直接理解任何除机器语言以外的语言，**所以必须要把程序员所写的语言翻译成机器语言，计算机才能执行程序。**将其他语言翻译成机器语言的工具，被称为编译器**

编译器翻译的方式有两种：一种是**编译**，另一种是**解释**。两种方式之间的区别在于**翻译时间点的不同**。当编译器**以解释方式运行的时候**，称之为**解释器**

![image-20220430115016819](C:\Users\28647\AppData\Roaming\Typora\typora-user-images\image-20220430115016819.png)

- **编译型语言**：程序再执行之前须要一个专门的编译过程，把程序编译成机器语言的文件，运行时不需要重新翻译，直接使用编译的结果。程序执行效率高，依赖编译器，跨平台性差。例如：c，c++
- **解释型语言**：解释性语言编写的程序不需要预先编译，以文本方式存储程序代码，会将代码一句一句直接运行。在发布程序时，看起来省了道编译工序，但是在运行程序的时候，必须先解释再运行。

**编译型语言和解释型语言对比**

- **速度**--编译型语言比解释型语言执行速度块
- **跨平台性**--解释型语言比编译型语言跨平台好

**终端下执行python**

- 使用 `gedit`编辑 `01_hellopython.py`，内容如下：

~~~python
print("hello world")
print("hello python")
~~~

- 在终端中执行以下命令：

~~~shell
zcb@zcb-virtual-machine:~/python_study/know_about_python$ python 01_hellopython.py 
hello world
hello python
~~~

**交互式运行Python程序**

- 直接在终端中运行解释器，而不输入要执行的文件名
- 在python的 `shell`中直接输入python的代码，会立即看到i程序执行的结果
- **优点**：使用于学习/验证python语法或者局部代码
- **缺点**：代码不能保存；不适合运行太大的程序
- 退出解释器的代码：

~~~shell
exit()
~~~

- 按 `ctrl+d`也可以退出

~~~shell
zcb@zcb-virtual-machine:~$ python
Python 2.7.12 (default, Mar  1 2021, 11:38:31) 
[GCC 5.4.0 20160609] on linux2
Type "help", "copyright", "credits" or "license" for more information.
>>> 1.01**365
37.78343433288728
>>> print("hello world")
hello world
>>> exit()
zcb@zcb-virtual-machine:~$ 
~~~

**IPython**

- 是一个**交互式shell**，比默认的 `python shell`好用很多
- 支持自动补全
- 支持自动缩进
- 支持 `bash shell`命令
- 内置诸多函数和功能
- python2的解释器为ipython
- python3的解释器为ipython3
- 退出解释器分为两种 第一种 `ctrl + d`
- 第二种：

~~~shell]
exit     不加括号
~~~

- 安装**ipython、ipython3**

~~~shell
sudo apt install ipython
sudo apt install ipython3
~~~

**第一次用pycharm打开项目**

- 直接点击 **open**按钮，选择项目路径
- 打开之后会在目录下新建一个 `.idea`的目录，用于保存 **项目相关的信息**，例如： **解释器版本、项目包含文件**等等
- 最开始打开时，右上方的运行键是灰色的，需要在要运行的文件上点击鼠标右键 选择**Run "目标文件.py"**，之后就可以使用

**下载/更新pycharm**

- 下载软件tar包后

~~~shell
sudo tar -zxvf pycharm-community-2022.1.tar.gz 
sudo mv pycharm-community-2022.1 /opt
cd /opt
cd pycharm-community-2022.1/
cd bin
./pycharm.sh 
~~~

**重装最新python**

- 因为最新版的pycharm不支持python3.5解释器，因此需要重新安装最新的python3版本，此处安装的是3.10.4版本，具体的操作如下：

在官网https://www.python.org/downloads/source/下载最新的python3.10.4版本，选择**Download XZ compressed source tarball**格式的包，如图所示：

![image-20220430205706145](C:\Users\28647\AppData\Roaming\Typora\typora-user-images\image-20220430205706145.png)

~~~

~~~

- 在终端中依次执行以下指令：

~~~shell
sudo mkdir Python3.10.4
sudo mv Python-3.10.4.tar.xz Python3.10.4/
cd Python3.10.4/
sudo tar -xvf Python-3.10.4.tar.xz 
cd Python-3.10.4/
sudo ./configure 
sudo make
sudo make install
~~~

**注释**

- **单行注释 **：以 `#`开头， `#`右边的所有东西被当作说明性文字，而不是真正要执行的程序。**可以位于代码上方 或者代码的后面**
- **小技巧**：当当前的注释格式不规范时，pycharm会在注释下显示灰色波浪线，此时可以全选该注释后右键 选择 **show context actions**后选择**reformat the file **可以自动调整注释格式

![image-20220430203739559](C:\Users\28647\AppData\Roaming\Typora\typora-user-images\image-20220430203739559.png)

![image-20220430203801245](C:\Users\28647\AppData\Roaming\Typora\typora-user-images\image-20220430203801245.png)

~~~python
# 这是第一个注释
print("hello hello")

print("hello world")  # 这是第二个注释
~~~

- **调试时遇到ModuleNotFoundError: No module named  _ctypes**的解决办法

  ~~~shell
  sudo apt install libffi-dev -y
  cd /usr/local/Python3.10.4/Python-3.10.4
  sudo ./configure
  sudo make
  sudo make install
  ~~~

- **多行注释**：要在python中使用多行注释，可以用 **一对连续的三个引号（单引号和双引号都可以）**表示

  ~~~python
  # 这是第一个注释
  print("hello hello")
  
  """
  这是一个多行注释
  11111
  22222
  注释结束
  """
  
  print("hello world")  # 这是第二个注释
  ~~~

- **pycharm 的注释快捷键**：**全选文字后 按 `ctrl+/`

**算数运算符**

| 运算符 |  描述  |           demo           |
| :----: | :----: | :----------------------: |
| **+**  |   加   |         10+20=30         |
| **-**  |   减   |        10-20=-10         |
| *****  |   乘   |        10*20=200         |
| **/**  |   除   |        10/20=0.5         |
| **//** | 取整除 | 返回商的整数部分，9//4=2 |
| **%**  | 取余数 |   返回商的余数，9%4=1    |
| ****** |   幂   |  又称次方，乘方，2**3=8  |

**交互式练习算数运算符**

~~~python
In [1]: 10+20
Out[1]: 30

In [2]: 10-20
Out[2]: -10

In [3]: 10*20
Out[3]: 200

In [4]: 10/20
Out[4]: 0.5

In [5]: 9//4
Out[5]: 2

In [6]: 9%4
Out[6]: 1

In [7]: 2**3
Out[7]: 8
~~~

- 在python中 `*`运算符还可以用于字符串计算，计算结果就是字符串反复输出指定次数

~~~python
In [9]: "-" * 10
Out[9]: '----------'
~~~

**算术运算符的优先级**

- 和数学中的运算符的优先级一致，在python中进行数学计算时，同样也是：

  - **先乘除后加减**
  - 同级运算是**从左至右**计算
  - 可以使用 `（）`**调整计算**优先级

- 以下表格的算数优先级由高到低顺序排序

  |  运算符  |          描述          |
  | :------: | :--------------------: |
  |    **    |    幂（最高优先级）    |
  | * / % // | 乘，除，取余数，取整数 |
  |   + -    |       加法，减法       |

**交互式ipython3打开时遇到的问题**

- **问题描述**

~~~shell
zcb@zcb-virtual-machine:~$ ipython3
Traceback (most recent call last):
  File "/usr/bin/ipython3", line 4, in <module>
    from IPython import start_ipython
ModuleNotFoundError: No module named 'IPython'
~~~

- 解决办法：

~~~shell
sudo gedit/usr/bin/ipython3
~~~

​     将内容改为下图：

![image-20220501121043665](C:\Users\28647\AppData\Roaming\Typora\typora-user-images\image-20220501121043665.png)

**变量定义**

- 在python中，**每个变量在使用前都必须赋值，变量赋值后该变量才会被创建**
- **等号 `(=)`用来给变量赋值**
  - `=`左边是一个变量名
  - `=`右边是存储在变量中的值
  - **变量名=值**

```python
In [1]: qq_number="123456"

In [2]: qq_password="123"

In [3]: qq
qq_number    qq_password  

In [3]: qq_number
Out[3]: '123456'

In [4]: qq
qq_number    qq_password  

In [4]: qq_password
Out[4]: '123'
```

```python
# 定义一个变量记录QQ帐号
qq_numnber = "1234567"
# 定义一个变量记录QQ密码
qq_password = "123"

# 注意：在使用解释起执行python程序的时候 不能直接使用变量名在控制台输出变量的信息
# 如果希望通过解释器的方式，输出变量的内容，需要使用print函数
print("qq_number")
print("qq_password")
```

- 可以使用 **其他变量计算的结果定义当前变量**

```python
# 定义苹果单价
price = 8.5
# 苹果质量
wight = 7.5
# 计算金额
money = price * wight

print(money)
```

**变量的类型**

- **在python中，定义变量时不需要指定变量的类型。在运行的时候，python解释器会根据赋值语句等号右侧的数据，自动推导出变量中保存数据的准确类型**

```python
"""
姓名： 小明
年龄： 18岁
性别： 男
身高： 1.75米
体重：75公斤
"""
# 在python中，定义变量时不需要指定变量的类型
# 在运行的时候，python解释器会根据赋值语句等号右侧的数据，自动推导出变量中保存数据的准确类型
# str 表示是一个字符串
name = "小明"
# int 表示是一个整数类型
age = 18
# bool 表示是一个布尔类型 真 True 假 False
gender = True
# float表示是一个小数类型，浮点数
hight = 1.75
wight = 75.0
```

- 数据类型可以分为 **数字型** 和 **非数字型**
- 数字型
  - 整形 `int`
  - 浮点型 `float`
  - 布尔型 `bool`
    - 真 `True`  `非0数`  --**非0即真**
    - 假 `False` `0`
  - 复数型 `complex`
- 非数字型
  - 字符串
  - 列表
  - 元组
  - 字典

- ipython中常用的数据类型查看函数 **type**

```python
In [1]: name = "xiaoming"

In [2]: age = 18

In [3]: hight = 1.75

In [4]: wight = 75

In [5]: gender = True

In [6]: type(name)
Out[6]: str

In [7]: type(age)
Out[7]: int

In [8]: type(hight)
Out[8]: float

In [9]: type(wight)
Out[9]: int

In [10]: type(gender)
Out[10]: bool
```

**不同类型变量之间的计算**

- 数字型变量之间的计算

  - 在python 中，两个数字型变量是可以直接进行数字运算符的
  - 如果变量是 `bool`型，在计算时
    -  `True`对应的数字是 `1`
    - `False`对应的数字是 `0`

  ```python
  In [8]: i = 10
  
  In [9]: f = 10.5
  
  In [10]: b = True
  
  In [11]: i + f
  Out[11]: 20.5
  
  In [12]: i + b
  Out[12]: 11
  
  In [13]: f - b
  Out[13]: 9.5
  
  In [14]: i * f
  Out[14]: 105.0
  ```

- **字符串变量之间 使用 + 进行拼接 **

  ```python
  In [16]: last_name = "zhang"
  
  In [17]: first_name = "san"
  
  In [18]: first_name + last_name
  Out[18]: 'sanzhang'
      
  In [19]: last_name + first_name
  Out[19]: 'zhangsan'
  ```

- **字符串变量可以和整数使用*重复拼接相同的字符串**

  ```python
  In [20]: "-" * 50
  Out[20]: '--------------------------------------------------'
  In [21]: (last_name + first_name) * 10
  Out[21]: 'zhangsanzhangsanzhangsanzhangsanzhangsanzhangsanzhangsanzhangsanzhangsanzhangsan'
  ```

- **除了上述的两种字符串和数字型变量计算方法之外，两者之间不能进行其他的计算**

  ```python
  In [23]: x = 10
  
  In [24]: x + first_name
  ---------------------------------------------------------------------------
  TypeError                                 Traceback (most recent call last)
  <ipython-input-24-b713358c07cd> in <module>()
  ----> 1 x + first_name
  
  TypeError: unsupported operand type(s) for +: 'int' and 'str'
  ```

**变量的输入**

- 所谓 **输入**，就是 **用代码获取**用户通过 **键盘**输入的信息

- 在python中，如果要获取用户在 **键盘**上输入的信息，需要用到 `input`函数
- 在pycharm中 `input`的结果都是字符串
- 在ipython3中 `input`的结果是任意变量类型

- `input`函数实现键盘输入

  - 语法如下：

    ```python
    变量 = input ("提示信息：")
    ```

    ```python
    In [30]: password = input ("情输入变量内容：")
    情输入变量内容：123456
    
    In [31]: type(password)
    Out[31]: int
    
    In [32]: password_str = input ("情输入变量内容：")
    情输入变量内容："123456"
    
    In [33]: type(password_str)
    Out[33]: str
    
    In [34]: password = input ("情输入变量内容：")
    情输入变量内容：1234.567
    
    In [35]: type(password)
    Out[35]: float
    
    In [36]: password = input ("情输入变量内容：")
    情输入变量内容：True
    
    In [37]: type(password)
    Out[37]: bool
    ```

    - 注意：课程中说函数 `input`的输出都是字符串，这种说法在现在是当前的交互式ipython3中是错误的，**ipython3中函数 `input`的输出可以是任意类型的变量，可以根据输入时的内容改变**
    - 注意：**在pycharm中 `input`的输出都是字符串**

**变量类型转换函数**

|      函数      |        说明         |
| :------------: | :-----------------: |
|  **int（x）**  |  将x转换成一个整数  |
| **float（x）** | 将x转换成一个浮点数 |

```python
In [39]: hight = input ("请输入身高：")
请输入身高：176

In [40]: type(hight)
Out[40]: int
In [41]: hight = float (hight)
In [42]: type(hight)
Out[42]: float

In [43]: hight = int(hight)

In [44]: type(hight)
Out[44]: int
In [47]: ps = int ("123")

In [48]: type(ps)
Out[48]: int

In [49]: ps = float ("123.5")

In [50]: type(ps)
Out[50]: float
```

```python
# 输入苹果的单价
price_str = input("请输入苹果的单价：")
price = float (price_str)
# 输入苹果的质量
wight_str = input("请输入苹果的质量：")
wight = float(wight_str)
# 计算苹果的价格
money = price * wight

print(money)
```

```python
# 输入苹果的单价
price = float (input("请输入苹果的单价："))
# 输入苹果的质量
wight = float(input("请输入苹果的质量："))
# 计算苹果的价格
money = price * wight

print(money)
```

```python
# 计算苹果的价格
money = float(input("请输入苹果的单价：")) * float(input("请输入苹果的质量："))
print(money)
```

**变量的格式化输出**

-  `%`被称为 **格式化操作符**，专门用于处理字符串中的格式
- 包含 `%`的字符串，被称为**格式化字符串**
- `%`和不同的**字符**连用，**不同类型的数据**需要使用**不同的格式化字符**

| 格式化字符 |                             含义                             |
| :--------: | :----------------------------------------------------------: |
|   **%s**   |                            字符串                            |
|   **%d**   | 有符号的十进制整数，**%06d**中6表示输出的整数显示位数，0表示不到6位时0补全，超过6位则正常输出 |
|   **%f**   |           浮点数，**%.02f**表示小数点后只显示两位            |
|   **%%**   |                            输出 %                            |

- 语法格式如下：

  ```python
  print ("格式化字符串" % 变量1)
  print ("格式化字符串" % (变量1，变量2...))
  ```

```python
# 定义字符串变量 name 输出  我的名字叫 小明，请多关照
name = "大小明"
print("我的名字叫%s，请多关照" % name)

# 定义整形变量 student_num，输出 我的学号是 000001
student_num = 100777
print("我的学号是 %06d" % student_num)

# 定义小数 price wight money
# 输出 苹果单价 9.00 元/斤 购买了 5。00斤 共花费了 45.00元
price = 9.00
wight = 5.00
money = price * wight
print("苹果单价 %.02f 元/斤 购买了 %.02f斤 共花费了 %.02f元" % (price, wight, money))

# 定义一个小数 输出其百分比表达式
scale = 0.80
print("当前百分比为：%.02f%%" % (scale * 100))
```

**变量的命名**

**标示符**：是程序员定义的**变量名**，**函数名**，标识符需要有**见名知义**的效果，**区分大小写**

**标示符的要求**标示符可以由**字母、下划线、数组**组成，但是标识符**不能以数字开头、不能与关键字重名**

**关键字**：是在python内部已经使用的标识符，具有特殊的功能于含义，开发者**不允许定义和关键字相同的名字的标示符**

**查看 `python`中的关键字**

~~~python
In [1]: import keyword
In [2]: print(keyword.kwlist)
['False', 'None', 'True', 'and', 'as', 'assert', 'break', 'class', 'continue', 'def', 'del', 'elif', 'else', 'except', 'finally', 'for', 'from', 'global', 'if', 'import', 'in', 'is', 'lambda', 'nonlocal', 'not', 'or', 'pass', 'raise', 'return', 'try', 'while', 'with', 'yield']
~~~

**课程讲解的变量命名方法**

- 在定义变量时，为了保证代码格式， `=`的左右应该**各保留一个空格**
- 在 `python `中，如果**变量名**需要由**两个、多个单词**组成时，可以按照以下方式命名：
  - 每个单词都使用小写字母
  - 单词与单词之间使用 `_`**下划线**连接

**驼峰命名法**

- **小驼峰命名法**：第一个单词以小写字母开始，后续单词的首字母大写
- **大驼峰命名法**：每一个单词的首字母都采用大写字母

**if语句的基本语法**

在 `python`中，**if语句**就是用来进行判断的：

```python
if 要判断的条件
	条件成立时，要做的事情
	.....
else
    条件不成立时，要做的事情
	.....	
```

**注意**：代码的缩进为一个 `tab`键，或者**4**个空格--**建议使用空格**；在开发过程中，**Tab和空格不要混用**

```python
# 定义一个年龄变量 从控制台输入年龄大小
age = int(input("请输入您的年龄："))
# 判断年龄是否大于 18
if age >= 18:
    # 当年龄大于18时执行的程序
    print("你已经成年 欢迎来网吧玩耍")
else:
    # 当年龄小于18时执行的程序
    print("你还未满18岁，回家写作业吧")
```

**比较运算符**

| 运算符 |                             描述                             |
| :----: | :----------------------------------------------------------: |
| **==** | 检查两个操作数的值**是否相等**，如果是，则条件成立，返回 `True` |
| **!=** | 检查两个操作数的值**是否不相等**，如果是，则条件成立，返回 `True` |
| **>**  | 检查左操作数的值**是否大于**右操作数的值，如果是，则条件成立，返回 `True` |
| **<**  | 检查左操作数的值**是否小于**右操作数的值，如果是，则条件成立，返回 `True` |
| **>=** | 检查左操作数的值**是否大于等于**右操作数的值，如果是，则条件成立，返回 `True` |
| **<=** | 检查左操作数的值**是否小于等于**右操作数的值，如果是，则条件成立，返回 `True` |

**逻辑运算**

- 在程序开发中，通常**在判断条件时，需要同时判断多个条件**

- 只有多个条件满足时，才能执行后续代码，这个时候需要使用到**逻辑运算符**

- **逻辑运算符**可以把**多个条件**按照**逻辑**进行**连接**，变成**更复杂的条件**

- python中的**逻辑运算符**包括：**与and/或or/取反not 三种**

  **and与**

  - ```python
    条件1 and 条件2
    ```

  - 两个条件同时满足，返回 `True`

  - 只要 一个不满足，就返回 `False`

  **or或**

  - ```python
    条件1 or 条件2
    ```

  - 两个条件只要满足一个，返回 `True`

  - 两个条件都不满足，返回 `False`

  **not取反**

  - ```python
    not 条件
    ```

  - 条件成立时，结果取反不成立

  - 条件不成立时，结果取反成立

```python
# 创建一个变量，记录年龄
age = int(input("请输入您的年龄："))
# 判断该年龄是否为人类正常年龄
if age >= 0 and age <= 120:
    print("年龄正确")
else:
    print("年龄错误")

# 创建两个分别用于存储 c语言和python成绩的变量
python_score = int(input("请输入您的python成绩："))
c_score = int(input("请输入您的 c语言成绩："))
# 判断两门课程的成绩是否大于60 有一门大于60即为合格
if python_score >= 60 or c_score >= 60:
    print("您的成绩合格，恭喜")
else:
    print("您的成绩不合格，请继续努力")

# 定义一个布尔变量 判断是否为本公司员工
is_employee = True
if not is_employee:
    print("非本公司员工 请勿入内")
```

**elif**

- 在开发中，使用 `if`可以**判断条件**，使用 `else`可以处理**条件不成立**的情况，但是，如果希望**再增加一些条件，条件不同，需要执行的代码也不相同**时，就可以使用 `elif`
- `elif`的应用场景是：**同时判断多个条件，所有的条件都是平级的**
- 语法格式如下：

```python
if 条件1：
	条件1满足时执行的代码
elif 条件2：
	条件2满足时执行的代码
elif 条件3：
	条件3满足时执行的代码
else：
	以上条件都不满足时执行的代码
```

- `elsf`和 `else`都必须和 `if`联合使用，而不能单独使用

```python
# 定义holiday_name字符串变量记录节日名称
holiday_name = "情人节"
# 如果是情人节 应该买玫瑰 看电影
if holiday_name == "情人节":
    print("买玫瑰")
    print("看电影")
# 如果是 平安夜 应该买苹果 吃大餐
elif holiday_name == "平安夜":
    print("买苹果")
    print("吃大餐")
# 如果是生日 应该 买蛋糕
elif holiday_name == "生日":
    print("买蛋糕")
# 其他的日子每天都是节日啊
else:
    print("其他的日子每天都是节日啊")
```

**if嵌套**

- 在开发中，使用 `if`进行条件判断，如果希望**在条件成立的执行语句中再增加条件判断**，就可以使用 **if嵌套**
- **if嵌套**的应用场景是：**再之前条件满足的前提下，再增加额外的判断**

```python
if 条件 1：
	if 条件1 基础上的条件2:
		条件2 满足时，执行的代码
		....
	else:
		条件2 不满足时，执行的代码
else:
	条件1 不满足时，执行的代码
	....
```

```python
# 定义一个布尔变量 用于判断是否有车票
has_ticket = True
# 定义一个整形变量 用于存放刀片的长度
knife_length = 50
# 判断是否有车票
if has_ticket:
    print("车票检查通过，准备开始安检")
    # 判断刀的长度
    if knife_length > 20:
        print("您携带的刀太长了，有 %d 公分长！" % knife_length)
        print("不允许上车")
    else:
        print("安检已经通过，祝您旅途愉快")
else:
    print("您没购票，请先购票")
```

**随机数的处理**

- 在 `python`中，要使用随机数，首先需要导入 **随机数**的**模块**--”工具包“

  ```python
  import random
  ```

- 导入模块后，可以通过**ipython3**，查看模块内部函数：

  ```python
  In [1]: import random
  
  In [2]: random.
  random.BPF              random.expovariate      random.randrange
  random.LOG4             random.gammavariate     random.sample
  random.NV_MAGICCONST    random.gauss            random.seed
  random.RECIP_BPF        random.getrandbits      random.setstate
  random.Random           random.getstate         random.shuffle
  random.SG_MAGICCONST    random.lognormvariate   random.triangular
  random.SystemRandom     random.normalvariate    random.uniform
  random.TWOPI            random.paretovariate    random.vonmisesvariate
  random.betavariate      random.randint          random.weibullvariate
  random.choice           random.random    
  ```

- 函数 `random.randint(a, b)`的作用是返回 `[a, b]`区间之间的随机整数，包括 `a`和 `b`

```python
# 导入随机工具包 注意：在导入工具包的时候，应该将导入的语句放在文件的顶部
import random
# 定义一个整形变量 用于存放玩家的出拳结果
player = int(input("请玩家出拳，其中：石头为1 剪刀为2 布为3："))
# 定义一个整形变量 用于存放电脑的出拳结果
computer = random.randint(1, 3)
# 输出玩家与电脑的出拳结果
print("玩家出拳为 %d 电脑出拳为 %d " % (player, computer))
# 比较胜负
if (player == 1 and computer == 2) or (player == 2 and computer == 3) or (player == 3 and computer == 1):
    print("欧耶 电脑弱包了")
elif player == computer:
    print("真是心有灵犀 再来一局")
else:
    print("不服气 我们决战到天亮")
```

**while循环基本使用**

- `while`循环最常用的场景就是 **让执行的代码**按照**指定的次数重复**执行

- `while`语句基本语法

  ```python
  初始条件设置 - 通常是重复执行的计数器
  
  while 条件 （判断计数器是否达到目标次数）:
  	条件满足时，做的事情1
  	条件满足时，做的事情2
  	条件满足时，做的事情3
  	...(省略)...
  	
  	计数器 + 1
  ```

  ```python
  i = 1
  while i <= 5:
      print("hello python")
      i += 1
  ```
  
  ```python
  num = 0
  i = 0
  while i <= 100:
      num += i
      i += 1
  
  print("0-100之间的数字累加结果为%d " % num)
  ```
  
  ```python
  num = 0
  i = 0
  while i <= 100:
      if i % 2 == 0:
          num += i
  
      i += 1
  print("0-100之间的偶数和为：%d" % num)
  ```

**break和continue**

- **break 某条件满足时，退出循环，不再执行后续的重复代码**

- **continue 某条件满足时，不会退出循环 只是不再执行当前循环中的代码**

  ```python
  i = 0
  while i < 10:
      if i == 3:
          break
      print(i)
      i += 1
  print("over")
  ```

  ```python
  i = 0
  while i < 10:
      if i == 3:
          i += 1
          # 注意在使用 continue时，需要确认循环的计数是否修改 否则会导致死循环
          continue
      print(i)
      i += 1
  print("over")
  ```

**print 函数扩展**

- 在默认情况下，`print`函数输出内容后，会自动在末尾换行

- 如果不希望在末尾换行，可以在 `print`函数输出的内容后面增加 `,end=`

- 其中`""`中间可以指定 `print`函数输出内容之后，希望继续显示的内容

  ```python
  # 向控制台输出内容结束后，不会换行
  print("*",end="")
  # 单纯的换行
  print("")
  ```

**打印小星星**

```python
i = 1
while i <= 9:
    k = 1
    while k <= i:
        print("*", end="")
        k += 1
    print("")
    i += 1
```

**99乘法表**

```python
i = 1
while i <= 9:
    k = 1
    while k <= i:
        print("%d * %d = %d" % (i, k, i * k), end="\t")
        k += 1
    print("")
    i += 1
```

**字符串中的转义字符**

- `\t`在控制台输出一个 **制表符**，协助在输出文本时，**垂直方向**保持对齐（如上九九乘法表代码效果）
- `\n`在控制台输出一个**换行符**

| 转义字符 |    描述    |
| :------: | :--------: |
|    \\    | 反斜杠符号 |
|    \'    |   单引号   |
|   \\"    |   双引号   |
|    \n    |    换行    |
|    \t    | 横向制表符 |
|    \r    |    回车    |

**函数**

- 所谓**函数**，就是把**具有独立功能的代码块**组织为一个小模块，在需要的时候**调用**
- 函数的使用包含两个步骤：**定义函数 调用函数**
- **函数必须先定义后调用 **

**函数快速体验**

```python
def multiple_table():
    i = 1
    while i <= 9:
        k = 1
        while k <= i:
            print("%d * %d = %d" % (i, k, i * k), end="\t")
            k += 1
        print("")
        i += 1
```

```python
import hm_01_99乘法表
hm_01_99乘法表.multiple_table()
```

**函数的定义**

函数定义格式如下：

```python
def 函数名():
	函数封装代码
	......
```

- `def`是英文 `define`的缩写
- **函数名称应该能够表达函数封装代码的功能，方便后续的调用**
- **函数名称的命名应该符合标识符的命名规则**
  - 可以由**字母，下划线和数字**组成
  - **不能以数字开头**
  - **不能与关键字重名**

- 函数的注释：应该在**定义函数下方第一行，使用连续的三对引号，在引号中编写对函数的说明文字**

  ```python
  name = "小明"
  print(name)
  
  
  def say_hello():
      """说你好"""
      print("hello 1")
      print("hello 2")
      print("hello 3")
  
  
  say_hello()
  print(name)
  ```

**函数的参数**

- **在函数名的后面的小括号内部写参数**
- **多个参数之间使用 `,`分隔**

```python
def sum_2_num(num1, num2):
    """两个数字求和函数"""
    result = num1 + num2
    print("%d + %d = %d" % (num1, num2, result))


sum_2_num(10, 20)
```

**参数的作用**

- 在函数**内部**，把参数当作**变量**使用，进行需要的数据处理
- 函数调用时，按照函数定义的**参数顺序**，把**希望在函数内部处理的数据，通过参数**传递

**形参和实参**

- **形参：定义函数时**，小括号中的参数，是用来接受参数用的，在函数内部**作为变量使用**
- **实参：调用函数时**，小括号中的参数，使用来把数据转递到**函数内部**用的

**函数返回值**

- **返回值**是函数**完成工作后，返回给调用者的一个结果**
- 在函数中使用 `return`关键字可以返回结果
- 调用函数一方，可以**使用变量**来**接收**函数的返回结果

- 函数定义中函数体在`return`之后的代码不会被执行

```python
def sum_2_num(num1, num2):
    """使用返回值返回数据相加结果"""
    return num1 + num2


result = sum_2_num(20, 20)
print(result)
```

**函数嵌套使用**

```python
def test1():
    print("-" * 50)


def test2():
    print("*" * 50)
    test1()
    print("+" * 50)


test2()
```

**打印分割线**

```python
def print_line(char, time):
    print(char * time)


def print_lines(num, char, time):
    """打印多行分割线
    :param num:   分割线行数
    :param char:  分割线字符
    :param time:  一条分割线有time个字符
    """
    i = 1
    while i <= num:
        print_line(char, time)
        i += 1


print_lines(5, "-", 50)

```

**模块以及模块中的函数**

- **模块**类似于**工具包**，要想使用这个工具包中的工具，就需要**导入import**这个模块
- 每个以拓展名 `py`结尾的 `python`源代码都是一个**模块**
- 在模块中定义的**全局变量，函数**都是模块能够提供给外界直接使用的工具

- `hm_08_打印多个分割线模块`

  ```python
  def print_line(char, time):
      """打印一行分割线
      :param char:   分割线字符
      :param time:   一条分割线有time个字符
      """
      print(char * time)
  
  
  def print_lines(num, char, time):
      """打印多行分割线
      :param num:   分割线行数
      :param char:  分割线字符
      :param time:  一条分割线有time个字符
      """
      i = 1
      while i <= num:
          print_line(char, time)
          i += 1
  
  
  name = "黑马程序员"
  ```

- 调入上方  `hm_08_打印多个分割线模块`并调用内部函数与变量

  ```python
  import hm_08_打印多个分割线模块
  hm_08_打印多个分割线模块.print_line("-", 50)
  hm_08_打印多个分割线模块.print_lines(4, "-", 50)
  print(hm_08_打印多个分割线模块.name)
  ```

**模块名**：模块名也是一个标识符，需要满足标识符命名要求

- 可以由**字母，下划线和数字**组成
- **不能以数字开头**
- **不能与关键字重名**

**高级变量类型（非数字型变量）**：**字符串、列表、元组、字典**

**非数字型变量共同特点**

- 都是一个 **序列** `sequence`，也可以理解为 **容器**
- **取值** `[]`
- **遍历** `for in`
- **计算长度、最大值/最小值、比较、删除**
- **链接 `+`和重复 `*`**
- **切片**

**列表：可变对象**

- `list`（列表）是 `python`中使用**最频繁**的数据类型，在其他语言中通常叫做**数组**
- 用于存储 **一串信息**
- 列表用 `[]`定义，列表中个元素之间使用 `,`分隔
- 列表的**索引**从 `0`开始，用 `[索引号/下标号]`提取列表中元素
- **索引**就是数据在**列表**中的位置编号，又可以称为**下标**

**列表能使用的方法如下**

```python
In [4]: name_list.
name_list.append   name_list.count    name_list.insert   name_list.reverse
name_list.clear    name_list.extend   name_list.pop      name_list.sort
name_list.copy     name_list.index    name_list.remove  
```

| 序号 | 分类 |     关键字/函数/方法      |           说明           |
| :--: | :--: | :-----------------------: | :----------------------: |
|  1   | 增加 |  列表.insert(索引，数据)  | 在指定索引位置查插入数据 |
|      |      |     列表.append(数据)     |      在末尾追加数据      |
|      |      |    列表.extend(列表2)     | 将列表2的数据追加到列表  |
|  2   | 修改 |      列表[索引]=数据      |  修改指定索引位置的数据  |
|  3   | 删除 |      del 列表[索引]       |  删除指定索引位置的数据  |
|      |      |     列表.remove[数据]     | 删除第一次出现的指定数据 |
|      |      |         列表.pop          |     函数列表末尾数据     |
|      |      |      列表.pop[索引]       |  删除指定索引位置的数据  |
|      |      |        列表.clear         |         清空列表         |
|  4   | 统计 |        len（列表）        |         列表长度         |
|      |      |    列表.count（数据）     |  数据在列表中出现的次数  |
|  5   | 排序 |       列表.sort（）       |         升序排序         |
|      |      | 列表.sort（reverse=True） |         降序排序         |
|      |      |     列表.reverse（）      |        逆序，反序        |

![image-20220504175041774](C:\Users\28647\AppData\Roaming\Typora\typora-user-images\image-20220504175041774.png)

- del 关键字本质上是用来将一个变量从内存中删除，如果使用del删除某变量后，后续的代码中就不能再使用该变量了

- 在日常开发中，要从列表删除数据，建议使用列表提供的方法，而不用del

  ```python
  name_list = ["张三", "李四", "王五"]
  # del关键字删除列表元素
  del  name_list[0]
  print(name_list)
  ```

- `len()`函数可以统计列表中元素总数

- `列表.count()`可以统计列表中某元素出现的次数

  ```python
  name_list = ["张三", "李四", "王五"]
  
  # len()函数可以统计列表中元素的总数
  num = len(name_list)
  print(num)
  
  # comut方法可以统计列表中某个数据出现的次数
  time = name_list.count("张三")
  print(time)
  ```

- 列表.sort（） 实现列表升序排序

- 列表.sort（reverse=True）  实现列表降序排序

- 列表.reverse（）  实现列表逆序，反序

  ```python
  name_list = ["zhangsan", "lisi", "wangwu", "wangxiaoer"]
  num_list = [0, 9, 7, 8, 4, 6, 3]
  
  # 升序
  name_list.sort()
  num_list.sort()
  # 降序
  name_list.sort(reverse=True)
  num_list.sort(reverse=True)
  # 逆序
  name_list.reverse()
  num_list.reverse()
  
  
  print(name_list)
  print(num_list)
  ```


**列表的循环遍历**

- **遍历**就是**从头到尾依次**从**列表**中获取数据--在**循环体内部**针对**每一个元素**执行相同的操作

- 使用 `for`就能够实现迭代遍历

  ```python
  # for 循环内部使用的变量  in 列表名
  for name in name_list
  	
  	# 循环内部针对列表元素进行操作
  	print(name)
  ```

  ```python
  name_list = ["zhangsan", "lisi", "wangwu", "wangxiaoer"]
  for my_name in name_list:
      """顺序的从列表中一次获取数据,每次循环过程中,数据的都会保存在 name_list变量中"""
      print("my name is : %s" % my_name)
  ```

**元组的定义：不可变对象**

- **元组（tuple）**表示多个元素组成的序列，在 `python`开发中，有特定的应用场景
- 元组与列表类似，不同之处在于元组的**元素不能修改**
- 元组主要用于存储**一串信息，数据**，元素之间用 `，`分隔
- 元素用 `()`定义
- 元组的**索引**从 `0`开始；**索引**就是元素在**元组**中的**位置编号**
- 元组的**索引**符号用 `[]`

- 空元组定义：

  ```python
  In [1]: empty_tuple = ()
  
  In [2]: type(empty_tuple)
  Out[2]: tuple
  ```

- 定义一个只包含一个元素的元组：**需要在元素后面添加逗号**

  ```python
  In [3]: single_tuple = (5, )
  
  In [4]: type(single_tuple)
  Out[4]: tuple
  ```

**元组的常用操作：元组为不可变对象，因此无法用del删除其内部元素**

```python
In [1]: empty_tuple = ()
In [5]: empty_tuple.
empty_tuple.count  empty_tuple.index  
```

```python
info_tuple = ("zhangsan", 18, 1.75)
# 取值和去索引
print(info_tuple[0])
# 以知元素内容,查看元素在元组中的下标
print(info_tuple.index("zhangsan"))

# 统计计算
print(info_tuple.count("zhangsan"))
print(len(info_tuple))

print(info_tuple)
```

**元组的循环遍历**

- **遍历就是从头到尾依次从元组中获取数据**

  ```python
  # for 循环内部使用变量 in 元组
  for item in info
  	循环内部针对元组元素进行操作
  	print(item
  ```

- 在 `python`中，可以使用 `for`循环遍历所有非数字型类型的变量：**列表、元组、字典以及字符串**
- 在实际开发中，除非**能够确认元组中的数据类型，否则针对元组的循环遍历需求并不是很多**

**元组的应用场合**

- 作为**函数参与或者返回值，一个函数可以接收任意多个参数，或者一次返回任意多个数据**
- **格式字符串后面的（）本质上就是一个元组**
- **让列表不可以被修改，可以将列表转换成元组，用以保护数据安全&**

**元组与列表之间的转换**

- 使用 `list`函数可以把元组转换成列表

  ```python
  list（元组）
  ```

- 使用 `tuple`函数可以把列表转换成元组

  ```python
  tuple（列表）
  ```

  ```python
  In [5]: num_list = [1, 2, 3, 4]
  
  In [6]: type(num_list)
  Out[6]: list
  
  In [7]: num_tuple = tuple(num_list)
  
  In [8]: type(num_tuple)
  Out[8]: tuple
  
  In [9]: num_list = list(num_tuple)
  
  In [10]: type(num_list)
  Out[10]: list
  ```

**字典的定义：可变对象**

- `dictionary`（字典）是除列表以外 `python`之中，最灵活的数据类型

- 字典同样可以用来存储多个数据，主要用来表述一个物体的相关信息

- 字典和列表的区别

  - 列表是有序的对象集合
  - 字典是无序的对象集合（使用print函数输出字典时，通常的输出顺序与定义顺序不同）

- 字典用{}定义

- 字典使用**键值对**存储数据，键值对之间使用 `,`分隔

  - **键** `key`是索引（对应于元组和列表中的索引/下角标）
  - **值** `value`是数据
  - **键**和**值**之间使用 `：`分隔
  - **键是唯一的**
  - **值**可以是任何数据类型，但是**键**只能使用**字符串、数字或者元组**

  ```python
  xiaoming = {"name": "小明",
              "age": 18,
              "gender": True,
              "hight": 1.75,
              "wight": 75.5}
  print(xiaoming)
  print(xiaoming.values())
  print(xiaoming.keys())
  ```

**字典的基本使用**

```python
In [11]: empty_dict = {}
In [12]: empty_dict.
empty_dict.clear       empty_dict.items       empty_dict.setdefault
empty_dict.copy        empty_dict.keys        empty_dict.update
empty_dict.fromkeys    empty_dict.pop         empty_dict.values
empty_dict.get         empty_dict.popitem     
```



```python
xiaoming_dict = {"name": "xiaoming"}
# 取值
print(xiaoming_dict["name"])
# 增加/修改
#  key不存在则增加键值对
xiaoming_dict["age"] = 18
#  key存在则修改value的内容
xiaoming_dict["name"] = "xiaoxiaoming"
# 删除
xiaoming_dict.pop("name")


print(xiaoming_dict)
```

```python
xiaoming_dict = {"name": "小明",
                 "age": 18}
# len统计键值对数
print(len(xiaoming_dict))

# 合并字典
temp_dict = {"height": 1.75,
             "age": 20}
# 如果被合并的字典中包含已经存在的键值对,则会覆盖在之前原有的键值对内容
xiaoming_dict.update(temp_dict)

# 清空字典
xiaoming_dict.clear()

print(xiaoming_dict)
```

**字典循环遍历**：就是**依次**从**字典**中获取所有键值对

- 实际开发过程中，字典中的键值对保存的数据类型不同，所以针对字典的循环遍历需求并不多

```python
# for 循环内部使用的 key的变量 in 字典
for k in xiaoming
	print("%s: %s" % (k, xiaoming[k]))
```

```python
xiaoming_dict = {"name": "小明",
                 "qq": "12345",
                 "phone": "28647"}
# k是每一次循环中,获取到的键值对中的key
for k in xiaoming_dict:
    print("%s: %s" % (k, xiaoming_dict[k]))
```

 **列表与字典结合**

- 使用一个**字典（包含多个键值对），存储描述一个物体的相关信息**
- 将**多个字典放到一个列表中，再进行遍历，在循环体中对每个字典进行相同的处理**

```python
car_list = [{"name": "zhangsan",
             "qq": "123456",
             "phone": "11111"},
            {"name": "lisi",
             "qq": "654321",
             "phone": "22222"}]

print(car_list)
```

**字符串的定义**

- **字符串**就是**一串字符，是编程语言中表示文本的数据类型**
- 在 `python`中可以使用**一对双引号""**或者**一对单引号''**定义一个字符串
- 大多数编程语言使用**双引号""**定义字符串，但是在实际开发中：

  - 可以使用 `\"` 或者`\'`做字符串的转移
  - 如果字符串内部需要使用 `""`，可以使用 `''`定义字符串
  - 果字符串内部需要使用 `''`，可以使用 `""`定义字符串
- 可以使用**索引**获取字符串中**指定位置的字符**，索引计数从0开始
- 也可以使用 `for`循环遍历字符串中每一个字符

**字符串常用操作：字符串为不可变对象，所有操作都是在原有字符串的基础上通过函数作用生成一个新的字符串，因此无法用del删除字符串内部元素**

```python
In [12]: str1 = "hello python"

In [13]: str1.
str1.capitalize    str1.isalnum       str1.join          str1.rsplit
str1.casefold      str1.isalpha       str1.ljust         str1.rstrip
str1.center        str1.isdecimal     str1.lower         str1.split
str1.count         str1.isdigit       str1.lstrip        str1.splitlines
str1.encode        str1.isidentifier  str1.maketrans     str1.startswith
str1.endswith      str1.islower       str1.partition     str1.strip
str1.expandtabs    str1.isnumeric     str1.replace       str1.swapcase
str1.find          str1.isprintable   str1.rfind         str1.title
str1.format        str1.isspace       str1.rindex        str1.translate
str1.format_map    str1.istitle       str1.rjust         str1.upper
str1.index         str1.isupper       str1.rpartition    str1.zfill
```

```python
str1 = "hello python"
str2 = 'hello my name is "zhangsan"'

for char in str2:
    print(char)

for char in str1:
    print(char)

# 统计字符串长度
print(len(str1))
print(len(str2))

# 统计字符串中某一个字符/子字符串出现的次数
print(str1.count("o"))
print(str2.count("a"))

# 索引字符串某位置上的字符
print(str1[5])
print(str2[5])

# 求取字符串中某字符/子字符串第一出现的下标
print(str1.index("o"))
print(str2.index("a"))
```

|        方法        |                             说明                             |
| :----------------: | :----------------------------------------------------------: |
|  string.isspace()  | 如果string中只包含空白字符（包括空格以及'\t\n\r'三个转义字符），则返回True |
|  string.isalnum()  | 如果string中至少有一个字符并且所有字符都是字母或者数字则返回True |
|  string.isalpha()  |   如果string中至少有一个字符并且所有字符都是字母则返回True   |
| string.isdecimal() |  如果string中只包含数字则返回True，全角数字（不能判断小数）  |
|  string.isdigit()  | 如果string只包含数字则返回True，全角数字、（1）、\u00b2（不能判断小数） |
| string.isnumeric() | 如果string只包含数字则返回True，全角数字、汉字数字（不能判断小数） |
|  string.istitle()  |    如果string是标题化的（每个单词的首字母大写）则返回True    |
|  string.islower()  | 如果string中包含至少一个区分大小写的字符，并且所有这些（区分大小写的）字符都是小写，则返回True |
|  string.isupper()  | 如果string中包含至少一个区分大小写的字符，并且所有这些（区分大小写的）字符都是大写，则返回True |

|                         方法                          |                             说明                             |
| :---------------------------------------------------: | :----------------------------------------------------------: |
|                string.startswith(str)                 |            检查字符串是否为str开头，是则返回True             |
|                 string.endswith(str)                  |            检查字符串是否为str结尾，是则返回True             |
|         string.find(str,start=0,end=len(str))         | 检查string中是否包含str，其中start和end用于指定范围，如果包含则返回str字符串在string字符串中索引值，不包含的话返回-1 |
|        string.rfind(str,start=0,end=len(str))         |           类似于find（）函数，不过是从右边开始查找           |
|        string.index(str,start=0,end=len(str))         |    类似于find（）函数，只不过如果str不再string中不会报错     |
|        string.rindex(str,start=0,end=len(str))        |          类似于index（）函数，不过是从右边开始查找           |
| string.replace(old_str,new_str,num=string.count(old)) | 把string中的old_str替换成new_str，如果num指定，则替换不超过num次 |

|        方法         |              说明              |
| :-----------------: | :----------------------------: |
| string.capitalize() |    把字符串的第一个字符大写    |
|   string.title()    |  把字符串的每个单词首字母大写  |
|   string.lower()    | 转换string中所有大写字符为小写 |
|   string.upper()    |  转换string中的小写字母为大写  |
|  string.swapcase()  |      翻转string中的大小写      |

|         方法         |                             说明                             |
| :------------------: | :----------------------------------------------------------: |
| string.ljust(width)  | 返回一个原字符串左对齐，并使用空格填充至长度为width的新字符串 |
| string.rjust(width)  | 返回一个原字符串右对齐，并使用空格填充至长度为width的新字符串 |
| string.center(width) | 返回一个原字符串居中对齐，并使用空格填充至长度为width的新字符串 |

|      方法       |               说明               |
| :-------------: | :------------------------------: |
| string.lstrip() | 截掉string左边（开始）的空白字符 |
| string.rstrip() | 截掉string右边（结尾）的空白字符 |
| string.strip()  |     截掉string两边的空白字符     |

|           方法           |                             说明                             |
| :----------------------: | :----------------------------------------------------------: |
|  string.partition(str)   |  把字符串string分成一个3元素的元组（str前面，str，str后面）  |
|  string.rpartition(str)  |    类似于string.partition(str)函数，不过是从右边开始查找     |
| string.split(str="",num) | 以str为分隔符切片string，如果num右指定值，则仅分隔num+1个子字符串，str默认包含'\r','\t','\n'和空格 |
|   string.splitilines()   | 按照行（'\r','\n','\r\n'）分隔，返回一个包含各行作为元素的列表 |
|     string.join(seq)     | 以string作为分隔符，将seq中所有的元素（的字符串表示）合并为一个新的字符串 |

```python
# 判断字符串是否为全空格
str_space = "    \t\n\r"
print(str_space.isspace())

# 字符串数字判断
# # 阿拉伯数字
# str_num = "1"
# print(str_num)

# # unicode 字符串
# str_num = "\u00b2"
# print(str_num)

# 中文数字字符串
str_num = "一千零一"
print(str_num)

print(str_num.isdecimal())
print(str_num.isdigit())
print(str_num.isnumeric())
```

```python
hello_str = "hello world"
# 判断是否以指定字符串开始
print(hello_str.startswith("hello"))
# 判断是否以指定字符串结束
print(hello_str.endswith("world"))
# 查找指定字符串
# index函数如果指定的字符串不存在,会报错
# find函数如果指定的字符串不存在,会返回-1
print(hello_str.find("abc"))
print(hello_str.index("llo"))
# 替换字符串
# replace 函数不会修改原有字符串内容 但是会生成一个新的字符串
print(hello_str.replace("world", "python"))
print(hello_str)

hello_str_replace = hello_str.replace("world", "python")
print(hello_str_replace)
```

```python
pome = ["登鹳雀楼", "王之涣", "白日依山尽", "黄河入海流", "欲穷千里目", "更上一层楼"]

# 居中对齐
for pome_str in pome:
    print("|%s|" % pome_str.center(10, "　"))

# 左对齐
print("")
for pome_str in pome:
    print("|%s|" % pome_str.ljust(10, "　"))

# 右对其
print("")
for pome_str in pome:
    print("|%s|" % pome_str.rjust(10, "　"))
```

```python
pome = ["登鹳雀楼", "\t\n王之涣", "白日依山尽", "黄河入海流\t\n", "欲穷千里目", "更上一层楼"]

# 居中对齐
for pome_str in pome:
    # 先使用strip去除空白字符,提取主要内容
    # 再使用center方法剧中显示文本
    print("|%s|" % pome_str.strip().center(10, "　"))
```

```python
pome = "登鹳雀楼\t \t\n王之涣 \n白日依山尽 黄河入海流\t\n \t欲穷千里目\n更上一层楼"
print(pome)

# 拆分字符串  返回一个字符串列表
pome_list = pome.split()
print(pome_list)

# 合并字符串
pome = " ".join(pome_list)
print(pome)
```

**字符串的切片**

- **切片**使用**索引值**来限定范围，从一个大的**字符串**中**切出**小的**字符串**
- **切片**方法适用于**字符串、列表、元组**，因为三者都是**有序**的集合，能**通过索引值**获取到对应的数据，但是**字典**是一个**无序**的集合，是使用**键值对**保存数据

![image-20220506102929316](C:\Users\28647\AppData\Roaming\Typora\typora-user-images\image-20220506102929316.png)

```python
字符串[开始索引:结束索引:步长]
```

**注意：**

- 指定的区间属于**左闭右开**型 `[开始索引，结束索引）`=> `开始索引 >= 范围 < 结束索引`
- **从 `起始`位开始，到 `结束`位的前一位结束（不包含结束位本身）**
- 从头开始，**开始索引数字可以省略，冒号不能省略**
- 到末尾结束，**结束索引数字可以省略，冒号不能省略**
- 步长默认位 `1`，如果连续切片，**数字和冒号都可以省略**

```python
In [1]: str_num = "0123456789"

In [2]: str_num[2:6]
Out[2]: '2345'

In [3]: str_num[2:]
Out[3]: '23456789'

In [4]: str_num[:6]
Out[4]: '012345'

In [5]: str_num[:]
Out[5]: '0123456789'

In [6]: str_num[::2]
Out[6]: '02468'

In [7]: str_num[1::2]
Out[7]: '13579'

In [10]: str_num[2:-1]
Out[10]: '2345678'

In [12]: str_num[-2:]
Out[12]: '89'

In [14]: str_num[::-1]
Out[14]: '9876543210'
```

**python内置函数**

|       函数       |                 描述                 |                             备注                             |
| :--------------: | :----------------------------------: | :----------------------------------------------------------: |
|    len(item)     |         计算容器中元素的个数         |                                                              |
|    del(item)     | 删除变量（容器本身以及容器中的元素） | del有两种方式(只有列表和字典可以用del删除内部的元素，其他的容器都不可以)（可以整体删除容器） |
|    max(item)     |         返回容器中元素最大值         |                  如果是字典，只针对key比较                   |
|    min(item)     |         返回容器中元素最小值         |                  如果是字典，只针对key比较                   |
| cmp(item1,item2) |              比较两个值              |         python3.x取消该函数，可以通过 `< >`进行比较          |

- **上表中容器包含，字符串、列表、元组、字典**

- **字符串**比较符合该规则： "0"<"A"<"a"

  ```python
  In [4]: list_num = [1, 2, 3, 4, 5, 6, 7]
  In [5]: del list_num[0]
  
  In [6]: list_num
  Out[6]: [2, 3, 4, 5, 6, 7]
  
  In [12]: dict_num={"name": "a", "age": "b"}
  
  In [13]: del dict_num["name"]
  
  In [14]: dict_num
  Out[14]: {'age': 'b'}
  
  
  In [7]: str_num = "12345678"
  
  In [8]: del str_num[0]
  ---------------------------------------------------------------------------
  TypeError                                 Traceback (most recent call last)
  <ipython-input-8-62026b551fb1> in <module>()
  ----> 1 del str_num[0]
  
  TypeError: 'str' object doesn't support item deletion
  
  
  
  In [9]: tuple_num = (1, 2, 3, 4, 5, 6)
  
  In [10]: del tuple_num[0]
  ---------------------------------------------------------------------------
  TypeError                                 Traceback (most recent call last)
  <ipython-input-10-8f7b7879a63f> in <module>()
  ----> 1 del tuple_num[0]
  
  TypeError: 'tuple' object doesn't support item deletion
  
  ```

  ```python
  In [17]: str_num = "12345678"
  
  In [18]: del str_num
  
  In [19]: str_num
  ---------------------------------------------------------------------------
  NameError                                 Traceback (most recent call last)
  <ipython-input-19-6952abce6908> in <module>()
  ----> 1 str_num
  
  NameError: name 'str_num' is not defined
  
  In [20]: list_num = [1, 2, 3, 4, 5, 6]
  
  In [21]: del list_num
  
  In [22]: list_num
  ---------------------------------------------------------------------------
  NameError                                 Traceback (most recent call last)
  <ipython-input-22-e16babb20e42> in <module>()
  ----> 1 list_num
  
  NameError: name 'list_num' is not defined
  
  
  In [23]: tuple_num = (1, 2, 3, 4, 5, 6, 7)
  
  In [24]: del tuple_num
  
  In [25]: tuple_num
  ---------------------------------------------------------------------------
  NameError                                 Traceback (most recent call last)
  <ipython-input-25-40e80bfcbe68> in <module>()
  ----> 1 tuple_num
  
  NameError: name 'tuple_num' is not defined
  
  
  In [26]: dict_num = {"name": "a"}
  
  In [27]: del dict_num
  In [29]: dict_num
  ---------------------------------------------------------------------------
  NameError                                 Traceback (most recent call last)
  <ipython-input-29-a9c2128a482f> in <module>()
  ----> 1 dict_num
  ```

**切片**

| 描述0 |    python表达式    |  结果   |   支持的数据类型   |
| :---: | :----------------: | :-----: | :----------------: |
| 切片  | “0123456789”[::-2] | "97531" | 字符串、列表、元组 |

- **切片**使用**索引值**来限定范围，从一个大的**高级数据类型变量**中**切出**小的**同类型变量**
- **字符串、列表、元组**都是**有序**集合，能够**通过索引值**获取对应的数据
- **字典**是**无序**集合，通过**键值对**保存数据，不存在索引值

```python
In [33]: str_num = "123456789"

In [34]: str_num[2:6]
Out[34]: '3456'

In [35]: list_num = [1, 2, 3, 4, 5, 6, 7, 8, 9]

In [36]: list_num[2:6]
Out[36]: [3, 4, 5, 6]

In [37]: tuple_num = (1, 2, 3, 4, 5, 6, 7, 8, 9)

In [38]: tuple_num[2:6]
Out[38]: (3, 4, 5, 6)
```

**运算符**

|    运算符    |   python表达式   |           结果            |      描述      |    支持的高级数据类型    |
| :----------: | :--------------: | :-----------------------: | :------------: | :----------------------: |
|      +       |   [1,2]+[3,4]    |         [1,2,3,4]         |      合并      |    字符串、列表、元组    |
|      *       |    ["hi!"]*4     | ["hi!","hi!","hi!","hi!"] |      重复      |    字符串、列表、元组    |
|      in      |   3 in (1,2,3)   |           True            |  元素是否存在  | 字符串、列表、元组、字典 |
|    not in    | 4 not in (1,2,3) |           True            | 元素是否不存在 | 字符串、列表、元组、字典 |
| > >= == < <= | (1,2,3)<(2,2,3)  |           True            |    元素比较    |    字符串、列表、元组    |

```python
In [1]: "hello" + "python"
Out[1]: 'hellopython'

In [2]: [1, 2] + [3, 4]
Out[2]: [1, 2, 3, 4]

In [3]: (1, 2) + (3, 4)
Out[3]: (1, 2, 3, 4)

In [4]: {"name": "1"} + {"age": "2"}
---------------------------------------------------------------------------
TypeError                                 Traceback (most recent call last)
<ipython-input-4-702c2070f320> in <module>()
----> 1 {"name": "1"} + {"age": "2"}

TypeError: unsupported operand type(s) for +: 'dict' and 'dict'
```

```python
In [9]: "hi!"*4
Out[9]: 'hi!hi!hi!hi!'

In [10]: [1, 2]*4
Out[10]: [1, 2, 1, 2, 1, 2, 1, 2]

In [11]: (1, 2)*4
Out[11]: (1, 2, 1, 2, 1, 2, 1, 2)

In [12]: {"name": "a"}*4
---------------------------------------------------------------------------
TypeError                                 Traceback (most recent call last)
<ipython-input-12-ca7273a5e6f9> in <module>()
----> 1 {"name": "a"}*4

TypeError: unsupported operand type(s) for *: 'dict' and 'int'
```

**成员运算符**

- `in`和 `not in`被称为 **成员运算符**，两者在对**字典**操作时，判断的是**字典的键**
- 成员运算符用于**测试**容器中是否包含指定的**成员**

```python
In [13]: "a" in "abcd"
Out[13]: True

In [14]: "a" not in "abcd"
Out[14]: False

In [15]: 1 in [0, 1, 2]
Out[15]: True

In [16]: 1 not in [0, 1, 2]
Out[16]: False

In [17]: 1 in (0, 1, 2)
Out[17]: True

In [18]: 1 not in (0, 1, 2)
Out[18]: False

In [19]: "a" in {"a": "laowang"}
Out[19]: True

In [20]: "a"not in {"a": "laowang"}
Out[20]: False

In [21]: "laowang" in {"a": "laowang"}
Out[21]: False

In [22]: "laowang" not in {"a": "laowang"}
Out[22]: True
```

**完整的for循环语法**

```python
for 变量 in 集合：
	循环体代码
else：
	没有通过break退出循环前提下，正常结束循环后会执行的代码
```

```
for num in [1, 2, 3, 4]:
    print(num)
    if num == 3:
        break
else:
    # 如果循环提内部使用break退出了循环
    # else下方的的代码就不会被执行 
    print("会执行吗?")

print("执行结束")
```

```python
student_list = [{"name": "阿土",
                 "age": "20",
                 "gender": True,
                 "height": 1.7,
                 "weight": 75.0},
                {"name": "小美",
                 "age": "19",
                 "gender": False,
                 "height": 1.6,
                 "weight": 45.0}]
find_name = "周"
for student in student_list:
    if student["name"] == find_name:
        print("找到阿土,该生的相关信息为")
        print(student)
        break
else:
    print("学生列表中不存在想要找的学生")
```

**在Linux终端中使用./文件名.py方式运行python文件的设置方法**

```shell
zcb@zcb-virtual-machine:~/python_study/06_名片管理$ which python3
/usr/local/bin/python3
在项目文件cards_main.py的首行 加入：#! /usr/local/bin/python3
zcb@zcb-virtual-machine:~/python_study/06_名片管理$ ls -l
total 16
-rw-rw-r-- 1 zcb zcb  604 5月   6 21:17 cards_main.py
-rw-rw-r-- 1 zcb zcb 2842 5月   6 21:15 cards_tools.py
drwxrwxr-x 2 zcb zcb 4096 5月   6 21:12 __pycache__
drwxrwxr-x 4 zcb zcb 4096 5月   6 15:50 venv
zcb@zcb-virtual-machine:~/python_study/06_名片管理$ chmod +x cards_main.py 
zcb@zcb-virtual-machine:~/python_study/06_名片管理$ ./cards_main.py 
```

**引用的概念**

- 变量和数据是分开存储的
- 数据保存在内存中的一个位置
- 变量中保存这数据在内存中的地址
- 每一个数据有一个内存地址，要用这个数据，需要用一个变量名去引用它
-  引用，其实就是把数据的地址放到变量名里面
- 使用 `id（）`函数可以查看变量中保存数据所在的内存地址
- 如果变量已经被定义，当给变量赋值的时候，是继善是修改了数据的引用
- 函数调用时进行传参，本质上传递的是变量名（变量名内部保存数据地址），而不是实参保存的数据
- 不懂看这：https://m.jb51.net/article/224991.htm

```python
def test(num):
    # 本质上传递的是实参保存数据的引用，而不是实参保存的数据
    print("在函数内部%d对应的内存地址为:%d" % (num, id(num)))
    result = "hello"
    print("函数要返回的内存地址为: %d" % id(result))
    # 将字符串变量返回,返回的是数据的引用,而不是数据本身
    return result


a = 10
print("a 变量保存数据的内存地址是 %d" % id(a))
# 如果函数有返回值,但是没有定义变量接受,程序不会报,但是无法获得返回结果
r = test(a)
print("%s 的内存地址是 %d" % (r, id(r)))
```

**可变和不可变类型**

- **不可变类型：数字类型、字符串、元组**

- **字典的 `key`只能使用不可变的数据类型**

- **可变类型：列表、字典**

- **可变类型的数据变化是通过方法来实现的** 

- 如果给一个可变类型的变量进行一个新的数据赋值，引用会改变

  ```python
  # 列表  通过方法修改（删除、增加、清空）列表中元素，列表的地址不变
  In [1]: a=[1, 2, 3, 4]
  
  In [2]: id(a)
  Out[2]: 140659971956232
  
  In [3]: a.append(99)
  
  In [4]: a
  Out[4]: [1, 2, 3, 4, 99]
  
  In [5]: id(a)
  Out[5]: 140659971956232
  
  In [6]: a.remove(4)
  
  In [7]: a
  Out[7]: [1, 2, 3, 99]
  
  In [8]: id(a)
  Out[8]: 140659971956232
  
  In [9]: a.clear
  Out[9]: <function list.clear>
  
  In [10]: a.clear()
  
  In [11]: id(a)
  Out[11]: 140659971956232
  
  In [12]: a = []
  
  In [13]: id(a)
  Out[13]: 140659971848840
  
  # 字典同上方列表
  In [14]: d = {"name": "xiaoming"}
  
  In [16]: id(d)
  Out[16]: 140659956310280
  
  In [17]: d["age"] = 18
  
  In [18]: d
  Out[18]: {'age': 18, 'name': 'xiaoming'}
  
  In [19]: id(d)
  Out[19]: 140659956310280
  
  In [20]: d.clear()
  
  In [21]: id(d)
  Out[21]: 140659956310280
  
  In [22]: d= {}
  
  In [23]: id(d)
  Out[23]: 140659956313608
  ```

  **字典的 `key`只能使用不可变的数据类型**

  ```python
  In [25]: dict = {}
  
  In [26]: dict["name"] = "xiaoming"
  
  
  In [29]: dict
  Out[29]: {'name': 'xiaoming'}
  
  In [30]: dict[1] = "zhangshu"
  
  In [31]: dict
  Out[31]: {1: 'zhangshu', 'name': 'xiaoming'}
  
  In [32]: dict[(1,)] = "yuanzu"
  
  In [33]: dict
  Out[33]: {1: 'zhangshu', (1,): 'yuanzu', 'name': 'xiaoming'}
  
  In [34]: dict[[1,2,3]]= "liebiao"
  ---------------------------------------------------------------------------
  TypeError         Traceback (most recent call last)
  <ipython-input-34-c4ab0ce11d4e> in <module>()
  ----> 1 dict[[1,2,3]]= "liebiao"
  
  TypeError: unhashable type: 'list'
  In [35]: dict[{"age":18}] = "zidian"
  ---------------------------------------------------------------------------
  TypeError                                 Traceback (most recent call last)
  <ipython-input-35-0c3653c5d3e0> in <module>()
  ----> 1 dict[{"age":18}] = "zidian"
  
  TypeError: unhashable type: 'dict'
  ```

  **注意观察报错 TypeError: unhashable type: 'dict'  TypeError: unhashable type: 'list' ，其中unhashable 包含一个函数 哈希（hash）**

**哈希（hash）**

- `python`中内置有一个**hash（）**函数
  - 该函数接收一个**不可变类型**数据作为**参数**
  - 该函数返回值是一个**整数**
- `哈希（hash）`是一种**算法**，其作用是提取数据的**特征码（指纹）**
  - **相同的内容得到相同的结果**
  - **不同的内容得到不同的结果**
- `python`中，设置字典的**键值对**时，会首先对**key进行hash**用于决定如何在内存中白村字典的数据，方便后续对字典的操作：**增删改查**
  - 键值对的 `key`必须时不可变类型数据
  - 键值对 `value`可以是任意类型的数据

**局部变量和全局变量**

- **局部变量**是在**函数内部**定义的变量，**只能在函数内部使用**
- **全局变量**是在**函数外部定义（没有定义在任何一个函数内部）的变量**，**所有函数**内部**都可以使用这个变量**

**局部变量**

- **局部变量**是在**函数内部**定义的变量，**只能在函数内部使用**
- 函数执行结束后，**寒素内部的局部变量，会被系统回收**
- 不同的函数，可以定义相同名字的局部变量，但是在不同函数中的相同名字的局部变量不会产生影响
- **局部变量的作用**：在函数内部使用，**临时保存函数内部需要使用的数据**

**局部变量的生命周期**

- 所谓**生命周期**就是变量从**被创建到被系统回收**的过程
- **局部变量在函数执行时**被创建
- **函数执行结束后**局部变量**被系统回收**
- **局部变量在生命周期**内，可以用来存储**函数内部临时使用到的数据**

**全局变量**

- **全局变量**是在**函数外部定义**的变量，所有函数内部都可以使用这个变量

- 函数执行时，**需要处理变量时**会：

  - 首先查找函数内部是否存在指定名称的局部变量，如果有直接使用
  - 如果没有，查找函数外部是否存在指定名称的全局变量，如果有直接使用
  - 如果上述两步都没找到，程序报错

- 在函数内部，可以**通过全局变量的引用获取对应的数据**

- 但是，**不允许直接修改全局变量的引用（不允许使用赋值语句修改全局变量的值）**

- **在某函数内修改全局变量后，只会在该函数内部起作用，在该函数外部，变量的值不变**

  ```python
  num = 10
  
  
  def demo1():
      num = 99
      print("demo1 ==> %d" % num)
  
  
  def demo2():
      print("demo2 ==> %d" % num)
  
  
  demo1()
  demo2()
  
  /usr/local/bin/python3 /home/zcb/python_study/07_语法进阶/hm_02_函数无法全局修改全局变量.py
  demo1 ==> 99
  demo2 ==> 10
  ```

- **如果想在函数内部修改全局变量的值，可以使用global声明一下变量**

```python
num = 10


def demo1():
    # global 关键字会告诉解释器这个变量是一个全局变量,在使用赋值语句时,就不会创建局部变量
    global  num
    num = 99
    print("demo1 ==> %d" % num)


def demo2():
    print("demo2 ==> %d" % num)


demo1()
demo2()


/usr/local/bin/python3 /home/zcb/python_study/07_语法进阶/hm_03_global在局部函数内修改全局变量.py
demo1 ==> 99
demo2 ==> 99
```

-   **注意：在开发时，应该把模块中的所有全局变量定义在所有函数上方，用于保证所有的函数都能正常的访问到每一个全局变量**

**函数参数和返回值的作用**

- 如果**函数内部处理的数据不确定**就可以将外界的数据以参数传递到函数内部
- 如果希望**函数执行完成后，向外界汇报执行结果**，可以增加函数的返回值

![image-20220507190540419](C:\Users\28647\AppData\Roaming\Typora\typora-user-images\image-20220507190540419.png)

**函数返回值**

- 在程序开发中，会希望**一个函数执行结束后告诉调用者一个结果**以便调用者针对具体的结果做后续的处理

- **返回值**是函数**完成工作后，给调用者的一个结果**

- 在函数中使用 `return`关键字返回结果

- 调用函数一方，使用**同类型变量接受函数返回结果**

- 当需要返回多个值时，可以使用元组让函数一次返回多个值

- **如果函数返回值的类型是元组，可以省略定义元组的括号**

  ```python
  def measure():
      """测量温度和湿度"""
      print("测量开始")
      temp = 50
      wetness = 100
      print("测量结束")
      return temp, wetness
  
  
  result = measure()
  print(result)
  type(result)
  
  /usr/local/bin/python3 /home/zcb/python_study/07_语法进阶/hm_04_让元组作为返回值.py
  测量开始
  测量结束
  (50, 100)
  <class 'tuple'>
  ```

- **如果函数返回的类型是元组，同时希望单独处理元组中的元素，可以使用多个变量（多个变量之间使用 `，`分隔），一次接收函数的返回值**

  ```python
  def measure():
      """测量温度和湿度"""
      print("测量开始")
      temp = 50
      wetness = 100
      print("测量结束")
      return temp, wetness
  
  
  result = measure()
  print(result)
  print(type(result))
  
  print(result[0])
  print(result[1])
  
  gl_temp, gl_wetness = measure()
  print(gl_temp)
  print(gl_wetness)
  
  /usr/local/bin/python3 /home/zcb/python_study/07_语法进阶/hm_04_让元组作为返回值.py
  测量开始
  测量结束
  (50, 100)
  <class 'tuple'>
  50
  100
  测量开始
  测量结束
  50
  100
  
  Process finished with exit code 0
  ```

**不可变和可变的参数**

- 在函数内部，针对参数使用**赋值语句**，不会影响调用函数时传递的**实参变量**

- 不论传递的参数是可变还是不可变，只要针对参数使用赋值语句，只会在函数内部修改局部变量的引用，不会影响到函数外部的变量的引用

  ```python
  def demo1(num, num_list):
      print("函数执行开始")
      num = 99
      num_list = [1, 2, 3]
      print(num)
      print(num_list)
      print("函数执行结束")
  
  
  gl_num = 100
  gl_num_list = [4, 5, 6]
  demo1(gl_num, gl_num_list)
  print(gl_num)
  print(gl_num_list)
  
  /usr/local/bin/python3 /home/zcb/python_study/07_语法进阶/hm_05_不可变和可变参数.py
  函数执行开始
  99
  [1, 2, 3]
  函数执行结束
  100
  [4, 5, 6]
  
  Process finished with exit code 0
  ```

- 如果传递的函数参数是**可变类型**，在函数内部通过**方法**修改了数据的内容，**同样会影响到外部的数据**

  ```python
  def demo1(num_list):
      print("函数执行开始")
      num_list.append(9)
      print(num_list)
      print("函数执行结束")
  
  
  gl_num_list = [1, 2, 3]
  demo1(gl_num_list)
  print(gl_num_list)
  
  /usr/local/bin/python3 /home/zcb/python_study/07_语法进阶/hm_06_使用方法修改变量的内容.py
  函数执行开始
  [1, 2, 3, 9]
  函数执行结束
  [1, 2, 3, 9]
  
  Process finished with exit code 0
  ```

- 列表变量 调用`+=`本质上是在执行列表变量的 `extend`方法，不会修改变量的引用

  ```python
  def demo1(num, num_list):
      print("执行开始")
      num += num
      # 本质上是调用列表的 expend方法,同时改变函数内外的变量值,但是不改变引用
      num_list += num_list
      # num_list.extend(num_list)
      print(num)
      print(num_list)
      print("执行结束")
  
      
  gl_num = 100
  gl_num_list = [1, 2, 3]
  demo1(gl_num, gl_num_list)
  print(gl_num)
  print(gl_num_list)
  
  
  /usr/local/bin/python3 /home/zcb/python_study/07_语法进阶/hm_07_加等于(面试题).py
  执行开始
  200
  [1, 2, 3, 1, 2, 3]
  执行结束
  100
  [1, 2, 3, 1, 2, 3]
  
  Process finished with exit code 0
  ```

**缺省参数**

- 定义函数时，可以给**某个参数指定一个默认值**，具有默认值的参数叫做**缺省参数**

- 调用函数时，如果没有传入**缺省参数**的值，则在函数内部使用定义函数时指定的**参数默认值**

- **将常见的值设置为参数的缺省值**，从而**简化函数调用**

  ```python
  def print_info(name, gender=True):
      """
      :param name: 班上同学的姓名
      :param gender:  True 男孩 False 女孩
      """
      gender_text = "男生"
      if not gender:
          gender_text = "女生"
  
      print("%s 是 %s" % (name, gender_text))
  
  
  print_info("xiaoming")
  print_info("xiaomei", False)
  
  /usr/local/bin/python3 /home/zcb/python_study/07_语法进阶/hm_08_函数的缺省参数定义.py
  xiaoming 是 男生
  xiaomei 是 女生
  
  Process finished with exit code 0
  ```

- **缺省参数的定义位置：必须保证带默认值的缺省参数在函数参数列表的末尾**

- 在**调用函数时，如果有多个缺省参数，需要指定参数名**这样解释器才能知道参数的对应关系

  ![image-20220507203408749](C:\Users\28647\AppData\Roaming\Typora\typora-user-images\image-20220507203408749.png)

  ```python
  def print_info(name, title='', gender=True):
      """
  
      :param name: 班上同学的名字
      :param title: 该同学在班里的职位
      :param gender: True男 False女
      """
      gender_text = "男生"
      if not gender:
          gender_text = "女生"
  
      print("[%s]%s 是 %s" % (title, name, gender_text))
  
  
  print_info("xiaoming")
  print_info("xiaomei", gender=False)
  
  /usr/local/bin/python3 /home/zcb/python_study/07_语法进阶/hm_09_函数缺省参数注意事项.py
  []xiaoming 是 男生
  []xiaomei 是 女生
  
  Process finished with exit code 0
  ```
  

**多值参数**

- 有时一个函数需要处理的参数个数可能是不确定的，这个时候就可以使用多值参数
- `python`中有**两种**多值参数
  - 参数名前增加**一个 **`*`可以接收**元组**
  - 参数名前增加**两个**`*`可以接收**字典**
- 一般在给多值参数命名时，习惯使用以下两个名字
  - `*args` --存放**元组**参数，前面有一个 `*`
  - `**kwargs` --存放**字典**参数，前面有两个 `*`
- `args`是 `arguments`的缩写，有变量的含义
- `kw`是 `keyword`的缩写，可以记忆**键值对参数**

```python
def demo1(num, *args, **kwargs):
    print(num)
    print(args)
    print(kwargs)


demo1(1, 2, 3, 4, name="xiaoming", age=18)

/usr/local/bin/python3 /home/zcb/python_study/07_语法进阶/hm_10_多值参数.py
1
(2, 3, 4)
{'name': 'xiaoming', 'age': 18}

Process finished with exit code 0
```

```python
def sum_number(*args):
    sum = 0
    for num in args:
        sum += num

    return sum


gl_sum = sum_number(1, 2, 3, 4, 5, 10)
print(gl_sum)

/usr/local/bin/python3 /home/zcb/python_study/07_语法进阶/hm_11_多值参数求和.py
25

Process finished with exit code 0
```

**元组和字典的拆包**

- 在调用带有多指参数的函数时，如果希望：**将一个元组变量传递给 `args`,将一个字典变量传递给 `kwargw`，就可以使用拆包。**
- **拆包的方式**：**在元组变量前，加一个 `*`，在字典变量前加两个 `*`**

```python
def demo1(*args, **kwargs):
    print(args)
    print(kwargs)


gl_args = (1, 2, 3, 4)
gl_kwargs = {"name": "xiaming"}

# demo1(gl_args, gl_kwargs)
# 拆包语法
demo1(*gl_args, **gl_kwargs)

# 拆包语法等同于下式:
demo1(1, 2, 3, 4, name = "xiaoming")

/usr/local/bin/python3 /home/zcb/python_study/07_语法进阶/hm_12_拆包.py
(1, 2, 3, 4)
{'name': 'xiaming'}
(1, 2, 3, 4)
{'name': 'xiaoming'}

Process finished with exit code 0
```

**函数的递归**

- 递归函数的特点：**一个函数内部，自己调用自己**
- 函数内部的代码是相同的，只是针对**参数**不同，处理的结果不同
- 当**参数满足一个条件**时，函数不再执行，此操作通常被称为递归的出口，否则会出现死循环

```python
def demo1(num):
    print(num)
    # 递归的出口,位置错误或者设置错误会出现死循环
    if num == 1:
        return
    # 函数递归
    demo1(num - 1)


demo1(3)

/usr/local/bin/python3 /home/zcb/python_study/07_语法进阶/hm_13_函数递归.py
3
2
1

Process finished with exit code 0
```

```python
def sum_number(num):
    if num == 1:
        return 1
    temp = sum_number(num - 1)
    return temp + num


gl_sum = sum_number(5)
print(gl_sum)

/usr/local/bin/python3 /home/zcb/python_study/07_语法进阶/hm_14_函数递归实现数字累加.py
15

Process finished with exit code 0
```

**面向对象的三大特性**

- **封装：根据职责将属性和方法封装到一个抽象的类中**
- **继承：实现代码的宠用，相同的代码不需要重复的编写**
- **多态：不同的对象调用相同的方法，产生不同的执行结果，增加代码的灵活度**

**面向对象基本语法**

- 在 `python`中，**对象几乎无处不在**，之前学习的**变量、数据、函数**都是对象
- 在 `python`中可以使用以下两种方法验证：
  - 在**标识符/数据**后输入一个 `.`然后按下 `tab`键， `ipython3`会提示该对象能够调用的**方法列表**
  - 使用内置函数**dir**传入**标识符/数据**，可以查看对象内的**所有属性及方法**
  - `_方法名_`格式的方法是 `python`提供的 **内置方法/属性**

```python
In [2]: def demo1():
   ...:     "这是函数注释"
   ...:     print("hello world")
   ...: 
In [3]: dir(demo1)
Out[3]: 
['__annotations__',
 '__call__',
 '__class__',
 '__closure__',
 '__code__',
 '__defaults__',
 '__delattr__',
 '__dict__',
 '__dir__',
 '__doc__',
 '__eq__',
 '__format__',
 '__ge__',
 '__get__',
 '__getattribute__',
 '__globals__',
 '__gt__',
 '__hash__',
 '__init__',
 '__kwdefaults__',
 '__le__',
 '__lt__',
 '__module__',
 '__name__',
 '__ne__',
 '__new__',
 '__qualname__',
 '__reduce__',
 '__reduce_ex__',
 '__repr__',
 '__setattr__',
 '__sizeof__',
 '__str__',
 '__subclasshook__']
```

**封装：创建只包含方法的类和对象**

- `python`中要创建一个值包含方法的类，语法格式如下：

  ```python
  class 类名：
  	def 方法1（self，参数列表）
  		pass
  	def 方法1（self，参数列表）
  		pass	
  ```

- **方法**的定义格式和之前学过的**函数**几乎一样

- 区别在于第一个参数必须是 `self`

- 类的命名规则要符合**大驼峰命名法**

- 定义类完成之后，可以使用这个类创建对象，语法格式如下：

  ```python
  对象变量 = 类名 （）
  ```

  ```python
  # 创建猫类
  # 创建猫类
  class Cat:
      def eat(self):
          print("小猫爱吃鱼")
  
      def drink(self):
          print("小猫要喝水")
  
  
  # 利用猫类创建对象
  Tom = Cat()
  Tom.eat()
  Tom.drink()
  print(Tom)
  
  addr = id(Tom)
  print("%d" % addr)
  
  
  /usr/local/bin/python3.10 /home/zcb/python_study/08_面向对象基础/hm_01_定义类和对象.py
  小猫爱吃鱼
  小猫要喝水
  <__main__.Cat object at 0x7fa8f4fa7fa0>
  140363641290656
  
  Process finished with exit code 0
  ```

- 使用 `print`输出**对象变量**，默认情况下是能够输出这个变量的引用的对象，是由哪一个类创建的，以及在内存中的地址（十六进制）

  - `%d`输出**10进制**数字
  - `%x`输出**16进制**数字

- 使用同一个类创建的不同对象，不是同一个对象，其内存地址不同

  ```python
  # 创建猫类
  class Cat:
      def eat(self):
          print("小猫爱吃鱼")
  
      def drink(self):
          print("小猫要喝水")
  
  
  # 利用猫类创建第一个对象
  Tom = Cat()
  Tom.eat()
  Tom.drink()
  print(Tom)
  
  # 利用猫类创建第二个对象
  lazy_cat = Cat()
  lazy_cat.eat()
  lazy_cat.drink()
  print(lazy_cat)
  
  /usr/local/bin/python3.10 /home/zcb/python_study/08_面向对象基础/hm_02_创建不同对象.py
  小猫爱吃鱼
  小猫要喝水
  <__main__.Cat object at 0x7fb07ecebfd0>
  小猫爱吃鱼
  小猫要喝水
  <__main__.Cat object at 0x7fb07ecebe80>
  
  Process finished with exit code 0
  ```

**给对象增加属性**

- 在 `python`中可以在**类的外部代码中直接通过 `.`设置一个属性**就可以给对象设置属性，但是***不推荐使用**。因为：对象属性的封装应该分装在类的内部

  ```python
  # 创建猫类
  class Cat:
      def eat(self):
          print("小猫爱吃鱼")
  
      def drink(self):
          print("小猫要喝水")
  
  
  # 利用猫类创建第一个对象
  Tom = Cat()
  # 给对象增加属性
  Tom.name = "Tom"
  Tom.eat()
  Tom.drink()
  print(Tom)
  
  # 利用猫类创建第二个对象
  lazy_cat = Cat()
  # 给对象增加属性
  lazy_cat.name = "lazy_cat"
  lazy_cat.eat()
  lazy_cat.drink()
  print(lazy_cat)
  ```

**在外界设置属性存在的问题**

- **如果先调用方法（方法中包含属性或需要用到属性），再设置属性，代码就会报错**

- 所以，在日常开发中不建议在**类的外部**给对象增加属性，如果在运行时，没有找到属性，程序就会报错

- 对象所包含的属性，应该**封装在类的内部**

  ```python
  # 创建猫类
  class Cat:
      def eat(self):
          # 哪个对象调用方法,self就是哪个对象的引用
          print("%s爱吃鱼" % self.name)
  
      def drink(self):
          print("%s要喝水" % self.name)
  
  
  # 利用猫类创建第一个对象
  Tom = Cat()
  # # 给对象增加属性
  # Tom.name = "Tom"
  print(Tom.name)
  Tom.eat()
  Tom.drink()
  print(Tom)
  # 给对象增加属性
  Tom.name = "Tom"
  
  /usr/local/bin/python3.10 /home/zcb/python_study/08_面向对象基础/hm_04_在外界设置属性存在的问题.py
  Traceback (most recent call last):
    File "/home/zcb/python_study/08_面向对象基础/hm_04_在外界设置属性存在的问题.py", line 15, in <module>
      print(Tom.name)
  AttributeError: 'Cat' object has no attribute 'name'
  
  Process finished with exit code 1
  ```

**初始化方法**

- 当使用 `类名（）`创建对象时，会**自动**执行以下操作：

  - 为对象在内存中**分配空间**--创建对象
  - 为对象的属性**设置初始值**--初始化方法（init）
  - 这个**初始化方法**就是 `__init__`方法，该方法是对象的内置方法

  ```python
  class Cat:
      def __init__(self):
          print("创建对象时u自动调用的方法")
  
  tom = Cat()
  
  /usr/local/bin/python3.10 /home/zcb/python_study/08_面向对象基础/hm_05_初始化方法.py
  创建对象时u自动调用的方法
  
  Process finished with exit code 0
  ```

**在初始化方法内部定义属性**

- 在 `__init__`方法内部使用 `self.属性名 = 属性的初始值`就可以**定义属性**

- 定义属性后，再使用 `Cat`类创建的对象，都会拥有该属性

  ```python
  class Cat:
      def __init__(self):
          print("创建对象时自动调用的方法")
          self.name = "tom"
  
      def eat(self):
          print("%s 爱吃鱼" % self.name)
  
      def drink(self):
          print("%s 要喝水" % self.name)
  
  
  tom = Cat()
  tom.eat()
  tom.drink()
  print(tom.name)
  
  
  /usr/local/bin/python3.10 /home/zcb/python_study/08_面向对象基础/hm_05_初始化方法.py
  创建对象时自动调用的方法
  tom 爱吃鱼
  tom 要喝水
  tom
  
  Process finished with exit code 0
  ```

**改造初始化方法--初始化的同时设置初始值**

- 在开发中，如果希望在**创建对象的同时，就设置对象的属性**，可以对 `__init__`方法进行**改造**

- 把希望设置的属性值，定义成 `__init__`方法的参数

- 在方法内部使用 `self.属性 = 形参`接收外部传递的参数

- 在创建对象时，使用 `变量名=类名（属性1，属性2..）`调用

  ```python
  class Cat:
      def __init__(self, new_name):
          print("创建对象时自动调用的方法")
          self.name = new_name
  
      def eat(self):
          print("%s 爱吃鱼" % self.name)
  
      def drink(self):
          print("%s 要喝水" % self.name)
  
  
  tom = Cat("tom")
  tom.eat()
  tom.drink()
  
  
  lazy_cat = Cat("lazy_cat")
  lazy_cat.eat()
  lazy_cat.drink()
  
  /usr/local/bin/python3.10 /home/zcb/python_study/08_面向对象基础/hm_06_改造初始化方法.py
  创建对象时u自动调用的方法
  tom 爱吃鱼
  tom 要喝水
  创建对象时u自动调用的方法
  lazy_cat 爱吃鱼
  lazy_cat 要喝水
  
  Process finished with exit code 0
  ```

**--del--方法**

- 在 `python`中，使用 `类名（）`创建对象时，为对象**分配完空间后，自动调用--init--方法**
- 当一个**对象从内存中销毁**前，会**自动调用--del--方法**
- `__init__`改造初始化方法，可以让创建对象更加灵活
- `__del__`在对象销毁前可以做一些事情

```python
class Cat:
    def __init__(self, new_name):
        print("我来了")

    def __del__(self):
        print("我走了")


tom = Cat("tom")
# 对象内存被系统回收时,自动调用del方法
del tom
print("-" * 50)

/usr/local/bin/python3.10 /home/zcb/python_study/08_面向对象基础/hm_07_del方法.py
我来了
我走了
--------------------------------------------------

Process finished with exit code 0

```

**--str--方法**

- 在 `python`中，使用`print`输出**对象变量**，默认情况下，会输出这个变量**引用的对象**是**由哪个类创建的对象，以及在内存中的地址（十六进制）**
- 如果在开发中，希望使用 `print`输出**对象变量**时，能够打印**自定义的内容**，就可以利用 `--str--`方法
- **`--str--`方法必须返回一个字符串**

```python
class Cat:
    def __init__(self, new_name):
        self.name = new_name
        print("小猫 %s 来了" % self.name)

    def __del__(self):
        print("小猫 %s 走了" % self.name)

    def __str__(self):
        return "我是小猫 %s" % self.name


tom = Cat("tom")
print("-" * 50)
print(tom)

/usr/local/bin/python3.10 /home/zcb/python_study/08_面向对象基础/hm_08_str方法.py
小猫 tom 来了
--------------------------------------------------
我是小猫 tom
小猫 tom 走了

Process finished with exit code 0
```

```python
class Person:
    def __init__(self, person_name, person_weight):
        self.name = person_name
        self.weight = person_weight
        print("我叫%s我的体重是%.2f" % (self.name, self.weight))

    def __str__(self):
        return "此时%s的体重为:%.2f" % (self.name, self.weight)

    def eat(self):
        self.weight += 1

    def run(self):
        self.weight -= 0.5


xiaoming = Person("小明", 75.5)
xiaoming.eat()
xiaoming.run()
print(xiaoming)

xiaomei = Person("小美", 45)
xiaomei.run()
xiaomei.eat()
print(xiaomei)

/usr/local/bin/python3.10 /home/zcb/python_study/08_面向对象基础/hm_09_小明爱跑步.py
我叫小明我的体重是75.50
此时小明的体重为:76.00
我叫小美我的体重是45.00
此时小美的体重为:45.50

Process finished with exit code 0
```

- 在**对象的方法内部，是可以直接访问对象的属性的**
- **在多个对象之间，属性是不会互相干扰的**

```python
class HouseItem:
    def __init__(self, HouseItem_name, HouseItem_area):
        self.name = HouseItem_name
        self.area = HouseItem_area

    def __str__(self):
        return "%s占地面积是%.2f" % (self.name, self.area)


class House:
    def __init__(self, house_type, area):
        self.type = house_type
        self.area = area
        self.free_area = area
        self.item_list = []

    def add_item(self, item):
        print("%s中添加了%s" % (self.type, item.name))
        if item.area > self.free_area:
            print("%s家具面积太大了,无法添加" % item.name)
            return

        self.item_list.append(item.name)
        self.free_area -= item.area

    def __str__(self):
        return "现在房子 [%s] 剩下的空余面积为 [%.2f] 添加的家具有%s" % \
               (self.type, self.free_area, self.item_list)


bed = HouseItem("席梦思", 4)
print(bed)
chest = HouseItem("衣柜", 2)
print(chest)
table = HouseItem("餐桌", 1.5)
print(table)

home = House("爱的小窝", 120)
home.add_item(bed)
home.add_item(chest)
home.add_item(table)
print(home)

/usr/local/bin/python3.10 /home/zcb/python_study/08_面向对象基础/hm_10_添加家具.py
席梦思占地面积是4.00
衣柜占地面积是2.00
餐桌占地面积是1.50
爱的小窝中添加了席梦思
爱的小窝中添加了衣柜
爱的小窝中添加了餐桌
现在房子 [爱的小窝] 剩下的空余面积为 [112.50] 添加的家具有['席梦思', '衣柜', '餐桌']

Process finished with exit code 0
```

- **在定义属性时，如果不知道设置什么类型的类为初始值时，可以将属性赋值为 `None`**

- **`None`关键字表示什么都没有**

- **表示一个空对象，没有方法和属性，是一个特殊的常量**

- **可以将 `None`赋值给任何一个变量**

  ```python
  class Gun:
      def __init__(self, model):
          self.model = model
          self.bullet_count = 0
  
      def add_bullet(self, count):
          self.bullet_count += count
  
      def shoot(self):
          if self.bullet_count <= 0:
              print("[%s]没有子弹了" % self.model)
              return
  
          self.bullet_count -= 1
          print("[%s]突突突...[%d]" % (self.model, self.bullet_count))
  
  
  class Soldier:
      def __init__(self, name):
          self.name = name
          self.gun = None
  
      def fire(self):
          # 判断是否有枪
          if self.gun is None:
              print("[%s]还没有枪,没枪你让我怎么开枪" % self.name)
              return
          # 高喊口号
          print("冲啊...[%s]" % self.name)
          # 装填子弹
          self.gun.add_bullet(50)
          #  发射子弹
          self.gun.shoot()
  
  
  ak47 = Gun("AK47")
  xusanduo = Soldier("许三多")
  xusanduo.gun = ak47
  xusanduo.fire()
  print(xusanduo.gun)
  
  /usr/local/bin/python3.10 /home/zcb/python_study/08_面向对象基础/hm_11_士兵突击.py
  冲啊...[许三多]
  [AK47]突突突...[49]
  <__main__.Gun object at 0x7f3245143f10>
  
  Process finished with exit code 0
  ```

**身份运算符**

- 身份运算符用于**比较**两个对象的**内存地址**是否一致--**是否是对同一个对象的引用**

- 在 `python`中针对 `None`比较时，建议使用 `is`判断

  | 运算符 |                   描述                    |              实例               |
  | :----: | :---------------------------------------: | :-----------------------------: |
  |   is   |  is是判断两个标识符是不是引用同一个对象   |   x is y 类似id（a）== id(b)    |
  | is not | is not 是判断两个标识符是不是引用不同对象 | x is not y 类似id（a）！= id(b) |

**is和==的区别**

- `is`用于判断**两个变量**引用对象是否为同一个

- `==`用于判断**引用变量的值**是否相等

  ```python
  In [7]: b
  Out[7]: [1, 2]
  
  In [8]: a = [1 ,2, 3]
  
  In [9]: id(a)
  Out[9]: 140068426052744
  
  In [10]: id(b)
  Out[10]: 140068441769032
  
  In [11]: b.append(3)
  
  In [12]: a == b
  Out[12]: True
  
  In [13]: a is b
  Out[13]: False
      
  In [14]: a is not b
  Out[14]: True
  
  ```

**私有属性和私有方法**

- 在实际开发中，**对象**的**某些属性或方法**可能只希望**在对象的内部被使用**，而**不希望再外部被访问到**
- **私有属性**就是**对象**不希望公开的**属性**
- **私有方法**就是**对象**不希望公开的**方法**
- 定义方式：**在定义私有属性或方法的时候，再属性名或者方法名前增加两个下划线**

```python
class Woman:
    def __init__(self, name):
        self.name = name
        self.__age = 18

    def __secret(self):
        # 在对象方法的内部,可以访问对象的私有属性
        print("%s 年龄是 %d" % (self.name, self.__age))


xiaofang = Woman("小芳")
# 私有属性在对象外部不能直接访问
# print(xiaofang.__age)

# 私有方法同样不允许外界直接访问
# xiaofang.__secret()
```

**伪私有属性和私有方法**

- `python`中，并没有**真正意义的私有**
- 在给**属性，方法**命名时，实际是对**名称**做一些特殊处理，使得外界无法访问
- 想要在外界访问私有属性或者方法，需要修改名称为 `_类名__属性/方法名`
- **在日常开发中，不要使用这种方式，访问对象的私有属性或私有方法**

```python
class Woman:
    def __init__(self, name):
        self.name = name
        self.__age = 18

    def __secret(self):
        # 在对象方法的内部,可以访问对象的私有属性
        print("%s 年龄是 %d" % (self.name, self.__age))


xiaofang = Woman("小芳")
# 私有属性在对象外部不能直接访问
# print(xiaofang.__age)

# 私有方法同样不允许外界直接访问
# xiaofang.__secret()

# 伪私有属性和方法的访问方法
# 私有属性在对象外部不能直接访问 需修改属性名用于访问
print(xiaofang._Woman__age)

# 私有方法同样不允许外界直接访问 需修改方法名用于访问
xiaofang._Woman__secret()

/usr/local/bin/python3.10 "/home/zcb/python_study/08_面向对象基础/hm_12_ 私有属性和方法.py"
18
小芳 年龄是 18

Process finished with exit code 0
```

**面向对象的三大特性**

- **封装：根据职责将属性和方法封装到一个抽象的类中**
- **继承：实现代码的宠用，相同的代码不需要重复的编写**
- **多态：不同的对象调用相同的方法，产生不同的执行结果，增加代码的灵活度**

**继承**

- **继承的概念：子类拥有父类所有的方法和属性**

- **继承的语法：**

  ```python
  class 类名（父类名）：
  	pass
  ```

- **子类继承自父类，可以直接享受父类中已经封装好的方法，不需要再次开发**

- **子类中应该有不同于父类的特殊职责，需要封装子类特有的属性和方法**

- **子类中拥有父类以及父类的父类中封装的所有属性以及方法**

```python
class Animal:
    def eat(self):
        print("吃---")

    def drink(self):
        print("喝---")

    def run(self):
        print("跑---")

    def sleep(self):
        print("睡---")


class Dog(Animal):
    def bark(self):
        print("小狗旺旺叫")


wangcai = Dog()
wangcai.sleep()
wangcai.run()
wangcai.eat()
wangcai.drink()
wangcai.bark()

/usr/local/bin/python3.10 /home/zcb/python_study/09_面向对象特性/hm_01_继承语法.py
睡---
跑---
吃---
喝---
小狗旺旺叫

Process finished with exit code 0
```

- **`Dog`类是 `Animal`类的子类， `Animal`类是`Dog`类的父类，`Dog`类从 `Animal`类继承**
- **`Dog`类是 `Animal`类的派生类， `Animal`类是`Dog`类的基类，`Dog`类从 `Animal`类派生**

```python
class Animal:
    def eat(self):
        print("吃---")

    def drink(self):
        print("喝---")

    def run(self):
        print("跑---")

    def sleep(self):
        print("睡---")


class Dog(Animal):
    def bark(self):
        print("小狗旺旺叫")


class XiaoTianQuan(Dog):
    def fly(self):
        print(" i can fly")


xtq = XiaoTianQuan()
xtq.fly()
xtq.bark()
xtq.run()
xtq.sleep()
xtq.drink()
xtq.eat()


/usr/local/bin/python3.10 /home/zcb/python_study/09_面向对象特性/hm_02_继承的传递.py
 i can fly
小狗旺旺叫
跑---
睡---
喝---
吃---

Process finished with exit code 0
```

**继承中方法的重写**

- **当父类的方法实现不能满足子类的需求时，可以对该方法进行重写（override）**

- **实现方式：在子类中定义一个和父类方法同名的方法并实现**

- **如果子类中重写了父类的方法，在使用子类对象调用方法时，会调用子类中重写的方法**

  ```python
  class Animal:
      def eat(self):
          print("吃---")
  
      def drink(self):
          print("喝---")
  
      def run(self):
          print("跑---")
  
      def sleep(self):
          print("睡---")
  
  
  class Dog(Animal):
      def bark(self):
          print("小狗旺旺叫")
  
  
  class XiaoTianQuan(Dog):
      def fly(self):
          print(" i can fly")
  
      def bark(self):
          print("神狗怒吼")
  
  
  
  xtq = XiaoTianQuan()
  xtq.bark()
  
  /usr/local/bin/python3.10 /home/zcb/python_study/09_面向对象特性/hm_03_方法重写.py
  神狗怒吼
  
  Process finished with exit code 0
  ```

**继承中父类方法扩展**

- **如果在开发中，子类的方法实现中包含父类的方法实现，父类原本封装的方法实现时子类方法的一部分**
- **方法扩展的步骤：在子类中重写父类方法；使用 `super().父类方法`来调用父类方法的执行；针对子类的其他需求，编写子类方法的特有需求实现**
- **关于 `super`：在 `python`中 `super`是一个特殊的类； `super()`就是使用 `super`类创建出来的对象；最常使用的场景就是在重写父类方法时，调用在父类中封装的方法实现**

```python
class Animal:
    def eat(self):
        print("吃---")

    def drink(self):
        print("喝---")

    def run(self):
        print("跑---")

    def sleep(self):
        print("睡---")


class Dog(Animal):
    def bark(self):
        print("小狗旺旺叫")


class XiaoTianQuan(Dog):
    def fly(self):
        print(" i can fly")

    def bark(self):
        super().bark()
        print("神狗怒吼")



xtq = XiaoTianQuan()
xtq.bark()

/usr/local/bin/python3.10 /home/zcb/python_study/09_面向对象特性/hm_04_父类方法扩展.py
小狗旺旺叫
神狗怒吼

Process finished with exit code 0
```

**父类的私有属性和私有方法**

- **子类对象不能在自己的方法内部，直接访问父类的私有属性或者私有方法**
- **子类对象可以通过父类的公有方法间接访问到私有属性或私有方法**
- **私有属性、方法是对象的隐私，不对外公开，外界以及子类都不能直接访问**

```python
class A():
    def __init__(self):
        self.num1 = 100
        self.__num2 = 200

    def __test(self):
        print("私有方法调用打印私有属性 %d" % self.__num2)

    def test(self):
        print("普通方法调用打印私有属性 %d" % self.__num2)


class B(A):
    def demo(self):
        # 在子类的方法中,不能访问父类的私有属性
        print(self.__num)
        # 在子类的方法中,不能调用父类的私有方法
        self.__test()


b = B()
# 在外界不能字节访问对象的私有属性/调用私有方法
# print(b.__num)
# b.__test()

b.demo()
```

```python
class A():
    def __init__(self):
        self.num1 = 100
        self.__num2 = 200

    def __test(self):
        print("私有方法调用打印私有属性 %d" % self.__num2)

    def test(self):
        print("普通方法调用打印私有属性 %d" % self.__num2)
        self.__test()


class B(A):
    def demo(self):

        self.test()

b = B()
b.demo()

/usr/local/bin/python3.10 /home/zcb/python_study/09_面向对象特性/hm_05_父类的私有属性和私有方法.py
普通方法调用打印私有属性 200
私有方法调用打印私有属性 200

Process finished with exit code 0
```

**多继承：子类可以拥有多个父类，并且具有所有父类的属性和方法**

```python
class 子类名（父类1， 父类2...）
	pass
```

```python
class A:
    def test(self):
        print("A类的test方法调用")


class B:
    def demo(self):
        print("B类的demo方法调用")


class C(A, B):
    def hello(self):
        print("C类自身定义的方法")


c = C()
c.test()
c.demo()
c.hello()

/usr/local/bin/python3.10 /home/zcb/python_study/09_面向对象特性/hm_06_多继承.py
A类的test方法调用
B类的demo方法调用
C类自身定义的方法

Process finished with exit code 0
```

- **在多继承中，不同的父类中可能存在同名的方法，子类在调用时就会根据继承先后顺序进行调用，在开发过程中，如果父类之间存在同名的属性或者方法，应该尽量避免使用多继承。**

```python
class A:
    def test(self):
        print("A类的test方法调用")

    def demo(self):
        print("A类的demo方法调用")


class B:
    def test(self):
        print("B类的test方法调用")

    def demo(self):
        print("B类的demo方法调用")


# 先继承的是A类,所以调用的是A类的方法  如果括号中先写的是B就调用的是B的方法
class C(A, B):
    pass


c = C()
c.test()
c.demo()

/usr/local/bin/python3.10 /home/zcb/python_study/09_面向对象特性/hm_07_多继承注意事项.py
A类的test方法调用
A类的demo方法调用

Process finished with exit code 0
```

- **`python`中针对类提供了一个内置属性 `__mro__`可以查看方法的搜索顺序**

- `__mro__`主要用于在多继承时判断方法、属性的调用路径

  ```python
  class A:
      def test(self):
          print("A类的test方法调用")
  
      def demo(self):
          print("A类的demo方法调用")
  
  
  class B:
      def test(self):
          print("B类的test方法调用")
  
      def demo(self):
          print("B类的demo方法调用")
  
  
  # 先继承的是A类,所以调用的是A类的方法  如果括号中先写的是B就调用的是B的方法
  class C(A, B):
      pass
  
  
  c = C()
  c.test()
  c.demo()
  
  
  # 确定C类对象调用方法的顺序
  print(C.__mro__)
  
  /usr/local/bin/python3.10 /home/zcb/python_study/09_面向对象特性/hm_07_多继承注意事项.py
  A类的test方法调用
  A类的demo方法调用
  (<class '__main__.C'>, <class '__main__.A'>, <class '__main__.B'>, <class 'object'>)
  
  Process finished with exit code 0
  ```

**多态**

- **多态是指不同的子类对象调用相同的父类方法，产生不同的执行结果**
- **多态可以增加代码的灵活度**
- **多态以继承和重写父类方法为前提**
- **多态时调用类中方法的技巧，不会影响到类的内部设计**

```python
class Dog:
    def __init__(self, name):
        self.name = name

    def game(self):
        print("普通的狗%s只是简单的玩耍" % self.name)


class XiaoTianQuan(Dog):
    def game(self):
        print("哮天犬%s需要在天上玩耍" % self.name)


class Person:
    def __init__(self, name):
        self.name = name

    def game_with_dog(self, dog):
        print("%s和%s快乐的玩耍" % (self.name, dog.name))
        dog.game()


wangcai = Dog("wangcai")
feitianwangcai = XiaoTianQuan("feitianwangcai")
xiaoming = Person("xiaoming")
xiaoming.game_with_dog(wangcai)
xiaoming.game_with_dog(feitianwangcai)

/usr/local/bin/python3.10 /home/zcb/python_study/09_面向对象特性/hm_08_多态演练.py
xiaoming和wangcai快乐的玩耍
普通的狗wangcai只是简单的玩耍
xiaoming和feitianwangcai快乐的玩耍
哮天犬feitianwangcai需要在天上玩耍

Process finished with exit code 0

```

**实例**

- **使用面向对象开发的第一步是设计类**
- **使用类名（）创建对象，创建对象时解释器有两步工作：在内存中为对象分配空间；调用初始化方法 `__init__`为对象初始化**
- **对象创建后，内存中就有了一个对象实实在在的存在**
- **创建出来的对象叫做类的实例**
- **创建对象的动作叫做实例化**
- **对象的属性叫做实例属性**
- **对象调用的方法叫做实例方法**
- **对象各自拥有自己的实例属性**
- **调用对象方法可以通过 `self`访问自己的属性、调用自己的方法**
- **每个对象都有自己独立的内存空间，保存各自不同的属性**
- **多个对象的方法，在内存中只有一份，在调用方法时，需要把对象的引用传递到方法内部**

**类对象**

- **`python`中一切皆对象**
- **`class AAA：`定义的类属于类对象**
- **`obj1 = AAA()`属于实例对象**
- **在程序运行时，类同样会被加载到内存**
- **运行程序时，类对象在内存中只有一份，但是使用一个类可以创建出很多个对象实例**
- **除了封装实例的属性和方法外，类对象还可以拥有自己的属性和方法：类属性；类方法**
- **通过类名.的方式可以访问类的属性或者调用类的方法**

**类属性和实例属性**

- **类属性就是在类对象中定义的属性**
- **使用赋值语句在 `class`关键字下方可以定义类属性**
- **通常用来记录与这个类型相关的特征**
- **类属性不会用于记录具体对象的特征**

```python
class Tool:
    # 定义类对象属性
    count = 0

    def __init__(self, name):
        Tool.name = name
        
        # 前面必须加类名
        Tool.count += 1


fuzi = Tool("斧子")
shuitong = Tool("水桶")
banshou = Tool("扳手")

# 访问类对象属性
print(Tool.count)

/usr/local/bin/python3.10 /home/zcb/python_study/09_面向对象特性/hm_09_类属性定义.py
3

Process finished with exit code 0
```

**属性的获取机制**

- **在 `python`中属性的获取存在一个向上查找机制**

![image-20220511202008361](C:\Users\28647\AppData\Roaming\Typora\typora-user-images\image-20220511202008361.png)

- **因此，访问类属性有两种方式：类名.类属性；对象.类属性(不推荐)**
- **如果使用 `对象.类属性 = 值`赋值语句，只会给对象添加一个属性，而不会影响类属性的值**

```python
class Tool:
    # 定义类对象属性
    count = 0

    def __init__(self, name):
        Tool.name = name

        # 前面必须加类名
        Tool.count += 1


fuzi = Tool("斧子")
shuitong = Tool("水桶")
banshou = Tool("扳手")

# 访问类对象属性  正常输出是3
print(banshou.count)
/usr/local/bin/python3.10 /home/zcb/python_study/09_面向对象特性/hm_10_类属性获取机制.py
3

Process finished with exit code 0


### 对象属性赋值###

class Tool:
    # 定义类对象属性
    count = 0

    def __init__(self, name):
        Tool.name = name

        # 前面必须加类名
        Tool.count += 1


fuzi = Tool("斧子")
shuitong = Tool("水桶")
banshou = Tool("扳手")

# 访问类对象属性  正常输出是3
# print(banshou.count)

# 定义一个对象属性后再输出
banshou.count = 99
print(banshou.count)
/usr/local/bin/python3.10 /home/zcb/python_study/09_面向对象特性/hm_10_类属性获取机制.py
99

Process finished with exit code 0
```

**类方法**

- **类属性就是针对类对象定义的属性**
- **使用赋值语句语句 `class`关键字下方可以定义类属性**
- **类属性用于记录与这个类相关的特征**
- **类方法就是针对类对象定义的方法**
- **在类方法内部可以直接访问类属性或者调用其他的类方法**

```python
@classmethod
def 类方法名称（cls）：
	pass
```

- **类方法需要用 `@classmethod`来标识，告诉解释器这是一个类方法**

- **类方法的第一个参数应该是 `cls`**

- **由哪个类调用的方法，方法内的 `cls`就是哪个类的引用**

- **这个参数和实例方法中的第一个参数 `self`类似**

- **通过类名，调用类方法，调用方法时不需要传递 `cls`参数**

- **在方法内部：可以通过 `cls`访问类的属性，也可以通过 `cls`调用其他方法**

  ```python
  class Tool:
      # 定义类对象属性
      count = 0
  
      # 定义类方法
      @classmethod
      def show_tool_count(cls):
          print(Tool.count)
  
      def __init__(self, name):
          Tool.name = name
  
          # 前面必须加类名
          Tool.count += 1
  
  
  fuzi = Tool("斧子")
  shuitong = Tool("水桶")
  banshou = Tool("扳手")
  
  print(Tool.count)
  # 调用类方法
  Tool.show_tool_count()
  
  /usr/local/bin/python3.10 /home/zcb/python_study/09_面向对象特性/hm_11_类方法.py
  3
  3
  
  Process finished with exit code 0
  ```

**静态方法**

- **在开发过程中，如果需要在类中封装一个方法，这个方法：既不需要访问实例属性或者调用实例方法，也不需要访问类属性或者调用类方法，这个时候就可以把这个方法封装成一个静态方法**

- 语法如下：

  ```python
  @staticmethod
  def 静态方法名（）：
  	pass
  
  ```

- **静态方法需要使用 `@staticmethod`来标识，告诉解释器这是一个静态方法**

- **通过类名.调用静态方法，不需要创建具体对象**

  ```python
  class Dog:
      @staticmethod
      def run():
          print("dog is running")
  
  
  Dog.run()
  
  /usr/local/bin/python3.10 /home/zcb/python_study/09_面向对象特性/hm_12_静态方法.py
  dog is running
  
  Process finished with exit code 0
  ```
  

```python
class Game:
    top_score = 0

    @staticmethod
    def show_help():
        print("打印游戏帮助")

    @classmethod
    def show_top_score(cls):
        print("游戏最高分为: %d" % cls.top_score)

    def __init__(self, player_name):
        self.play_name = player_name

    def start_game(self):
        print("开始当前玩家%s的游戏" % self.play_name)


Game.show_help()
Game.show_top_score()
xiaoming = Game("小明")
xiaoming.start_game()

/usr/local/bin/python3.10 /home/zcb/python_study/09_面向对象特性/hm_13_方法综合实例.py
打印游戏帮助
游戏最高分为: 0
开始当前玩家小明的游戏

Process finished with exit code 0
```

- **方法内部需要访问实例属性时定义为实例方法**
- **方法内部只需要访问类属性时定义为类方法**
- **方法内部不需要访问实例属性和类属性时定义为静态方法**
- **如果方法内部即需要访问实例属性又需要访问类属性，此时应该定义为实例方法**

**单例设计模式**

- **目的--让类创建的对象，在系统中只有唯一一个实例**
- **每次执行 `类名（）`返回的对象，内存地址都是相同的**

**--new--方法**

- **使用`类名（）`创建对象时， `python`解释器首先会调用 `__new__`方法为对象分配空间**
- **`__new__`方法是一个由 `object`基类提供的内置静态方法，主要作用为：在内存中为对象分配空间；返回对象的引用** 
- **`python`的解释器在获得对象的引用后，将引用作为第一个参数，传递给 `__init__`方法**
- **重写 `__new__`方法一定要 `return super().__new__(cls)`**
- **否则 `python`的解释器得不到分配了空间的对象引用，就不会调用对象的初始化方法**
- **注意： `__new__`是一个静态方法，在调用的时候需要主动传递 `cls`参数**

```python
class MusicPlayer(object):
    def __new__(cls, *args, **kwargs):
        # 定义对象自动调用
        print("创建对象,分配内存")
        # 分配空间看方法
        instance = super().__new__(cls)
        # 返回对象的引用
        return instance

player = MusicPlayer()
print(player)

/usr/local/bin/python3.10 /home/zcb/python_study/09_面向对象特性/hm_14_new方法重写.py
创建对象,分配内存
<__main__.MusicPlayer object at 0x7fb7ee9778e0>

Process finished with exit code 0
```

**单例--让类创建的对象在系统中只有唯一的一个实例**

- **定义一个类属性，初始值是 `None`，用于记录单例对象的引用**
- **重新 `__new__`方法**
- **如果类属性 `is None`，调用父类方法分配空间，并在类属性中记录结果**
- **返回类属性中记录的对象引用**

![image-20220512202515227](C:\Users\28647\AppData\Roaming\Typora\typora-user-images\image-20220512202515227.png)

```python
class MusicPlayer(object):
    # 记录第一个被创建对象的引用
    instance = None

    def __new__(cls, *args, **kwargs):
        # 判断类属性是否是空对象
        if cls.instance is None:
            # 调用父类的方法,为第一个对象分配空间
            cls.instance = super().__new__(cls)
        # 返回类属性保存的引用
        return cls.instance


player = MusicPlayer()
print(player)
player2 = MusicPlayer()
print(player2)

/usr/local/bin/python3.10 /home/zcb/python_study/09_面向对象特性/hm_15_单例.py
<__main__.MusicPlayer object at 0x7f66c9e17eb0>
<__main__.MusicPlayer object at 0x7f66c9e17eb0>

Process finished with exit code 0
```

**只执行一次初始化工作**

- **定义一个类属性 `init_flag`标记是否执行过初始化动作，初始值为 `False`**
- **在 `__init__`方法中，判断 `init_flag`，如果为`False`就执行初始化动作**
- **然后 `init_flag`设置为 `True`**
- **再次自动调用 `__init__`方法时，初始化动作就不会再被执行了**

```python
class MusicPlayer(object):
    # 记录第一个被创建对象的引用
    instance = None
    init_flag = False

    def __new__(cls, *args, **kwargs):
        # 判断类属性是否是空对象
        if cls.instance is None:
            # 调用父类的方法,为第一个对象分配空间
            cls.instance = super().__new__(cls)
        # 返回类属性保存的引用
        return cls.instance

    def __init__(self):

        if MusicPlayer.init_flag:
            return 
        print("初始化对象")
        MusicPlayer.init_flag = True



player = MusicPlayer()
print(player)
player2 = MusicPlayer()
print(player2)

/usr/local/bin/python3.10 /home/zcb/python_study/09_面向对象特性/hm_16_只执行一次初始化工作.py
初始化对象
<__main__.MusicPlayer object at 0x7f25856ffe20>
<__main__.MusicPlayer object at 0x7f25856ffe20>

Process finished with exit code 0
```

**异常**

- **程序在运行时，如果 `python解释器`遇到一个错误，会停止程序的执行，并且提示一些错误信息，这就是异常**
- **程序停止执行别切提示错误信息这个动作，我们通常称之为：抛出异常**
- **开发过程中，很难讲所有的特殊情况都处理的面面俱到，通过异常捕获可以针对突发事件做几种处理，从而保证程序的稳定性和健壮性**

**捕获异常**

- **在程序开发中，如果对某些代码的执行不能确定是否正确，可以添加 `try（尝试）`来捕获异常**

- **捕获异常最简单的语法格式：**

  ```python
  try:
  	尝试执行的代码
  except:
  	出现错误的处理
  ```

- **`try`尝试，下方编写要尝试的代码，不去欸的那个是否能够正常执行的代码**

- **`except`如果不是，下方编写尝试失败的方法**

  ```python
  try:
      num = int(input("请输入整数:"))
  except:
      print("你瞎嘛?看不见让你输入整数吗 憨皮")
  
  print("-"*50)
  
  /usr/local/bin/python3 /home/zcb/python_study/10_异常/hm_01_try_except.py
  请输入整数:1
  --------------------------------------------------
  
  Process finished with exit code 0
  
  /usr/local/bin/python3 /home/zcb/python_study/10_异常/hm_01_try_except.py
  请输入整数:a
  你瞎嘛?看不见让你输入整数吗 憨皮
  --------------------------------------------------
  
  Process finished with exit code 0
  ```

**错误类型捕获异常**

- **在执行程序时，可能会遇到不同类型的异常，并且需要针对不同类型的异常，做出不同的相应，这个时候就需要捕获错误类型**
- **当 `python`解释器抛出异常时，最后一行错误信息的第一个单词就是错误类型**

```python
try:
    num = int(input("请输入整数:"))
    result = 8 / num
except ZeroDivisionError:
    print("除0错误,你家除法里面被除数可以等于0吗?回去学小学数学吧 写什么代码啊")
except ValueError:
    print("你瞎嘛?看不见让你输入整数吗 憨皮")
    
/usr/local/bin/python3 /home/zcb/python_study/10_异常/hm_02_错误类型捕获类型.py
请输入整数:a
你瞎嘛?看不见让你输入整数吗 憨皮

Process finished with exit code 0

/usr/local/bin/python3 /home/zcb/python_study/10_异常/hm_02_错误类型捕获类型.py
请输入整数:0
除0错误,你家除法里面被除数可以等于0吗?回去学小学数学吧 写什么代码啊

Process finished with exit code 0
```

**捕获未知错误**

- **在开发时，需要预判到所有可能出现的错误，具有很大的难度**
- **如果希望程序无论出现任何错误，都不会因为 `python`解释器抛出异常而被终止，可以再增加一个 `except`**
- **语法如下：**

```python
excpet Exception as result:
	print("未知错误 %s" % result)
```

```python
try:
    num = int(input("请输入整数:"))
    result = 8 / num

except ValueError:
    print("你瞎嘛?看不见让你输入整数吗 憨皮")

except Exception as result:
    print("勾八我不知道你输入了什么 反正你是错了 好好看错误提示 快给老子改正确")
    print("错误提示 %s" % result)

/usr/local/bin/python3 /home/zcb/python_study/10_异常/hm_03_捕获未知错误.py
请输入整数:0
勾八我不知道你输入了什么 反正你是错了 好好看错误提示 快给老子改正确
错误提示 division by zero

Process finished with exit code 0

```

**异常捕获完整语法**

- **在实际开发中，为了能处理复杂的异常情况，完整的一场语法如下：**
- **`else`只有在没有异常时才会执行的代码**
- **`finally`无论是否有异常，都会执行的代码**

```python
try：
	# 尝试执行的代码
	pass
except 错误类型1：
	# 针对错误类型1的处理代码
	pass
except 错误类型2：
	# 针对错误类型2的处理代码
	pass	
except （错误类型3，错误类型4）
	# 针对错误类型3，4的处理代码
	pass
except Exception as result：
	# 打印错误信息
	pass
else：
	# 没有异常才会执行的代码
	pass
finally：
	# 无论是否有异常，都会执行的代码
	print（“无论是否有异常，都会执行的代码”）
```

```python
try:
    num = int(input("请输入整数:"))
    result = 8 / num

except ValueError:
    print("你瞎嘛?看不见让你输入整数吗 憨皮")

except Exception as result:
    print("勾八我不知道你输入了什么 反正你是错了 好好看错误提示 快给老子改正确")
    print("错误提示 %s" % result)

else:
    print("尝试成功,代码输入没有错误")
finally:
    print("我也不知道你输入的对不对 因为上面的代码无论对错 我都要被执行")


print("-" * 50)

/usr/local/bin/python3 /home/zcb/python_study/10_异常/hm_04_异常捕获完整语法.py
请输入整数:1
 尝试成功,代码输入没有错误
我也不知道你输入的对不对 因为上面的代码无论对错 我都要被执行
--------------------------------------------------

Process finished with exit code 0

/usr/local/bin/python3 /home/zcb/python_study/10_异常/hm_04_异常捕获完整语法.py
请输入整数:0
勾八我不知道你输入了什么 反正你是错了 好好看错误提示 快给老子改正确
错误提示 division by zero
我也不知道你输入的对不对 因为上面的代码无论对错 我都要被执行
--------------------------------------------------

Process finished with exit code 0

/usr/local/bin/python3 /home/zcb/python_study/10_异常/hm_04_异常捕获完整语法.py
请输入整数:a
你瞎嘛?看不见让你输入整数吗 憨皮
我也不知道你输入的对不对 因为上面的代码无论对错 我都要被执行
--------------------------------------------------

Process finished with exit code 0
```

**异常传递**

- **当函数/方法执行出现异常，会将异常传递给函数/方法的调用一方**
- **如果传递到主程序，仍然没有异常处理，程序才会被终止**
- **在开发中，可以在主函数中增加异常捕获**
- **而在主函数中调用的其他函数，只要出现异常，都会传递到主函数的异常捕获中**
- **这样就需要在代码增加大量的异常捕获，以此保持代码的整洁**

```python
def demo1():
    return int(input("请输入整数: "))


def demo2():
    return demo1()


try:
    print(demo2())
except Exception as result:
    print("未知错误 %s" % result)
    
    
/usr/local/bin/python3 /home/zcb/python_study/10_异常/hm_05_异常传递.py
请输入整数: 1
1

Process finished with exit code 0

/usr/local/bin/python3 /home/zcb/python_study/10_异常/hm_05_异常传递.py
请输入整数: a
未知错误 invalid literal for int() with base 10: 'a'

Process finished with exit code 0
```

**抛出raise异常**

- **在开发中，除了代码执行错误，解释器会抛出异常之外**
- **也可以根据应用程序特有的也无需求主动抛出异常**
- **`python`中提供了一个 `Exception`异常类**
- **在开发时，如果满足特定业务需求时，希望抛出异常可以：创建一个 `Exception`的对象；使用 `raise`关键字抛出异常对象**

```python
def info_password():
    passwd = input("请输入您的密码: ")
    if len(passwd) >= 8:
        return passwd

    print("密码错误,太短了")
    # 创建一个 `Exception`的对象  可以使用错误信息字符串作为参数
    except_passwd = Exception("密码长度不够")
    # 使用 `raise`关键字抛出异常对象
    raise except_passwd

try:
    print(info_password())
except Exception as result:
    print(result)
    
    
/usr/local/bin/python3 /home/zcb/python_study/10_异常/hm_06_主动抛出异常.py
请输入您的密码: 123
密码错误,太短了
密码长度不够

Process finished with exit code 0
```

**模块**

- **每个以扩展名 `py`结尾的 `python`源代码都是一个模块**
- **模块名同样也是一个标识符，需要符合标识符的命名规则**
- **在模块中定义的全局变量，函数，类都是提供给外界直接使用的工具**
- **模块好比工具包，要想使用这个工具包中的工具，就要先导入这个模块**
- **导入模块的正确方法：**

```python
import 模块1
import 模块2
```

- **导入模块后通过 `模块名.`调用模块中的全局变量，类，方法**

```python
hm_01_测试模块1
num1 = 90


def say_hello():
    print("测试模块1的函数")


class Dog:
    pass
    
hm_02_测试模块2
num2 = 100


def say_hello():
    print("测试模块2的函数")


class Cat:
    pass

import hm_01_测试模块1
import hm_02_测试模块2

hm_01_测试模块1.say_hello()
hm_02_测试模块2.say_hello()

dog = hm_01_测试模块1.Dog()
print(dog)

cat = hm_02_测试模块2.Cat()
print(cat)

/usr/local/bin/python3 /home/zcb/python_study/11_模块/hm_03_import导入模块.py
测试模块1的函数
测试模块2的函数
<hm_01_测试模块1.Dog object at 0x7ff352e63a00>
<hm_02_测试模块2.Cat object at 0x7ff352e639d0>

Process finished with exit code 0
```

- **如果模块的名字太长，可以使用 `as`指定模块名称，以便在代码中使用**

- **模块别名应该符合大驼峰命名法**

- **语法：**

  ```python
  import 模块1 as 模块别名
  ```

```python
import hm_01_测试模块1 as DogMoule
import hm_02_测试模块2 as CatMoule

DogMoule.say_hello()
CatMoule.say_hello()

dog = DogMoule.Dog()
print(dog)

cat = CatMoule.Cat()
print(cat)
```

**from..import导入**

- **`import 模块名`是一次性把模块中所有工具全部导入，并且通过模块名/别名访问**
- **如果希望从某个模块中，导入部分工具，就可以使用 `from...import`的方法**

```python
# 从模块中导入某个工具
from 模块名1 import 工具名
```

- **导入之后，不需要通过 `模块名.`调用工具；可以直接使用模块提供的工具**
- **如果两个模块存在同名的函数，那么后倒入的模块函数会覆盖先导入的函数**
- **一旦发现命名冲突，可以使用 `as`关键字给其中一个工具取一个别名**

```python
from hm_02_测试模块2 import say_hello
from hm_01_测试模块1 import Dog
from hm_01_测试模块1 import say_hello as say_hello_test1

say_hello()
say_hello_test1()

dog = Dog()
print(dog)

/usr/local/bin/python3 /home/zcb/python_study/11_模块/hm_05_from_imoprt导入模块工具.py
测试模块2的函数
测试模块1的函数
<hm_01_测试模块1.Dog object at 0x7f626ce37a90>

Process finished with exit code 0
```

**from...import * **

```python
# 从 模块 导入 所有工具
from 模块名1 import *
```

- **这种方式不推荐使用，因为函数重名并没有任何提示，出现问题不好排查**

```python
from hm_01_测试模块1 import *
from hm_02_测试模块2 import *

print(num)

say_hello()

dog = Dog()
print(dog)

/usr/local/bin/python3 "/home/zcb/python_study/11_模块/hm_o6_from_import *.py"
90
测试模块2的函数
<hm_01_测试模块1.Dog object at 0x7ff7d24ef340>

Process finished with exit code 0
```

**模块搜索顺序**

- **`python`的解释器在导入模块时，会：首先搜索当前目录指定模块名的文件，如果有就会直接导入，如果没有就会再次搜索系统目录**
- **在开发中，给文件起名字时，不要和系统的模块文件重名**
- **`python`中每一个模块都有一个内置属性 `__file__`可以查看模块的完成路径**

```python
import random
print(random.__file__)

/usr/local/lib/python3.10/random.py
```

- **一个独立的 `python`文件就是一个模块**
- **在文件导入的时候，文件中所有没有任何缩进的代码都会被执行一遍**

- **`__name__`是 `python`的一个内置属性，记录一个字符串**
- **如果是当前执行的程序 `__name__`就是 `__main__`**
- **如果是作为模块被导入其他文件中，此时的 `__name__`就是模块名**

```python
# 导入模块
# 定义全局变量
# 定义类
# 定义函数

#在代码最下方
def main():
	# 代码内容
	pass
	
# 根据__name__判断是否执行下方代码
if __name__ == "__main__"
	main()
```

**包**

- **包是一个包含多个模块的特殊目录**
- **目录下有一个特殊的文件 `__init__.py`**
- **包名的命名方式和变量名一致，小写字母+ `_`**
- **使用 `import 包名`可以一次性导入包中所有的模块**
- **右键项目名 ->new->python package创建python包**
- **要在外界使用包中的模块，需要在 `__init__.py`中指定对外界提供的模块列表**

```python
from . import send_message
from . import receive_message
```

**一个自己的创建的包的demo**

```python
send_message.py
def send(text):
    print("正在发送 %s ...." % text)

receive_message.py
def receive():
    return "this is a message from 100xx"

__init__.py
from . import send_message
from . import receive_message

hm_07_导入包.py
import hm_message

hm_message.send_message.send("hello")

print(hm_message.receive_message.receive())


/usr/local/bin/python3 /home/zcb/python_study/11_模块/hm_07_导入包.py
正在发送 hello ....
this is a message from 100xx

Process finished with exit code 0
```

**pip安装第三方模块**

- **第三方模块通常是指由知名的第三方团队开发的并且被成学院广泛使用的 `python`包/模块**
- **`pip`是一个现代的，通用的 `python`管理工具**
- **`pip`提供了对 `python`包的查找，下载，安装，卸载等功能**

```shell
# 将模块安装到python2.x环境
sudo pip install pygame
# 卸载
sudo pip uninstall pygame

# 将模块安装到python3.x环境
sudo pip3 install pygame
# 卸载
sudo pip3 uninstall pygame

#安装速度较慢时可以换源安装 指令如下：  其中scipy是包名
pip --default-timeout=100 install scipy -i https://pypi.tuna.tsinghua.edu.cn/simple
```

**文件的基本操作**

| 函数/方法 |              说明              |
| :-------: | :----------------------------: |
| **open**  | 打开文件，并且返回文件操作对象 |
| **read**  |      将文件内容读取到内存      |
| **write** |       将指定内容写入文件       |
| **close** |            关闭文件            |

-  **`open`函数负责打开文件，第一个参数是要打开的文件名（文件名区分大小写）如果文件存在，返回文件操作对象；如果文件不存在，会抛出异常**

- **`read/write/close`三个方法都需要通过文件对象来调用，`read`方法可以一次性读入并返回文件的所有内容，`close`方法负责关闭文件，如果忘记关闭文件，会造成系统资源消耗，而且会影响后续对文件的访问**

- **方法执行后，会把文件指针移动到文件的末尾**

  ```python
  file = open("readme")
  
  text = file.read()
  print(text)
  
  file.close()
  
  /home/zcb/python_code/13_document/venv/bin/python /home/zcb/python_code/13_document/hm_01_readfile.py
  hello world
  hello python
  hello zhouchongbo
  
  Process finished with exit code 0
  ```

- **文件指针标记从哪个位置来时读取数据**
- **第一次打开文件时，通常文件指针会指向文件的开始位置**
- **当执行了 `read`方法后，文件指针会移动到读取内容的末尾**
- **使用 `read`读取所有内容后，再次调用 `read`方法，不会读取到任何的内容**

```python
file = open("readme")

text = file.read()
print(text)
print("-" * 50)

text = file.read()
print(text)
file.close()

/home/zcb/python_code/13_document/venv/bin/python /home/zcb/python_code/13_document/hm_02_file_point.py
hello world
hello python
hello zhouchongbo
--------------------------------------------------


Process finished with exit code 0
```

**打开文件的方式**

- **`open`函数默认以只读方式打开文件，并且返回文件对象**

```python
file = open ("文件名", "访问方式")
```

| 访问方式 |                             说明                             |
| :------: | :----------------------------------------------------------: |
|  **r**   | **以只读方式打开文件。文件的指针将会放在文件的开头，该模式为默认模式。如果文件不存在，则抛出异常** |
|  **w**   | **以只写方式打开文件。如果文件存在会被覆盖，如果文件不存在，创建新的文件** |
|  **a**   | **以追加方式打开文件。如果文件存在，文件指针将会放在文件的结尾，如果文件不存在，创建新文件进行写入** |
|  **r+**  | **以读写方式打开文件。文件的指针将会放在文件的开头，如果文件不存在，抛出异常** |
|  **w+**  | **以读写的方式打开文件。如果文件存在会被覆盖。如果文件不存在，创建新文件** |
|  **a+**  | **以读写方式打开文件，如果该文件存在，文件指针将会放在文件的结尾，如果文件不存在，创建新文件进行写入** |

**readline方法**

- **该方法一次只读一行内容**
- **方法执行后，会把文件指针移动到下一行，准备再次读取**

```python
file = open("readme")
while True:
    TEXT = file.readline()
    if not TEXT:
        break

    print(TEXT)

file.close()

/home/zcb/python_code/13_document/venv/bin/python /home/zcb/python_code/13_document/hm_03_readline.py
hello123

hello

123hello

Process finished with exit code 0
```

```python
file_origin = open("readme")

text = file_origin.read()

file_copy = open("readme_copy", "w")
file_copy.write(text)

file_copy.close()
file_origin.close()
```

```python
file_origin = open("readme")
file_copy = open("readme_copy", "w")
while True:
    text = file_origin.readline()
    if not text:
        break
    file_copy.write(text)

file_copy.close()
file_origin.close()
```

**eval()函数**

- **该函数将字符串当成有效的表达式进行求值并返回计算结果**

```python
In [2]: eval("1+1")
Out[2]: 2

In [3]: eval("'*' * 10 ")
Out[3]: '**********'

In [4]: type(eval("[1, 2, 3, 4, 5]"))
Out[4]: list
```

```python
input_str = input("Please enter the arithmetic problem:")
print(eval(input_str))
```

