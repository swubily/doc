jvm 调优



1. 查看linux所有进程内存占用并按大小排序

   **ps aux  --sort  -rss**

JAVA_OPT="-Xms512m -Xmx512m -Xmn256m -Djava.ext.dirs=${JAVA_HOME}/jre/lib/ext:${JAVA_HOME}/lib/ext -Xloggc:/var/log/yaomi/gc/admin_gc.log -verbose:gc -XX:+PrintGCDetails -XX:+PrintGCDateStamps -XX:+PrintGCTimeStamps -XX:+UseGCLogFileRotation -XX:NumberOfGCLogFiles=5 -XX:GCLogFileSize=10M"

nohup java -jar ${JAVA_OPT} 



2. java进程高cpu分析

   top  查看cpu高的进程

   top -p <pid>  -H 查看cpu高的线程

   jstack <pid>|grep -A 10 <ppid 十六进制>
   
   

3. java进程退出

   - linux的OOM killer杀死

     egrep -i 'killed process' /var/log/messages

     dmesg | grep java

     输出如下

     ```
     [5673702.665338] Out of memory: Kill process 29953 (java) score 431 or sacrifice child
     [5673702.665338] Killed process 29953, UID 500, (java) total-vm:9805316kB, anon-rss:2344496kB, file-rss:128kB
     ```

   - JVM自身故障

   - jvm的OOM导致进程退出

   4. tcp ：
   
      <https://blog.csdn.net/smileiam/article/details/78226816>