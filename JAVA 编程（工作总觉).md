**ls**

**1.工作中遇到的死锁问题：**

​     \1. Hession问题，使用hession时做webservice的时候，发现文件输出没有成功，并且没有错误和异常发生。

​       猜测是文件过大，没有足够的内存分配。使用jstatc工具分析，证实确实程序阻塞在数组拷贝阶段，hession的实现机制过于死板，不适合大文件传输，升级Hession问题解决。

​     2.NPS线程池问题，在跑NPS capa 测试的时候会出现capa的TPS一直为0，且不可恢复。猜测程序死锁，测试多次无果，且程序有大量的进程和线程，及使用第三方的包多，没法用jstatc做分析。于是只有代码走查，后发现程序在使用线程池的时候不正常，一个操作中使用了两个单独的线程池连接，导致开始的第一步操作就耗光了连接，而后面的操作无法取到连接而程序一直阻塞。解决办法使用两个单独的线程池。

​     3.NPS线程池问题，Bytel vaas平台BE存错掉了，oracle采用RAC active-active模式，OS层socket正常，导致连接永不超时，出现个别连接hung住，connection pool从而死锁。





<http://www.oracle.com/technetwork/java/javase/index-138283.html#guides>

<http://docs.oracle.com/javase/7/docs/index.html>

<http://docs.oracle.com/javase/specs/index.html>

<http://docs.oracle.com/javase/7/docs/webnotes/tsg/index.html>

<http://tech.qq.com/a/20060726/000329.htm>

<http://program-think.blogspot.com/2009/04/java-performance-tuning-3-gc.html>

<http://www.oracle.com/technetwork/java/javase/gc-tuning-6-140523.html>

<http://docs.oracle.com/javase/specs/jvms/se7/jvms7.pdf>







jvm training :



<http://www.csee.umbc.edu/courses/graduate/631/Fall2002/hotspot.pdf>

<http://jiangyongyuan.iteye.com/blog/434703>

<http://www.oracle.com/technetwork/java/whitepaper-135217.html>

<http://www.oracle.com/technetwork/java/javase/documentation/whitepapers-jsp-139357.html>