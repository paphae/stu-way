---
title: python-笔记
date: 2019-08-19 10:19:11
tags: 笔记
---

## 异常处理
try语句按照如下方式工作；
首先，执行try子句（在关键字try和关键字except之间的语句）
如果没有异常发生，忽略except子句，try子句执行后结束。
<!-- more -->
如果在执行try子句的过程中发生了异常，那么try子句余下的部分将被忽略。如果异常的类型和 except 之后的名称相符，那么对应的except子句将被执行。最后执行 try 语句之后的代码。
如果一个异常没有与任何的except匹配，那么这个异常将会传递给上层的try中。

一个 try 语句可能包含多个except子句，分别来处理不同的特定的异常。最多只有一个分支会被执行。

处理程序将只针对对应的try子句中的异常进行处理，而不是其他的 try 的处理程序中的异常。

一个except子句可以同时处理多个异常，这些异常将被放在一个括号里成为一个元组
### 用户自定义异常 ：
~~~python
class Ageerr(Exception):
    pass

try:
    age = int(input("Enter the age:"))
    if age < 18:
        raise Ageerr("error message ")
except Exception as err:
    print("{}".format(err))
~~~
输出
Enter the age:15
error message
### range()参数
def xrange(star,stop=None,step=1):
if stop == None:
star,stop =0,star
print(star,stop,step)
~~~python
if __name__ == '__main__':
    xrange(1,2)
~~~
### 不定长参数
加了星号 * 的参数会以元组(tuple)的形式导入，存放所有未命名的变量参数。
~~~python
def add_employee(name,*skills):
    dt = {}
    dt[name]=skills

professional_skills = tuple(input("输入专业技能(用,隔开)：").split(","))
    add_employee(name,*professional_skills)
~~~
加了两个星号 ** 的参数会以字典的形式导入。
~~~python
def printinfo( arg1, **vardict ):
   "打印任何传入的参数"
   print ("输出: ")
   print (arg1)
   print (vardict)

# 调用printinfo 函数
printinfo(1, a=2,b=3)
~~~
#### property() 方法的语法:
- fget – 获取属性值的函数
- fset – 设置属性值的函数
- fdel – 删除属性值函数
- doc – 属性描述信息

实例
~~~python
class C(object):
    def __init__(self):
        self._x = None

    def getx(self):
        return self._x

    def setx(self, value):
        self._x = value

    def delx(self):
        del self._x

x = property(getx, setx, delx, "I'm the 'x' property.")
~~~
### 装饰器
Python 函数装饰器
<https://www.runoob.com/w3cnote/python-func-decorators.html>



