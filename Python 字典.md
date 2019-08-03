# Python 字典(Dictionary)
字典是另一种可变容器模型，且可存储任意类型对象。

字典的每个键值 `key=>value` 对用冒号 `:` 分割，每个键值对之间用逗号 `,` 分割，整个字典包括在花括号 `{}` 中 ,格式如下所示：
```
d = {key1 : value1, key2 : value2 }
```
键一般是唯一的，如果重复最后的一个键值对会替换前面的，值不需要唯一。
```py
>>>dict = {'a': 1, 'b': 2, 'b': '3'}
>>> dict['b']
'3'
>>> dict
{'a': 1, 'b': '3'}
```
值可以取任何数据类型，但键必须是不可变的，如字符串，数字或元组。

一个简单的字典实例：
```
dict = {'Alice': '2341', 'Beth': '9102', 'Cecil': '3258'}
```
也可如此创建字典：
```
dict1 = { 'abc': 456 }
dict2 = { 'abc': 123, 98.6: 37 }
```
---
## 访问字典里的值
把相应的键放入熟悉的方括弧，如下实例:

**实例**
```py
#!/usr/bin/python

dict = {'Name': 'Zara', 'Age': 7, 'Class': 'First'}

print "dict['Name']: ", dict['Name']
print "dict['Age']: ", dict['Age']
```
以上实例输出结果：
```
dict['Name']:  Zara
dict['Age']:  7
```
如果用字典里没有的键访问数据，会输出错误如下：

**实例**
```py
#!/usr/bin/python

dict = {'Name': 'Zara', 'Age': 7, 'Class': 'First'}

print "dict['Alice']: ", dict['Alice']
```
以上实例输出结果：
```
dict['Alice']:
Traceback (most recent call last):
  File "test.py", line 5, in <module>
    print "dict['Alice']: ", dict['Alice']
KeyError: 'Alice'
```
---
## 修改字典
向字典添加新内容的方法是增加新的键/值对，修改或删除已有键/值对如下实例:

**实例**
```
#!/usr/bin/python

dict = {'Name': 'Zara', 'Age': 7, 'Class': 'First'}

dict['Age'] = 8 # 更新
dict['School'] = "RUNOOB" # 添加


print "dict['Age']: ", dict['Age']
print "dict['School']: ", dict['School']
```
以上实例输出结果：
```
dict['Age']:  8
dict['School']:  RUNOOB
```
---
## 删除字典元素
能删单一的元素也能清空字典，清空只需一项操作。

显示删除一个字典用del命令，如下实例：

**实例**
```py
#!/usr/bin/python
# -*- coding: UTF-8 -*-

dict = {'Name': 'Zara', 'Age': 7, 'Class': 'First'}

del dict['Name']  # 删除键是'Name'的条目
dict.clear()      # 清空字典所有条目
del dict          # 删除字典

print "dict['Age']: ", dict['Age']
print "dict['School']: ", dict['School']
```
但这会引发一个异常，因为用del后字典不再存在：
```shell
dict['Age']:
Traceback (most recent call last):
  File "test.py", line 8, in <module>
    print "dict['Age']: ", dict['Age']
TypeError: 'type' object is unsubscriptable
```
**注：** del()方法后面也会讨论。


#### 字典键的特性
字典值可以没有限制地取任何python对象，既可以是标准的对象，也可以是用户定义的，但键不行。

两个重要的点需要记住：

1）不允许同一个键出现两次。创建时如果同一个键被赋值两次，后一个值会被记住，如下实例：

**实例**
```py
#!/usr/bin/python

dict = {'Name': 'Zara', 'Age': 7, 'Name': 'Manni'}

print "dict['Name']: ", dict['Name']
```
以上实例输出结果：
```
dict['Name']:  Manni
```
2）键必须不可变，所以可以用数字，字符串或元组充当，所以用列表就不行，如下实例：

**实例**
```py
#!/usr/bin/python

dict = {['Name']: 'Zara', 'Age': 7}

print "dict['Name']: ", dict['Name']
```
以上实例输出结果：
```
Traceback (most recent call last):
  File "test.py", line 3, in <module>
    dict = {['Name']: 'Zara', 'Age': 7}
TypeError: list objects are unhashable
```
---
