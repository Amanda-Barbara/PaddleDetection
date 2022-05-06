# `workspace.py`代码解析

## `register(cls)`
* 把`cls`注册到以`cls.__name__`为字典的`key`，以`SchemaDict`类对象为字典的`value`的
  global_config字典对象中。
* 

## [对象的直接赋值、浅拷贝、深拷贝](https://www.runoob.com/w3cnote/python-understanding-dict-copy-shallow-or-deep.html)
* `dct = another_cfg or global_config`直接赋值相当于对象的引用，两个对象则指向了共同的区域
* 直接赋值相当于对象的引用，浅拷贝则指向了两个对象共同的子内存区域，深拷贝则是指向了两个不同的内存区域

## 参考链接
* 1 [`Python`模块`__all__`变量](http://c.biancheng.net/view/2401.html)