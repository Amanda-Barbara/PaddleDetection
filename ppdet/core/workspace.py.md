# `workspace.py`代码解析

## `register(cls)`
* 把`cls`注册到以`cls.__name__`为字典的`key`，以`SchemaDict`类对象为字典的`value`的
  global_config字典对象中。
* 

## [对象的直接赋值、浅拷贝、深拷贝](https://www.runoob.com/w3cnote/python-understanding-dict-copy-shallow-or-deep.html)
* `dct = another_cfg or global_config`直接赋值相当于对象的引用，两个对象则指向了共同的区域
* 直接赋值相当于对象的引用，浅拷贝则指向了两个对象共同的子内存区域，深拷贝则是指向了两个不同的内存区域

## 对于字典的直接赋值案例
* `dict_merge(dct[k], merge_dct[k])`如果`dct[k]`是字典，则相当于对象的引用，会对dct进行更新
* 
```text
d1 = dict(one=1, two=2)
d1['thr'] = {'t' : 3}
d1['four'] = 4
sub3 = d1['thr']
sub3['t'] = 8
print(d1)
sub4 = d1['four'] #如果d1['four']只是一个普通变量，sub4则相当于深拷贝
sub4 = 9 
print(sub4)
print(d1)
```
执行结果
```text
{'one': 1, 'two': 2, 'thr': {'t': 8}, 'four': 4}
9
{'one': 1, 'two': 2, 'thr': {'t': 8}, 'four': 4}
```

## 参考链接
* 1 [`Python`模块`__all__`变量](http://c.biancheng.net/view/2401.html)