

List of AMPQ & vRops & NSX:
vCloud X: AMPQ: 10.41.53.39, vRops:  10.41.53.37, NSX: 10.41.53.33
vCloud Y: AMPQ: 10.41.53.49, vRops:  10.41.53.47, NSX: 10.41.53.43
vCloud Z: AMPQ: 10.41.53.59, vRops:  10.41.53.57, NSX: 10.41.53.53
Cred:
AMPQ: vcloud/aaaaaaA.1
vRops:  admin/!Y2mvXXu
NSX: admin/aaaaaaA.1

If you need shell access for the ampq or the director please send a SSH public key.
===============================================================================================================
For CAMVs in the CAMV vCenter the range is: 10.41.54.2 – 10.41.54.20 (GW: 10.41.54.1, DNS: 10.41.49.1,10.41.49.2 NTP: 10.41.49.1,10.41.49.2)

For the vCloud the range is configured in the vCloud itself (External networks / pub_net)
vCloud X: 10.41.54.21 - 10.41.54.55
vCloud Y: 10.41.54.56 - 10.41.54.91
vCloud Z: 10.41.54.92 - 10.41.54.127

So, basically we have 3 vCloud and one vCenter for CAMV development.
All the vClouds has the same version & deployment. Versions: vCloud: 8.10, vSphere 6.0 U2, NSX: 6.2.2, vRops: 6.2.0
-     vCloud X: director: 10.41.53.31, vCenter:  10.41.53.30
-     vCloud Y: director: 10.41.53.41, vCenter:  10.41.53.40
-     vCloud Z: director: 10.41.53.51, vCenter:  10.41.53.50
-     CAMV vCenter: 10.41.53.10
Cred:
Director: administrator/12345678aA.1
vCenter: administrator@camv.nsn-rdnet.net/aaaaaaA.1






10.68.156.11 3128 代理
svn://git.oschina.net/genkyo/Momall


nameserver 10.56.130.139

◆

\\10.140.0.83\sprint_backlog\DevelopementTeam\Sprints\Backlog

MP2 security update to      2015-11-04

IMS simulator:
http://10.68.124.221:9000/api/counters/v1/


jboss console:
https://10.68.108.22:9943/console/App.html
jbossadmin/admin_123
0804  --register
https://10.68.110.22:19001/api/c4c-monitoring/monitoring/alert
f9d9e96ec260a3ccdff4c53def96f07f594294a8

列出rpm包的内容：
rpm -qpl *.rpm

解压rpm包的内容：（没有安装，就像解压tgz包一样rpm包）
rpm2cpio *.rpm | cpio -div

UT 单元测试：
jmockito测试循环时，需要测试多个返回值的情况可以用returns：
如：
new NonStrictExpectations(){
            {
                new URL(url);
                result = encodedUrl;
                encodedUrl.openConnection();
                result = conn;
                conn.getResponseCode();
                result = 404;
                br.readLine();
                returns("test",null);
            }
        };


VROPS:::::::
1.log :::::
/usr/lib/vmware-vcops/user/log/analytics-b6da23*.log

3. alert没有被cancel前，在对其操作不在发送相同的alert。默认20、15分钟自动cancel

https://a.liepin.com/23146995/job_7906440.shtml?ckid=6f192633d0bc41db&pageNo=0&pageIdx=1&totalIdx=1&imscid=R000000075

二.配置notifications：

Method：Rest Notification Plugin
Scope：Object，  orgname + children +virtual machine


三、返回的alert值：通过criticality区分poweroff还是poweron

powered on:

/api/c4c-monitoring/monitoring/alert/fdd72406-9451-4269-902a-f6142b78b816|ERROR|com.nsn.c4c.monitoring.rest.MonitoringServiceImpl|alertID>>>>>

fdd72406-9451-4269-902a-f6142b78b816,
Alert>>>Tue Oct 20 17:17:40 CST 2015,
ALERT_CRITICALITY_LEVEL_INFO,
d488075d-ff87-4fe7-9868-d5a7fab94fc9,fdd72406-9451-4269-902a-f6142b78b816,ACTIVE,ALERT_SUBTYPE_AVAILABILITY_PROBLEM,null,VirtualMachine,VMWARE,ALERT_TYPE_VIRTUALIZATION_PROBLEM,CSCF-1 (a6b93f6a-79fd-4ffb-a26b-d75b5fb59b7f),Tue Oct 20 17:17:40 CST 2015,
2015-Oct-20T17:18:17.626+0800

powered off：

/api/c4c-monitoring/monitoring/alert/f0982c87-6af9-46e4-ba1a-24fc528e381a|ERROR|com.nsn.c4c.monitoring.rest.MonitoringServiceImpl|alertID>>>>>f0982c87-6af9-46e4-ba1a-24fc528e381a,Alert>>>
Tue Oct 20 17:22:40 CST 2015,                   startDate
ALERT_CRITICALITY_LEVEL_CRITICAL,               criticality
d488075d-ff87-4fe7-9868-d5a7fab94fc9,           resourceId
f0982c87-6af9-46e4-ba1a-24fc528e381a,           alertId
ACTIVE,                                         status
ALERT_SUBTYPE_AVAILABILITY_PROBLEM,             subType
null,                                           cancelDate
VirtualMachine,                                 resourceKind
VMWARE,                                         adapterKind
ALERT_TYPE_VIRTUALIZATION_PROBLEM,              type
CSCF-1 (a6b93f6a-79fd-4ffb-a26b-d75b5fb59b7f),  resourceName
Tue Oct 20 17:22:40 CST 2015,                   updateDate
2015-Oct-20T17:22:55.906+0800                   info

四、问题，不能知道alert来之那个vcloud，需要做一个 resourceid对应vcloud mapping


maven ::::::
export MAVEN_OPTS="-Xmx512m -XX:MaxPermSize=128m"
(or on Windows:)
set MAVEN_OPTS=-Xmx512m -XX:MaxPermSize=128m

-server -Xms256m -Xmx512m -XX:PermSize=256m -XX:MaxPermSize=256m -XX:+CMSClassUnloadingEnabled -XX:+PrintGCDetails -Xloggc:%M2_HOME%/gc.log -XX:+HeapDumpOnOutOfMemoryError -XX:HeapDumpPath=%M2_HOME%/java_pid<pid>.hprof


Servers     IP
Jenkins     10.68.127.12
Nexus     10.68.127.13
Soanr     10.68.127.14
Vmware           10.68.127.15
TEM simulators     10.68.127.26,10.68.127.27


Jenkins : CAM  TEM 升级

10.68.127.12 root/NCEP1pr2!

jobs workspace path:   /var/lib/jenkins/jobs/cam-install-package-creation-mp1/workspace


change TEM version:
1. cd TEM/trunk
2. run mvn versions:set -DnewVersion=15.5.4.170-SNAPSHOT
    mvn versions:commit
3.commit pom.xml files

svn st | grep "M " | cut -c 8- > modified.txt
svn commit -m "change version" --targets modified.txt

4. change message_en.properties file in tem-gui.
https://10.141.50.90:8000/api/nodeinfo

export PYTHONPATH=./image-creation
python ./image-creation/src/image/CAMImageBuilder.py --build-phase build --version 15.5.2.1507.${BUILD_NUMBER} --vmware-ip '10.68.127.15'

vmstutio profile:/opt/vmware/var/lib/build/profiles
vmstutio log:/opt/vmware/www/build
/opt/vmware/www/build/tem_vm_15_5_1_1506_393-21907_20150626010802/status#

/opt/nsn/cam/var/lib/app/templates/application-mysql-cluster-app

cam configuration file:

/opt/c4c/common/config

vijava  --vcenter
vcenter/mob

vCloud Director REST API Reference Documentation
https://www.vmware.com/support/vcd/doc/rest-api-doc-1.5-html/index.html
vCloud SDK for Java Developer's Guide
http://pubs.vmware.com/vcd-51/topic/com.vmware.ICbase/PDF/vcd_51_sdk_java_dg.pdf
VMware vSphere API Reference Documentation
https://www.vmware.com/support/developer/vc-sdk/visdk400pubs/ReferenceGuide/
vSphere Web Services SDK 4.0 Programming Guide
http://pubs.vmware.com/vsphere-50/index.jsp


???????????????????????????????????????????????????
1.pronto Template 哪里需要单独为template指定空间呢？
2. storage policy 和 resource pool 怎么创建
3. ovf build server down？
4. TEM upgrade ear ,war包？？jboss  ？？ DRA 和ear的区别？？
5. postgressQL 介绍
6. svn 目录结构？？
7. CreateAppConfig 是什么东东？？
???????????????????????????????????????????????????

=======================================
https://10.68.127.66/api/vApps/query?&page=1&pageSize=1000&filter=(name==*)&format=idrecords


application/*+xml;version=5.1

x-vcloud-authorization=qNNw4eS1dBsNkF9+sOhQDMkigXMdIB21Ru9yvWxD7eI=

[Accept: application/*+xml;version=5.1, x-vcloud-authorization: qNNw4eS1dBsNkF9+sOhQDMkigXMdIB21Ru9yvWxD7eI=]