---
title: python笔记二
date: 2019-08-16 15:28:46
tags: 笔记
---
Python Number 数据类型用于存储数值。
数据类型是不允许改变的,这就意味着如果改变 Number 数据类型的值，将重新分配内存空间。
<!-- more -->
### 数字函数
|函数	|说明|
|----|----|
|abs(x)|	返回数字的绝对值，如abs(-10) 返回 10|
|fabs(x)	|返回数字的绝对值，如math.fabs(-10) 返回10.0|
|max(x1, x2,…)	|返回给定参数的最大值，参数可以为序列。|
|min(x1, x2,…)	|返回给定参数的最小值，参数可以为序列。|
|pow(x, y)|	x**y 运算后的值。|
|sqrt(x)	|返回数字x的平方根。|
|modf(x)	|返回x的小数部分与整数部分，整数部分以浮点型表示。(返回元组)|
|random()	|随机生成下一个实数，它在[0,1)范围内。|
### 字符串
字符串格式化
~~~python
print ("我叫 %s 今年 %d 岁!" % ('小明', 10))
~~~
|函数|	参数|	说明|
|-----|-----|
|count	|(str, beg= 0,end=len(string))	|返回 str 在 string 里面出现的次数，如果 beg 或者 end 指定则返回指定范围内 str 出现的次数|
|endswith	|(suffix, beg=0, end=len(string))|	检查字符串是否以 obj 结束，如果beg 或者 end 指定则检查指定的范围内是否以 obj 结束，如果是，返回 True,否则返回 False.|
|find	|(str, beg=0, end=len(string))|	检测 str 是否包含在字符串中，如果指定范围 beg 和 end ，则检查是否包含在指定范围内，如果包含返回开始的索引值，否则返回-1|
|index	|(str, beg=0, end=len(string))|	跟find()方法一样，只不过如果str不在字符串中会报一个异常.|
|split	|(str=””, num=string.count(str))	num=string.count(str)) |以 str 为分隔符截取字符串，如果 num 有指定值，则仅截取 num+1 个子字符串|
|replace	|(old, new [, max])|	将字符串中的 str1 替换成 str2,如果 max 指定，则替换不超过 max 次。|
|strip	|([chars])	|方法用于移除字符串头尾指定的字符（默认为空格）或字符序列。|
### 字符编码
~~~python
import chardet
s = '学习'
a = s.encode('utf-8')
print(chardet.detect(a))
a.decode("utf-8")
~~~
### 实例输出
~~~
{'encoding': 'utf-8', 'confidence': 0.7525, 'language': ''}
'学习'
~~~
### 列表函数
~~~python
list.append(obj)                            #在列表末尾添加新的对象
list.count(obj)                                #统计某个元素在列表中出现的次数
list.sort( key=None, reverse=False)            #reverse -- 排序规则，reverse = True 降序， reverse = False 升序（默认）。
~~~
实例
~~~python
ls1 = [ [i for i in range(5)] for i in range(5)]
~~~
输出
~~~python
[[0, 1, 2, 3, 4],
 [0, 1, 2, 3, 4],
 [0, 1, 2, 3, 4],
 [0, 1, 2, 3, 4],
 [0, 1, 2, 3, 4]]
~~~
实例 : 复制得到一个新列表并改变新列表内元素而不影响原列表
~~~python
>>> a = [1,2,3]
>>> b = a
>>> b[0] = 5
>>> a
>>> b
~~~
输出
~~~
[5, 2, 3]
[5, 2, 3]
~~~
方法一：
~~~python
>>> c = b.copy()
>>> c[0] = 6
>>> c
>>> b
~~~
~~~
[6, 2, 3]
[5, 2, 3]
~~~
方法二：
~~~python
>>> d = a[:]
>>> d[0] = 8
>>> a
>>> d
~~~
~~~
[5, 2, 3]
[8, 2, 3]
~~~