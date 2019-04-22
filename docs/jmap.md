# 内存溢出 jmap

## 如何导出内存映像文件

### 内存溢出自动导出

-XX:+HeapDumpOnOutOfMemoryError
-XX:+HeapDumpPath=./

EG:
```
-Xmx32M -Xms32M -XX:+HeapDumpOnOutOfMemoryError -XX:+HeapDumpPath=./
```

> 自动导出文件格式为hprof格式

### 使用jmap命令手动导出

```
$ jmap -dump:format=b,file=heap.hprof 2116
Dumping heap to /Users/fangle/heap.hprof ...
```

## map 分析内存溢出

使用[eclipse memory analyzer ](https://www.eclipse.org/mat/downloads.php)

![image.png](https://upload-images.jianshu.io/upload_images/11852957-fad077f73c609001.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)
