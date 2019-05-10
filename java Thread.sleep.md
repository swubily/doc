

备注：Unix操作系统是采用时间片算法处理多进程（线程），Windows是采用的抢占式算法。Thread.sleep 就是告诉操作系统在未来的多少时间里我不需要CPU的执行权，但是到sleep结束后不一定马上能获得cpu的执行权，有可能有高优先级的进程或者未排到你的进程。

JVM（java 虚拟机）也是采用抢占式的算法，sleep（）是告诉jvm我多少时间内不需要cpu，yield（）（应该和sleep（0）一个意思）就是告诉jvm外面还有其他优先级高的线程没有，有就让他们先执行，没有就继续

由Thread.sleep引发的 - chivalry - 博客频道 - CSDN.NET

![img](file:///C:/Users/zhanwang/AppData/Local/Temp/enhtmlclip/Image(1).png)

![img](file:///C:/Users/zhanwang/AppData/Local/Temp/enhtmlclip/favicon.ico.png)<http://blog.csdn.net/sunmenggmail/article/details/16118495>

以下是i3D的一篇Unity教程中的笔记.i3D的这篇教程是[i3D.Next-Gen.Game.Development.with.Unity3D.Volume.I]对Unity有兴趣的CGer可能有帮助.----------------------------------------------------------------Fbx、贴图导入Unity时的注意事项：在