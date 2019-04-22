# 线程死循环与死锁 jstack(cpu利用率高)

## 导出jstack文件

```
jps -l    # 获取进程
jstack 2116 > 2116.txt
```

## 线程的状态

![image.png](https://upload-images.jianshu.io/upload_images/11852957-80ae4b111b2e1e00.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)

![image.png](https://upload-images.jianshu.io/upload_images/11852957-3e23e7db3457c04c.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)

> 线程更多知识参考：https://mp.weixin.qq.com/s/GsxeFM7QWuR--Kbpb7At2w

## 实战

### 死循环
```
jps -l   
jstack pid >pid.txt
top -p pid -H                         #  显示线程，并找出cpu利用率最大的线程
printf "%x" 10进制线程id      # 转换成为16进制
# 可打开文件pid.txt，查看搜索16进制
``` 

### 死锁

与死循环类似，可直接在pid.txt文件中搜索到dead关键字。

