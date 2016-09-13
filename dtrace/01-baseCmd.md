# Dtrace基本命令

## 列出探测器:dtrace -l

列出所有探测器
```shell
# dtrace -l
```
列出某模块关联的探测器
```shell
# dtrace -l -m moudleName
```
列出某特定函数关联的探测器
```shell
# dtrace -l -f functionName
```
列出某特定提供者启动的探测器
```shell
# dtrace -l -P providerName
```

列出某特定名称的探测器
```shell
# dtrace -l -n name
```

根据ID指定某一个特定探测器
```shell
# dtrace -l -i 13
```
根据名称四元组指定某一个特定探测器
```shell
# dtrace -l -n provider:moudle:function:name
```
灵活使用名称四元组
```shell
# dtrace -l -n function:name //指定方法和名称
# dtrace -l -n moudle::name  //指定模块和名称
# dtrace -l -n provider:mou*::name  //模式匹配
```

> 注意： dtrace -l －n xx -m yy，含义相当于name＝xx OR moudole=yy。

* dtrace -l 的输出格式

|ID|PROVIDER|MODULE|FUNCTION|NAME|
|:----|:-----|:-----|:-----|:-----|
|13|lockstat|mach_kernel|lck_mtx_lock|adaptive-acquire|
