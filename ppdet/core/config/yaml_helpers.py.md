# yaml_helpers.py代码解析

## `serializable(cls)`
* 通过yaml.add_constructor、yaml.add_representer分别向yaml注册cls类的序列化(load:yaml对象转为python对象)，反序列化(dump:python对象转为yaml对象)的功能表单

## `yaml.add_constructor`的自定义类的注册函数(负责解析yaml对象并转为python对象)
```text
def _make_python_constructor(cls): # yaml对象转为python对象
    def python_constructor(loader, node):
        if isinstance(node, yaml.SequenceNode): #解析node初始化参数类型，如果是列表形式，则使用loader.construct_sequence
            args = loader.construct_sequence(node, deep=True)
            return cls(*args)
        else:
            kwargs = loader.construct_mapping(node, deep=True) #如果node的初始化参数是字典类型，则使用loader.construct_mapping
            try:
                return cls(**kwargs)
            except Exception as ex:
                print("Error when construct {} instance from yaml config".
                      format(cls.__name__))
                raise ex

    return python_constructor
```

## 参考链接
* 1 [yaml序列化与反序列化](https://www.cnblogs.com/klb561/p/9326677.html)