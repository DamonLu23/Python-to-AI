# Python Note

====

## 目录

----

- Python基础知识
  - Python数据类型
    1. numbers
    2. string
    3. list
    4. tuple 不能二次赋值
    5. dictionary 字典当中的元素是通过键来存取的，而不是通过偏移存取(列表)
    6. set
  - 比较运算符和关系运算符
  - 判断语句
  - 循环语句


### Python身份运算符
is 和 is not
is 用于判断两个变量引用对象是否为同一个(同一块内存空间)， == 用于判断引用变量的值是否相等

----

## Python基础知识

### 数据类型

#### 1. numbers 数字

#### Python支持三种不同的数据类型
- `int` - 包括`bool`类型
- `float`
- `complex` - 用`complex(x,y)`表示，`x`和`y`均为`float`类型

#### 常用的数字函数：
|  函数   | 描述  |
|  ----  | ----  |
| `abs(x)`  | `x`的绝对值 |
| `ceil(x)`  | 返回`x`的上入整数，例如 `math.ceil(2.5)` return `3`|
| `floor(x)` | 返回`x`的下舍整数，例如 `math.floor(2.5)` return `2`|
|`max(x1,x2,...)`|给定参数的最大值|
|`min(x1,x2,...)`|给定参数的最小值|
|`round(x,n)`|取距离`x`最近的整数，保留`n`位小数|
|`sqrt(x)`|`x`的算数平方根|
|`randrange(start, stop, step)`|在指定开始范围内，从开始值按`step`递增随机输出一个数，例如`random.randrange(1,5,2)`，输出值可能为|`1`或`3``
|`random()`|在`[0,1)`范围内取随机值|

#### 2. string 字符串

```py
str1 = "Hello World"
print(str1)
```
```py
Hello World
```
此处`Hello World`为字符串类型。创建字符串用`'`或`"`。

#### 访问字符串的值

`变量名[头下标:尾下标]`

索引从左往右从0开始，从右往左从-1开始，例如

```py
print(str1[0])
print(str1[-1])
```
```
H
d
```

#### 字符串更新

字符串可以截取一部分并于其他字符串拼接，例如

```py
str1 = "Hello World"
str2 = "Python"
print(str1[:6] + str2)
```
```
Hello Python
```

#### f-string

f-string 用来格式化字符串，以 f 开头，后接字符串，将变量名写入`{}`替换。例如

```py
str1 = "Hello"
f'{str1} world'
```
```
'Hello world'
```

#### 字符串常用函数

|函数|描述|
|----|----|
|`capitalize()`||
|`count(str,beg=0,end=len(string))`||
|`endwith(suffix,beg=0,end=len(string))`||
|`find(str,beg=0,end=len(string))`||
|`index(str,beg=0,end=len(string))`||
|`isalnum()`||
|`isalpha()`||
|`isdigit()`||
|`isnumeric()`||
|`isspace()`||
|`isupper()`||
|`join(seq)`||
|`len()`||
|`lower()`||
|`lstrip()`||
|`max(str)`||
|`min(str)`||
|`replace(old,new,[max])`||
|`rfind()`||
|`rindex(str,beg=0,end=len(string))`||
|`rstrip(str,beg=0,end=len(string))`||
|`split(str="",num=string,count(str))`||
|`startswith(substr,beg=0,end=len(string))`||
|`strip()`||
|`swapcase()`||
|`upper()`||
|`zfill(width)`||
|`isdecimal()`||