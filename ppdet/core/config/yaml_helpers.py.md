# yaml_helpers.py代码解析

## `serializable(cls)`
* 通过yaml.add_constructor、yaml.add_representer分别向yaml注册cls类的序列化(load:yaml对象转为python对象)，反序列化(dump:python对象转为yaml对象)的功能表单



## 参考链接
* 1 [yaml序列化与反序列化](https://www.cnblogs.com/klb561/p/9326677.html)