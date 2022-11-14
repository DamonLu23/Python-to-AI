# Python Note

==============================================================================================

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
| 函数                             | 描述                                                               |
|--------------------------------|------------------------------------------------------------------|
| `abs(x)`                       | `x`的绝对值                                                          |
| `ceil(x)`                      | 返回`x`的上入整数，例如 `math.ceil(2.5)` return `3`                        |
| `floor(x)`                     | 返回`x`的下舍整数，例如 `math.floor(2.5)` return `2`                       |
| `max(x1,x2,...)`               | 给定参数的最大值                                                         |
| `min(x1,x2,...)`               | 给定参数的最小值                                                         |
| `round(x,n)`                   | 取距离`x`最近的整数，保留`n`位小数                                             |
| `sqrt(x)`                      | `x`的算数平方根                                                        |
| `randrange(start, stop, step)` | 在指定开始范围内，从开始值按`step`递增随机输出一个数，例如`random.randrange(1,5,2)`，输出值可能为 |`1`或`3``
| `random()`                     | 在`[0,1)`范围内取随机值                                                  |

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

| 函数                                         | 描述                                                                                           |
|--------------------------------------------|----------------------------------------------------------------------------------------------|
| `capitalize()`                             | 将字符串第一个字母大写                                                                                  |
| `count(str,beg=0,end=len(string))`         | 返回 `str` 在 `string` 里面出现的次数，如果 `beg` 或者 `end` 指定则返回指定范围内 `str` 出现的次数                         |
| `endwith(suffix,beg=0,end=len(string))`    | 检查字符串是否以 `suffix` 结束，如果 `beg` 或者 `end` 指定则检查指定的范围内是否以 `suffix` 结束，如果是，返回 `True`,否则返回 `False` |
| `find(str,beg=0,end=len(string))`          | 检测 `str` 是否包含在字符串中，如果指定范围 `beg` 和 `end` ，则检查是否包含在指定范围内，如果包含返回开始的索引值，否则返回`-1`                 |
| `index(str,beg=0,end=len(string))`         | 检测 `str` 是否包含在字符串中，如果指定范围 `beg` 和 `end` ，则检查是否包含在指定范围内，如果包含返回开始的索引值，否则报一个异常                  |
| `isalnum()`                                | 如果字符串至少有一个字符并且所有字符都是字母或数字则返 回 `True`，否则返回 `False`                                            |
| `isalpha()`                                | 如果字符串至少有一个字符并且所有字符都是字母或中文字则返回 `True`, 否则返回 `False`                                           |
| `isdigit()`                                | 如果字符串只包含数字则返回 `True` 否则返回 `False`                                                            |
| `isnumeric()`                              | 如果字符串中只包含数字字符，则返回 `True`，否则返回 `False`                                                        |
| `isspace()`                                | 如果字符串中只包含空白，则返回 `True`，否则返回 `False`.                                                         |
| `isupper()`                                | 如果字符串中包含至少一个区分大小写的字符，并且所有这些(区分大小写的)字符都是大写，则返回 `True`，否则返回 `False`                            |
| `join(seq)`                                | 以指定字符串作为分隔符，将 `seq` 中所有的元素(的字符串表示)合并为一个新的字符串                                                 |
| `len()`                                    | 字符串长度                                                                                        |
| `lower()`                                  | 转换字符串中所有大写字符为小写                                                                              |
| `lstrip()`                                 | 截掉字符串左边的空格或指定字符                                                                              |
| `max(str)`                                 | 返回字符串 `str` 中最大的字母                                                                           |
| `replace(old,new,[max])`                   | 将字符串中的 `old` 替换成 `new`,如果 `max` 指定，则替换不超过 `max` 次                                            |
| `rfind()`                                  | 类似于 `find()`函数，不过是从右边开始查找                                                                    |
| `rindex(str,beg=0,end=len(string))`        | 类似于 `index()`，不过是从右边开始                                                                       |
| `rstrip(str,beg=0,end=len(string))`        | 删除字符串末尾的空格或指定字符                                                                              |
| `split(str="",num=string,count(str))`      | 以 `str` 为分隔符截取字符串，如果 `num` 有指定值，则仅截取 `num+1` 个子字符串                                           |
| `startswith(substr,beg=0,end=len(string))` | 检查字符串是否是以指定子字符串 `substr` 开头，是则返回 `True`，否则返回 `False`。如果`beg` 和 `end` 指定值，则在指定范围内检查           |
| `strip()`                                  | 在字符串上执行 `lstrip()`和 `rstrip()`                                                               |
| `swapcase()`                               | 将字符串中大写转换为小写，小写转换为大写                                                                         |
| `upper()`                                  | 转换字符串中的小写字母为大写                                                                               |
| `zfill(width)`                             | 返回长度为 `width` 的字符串，原字符串右对齐，前面填充`0`                                                           |
| `isdecimal()`                              | 检查字符串是否只包含十进制字符，如果是返回 `true`，否则返回 `false`                                                    |

#### 3. list 列表