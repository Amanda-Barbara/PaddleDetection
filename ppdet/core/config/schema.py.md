# schema.py代码解析

## SharedConfig类
**Q:** 某些配置项会在多个模块中用到(如 `num_classes`)，如何避免在配置文件中多次重复设置？ </br>
**A:** 框架提供了 `__shared__` 标记来实现配置的共享，用户可以标记参数，如 `__shared__ = ['num_classes']` ，配置数值作用规则如下：

1.  如果模块配置中提供了 `num_classes` ，会优先使用其数值。
2.  如果模块配置中未提供 `num_classes` ，但配置文件中存在全局键值，那么会使用全局键值。
3.  两者均为配置的情况下，将使用默认值(`81`)。

## 类对象可以在程序中添加自定义对象变量
```text
schema.pymodule = importlib.import_module(cls.__module__)
schema.inject = getattr(cls, '__inject__', [])
schema.shared = getattr(cls, '__shared__', [])
```


## 参考链接
* 1 [SharedConfig类解析](../../../static/docs/FAQ.md)