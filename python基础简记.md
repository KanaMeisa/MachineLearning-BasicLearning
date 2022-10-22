## 第三章 输入与输出
- 快捷键 `Ctrl+/` 可以快速对选中的代码进行注释

  ### format格式化字符串


(1) 通过位置来填充字符串
```python
print('hello {0} i am {1}'.format('world','python')) 
#输出结果：hello world i am python
print('hello {} i am {}'.format('world','python') ) 
#输出结果：hello world i am python
print('hello {0} i am {1} . a now language {1}'.format('world','python') 
#输出结果：hello world i am python . a now language python
```

(2) 通过key来填充

```python
obj = 'world'
name = 'python'
print('hello, {obj} ,i am {name}'.format(obj = obj,name = name))
# 输出结果：hello, world ,i am python
```



## 第五章 数据类型与数据结构

### 1. 数

(1) 二进制整常数必须以0b或者0B开头,如0b1010

(2) 八进制整常数必须以0o或者0O开头,如0o1777

(3) 十六进制整常数必须以0x或0X开头,如0xa0



- 十进制转换成二进制, 八进制和十六进制的示例如下

`bin(64) `	十进制数64转化为二进制数 输出`0b1000000`

`oct(64)`	十进制数64转化为八进制数 输出`0o100` 

`hex(64)`	十进制数64转化为十六进制数 输出`0x40`



- 其他进制转化为十进制示例如下

`int('0x40',x)`  x为进制数



### 2. 字符串

<img src="https://pic.imgdb.cn/item/631ff67d16f2c2beb1269b8a.png" style="zoom: 67%;" />

加号 **+** 是字符串的连接符， 星号 ***** 表示复制当前字符串，与之结合的数字为复制的次数。实例如下：

#### 实例

```py
str = 'Runoob'
print (str)          # 输出字符串
print (str[0:-1])    # 输出第一个到倒数第二个的所有字符 //后面的那个不包括其本身
print (str[0])       # 输出字符串第一个字符
print (str[2:5])     # 输出从第三个开始到第五个的字符
print (str[2:])      # 输出从第三个开始的后的所有字符
print (str * 2)      # 输出字符串两次，也可以写成 print (2 * str)
print (str + "TEST") # 连接字符串
```

执行以上程序会输出如下结果：

```py
Runoob
Runoo
R
noo
noob
RunoobRunoob
RunoobTEST
```



### 3. 列表(list)

##### 1.初始列表

使用中括号[ ]创建列表, 各个元素通过逗号分隔, 如下所示

```python
list1 = ['python', 'AI']
list2 = [1, 2, 3]
list3 = ["p", "y", ['python', 'AI']]
```



##### 2.列表的基本操作

![](https://pic.imgdb.cn/item/631706a216f2c2beb1afbc6f.jpg)

![](https://pic.imgdb.cn/item/631706a816f2c2beb1afc2c3.jpg)



### 4. 元组(tuple)

元组不可被修改

元组的定义方法和列表类似, 不过要使用小括号

```python
tuple1 = ('python', 'AI')
tuple2 = (1, 2, 3)
tuple3 = "p", "y"   #不加括号也可以
```

元组中的元素值不可以被修改或删除, 但可以对元组进行连接组合

```python
tup = tuple1 + tuple2 => tup = ('python', 'AI', 1, 2, 3)
```

- 列表和元组之间可以互相转化, 由`tuple(list)`和 `list(tuple)`实现



### 5. 字典

字典是一系列键-值(key-value)对, 表示如下

```python
dict = {key1:value1, key2:value2}
dict1 = {'Name': 'Bob', 'Age': 21}
```

字典的基本操作如下

![](https://pic.imgdb.cn/item/631837c016f2c2beb1c542ef.jpg)



### 6.集合

​		集合是一个无序的不重复元素序列. 使用集合可以检查是否是成员, 是否是另一个集合的子集, 以及得到两个集合的交集等.

​		可以使用大括号或者set()函数创建集合, 但是, 在创建空集合时, 必须使用set(), 而不是{}.    {}表示来创建一个空字典.

```python
thisset = ste(("python", "Hello"))
type(thisset)
```

集合的基本操作如下

![](https://pic.imgdb.cn/item/631839da16f2c2beb1c7ca9f.jpg)

![](https://pic.imgdb.cn/item/631839dd16f2c2beb1c7cd99.jpg)



## 类的使用

```py
#类的使用实例
class Car:
    #类中的函数称为方法
    #__init__是一个特殊方法，每次根据类创建新实例时，python都会自动运行它
    def __init__(self, band, model, year):
        self.band = band
        self.model = model
        self.year = year
        self.odometer_reading = 10

    def get_descriptive_name(self):
        long_name = f"{self.year} {self.band} {self.model}"
        return long_name.title()

    #预留一个修改汽车里程数的方法，同时防止回调里程数
    def update_odometer(self, mileage):
        if mileage <= self.odometer_reading:
            print("Rolling back an odometer is NOT allowed!!!")
        else:
            self.odometer_reading = mileage

#将实例用作属性
class Battery:
    def __init__(self, battery_size = 75):
        self.battery_size = battery_size

    def describe_battery(self):
        print(f"This car has a {self.battery_size}-KWh battery")

#类的继承
class ElectricCar(Car):
    def __init__(self, band, model, year):
        super().__init__(band, model, year) #继承父类
        self.battery_size = 75              #给子类添加新属性和新方法
        self.battery = Battery()            #将实例用作属性

    def discribe_battery(self):
        print(f"This car has a {self.battery_size}-KWh battery")

my_telsa = ElectricCar('telsa', 'S', 2019)
my_telsa.battery.describe_battery()


```

