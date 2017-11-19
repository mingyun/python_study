https://www.shiyanlou.com/courses/983/labs/3953/document
#!/usr/bin/env python3
其中第一行的前两个字符 #! 称为 Shebang ，目的是告诉 shell 使用 Python 3 解释器执行其下面的代码 
给脚本通过 Linux 的 chmod a+x XXX.py 命令增加了执行权限，则可以使用 ./XXX.py 这种方式直接执行脚本，否则需要用 python3 XXX.py 这种方式执行
```js
>>> import keyword
>>> keyword.kwlist
['False', 'None', 'True', 'and', 'as', 'assert', 'break', 'class', 'continue', '
def', 'del', 'elif', 'else', 'except', 'finally', 'for', 'from', 'global', 'if',
 'import', 'in', 'is', 'lambda', 'nonlocal', 'not', 'or', 'pass', 'raise', 'retu
rn', 'try', 'while', 'with', 'yield']

Python 3 中，包括以下几种基本数据类型：

整数：例如 100，-200，0 等
布尔数：True 或 False
浮点数：小数，例如 1.5，2.5
None：空值，注意与0是不同的，可以理解为未定义的值。
```str6 = """ hello, 
shiyanlou """
str1.strip('ab') 则只会删除 str1 字符串中头尾部的 a 和 b 字符
w = 100
while w > 10:
    print(w)
    w -= 10
最常见的异常类：

NameError 访问一个未定义的变量
SyntaxError 语法错误，这个严格讲算是程序的错误
IndexError 对于一个序列，访问的索引超过了序列的范围（序列的概念会在后续实验中讲到），可以理解为我的序列里只有三个元素，但要访问第4个
KeyError 访问一个不存在的字典 Key，字典也会在下一节实验中详细讲到，Key 如果不存在字典就会抛出这个异常
ValueError 传入无效的参数
AttributeError 访问类对象中不存在的属性
try:
    有可能抛出异常的代码
except 异常类型名称：
    处理代码
except 异常类型名称：
    处理代码
filename = input("Enter file path:")
try:
    f = open(filename)
    print(f.read())
    f.close()
except FileNotFoundError:
    print("File not found")
filename = '/etc/protocols'
f = open(filename)
try:
    f.write('shiyanlou')
except:
    print("File write error")
finally:
    print("finally")
    f.close()
finally 关键字是用来进行清理工作，经常和 except 一起使用，即无论是正常还是异常，这段代码都会执行。raise ValueError() 外部的代码就可以使用 except ValueError 进行捕获和处理了

每个 XXX.py 文件都是一个 Python 模块，文件的内容会在 import XXX 的时候直接执行。对于文件夹，Python 中可以识别成一个包，前提是这个文件夹中有一个 __init__.py 文件，文件中可以不用写任何内容。
创建一个目录 shiyanlou，在这个目录下有 __init__.py 和 louplus.py 两个代码文件，我们想要引入 louplus.py 文件就可以用 import shiyanlou.louplus 这种代码来引入，前提是 shiyanlou 目录已经放到了 Python 模块搜索的默认路径下了  sys.path
sys.argv[0] 为脚本名称， sys.argv[1] 为第一个参数 
python3 argtest.py 这样执行时可以执行到 if __name__ == '__main__': 这个代码块中 for 循环的内容，当通过 import argtest 作为模块导入到其他代码文件时不会执行if __name__ == '__main__':中的内容。
format(1.2345, ".2f") 得到的就是有两位小数的字符串 '1.23'

