java -server -Xms1024m -Xmx1024m -Xmn400m -Xss512k -XX:PermSize=64M -XX:MaxPermSize=64m

-XX:+UseFastAccessorMethods //不用设置，默认就是开启的，不过JDK7默认是false 因为JDK7采用多层编译

-XX:+UseConcMarkSweepGC

-XX:+CMSPermGenSweepingEnabled

-XX:+CMSClassUnloadingEnabled

-XX:MaxTenuringThreshold=5

-Dcom.sun.management.jmxremote.port=1090

-XX:SurvivorRatio=8 

-XX:GCTimeRatio=19

-XX:+DisableExplicitGC

-XX:+UseParNewGC
..................
-XX:+UseCMSCompactAtFullCollection //不用设置，默认就是开启的

-XX:CMSFullGCsBeforeCompaction=0

-XX:-CMSParallelRemarkEnabled  //不用设置，默认就是开启的

-XX:CMSInitiatingOccupancyFraction=70

-XX:SoftRefLRUPolicyMSPerMB=0


DisableExplicitGC //不是和 native memory

HeapDumpOnOutOfMemoryError

-XX:+PrintGCTimeStamps //JVM以启动时间为基准的相对时间，对于troubleshooting来说非常困难
-XX:+PrintGCDateStamps // 打印出来的就是真实的日期


http://answers.microsoft.com/zh-hans/windows/forum/windows_8-windows_update/windowsupdate80070057/a62fb7b5-a0db-440b-b397-93e364a3d438