[TOC]

## 2. Python  解释器

### 2.1. 调用解释器

可以通过以下命令启动 Python：

```powershell
python
```

#### 2.1.1. 传入参数

#### 2.1.2. 交互模式

使用`python`命令可以进入交互模式，如下图：

```powershell
PS C:\Users\15292> python
Python 3.9.0 (tags/v3.9.0:9cf6752, Oct  5 2020, 15:34:40) [MSC v.1927 64 bit (AMD64)] on win32
Type "help", "copyright", "credits" or "license" for more information.
>>>
```

在该模式中，会显示*主提示符*，提示输入下一条指令，主提示符通常用三个大于号(`>>>`)表示；显示*次要提示符*，默认是三个点(`...`)。

```powershell
>>> the_world_is_flat = True
>>> if the_world_is_flat:
...     print("Be careful not to fall off!")
...
Be careful not to fall off!
```

### 2.2. 解释器的运行环境

#### 2.2.1. 源文件的字符编码

默认情况下，Python 源码文件的编码是 UTF-8。这种编码支持世界上大多数语言的字符，可以用于字符串字面值、变量、函数名及注释 —— 尽管标准库只用常规的 ASCII 字符作为变量名或函数名，可移植代码都应遵守此约定。要正确显示这些字符，编辑器必须能识别 UTF-8 编码，而且必须使用支持文件中所有字符的字体。

如果不使用默认编码，则要声明文件的编码，文件的`第一`行要写特殊注释，语法如下：

```python
# -*- coding: encoding -*-
```

*encoding* 可以是 Python 支持的任何一种 `codecs`。

如使用 Windows-1252 编码，源码文件需要如下：

```python
# -*- coding: cp1252 -*-
```

## 3. Python 速览

> 已速览

## 4. 其他流程控制工具

### 4.1. if 语句

### 4.2. for 语句

### 4.3. range() 函数

内置函数`range()`常用于遍历数字序列，该函数可以生成算术级数：

```python
>>> for i in range(5):
...     print(i)
...
0
1
2
3
4
```

生成的序列不包含给定的终止数值；`range(10)` 生成 10 个值，这是一个长度为 10 的序列，其中的元素索引都是合法的。range 可以不从 0 开始，还可以按指定幅度递增（递增幅度称为 '步进'，支持负数）：

```python
>>> list(range(5))
[0, 1, 2, 3, 4]
>>> list(range(1, 5))
[1, 2, 3, 4]
>>> list(range(1, 6))
[1, 2, 3, 4, 5]
>>> list(range(2, 10, 3))
[2, 5, 8]
```

`range()`和`len()`组合在一起，可以按索引迭代序列：

```python
>>> a = ['a', 'b', 'c', 'd', 'e']
>>> for i in range(len(a)):
...     print(i, a[i])
...
0 a
1 b
2 c
3 d
4 e
```

### 4.4. 循环中的 break、continue 语句及 else 子句

### 4.5. pass 语句

### 4.6. 定义函数

定义函数使用关键字`def`，后跟函数名与括号内的形参列表。函数语句从下一行，*而且必须缩进*。

函数内的第一条语句是字符串时，该字符串就是文档字符串。利用文档字符串可以让开发者在浏览代码时直接查询文档；Python 开发者最好养成在代码中加入文档字符串的好习惯。