# 虚拟机统计信息 jstat


## jstat作用

* 类加载信息
* 垃圾回收信息
* jit编译

## 命令格式
```
# jstat 
invalid argument count
Usage: jstat -help|-options
       jstat -<option> [-t] [-h<lines>] <vmid> [<interval> [<count>]]

```


## 实战

* 查看类加载信息
```
# jstat -class 19870
Loaded  Bytes  Unloaded  Bytes     Time   
 13091 25923.0        0     0.0      15.03
```

* 每隔1S打印一次GC信息，打印3次

```
jstat -gc 19870 1000 3
 S0C    S1C    S0U    S1U      EC       EU        OC         OU       MC     MU    CCSC   CCSU   YGC     YGCT    FGC    FGCT     GCT   
78592.0 78592.0 8501.5  0.0   629248.0 84831.4  1310720.0   85024.1   84824.0 82467.8 9344.0 8803.0     38    1.439   3      0.711    2.150
78592.0 78592.0 8501.5  0.0   629248.0 86797.7  1310720.0   85024.1   84824.0 82467.8 9344.0 8803.0     38    1.439   3      0.711    2.150
78592.0 78592.0 8501.5  0.0   629248.0 86895.2  1310720.0   85024.1   84824.0 82467.8 9344.0 8803.0     38    1.439   3      0.711    2.150
```



[官方文档](https://docs.oracle.com/javase/8/docs/technotes/tools/unix/index.html)