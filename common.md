IT :

归还电脑，

share folder访问问题

功能键问题







\\10.140.0.134\sharefolder\global\CHENGDU_MESSAGING\NEMS
联通账号02802317094   000000   Qwer!234
10.159.224.230 8080  10.144.1.10 8080   10.140.0.135

rpm -qa --queryformat "%{name}.%{arch}\n" |grep gcc

https_proxy = http://10.144.1.10:8080

pip --proxy=http://10.144.1.10:8080     install --upgrade robotframework==2.8.5


http://finance.sina.com.cn/money/fund/20131009/070116928367.shtml#J_Comment_Wrap
删除目录及子目录下所有的class文件：find  .  -name  '*.exe'  -type  f  -print  -exec  rm  -rf  {} \;

BigIP:
https://10.69.171.41/xui/
admin
VaaS1.1!
删除clearcase的view
ct rmview -f -tag mmsc_mc50ed01_mc50ed02_mc5021_license_zhanwang

@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@TEST drivering@@@@@@@@@@@@@@@@@@@@@@@@@@@@@
1.大概关键，逻辑代码
2.测试类编写（UT）
3.完善代码，测试代码

<a LDAP 浏览器:
10.68.72.100
cn=Manager,fsClusterId=caui,dc=nsn,dc=com
admin

10.56.239.125
fsClusterId=ClusterRoot
secret

10.140.2.151
cn=Manager,fsClusterId=adapp,dc=nsn,dc=com
admin
<a>
<a
#########################################NET STAT#################################
netstat -an|grep 8999

<a>
######################################## LDAP MANAGEMENT ########################################################
1.   LDAP backup&Restore

ldapsearch -w 'admin' -x -b 'fsClusterId=caui,dc=nsn,dc=com' -D 'cn=Manager,fsClusterId=caui,dc=nsn,dc=com'> test.ldif

ldapadd -w 'admin' -x -D'cn=Manager,fsClusterId=caui,dc=nsn,dc=com'  -f ./init.ldif

2.启动LDAP

slapd/service ldap start

3.LDAP数据文件
/var/lib/ldap-mind/.


4.MMSC 重装LDAP
1）stop LDAP
2）cd /var/mnt/local/ldap/  rm -f *
3)start LDAP
4)/opt/Nokia/SS_MMSC_LDAPDATA/initLdap.sh
5)restart LDAP


5. LDAP 浏览器添加节点
1）新建节点
2）copy branch。

//conf
/opt/Nokia/SS_MMSC/conf/fssescldap.ldaproot

mysqldump -u root -p2008 caui >test.sql

启动ＭＹＳＱＬ ＆ ＬＤＡＰ & infomix
如果没有启动mysql，先启动mysql
service mysqld start
若果没有注册service，则 /etc/rc.d/init.d/mysqld start

imformix
启动：oninit -v
停止：onmode -ky
查看：onstat -

1.clearcase:
host: gemini.nsn-net.net

2.


LDAPURI=ldap://10.68.72.100:389/fsClusterId=caui,dc=nsn,dc=com


#################################################CRONTAB---crontab######################################
1.crontab -u caui /var/spool/cron/caui 重新执行crontab

XSS-----------------------------XSS-----------------------------
http://www.javaeye.com/problems/10135
http://www.javaeye.com/problems/9857
http://www.javaeye.com/problems/37503
http://baike.baidu.com/view/2161269.htm
http://topic.csdn.net/u/20091221/18/6693545C-A659-4E3B-9454-EBB77D6C8D1F.html
http://topic.csdn.net/u/20081205/09/3dd06076-bcbe-45d4-998c-8999fdbe6fae.html?84220
http://www.knowsky.com/15399.html
http://qingbo.net/blog/post380.html
http://hi.baidu.com/haifengjava/blog/item/39857e3d9ab879e63d6d97d3.html
http://tdcq.javaeye.com/blog/572137

http://www.owasp.org/index.php/Top_10_2010


if(true){
          window.open ("../common/recordList.jsp", "newwindow", "height=200, width=600, location=no toolbar=no, menubar=no, scrollbars=yes, resizable=no, location=no, status=no");
     }



MMSC CONF

/etc/opt/nokia/mmsc/conf



###########################################LINUX----COMMON ##################################################
1.查看java线程
用ps -eLf | grep java | wc 查看系统里运行的java线程数

2.查看java线程信息
1） 先用ps + grep找出该死的进程pid，比如 30420
2） top -H -p 30420，所有该进程的线程都列出来了。看看哪个线程pid占用最多，然后将这个pid转换为16进制，如 44bf，注意要小写
3） jstack 30420 | less，然后查找 nid=0x44bf，哦，找到了
Shell代码

   1. "main" prio=10 tid=0x0000000053911400 nid=0x44bf runnable [0x0000000040f5c000..0x0000000040f5ced0]  
   2.    java.lang.Thread.State: RUNNABLE  
   3.         at java.net.SocketInputStream.socketRead0(Native Method)  
   4.         at java.net.SocketInputStream.read(SocketInputStream.java:129)  
   5.         at java.net.SocketInputStream.read(SocketInputStream.java:182)  
   6.         at com.caucho.server.resin.Resin.waitForExit(Resin.java:524)  
   7.         at com.caucho.server.resin.Resin.main(Resin.java:614) 

"main" prio=10 tid=0x0000000053911400 nid=0x44bf runnable [0x0000000040f5c000..0x0000000040f5ced0]
   java.lang.Thread.State: RUNNABLE
        at java.net.SocketInputStream.socketRead0(Native Method)
        at java.net.SocketInputStream.read(SocketInputStream.java:129)
        at java.net.SocketInputStream.read(SocketInputStream.java:182)
        at com.caucho.server.resin.Resin.waitForExit(Resin.java:524)
        at com.caucho.server.resin.Resin.main(Resin.java:614)


p.s 严重提示：jstack操作有风险，使用虚谨慎，俺不止一次执行jstack操作导致jvm退出，不知为啥，rp啊rp。。。本来使用JMX会安全一些的，但是翻遍ThreadInfo的doc，没有找到有关的方法


java线程使用的虚拟内存和物理内存
ps -eo pid,vsz,rss  |grep  20634

<%
double total = (Runtime.getRuntime().totalMemory()) / (1024.0 * 1024);
double max = (Runtime.getRuntime().maxMemory()) / (1024.0 * 1024);
double free = (Runtime.getRuntime().freeMemory()) / (1024.0 * 1024);
out.println("Java 虚拟机试图使用的最大内存量(当前JVM的最大可用内存)maxMemory(): " +
max + "MB<br/>");
out.println("Java 虚拟机中的内存总量(当前JVM占用的内存总数)totalMemory(): " +
total + "MB<br/>");
out.println("Java 虚拟机中的空闲内存量(当前JVM空闲内存)freeMemory(): " + free +
"MB<br/>");
out.println("因为JVM只有在需要内存时才占用物理内存使用，所以freeMemory()的值一般情况下都很
小，<br/>" +
"而JVM实际可用内存并不等于freeMemory()，而应该等于 maxMemory()-totalMemory()
+freeMemory()。<br/>");
out.println("JVM实际可用内存: " + (max - total + free) + "MB<br/>");
out.println("13亿宝藏");
%>
<%
double total = (Runtime.getRuntime().totalMemory()) / (1024.0 * 1024);
double max = (Runtime.getRuntime().maxMemory()) / (1024.0 * 1024);
double free = (Runtime.getRuntime().freeMemory()) / (1024.0 * 1024);
out.println("jvm maxMemory(): " + max + "MB<br/>");
out.println("jvm totalMemory(): " + total + "MB<br/>");
out.println("freeMemory(): " + free + "MB<br/>");
out.println("available memory:" + (max - total + free) + "MB<br/>");
%>

查找文件内容：
grep Gwpmanmx . -r
或 find . -type f -exec grep "fsFragmentId " {} \;

查看系统文件大小：
du -k | sort -n
df
cd /opt/NSN/SS_NEMS_DEPLOYMENT_LIN/scripts/
./listsets
./uninstallincrement R_NEMS_3.0_19

安装NEMS RPM包：
./installincrement /tmp/R_NEMS_3.0_104.rpm
./activateset R_NEMS_3.0_104
/opt/NSN/SS_NEMS_DEPLOYMENT_LIN
./copy.sh
cd /home/nems/cust_deploy
./deploy.sh

更新LDAP
cd /opt/NSN/SS_NEMS/scripts
./restore_ldap.sh -f ../ldapconf/ldapinit.ldif

克隆NEMS虚拟机：


####################################Jconsole & VisualVM ############################
Jconsole & VisualVM 远程监控Tomcat

1. vi catalina.sh
在第一行添加：
JAVA_OPTS='-Djava.rmi.server.hostname=10.68.74.151 -Dcom.sun.management.jmxremote.port=8999 -Dcom.sun.management.jmxremote.ssl=false -Dcom.sun.management.jmxremote.authenticate=false'

2../shutdown.sh ./catalina.sh start

3. remote :  10.68.72.93:8999
//////////////////////////////////
http://blog.csdn.net/huoyijie/archive/2010/09/26/5907169.aspx
http://os.51cto.com/art/200910/159072.htm

二十世纪最“反直觉”的伟大生物学发现–化学渗透（chemiosmosis）

###############################远程调试 J P D A ###################################
###http://libeey.blogbus.com/logs/104576920.html###
1.普通java进程： java -Xdebug -Xrunjdwp:transport=dt_socket,address=8000,server=y,suspend=y
2.Tomcat进程 ： ./catalina.sh jpda start

find . -type f  | xargs grep "2.16.840.1.113730.3.4.2"


vi /var/spool/mail/caui

sh ygs_mmsctrafficreport.sh csv hours 1 all all 13.02.2011_01:01 14.02.2011_01:01



在spring框架下用commons-fileupload组件上传文件可以在xml里面定义上传文件的最大长度，如：
<bean id="multipartResolver"
class="org.springframework.web.multipart.commons.CommonsMultipartResolver">
<!-- 设置上传文件的最大尺寸为5MB -->
<property name="maxUploadSize">
<value>5120000</value>
</property>
</bean>

http://hanxin0311.javaeye.com/blog/200990

description=%E4%BD%86%E6%98%AF


##########################################hessian 分片传输文件##########################################
package test.hessian;

import java.io.File;
import java.io.FileInputStream;
import java.io.FileNotFoundException;
import java.net.MalformedURLException;
import java.util.ArrayList;
import java.util.Date;
import java.util.HashMap;
import java.util.List;
import java.util.Map;

import com.nsn.mmsc.caui.business.FileTransferService;
import com.nsn.mmsc.caui.exception.CAUIException;

public class Test{
    
     public static void main(String[] args) throws FileNotFoundException {
          FileTransferService fileTransferService = new FileTransferService();
          File file =new File("D:/software/site-1.6.13.zip");
          String url = "http://10.68.72.93:8080/cmaui/";
          long len = file.length();
          int size = (int) ((len-1)/1024000+1);
          FileInputStream fis = new FileInputStream(file);
          byte[] buff = new byte[1024000];
          Map map = new HashMap();
          map.put("fileName", "/opt/NSN/SS_CMAUI/log/test.zip");
          map.put("append", "true");
          Date date1 = new Date();
          for (int i = 0; i < size; i++) {
               try {
                    if(i==size-1){
                         buff = new byte[(int)len%1024000];
                         System.out.println(fis.read(buff));
                    }else{
                         fis.read(buff);
                    }
               } catch (Exception e) {
               }
               List<byte[]> list = new ArrayList<byte[]>();
               list.add(buff);
               map.put("file", list);
               try {
                    fileTransferService.getMMSCService(url, map, "hessianFileTransfer", 1000);
//                    fileTransferService.execute(map);
               } catch (MalformedURLException e) {
                    // TODO Auto-generated catch block
                    e.printStackTrace();
               } catch (CAUIException e) {
                    // TODO Auto-generated catch block
                    e.printStackTrace();
               }
          }
          Date dd = new Date();
          System.out.println(dd.getTime()-date1.getTime());
     }
    
}


http://vip.book.sina.com.cn/book/index_160851.html


tcpdump -i any -s 0 port 162 -w /tmp/trap.cap

java -Djava.security.policy=scripts/java.policy -Djava.rmi.server.hostname=198.18.47.121 com/nsn/om/management/fm/AlarmDaemon
java -Djava.rmi.server.hostname=LICENSESERVER -Djava.rmi.server.codebase=file:///opt/NSN/SS_NEMS/licenseserver/jar/licensep2server.jar -Djava.security.policy=scripts/java.policy com/nsn/license/server/LicenseServer
java -Dcom.nsn.om.prefs.type=SYSTEM -Dcom.nsn.om.platform.type=STAND_ALONE com/nsn/om/management/jmx/ServerMain
java -Djava.security.policy=scripts/java.policy -Djava.rmi.server.hostname=198.18.47.121 com/nsn/iim/adaptor/eaif/client/EAIFClient
java -Djava.security.policy=scripts/java.policy -Djava.rmi.server.hostname=198.18.47.121 com/nsn/om/management/pm/PMMain
java -Dcom.nsn.iim.prefs.type=SYSTEM -Dcom.nsn.iim.platform.type=STAND_ALONE com/nsn/iim/storagecleaner/Main

-Xdebug -Xrunjdwp:transport=dt_socket,address=8000,server=y,suspend=y
-Dsun.rmi.transport.proxy.connectTimeout=6000 -Dsun.rmi.transport.tcp.responseTimeout=6000


disabled

NoiSystemDistinguishedName has invalid format, missing Object class or Instance Identifier in the RDN "CMAUI" : "CMAUI/ORIG-Applicatr"


//127.0.0.1:9996/alarmDaemon
Proxy[AlarmBaseRMI,RemoteObjectInvocationHandler[UnicastRef [liveRef: [endpoint:[10.68.72.93:52631](remote),objID:[-39041fbe:12f571c5fc3:-7f4d, -7366492342065065607]]]]]

RMI tips:

registry   =   LocateRegistry.createRegistry(Constants.RMI_REGISTRY_PORT);

  在应用程序一端，在JMXAgent.stop()中停止JMXConnectorServer之后，调用下列方法来终止该注册:

UnicastRemoteObject.unexportObject(registry,true);



%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%
http://localhost:8080/nems_web/feeds/aggregated?services=flickr%2Crss&requestID=1305189302353

http://plugins.grails.org/.plugin-meta/plugins-list.xml




###########################################################     NEMS   #####################################<a
mysql --port=3306 --socket=/var/NSN/SS_NEMS_MYSQLOM/data/mysql_om.sock -unems -pnems

mysql --port=3307 --socket=/var/NSN/SS_NEMS_MYSQLMAP/data/mysql_map.sock -unems -pnems

cyradm -u cyrus localhost --auth plain

151 mysql 启动命令：
1.    /opt/NSN/SS_NEMS/licenseserver/scripts
2.    /usr/libexec/mysqld --basedir=/usr --datadir=/var/lib/mysql --user=mysql --pid-file=/var/run/mysqld/mysqld.pid --skip-locking --socket=/var/lib/mysql/mysql.sock

查看nems系统所有进程：
chkconfig --list |grep nems

x-western

en-us, en

/a>##################################################  GRAILS #####################################################
grails test war
grails dev war
grails prod war
grails war /foo/bar/mywar.war

DELIVER_SM

Hessian is a binary web service protocol that makes web services usable without requiring a large framework,
and without learning a new set of protocols.
Because it is a binary protocol, it is well-suited to sending binary data without any need to extend the protocol with attachments.
Hessian is also designed around HTTP POST whereby a client connects to a URL on the server and sends data


//debug nems process
#!/bin/sh
unset CP
for jar in `ls ${SS_NEMSPATH}/jar/*.jar`
do
  CP=$jar:$CP
done

for jar in `ls ${SS_NEMSPATH}/jar/esymac/*.jar`
do
  CP=$jar:$CP
done


CP=${SS_NEMSPATH}/deploy/nems.jar:${SS_NEMSPATH}/deploy/MimeEncoder.jar:$CP

CLASSPATH=$CP
export CLASSPATH
java -server -Xmx512m -Xmn200m -Xss512k -XX:PermSize=64m -XX:MaxPermSize=64m -Djava.security.policy=scripts/java.policy -Djava.rmi.server.hostname=127.0.0.1 com/nsn/om/platform/loggerwriter/server/Main


Client ID:    
20616148389.apps.googleusercontent.com
Client secret:    
jRdDvCdhvwfoirSMh55tvTbB
Redirect URIs:     http://localhost:8080/wcs
JavaScript origins:     http://localhost:8080



https://accounts.google.com/o/oauth2/auth?client_id=20616148389.apps.googleusercontent.com&redirect_uri=http://localshost:8080/wcs&scope=https://www.google.com/m8/feeds/&response_type=token
https://accounts.google.com/o/oauth2/auth?scope=https://www.google.com/m8/feeds&client_id=20616148389.apps.googleusercontent.com&redirect_uri=http://localhost:8080/wcs&response_type=token

https://www.google.com/m8/feeds/contacts/default/full?access_token=ya29.AHES6ZRAmTYvcRRDj_67U_JXGVVelSi6Bb5AcpCPSz0t2pCaiM8qQQ

解压RPM包：
rpm2cpio oracle-instantclient11.2-basic-11.2.0.2.0.i386.rpm | cpio -div


google contact API:
http://code.google.com/apis/contacts/docs/2.0/developers_guide_java.html#Creating

red hat support:

https://access.redhat.com/support/cases/00528091


Please use this account:
larry.yang     C5KsqtWc7w

WCS java change:

locale  : com.nsn.iim.storage.IMAPPool 64 ---------->2
com.nsn.iim.webgui.enduser.business  TransactionTrace.log  ------------------->comment


Apache + Tomcat +JK  load balance and clusting:

http://soft6.com/html/tech/17/170935.shtml
http://weijie.blog.51cto.com/340746/68195
http://www.ibm.com/developerworks/cn/opensource/os-lo-apache-tomcat/
http://kaowww153.iteye.com/blog/728358
http://www.360doc.com/content/10/0309/14/495229_18116558.shtml


NEMS 多前端 BIG IP 负载均衡
http://daodao.blog.51cto.com/544971/123121

Music :http://www.xiami.com/song/play?ids=/song/playlist/id/382788/type/1



.encodeAsHTML()

NEMS打包问题日志： 10.140.0.133：/opt/build/nems/log


IP 问题：  打上ipconfig/release后再打ipconfig/renew



Hi
   Below is NEMS3.0 demo minutes
1. PM will clarify whether legacy user can use WebCS or not.
2. Composer and Reply can be configurable just like NEMS existing end-user. It allows operator to disable or enable composer and reply.
3. The number of displayed messages is 20 by default and 20 more messages will be shown when users scroll down to the bottom of My Messages page. Both of these figures can be configurable. We need to test 100 messages to see how these figures impact NEMS's performance.
4. If one month doesn't have any message, it will not been displayed in "Jump to" .

<script type="text/javascript">  
function trim(str){  //删除左右两端的空格  
return str.replace(/(^\s*)|(\s*$)/g, "");  
}  
function ltrim(str){  //删除左边的空格  
return str.replace(/(^\s*)/g,"");  
}  
function rtrim(str){  //删除右边的空格  
return str.replace(/(\s*$)/g,"");  
}  
</script>  

断开网络：
route add -host 10.68.120.11 gw 10.68.74.2

恢复：
route del -host 10.68.120.11 gw 10.68.74.2

永久路由：
1. vi /etc/sysconfig/static-routes
   any 10.140.0.0/16 gw 1o.68.74.1
2./etc/rc.local


flash play images and videos:
http://www.cnblogs.com/dequan-lee/archive/2007/06/07/775300.html
http://www.cnblogs.com/cm186man/archive/2009/03/14/1411384.html
http://www.jzxue.com/Html/daima/2007/4/15727EJB.html
http://tw.myblog.yahoo.com/hlele3109/article?mid=14609&prev=-1&next=14607


mysql 启动错误：
mysql dead but subsys locked
1、查看日志文件/var/log/mysqld_map.log 或者mysql_om.log
2、错误日志：InnoDB: Error: log file ./ib_logfile0 is of different size 0 5242880 bytes
3、删除旧的日志文件：
cd /var/NSN/SS_NEMS_MYSQLMAP/data
rm ib_logfile*
cd /var/NSN/SS_NEMS_MYSQLOM/data
rm ib_logfile*
4. 重启mysql服务
service mysqld_om restart
service mysqld_map restart

skip-locking --->skip-external-locking



MMSC informix 表空间查询：onstat -d

MySQL+Hibernate下连接空闲8小时自动断开问题DBCP解决方案:
http://hi.baidu.com/%CA%AB%D5%B9/blog/item/dc1a28734563021a8601b0d2.html
http://java.dzone.com/news/database-connection-pooling
http://database.51cto.com/art/201107/276325.htm

NEMS2.1.2:
service cyrus-imapd restart
(login in IMAP: cyradm –user cyrus localhost  ) password :123

手动创建Eventlog表：
mysql> INSERT INTO event_config(begin_ts,end_ts,event_log_table) values (20120413000000, 20120413000000, "Eventlog2012041300");
Query OK, 1 row affected (0.07 sec)

mysql> CREATE TABLE Eventlog2012041300(
    ->           recordid bigint auto_increment PRIMARY KEY,
    ->     NODEID varchar(32) NOT NULL,
    ->     timestamp datetime NOT NULL,
    ->     msgid varchar(64)  NOT NULL,
    ->     fromAddress varchar(64) NOT NULL,
    ->     toAddress varchar(64) NOT NULL,
    ->     successIndicator int(4) NOT NULL,
    ->     errorcause int(4) NOT NULL,
    ->     VO varchar(255) default NULL,
    ->     msgsize bigint(8) default 0);
Query OK, 0 rows affected (0.20 sec)

mysql> update event_config set end_ts=20120413000000 where end_ts=00000000000000;

quicktime：
https://developer.apple.com/search/index.php?q=quicktime+word+style

Europe/Helsinki

Vaas 部署MMSC
1.deploy MMSC OVF
2.vi /etc/sysconfig/network-scripts/ifcfg-eth0
IP = 10.68.75.209
Netmask = 255.255.254.0
Network = 10.68.74.1
3. service network restart
4. vi /etc/ssh/sshd_config
change listenAddress
5. service sshd restart

./yhtHTTPClient 111 222 yhtman.cf msisdntest_mm_send_req_v1.1.mm

测试inter mmsc traffic
/ MM4 / Yitmanmx / General  NoMM4ForwardRes  0    
      

com.nokia.mmsc.ygsman.dao.ReportingOperation
com.nokia.mmsc.ygsman.hessian.EventLogServer
com.nokia.mmsc.ygsman.util.dto.ApplicationInterfacesDataSpec
com.nokia.mmsc.ygsman.util.dto.ApplicationInstanceData
/work/.java_new/src/com/nokia/mmsc/ygsman/    
沟通要尽早

我希望能看到：
1. 框架的架构
2. 内部执行的流程
3. 如何配置
4. 环境
等内容

The error info when login webUI

precondition:
1. All services are up and work normally.
2. Services imap,mysql_om are working on FE1, services ldap, license,
mysql_imap,nemsfe are working on FE0.
3. Interface for webui is bond0.4049

Test Step:
1. Use command 'ifdown bond0.4049' on FE0 to disconnect webUI link
results: nemsfe is recoverable on FE1. All transactions are successful, and
users can login end-user webUI to view messages.

2. Use command 'ifup bond0.4049' on FE0 to recover webUI link
results: nemsfe work normally, all transactions are successful,and users can
login end-user webUI to view message.

3. Use command 'ifdown bond0.4049'on FE1 to disconnect webUI link
results: nemsfe is recoverable on FE0. All transactions are successful, and
then users cannot login end-user webUI. The error info shows that 'The
connection was reset'. Please refer to screenshot and nems-enduser.log.

PC-Notebook     2008L3RR379     unknown     NSN-STD     2008L3RR379

http://10.68.75.167:8081/webgui/login.do?method=ssoLogin&m=130000222&BV_SessionID=w11DP9PNsZDpddw7VmFbj2TQk5vFc21WG1JM9J1p9vN7yGy9LsN9!1784003188!1342017517123&BV_EngineID=1&mac=38858564768&subno=0928817207&serviceId=5221&noemome=null

HN0: zookeeper namenode  hmaster

hn1: zookeeper secondarynamenode datanode hmaster hregionserver

hn3: zookeeper  datanode hmaster hregionserver

