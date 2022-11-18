# Python Note

----

## 目录

----

- Python基础知识
  - Python数据类型
    1. [numbers] (#numbers-数字)
    2. string
    3. list
    4. tuple
    5. dictionary
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

#### 列表创建

```py
list1 = ["red", "yellow", 3, 4]
```

列表中每一个元素用`,`分隔，列表里可以有数字和字符串，列表用`[]`创建

#### 列表索引
列表中第一个元素索引值为`0`，从左往右递增；列表最后一个元素索引值可以为`-1`，从右往左递减

#### 列表截取
列表可用`[beg=0:end=len(list)]`截取

#### 列表更新
列表可以被更新，包括添加元素，替换元素和删除元素。添加元素时使用`+`做拼接；替换元素可以直接将元素赋予到列表的某个索引处，例如`list1[1] = 2`，在列表末尾添加元素可使用`append()`函数；删除元素时使用`del`，例如`del list1[1]`可删除列表`list1`的第二个元素

#### 列表脚本操作符
|表达式|结果|描述|
|----|----|----|
|`len([1,2,3])`|`3`|列表长度|
|`[1,2]+[3,4]`|`[1,2,3,4]`|列表拼接|
|`[1]*4`|`[1,1,1,1]`|重复列表|
|`2 in [1,2,3]`|`True`|检查元素是否在列表中|
|`for i in [1,2,3]: print(i,end=' ')`|1 2 3|迭代|

#### 列表嵌套

```py
a = ['a', 'b', 'c']
n = [1, 2, 3]
x = [a, n]
x
x[0]
x[0][1]
```
运行结果为
```py
>>> x
[['a', 'b', 'c'], [1, 2, 3]]
>>> x[0]
['a', 'b', 'c']
>>> x[0][1]
'b'
```

#### 列表常用函数
|函数|描述|
|----|----|
|`max(list)`|返回列表元素最大值|
|`list(seq)`|将元组转换为列表|
|`list.append(obj)`|在列表末尾添加新的对象|
|`list.count(obj)`|统计`obj`在列表中出现的次数|
|`list。extend(seq)`|在列表末尾一次性追加另一个序列中的多个值（用新列表扩展原来的列表）|
|`list.index(obj)`|从列表中找出某个值第一个匹配项的索引位置|
|`list.insert(index,obj)`|将对象插入列表|
|`list.pop([index=-1])`|移除列表中的一个元素（默认最后一个元素），并且返回该元素的值|
|`list.remove(obj)`|移除列表中某个值的第一个匹配项|
|`list.reverse()`|反向列表中元素|
|`list.sort(key=None,reverse=False)`|对原列表进行排序|
|`list.clear()`|清空列表|
|`list.copy()`|复制列表|

#### 4. tuple 元组

元组与列表类似，不同之处在于**元组里的元素不可修改**

#### 元组创建

```py
tup1 = ('red', 'yellow' ,3, 4)
tup2 = 'a', 'b', 'c'  # 不用括号也可以创建元组
tup3 = ()             # 可以创建空元组
tup4 = (1,)           # 只有一个元素时，需要加","是类型变为元组，否则类型为数字或字符串
```

#### 元组性质

1. 元组中的元素可以通过索引被访问、截取
2. 元组整体可以`+`拼接，`*`复制，`in`查询是否存在，以及`for`循环迭代
3. 整个元组可以通过`del`删除
4. 元组中的元素不可改变是因为元组所指向的内存中的内容不可改变

#### 元组常用函数
|函数|描述|
|----|----|
|`len(tuple)`|输出元组的元素个数|
|`max(tuple)`|输出元组中元素最大值|
|`tuple(iterable)`|将可迭代系列(例如列表)转换为元组|

#### 5. dictionary 字典

#### 字典创建

```py
d = {key1: value1, key2, value2, key3, value3}
```

1. 字典用`{}`或`dict()`创建
2. **`dict`为Python的关键字和内部函数，所以变量名不建议为`dict`**
3. 字典中`key`是唯一的，但`value`不必唯一
4. 可创建空字典

#### 访问字典里的值

将`key`当索引值，例如
```py
d = {'Hello': 'Python', 'age': 25}
print(d['Hello'])
print(d['age'])
```
输出结果为
```py
Python
25
```

#### 字典修改

字典可以将新的`value`值赋予到字典的某个`key`后，例如`d['age'] = 26`

#### 字典删除

```py
del d['age']   # 删除key = 'age'
d.clear()      # 清空字典d
del d          # 删除字典d
```
#### 字典特征

1. 同一个`key`不可出现两次。创建字典时如果同一个`key`被赋值两次，字典只保存后一个值
2. `key`不可变，故数字，字符串或元组可以做`key`，但列表不可以做`key`

#### 字典常用函数

|函数|描述|
|----|----|
|`len(dict)`|返回字典`key`的个数|
|`str(dict)`|将字典输出为字符串|
|`dict.clear()`|删除字典内所有元素|
|`dict.copy()`|返回一个字典的浅复制|
|`dict.fromkeys(seq，val)`|创建一个新字典，以`seq`中元素做新字典的`key`，`val`为新字典`key`对应的`value`|
|`dict.get(key,default=None)`|返回指定`key`的`value`，如果`key`不在字典中返回 `default`设置的默认值|
|`key in dict`|如果`key`在字典里返回`true`，否则返回`false`|
|`dict.items()`|返回一个包含所有`key`和`value`的列表|
|`dict.keys()`|返回一个包含所有`key`的列表|
|`dict.setdefault(key,default=None)`|和`get()`类似, 但如果`key`不存在于字典中，将会添加`key`并将`value`设为`default`|
|`dict.update(dict2)`|把字典`dict2`的`key`/`value`对更新到`dict`里|
|`dict.values()`|返回一个包含所有`value`的列表|
|`pop(Key[,default])`|删除字典`key`所对应的值，返回被删除的`value`|
|`popitem()`|返回并删除字典中的最后一对`key`和`value`|

#### 6. set 集合





人工智能三要素：算法、算力、数据