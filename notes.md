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

>>> courses.insert(0, 'Java')
>>> courses
['Java', 'Linux', 'Python', 'Vim', 'C++', 'PHP']
>>> courses.insert(1, 'Ruby')
>>> courses
['Java', 'Ruby', 'Linux', 'Python', 'Vim', 'C++', 'PHP']
>>> courses.count('Java')
1 Java 这个元素在列表中出现了多少次。

>>> courses.remove('Java')
>>> courses
['Ruby', 'Linux', 'Python', 'Vim', 'C++', 'PHP']
>>> del courses[-1]
>>> courses
['Ruby', 'Linux', 'Python', 'Vim', 'C++']
>>> new_courses = ['BigData', 'Cloud']
>>> courses.extend(new_courses)
>>> courses
['PHP', 'C++', 'Vim', 'Python', 'Linux', 'Ruby', 'BigData', 'Cloud']

传入一个参数 i 即 pop(i) 会将第 i 个元素弹出
不同点是元组一旦创建就不能修改，上述的所有会修改列表内容的操作例如 sort()、append()等对于元组都不再适用
>>> new_courses = ('Linux', ['BigData1','BigData2','BigData3'], 'Vim')
>>> new_courses[1]
['BigData1', 'BigData2', 'BigData3']
>>> new_courses[1].append('BigData4')
>>> new_courses
('Linux', ['BigData1', 'BigData2', 'BigData3', 'BigData4'], 'Vim')
需要注意空的集合不能够使用 {} 创建，只能使用 set 函数，因为{} 创建的是一个空的字典 ：
>>> courses = set()
>>> type(courses)
<class 'set'>
>>> courses = {'Linux', 'C++', 'Vim', 'Linux'}
>>> courses
{'Linux', 'Vim', 'C++'}

>>> nameset = set('shiyanlou.com')
>>> nameset
{'c', 'o', '.', 'm', 'u', 'h', 's', 'a', 'n', 'i', 'y', 'l'}

>>> 'Linux' in courses
True
>>> 'Python' in courses
False
>>> 'Python' not in courses
True
>>> set1 = {1,2,3,4}
>>> set2 = {3,4,5,6}
^ 操作，返回只存在两个集合中的元素：

>>> set1 ^ set2
{1, 2, 5, 6}
>>> coursesdict.get(2)
'Vim'
>>> coursesdict.get(4, 'default')
'default'
>>> dict_from_tuple = dict(((1,'Linux'), (2,'Vim'))) 参数是一个包含若干个二元组的元组
>>> dict_from_tuple
{1: 'Linux', 2: 'Vim'}

字典中也存在 pop(key) 函数，可以返回 key 对应的 value，并将该 key:value 键值对删除：

>>> coursesdict
{2: 'Vim', 5: 'Bash', 6: 'Python'}
>>> coursesdict.pop(2)
'Vim'
>>> coursesdict
{5: 'Bash', 6: 'Python'}

def char_count(str):
    countdict = {}
    for char in str:
        c = countdict.get(char)
        if c is None:
            countdict[char] = 1
        else:
            countdict[char] += 1
    print(countdict)
def char_count(str):
    countdict = {}
    for char in str:
        countdict[char] = countdict.setdefault(char, 0) + 1
    print(countdict)
使用 global 关键字，对函数中的 a 标志为全局变量，让函数内部使用全局变量的 a，那么整个程序中出现的 a 都将是这个


#!/usr/bin/env python3
a = 9
def change():
    global a
    print(a)
print("Before the function call ", a)
print("inside change function", end=' ')# end=' ' 参数表示，print 打印后的结尾不用换行，而用空格。默认情况下 print 打印后会在结尾换行。
change()
print("After the function call ", a)
>>> def connect(ipaddress, port):
...     print("IP: ", ipaddress)
...     print("Port: ", port)
>>> connect(port=22, ipaddress='192.168.1.1')
IP:  192.168.1.1
Port:  22
第一个是具有默认值的参数后面不能再有普通参数，比如 f(a,b=90,c) 就是错误的。
第二个是默认值只被赋值一次，因此如果默认值是任何可变对象时会有所不同，比如列表、字典或大多数类的实例。例如，下面的函数在后续调用过程中会累积（前面）传给它的参数:
>>> def f(a, data=[]):
...     data.append(a)
...     return data
...
>>> print(f(1))
[1]
>>> print(f(2))
[1, 2]

如果默认 data = [] 第二次的 data 默认值会包含第一次的结果，所以造成每次默认值是不同的
>>> def f(a, data=None):
...     if data is None:
...         data = []
...     data.append(a)
...     return data
...
>>> print(f(1))
[1]
>>> print(f(2))
[2] 

可变参数的使用方法是在参数列表前加上 *
>>> def connect(ipaddress, *ports):
...     print("IP: ", ipaddress)
...     for port in ports:
...         print("Port: ", port)


Python 中的对象有不可变对象，指的是数值、字符串、元组等，和可变对象，指的是列表、字典等。如果是不可变对象作为参数，相当于是值的传递，函数中对该参数的修改不会保留。如果是可变对象，则相当于传引用，函数中的修改会保留。

面向对象的 4 个核心概念：

抽象
封装
继承
多态

object 是 Python 中所有对象的祖先，它是所有类的基类。类需要一个初始化方法，__init__ 是 Python 的初始化方法，注意前后各有两个下划线 _，self指代当前的对象
class Dog(object):
    def __init__(self, name):
        self._name = name
    def get_name(self):
        return self._name
    def set_name(self, value):
        self._name = value
    def bark(self):
        print(self.get_name() + 'is making sound wang wang wang...')

类是一个抽象的概念，而实例是一个具体的对象。比如说狗是一个抽象的概念，因为狗有很多种，而那个正在 wang wang 叫的叫旺财的狗是一个实例。
class Animal(object):
    def __init__(self, name):
        self._name = name
    def get_name(self):
        return self._name
    def set_name(self, value):
        self._name = value
    def make_sound(self):
        pass
class Dog(Animal):
    def make_sound(self):
        print(self.get_name() + ' is making sound wang wang wang...')
cat = Dog('Kitty')
dog.make_sound()

多态就是使用同一方法对不同对象可以产生不同的结果。
animals = [Dog('旺财'), Cat('Kitty'), Dog('来福'), Cat('Betty')]
for animal in animals:
    animal.make_sound()
在 Python 中约定在属性方法名前添加 __ （两个下划线 _）来拒绝外部的访问

>>> class Shiyanlou:                                                                                                                                                                                                
...   __private_name = 'shiyanlou'                                                                                                                                                                                
...   def __get_private_name(self):                                                                                   
...     return self.__private_name                                                                                    
...                                                                                                                   
>>> s = Shiyanlou()                                                                                                                                                                                                                
>>> s.__private_name                                                                                                  
Traceback (most recent call last):                                                                                    
  File "<stdin>", line 1, in <module>                                                                                 
AttributeError: 'Shiyanlou' object has no attribute '__private_name'   
Python 中不是绝对的私有，还是通过 obj._Classname__privateAttributeOrMethod 来访问：

>>> s._Shiyanlou__private_name                                                                                        
'shiyanlou'
>>> s._Shiyanlou__get_private_name()                                                                                  
'shiyanlou'
静态变量和类方法是可以直接从类访问，不需要实例化对象就能访问。

class Animal(object):
    owner = 'jack'
    def __init__(self, name):
        self._name = name
现在可以通过 Animal 或者子类直接访问

print(Animal.owner)  # 'jack'
print(Cat.owner)  # 'jack'
类方法和静态变量类似，它也可以通过类名直接访问，类方法用 @classmethod 装饰，类方法中可以访问类的静态变量，下面添加了一个类方法 get_owner：
class Animal(object):
    owner = 'jack'
    def __init__(self, name):
        self._name = name
    @classmethod
    def get_owner(cls):
        return cls.owner
注意类方法的第一个参数传入的是类对象，而不是实例对象，所以是 cls。 

print(Animal.get_owner())  # 'jack'
print(Cat.get_owner())  # 'jack'
property 可以将方法变成一个属性来使用，借助 property 可以实行 Python 风格的 getter/setter，即可以通过 property 获得和修改对象的某一个属性
 class Animal(object):
    def __init__(self, name):
        self._name = name
    @property
    def name(self):
        return self._name
    @name.setter
    def name(self, value):
        self._name = value
    def make_sound(self):
        pass     
 静态方法用 @staticmethod 装饰，和 classmethod 有点类似。staticmethod 在运行时不需要实例的参与，它被放在类下面只是因为它和类有一点关系，但并不像类方法那样需要传递一个 cls 参数。

静态方法的应用场景是当一个函数完全可以放到类外面单独实现的时候，如果这个函数和类还有一点联系，那么放入类中能更好的组织代码逻辑，那么可以考虑使用类中的静态方法。

class Animal(object):
    owner = 'jack'
    def __init__(self, name):
        self._name = name

    @staticmethod
    def order_animal_food():
        print('ording...')
        print('ok')
        
Animal.order_animal_food()        
 >>> with open('/etc/protocols') as file:
...     count = 0
...     for line in file:
...         count += 1
...     print(count)     
通常会采用逐行处理，readline() 就是用来每次读取文件的一行，readlines() 可以读取所有行，但不同于 read()，这个函数的返回的是一个列表，列表中每个元素都是对应文本文件中一行内容的字符串
>>> file = open(filename)
>>> file.readline()
'I love Python\n'
>>> file.readline()
'lou+ at shiyanlou.com\n'
>>> file.close()

 for 循环遍历文件对象来读取文件中的每一行：

>>> file = open(filename)
>>> for x in file:
...     print(x, end = '')
import sys

def copy_file(src, dst):
    with open(src, 'r') as src_file:
        with open(dst, 'w') as dst_file:
            dst_file.write(src_file.read())

if __name__ == '__main__':
    if len(sys.argv) == 3:
        copy_file(sys.argv[1], sys.argv[2])
    else:
        print("Parameter Error")
        print(sys.argv[0], "srcfile dstfile")
        sys.exit(-1)
    sys.exit(0)
    写入和读取文件都需要使用 b 二进制模式
    >>> import pickle
>>> courses = { 1:'Linux', 2:'Vim', 3:'Git'}
>>> with open('./courses.data', 'wb') as file:
...     pickle.dump(courses, file)
...
>>> with open('./courses.data', 'rb') as file:
...     new_courses = pickle.load(file)
# 获取 numbers 中的所有偶数
>>> [x for x in numbers if x % 2 == 0]
[2, 4, 6, 8, 10]
# 对 numbers 的每个数求平方
>>> [x * x for x in numbers]
[1, 4, 9, 16, 25, 36, 47, 84, 81, 100]
>>> numbers = [1, 2, 3, 4, 5, 6, 7, 8, 9, 10]
>>> f = filter(lambda x: x % 2 == 0, numbers)
>>> m = map(lambda x: x * x, numbers)      
>>> d = {'a': 1, 'b': 2, 'c': 3}
>>> {k:v*v for k, v in d.items()}
{'a': 1, 'b': 4, 'c': 9}

>>> letters = ['a', 'b', 'c']
>>> it = iter(letters)
>>> next(it)
'a'
>>> next(it)
'b'
>>> next(it)
'c'
>>> next(it)
Traceback (most recent call last):
  File "<stdin>", line 1, in <module>
StopIteration
要用 next 函数不断的去获取它的下一个值，直到迭代器返回 StopIteration异常。所有的可迭代对象都可以通过 iter 函数去获取它的迭代器
字典是不能被迭代的，需要使用字典的方法 items() 把字典变成一个可迭代对象 
能被 for 循环访问的都是可迭代的对象，能被 next() 函数获取下一个值的是迭代器。
生成器只能被迭代一次，因为每次迭代的元素不是像列表元素一样，已经在内存中，而是你每迭代一次，它生成一个元素。
>>> g = (x**x for x in range(1, 4))
>>> g
<generator object <genexpr> at 0x10d1a5af0>
>>> for x in g:
...     print(x)
...
1
4
27
 和列表解析有点像，只不过使用的是圆括号。不同于列表可以反复迭代，再迭代这个迭代器，它不会打印元素，也不回报错。

使用生成器有什么好处呢？因为生成器不是把所有元素存在内存，而是动态生成的，所以当你要迭代的对象有非常多的元素时，使用生成器能为你节约很多内存，这是一个内存友好的特性。
 yield 的使用方法和 return 类似。不同的是，return 可以返回有效的 Python 对象，而 yield 返回的是一个生成器，函数碰到 return 就直接返回了，使用了 yield 的函数，到 yield 返回一个元素，当再次迭代生成器时，会从 yield 后面继续执行，直到遇到下一个 yield 或者函数结束退出。
>>> def fib(n):
...     current = 0
...     a, b = 1, 1
...     while current < n:
...         yield a
...         a, b = b, a + b
...         current += 1
>>> f5 = fib(5)
>>> f5
<generator object fib at 0x10d1a5888>  https://www.shiyanlou.com/courses/983/labs/3961/document


