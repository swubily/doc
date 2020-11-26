# **Adapation 工作笔记**

'%WIP FC:OSS_FC_018032 add imb component'

https://gerrite1.ext.net.nokia.com/a/netact/adap_ztsl



## **1. NetAct 常用日志目录：**

|             Name              | Value                                                        |
| :---------------------------: | ------------------------------------------------------------ |
|              IM               | /var/opt/oss/log/NSN-integrationmanager                      |
|            AM/ADS             | /var/opt/oss/log/am                                          |
|            DA/PDDS            | /var/opt/oss/log/ne3sws_dynamicadaptation                    |
|              OIB              | /var/opt/oss/log/aib                                         |
|              AIF              | /var/opt/oss/log/aif                                         |
|       common mediation        | /var/opt/oss/log/common_mediations                           |
|             etlod             | /var/opt/oss/log/etload/werlogA51A.0.log                     |
|        ADAP deploy dir        | /var/opt/oss/global/adaptations/o2ml/ PMB:                   |
|         cloudLab3351          | <https://clab3351lbwas.netact.nsn-rdnet.net/authentication/Login>  <https://cloud01.tre.nsn-rdnet.net/ui/index.php?project=NM-CD-Core&page=Labs&name=CLAB3351> |
|         DA add NETYPE         | /opt/oss/NSN-ne3sws_dynamicadaptation/smx/conf/ 下面有个nacdynamicadaptation.properties  9:58  Kaizhou Zhang  改两个属性  SUPPORT_NE_TYPE  SUPPORT_NE_TYPE_ADAPTATION_ID  你按着里面例子加就可以了  9:59  Kaizhou Zhang  然后重起下ne3sws_dynamicadaptation |
|     NE3S registration url     | curl http://10.96.180.114:8080/NE3S/1.0/NE3SRegistrationService |
| adaptation template directory | /var/opt/oss/global/NSN-integrationmanager/integration_metadata_template |

## **2.常用地址**

| Name                                                         | Value                                                        |
| ------------------------------------------------------------ | ------------------------------------------------------------ |
| Team Wiki                                                    | <https://confluence.int.net.nokia.com/display/NCEPdev/Archer+team> |
| ARS link                                                     | <https://sharenet-ims.int.net.nokia.com/livelink/livelink?func=ll&objId=431985352&objAction=browse&sort=name&viewType=1> |
| Co-Labs Wiki(vsp0114 )                                       | <https://confluence.int.net.nokia.com/pages/viewpage.action?pageId=556430155>  <https://confluence.int.net.nokia.com/display/Unify60/Co-labs+for+NetAct+and+UDM+19.0> |
| SP Build Jenkins                                             | <http://cidash.netact.nsn-rdnet.net/jenkins/job/I_NA_FastPass_SP_Builder/> |
| TA server Jenkins                                            | [http://135.242.205.43:8080](http://135.242.205.43:8080/)    |
| LAB 硬件相关jira                                             | <https://srvjira.int.net.nokia.com/browse/DCINFRA-75792>     |
| NetAct maintaince lab                                        | <https://confluence.int.net.nokia.com/display/OSSNetAct/NetAct+16.X+Maintenance+Labs> |
| OIB Excel Generation                                         | <https://confluence.int.net.nokia.com/display/OSSChinaCuDoUA/OIB+Excel+Generation+workspace> |
| Adaption Engine                                              | <http://adapengine.eecloud.dynamic.nsn-net.net/tasks?name=com.nokia.albvm.pmb>   Product trigger URL: <http://api.ae.eecloud.dynamic.nsn-net.net/notif/trigger> |
| JOMA&VTK download                                            | <http://bhlbmw06.apac.nsn-net.net/download/>                 |
| HSSFE ARS                                                    | <https://sharenet-ims.int.net.nokia.com/livelink/livelink?func=ll&objId=426696141&objAction=browse&viewType=1> |
| VTK ENV                                                      | <https://confluence.int.net.nokia.com/display/ygHome/Setup+Fast+Pass+VTK+running+environment> |
| FMB specification                                            | https://sharenet-ims.int.net.nokia.com/livelink/livelink/overview/D564358173 |
| PMB specification                                            | <https://sharenet-ims.int.net.nokia.com/livelink/livelink/overview/D515936783> |
| Adaption fragment specification                              | <https://sharenet-ims.int.net.nokia.com/livelink/livelink?func=LL.getlogin&NextURL=%2Flivelink%2Flivelink%2Foverview%2FD564358173> |
| [PM Adaptation Uninstall For Fast Pass](https://confluence.int.net.nokia.com/display/rangers/PM+Adaptation+Uninstall+For+Fast+Pass) | <https://confluence.int.net.nokia.com/display/rangers/PM+Adaptation+Uninstall+For+Fast+Pass> |
| NIDD tool（man2nidd）                                        | <https://gitlabe1.ext.net.nokia.com/INES/INES-ToolKit/tree/master/man2nidd-import-converter> |

**3.常用命令**

| Name                     | Value                                                        |
| ------------------------ | ------------------------------------------------------------ |
| ZTS manual deploy        | sh ads_client.sh -nt 000_DA_BASE_000 -v 000_BASE_000         |
| UDM send Alarm           | [rtp99@regudmatom-udmuecm-77b495f644-5xgw7 [mcc] ~]$ RtpSendEvent64<br/>Usage: RtpSendEvent [-s] [-p PLID] [faulty] set num format [ args ... ]<br/>       RtpSendEvent [-p PLID] [-f file] [-t delay]<br/>-s         suppress attach/detach/fully functional events sent by nodemanager<br/>-p PLID    use PLID as the current platform identifier<br/>  -f file    read the event arguments from the given file,<br/>               one event each line<br/>  -t delay   issue an event each delay milliseconds<br/><br/>event arguments:<br/>  faulty     a string used as the faulty managed object<br/>  set        the event's set number (1 ... 255 )<br/>  num        the event's message number (1 ... 65536 )<br/>  format     the event's format string (short text) quoted by ""<br/>  args       list of variable arguments matching the format string.<br/>Example:<br/>  RtpSendEvent 200 11 "got a message of type %d from %s" 25 AppTestLog<br/>login to mcc container and execute the above command.<br/>you can even try the below comamnd from mcc<br/>execRTPenv RtpSendEvent 102 628 "test %d" 60 |
| git commit command       | git push origin HEAD:refs/for/master/<topic branch>          |
| smanager.pl omc用户执行: | /opt/cpf/sbin/netact_status.sh status                        |
| Iptables测试firewall     | 193  iptables -A OUTPUT -p tcp  -d  10.103.200.50  --dport 8080 -j ACCEPT    194  iptables -A OUTPUT -p tcp  -d  10.103.200.49  --dport 8080 -j ACCEPT    195  iptables -A OUTPUT -p tcp  -d  10.103.200.50  --dport 8080 -j ACCEPT    196  iptables -A OUTPUT -p tcp  -d  10.103.200.51  --dport 8080 -j ACCEPT    197  iptables -A OUTPUT -p tcp  -d  10.103.200.52  --dport 8080 -j ACCEPT    198  iptables -A OUTPUT -p tcp  -d  10.103.200.52  --dport 8443 -j ACCEPT    199  iptables -A OUTPUT -p tcp  -d  10.103.200.51  --dport 8443 -j ACCEPT    200  iptables -A OUTPUT -p tcp  -d  10.103.200.50  --dport 8443 -j ACCEPT    201  iptables -A OUTPUT -p tcp  -d  10.103.200.49  --dport 8443 -j ACCEPT          206  iptables -A OUTPUT -d 10.103.200.52/32 -j DROP    207  iptables -A OUTPUT -d 10.103.200.51/32 -j DROP    208  iptables -A OUTPUT -d 10.103.200.50/32 -j DROP    209  iptables -A OUTPUT -d 10.103.200.49/32 -j DROP       211  iptables -A INPUT -s 10.103.200.49/32 -j ACCEPT    212  iptables -A INPUT -s 10.103.200.50/32 -j ACCEPT    213  iptables -A INPUT -s 10.103.200.51/32 -j ACCEPT    214  iptables -A INPUT -s 10.103.200.52/32 -j ACCEPT           82  iptables -A INPUT -m conntrack --ctstate RELATED,ESTABLISHED -s 10.103.200.52/32 -j ACCEPT -m comment --comment "Stateful_INPUT"     83  iptables -A INPUT -m conntrack --ctstate RELATED,ESTABLISHED -s 10.103.200.51/32 -j ACCEPT -m comment --comment "Stateful_INPUT"     84  iptables -A INPUT -m conntrack --ctstate RELATED,ESTABLISHED -s 10.103.200.50/32 -j ACCEPT -m comment --comment "Stateful_INPUT"     85  iptables -A INPUT -m conntrack --ctstate RELATED,ESTABLISHED -s 10.103.200.49/32 -j ACCEPT -m comment --comment "Stateful_INPUT"     86  iptables -A INPUT -s 10.103.200.52/32 -j DROP     87  iptables -A INPUT -s 10.103.200.51/32 -j DROP     88  iptables -A INPUT -s 10.103.200.50/32 -j DROP     89  iptables -A INPUT -s 10.103.200.49/32 -j DROP         iptables -A INPUT -p tcp -d 10.92.99.189 -s  10.103.200.49  --dport 30505 -j ACCEPT     iptables -A INPUT -p tcp -d 10.92.99.189 -s  10.103.200.50  --dport 30505 -j ACCEPT     iptables -A INPUT -p tcp -d 10.92.99.189 -s  10.103.200.51  --dport 30505 -j ACCEPT     iptables -A INPUT -p tcp -d 10.92.99.189 -s  10.103.200.52  --dport 30505 -j ACCEPT     iptables -A INPUT -p tcp -d 10.92.99.189 -s  10.103.200.52  --dport 30510 -j ACCEPT     iptables -A INPUT -p tcp -d 10.92.99.189 -s  10.103.200.51  --dport 30510 -j ACCEPT     iptables -A INPUT -p tcp -d 10.92.99.189 -s  10.103.200.50  --dport 30510 -j ACCEPT     iptables -A INPUT -p tcp -d 10.92.99.189 -s  10.103.200.49  --dport 30510 -j ACCEPT |
| OMES 抓取                | #Node08#!/bin/sh  while true  do  cp /d/oss/global/var/mediation/south/pm/import/com.nsn.oss.mediation.south.ne3soappm/*.gz  /tmp/wzc/sleep 1  done |
| TA svn提交格式           | %TBC IWI:testing : update HSSFE NEIW cases%CR TR: Arther     |
| etload command           | etlcolDBInfo.pl -t NOKREG%RAW                                |
| etload 抓取脚本          | #!/bin/sh
dest_dir=/root/temp_omes
omes_dir=/var/opt/nokia/oss/global/mediation/south/pm/import/com.nsn.oss.mediation.south.ne3soappm
mkdir -p $dest_dir<br />while true<br />do<br />     test $(find  $omes_dir -type f  -name "*.xml*"<br />     sleep 1<br />done |
|                          |                                                              |

**4.NE网元常用信息**

| Name    | Value                                                        |
| ------- | ------------------------------------------------------------ |
| SurePay | ainet/ainet1 (default)  rmtadm/Surepay@123                   |
| DDE     | 1. snmpbulkget -v 2c -c nagios localhost 1.3.6.1.4.1.28458.2.78.5.6.9.1.2 -t 20  2. snmpbulkget -v 3 -u nagiosV3 -l authPriv -a MD5 -x DES -A nagios_pwd -X nagios_pwd  10.75.198.40 1.3.6.1.4.1.28458.2.78.5.6.9.1.11 -t 5  3. 发送test alarm：aladmin create --object-name="DDEOBJ" --specific-problem="HA MASTER RECOVERING" --probable-cause=51 --severity=Critical --additional-text="addiS."  4. 网元端查看alarms： aladmin list  5. DDE snmpd.conf, 需要配置LBJBI ip 和所有的common mediation ips  com2sec sec_nagiosV2c <LBJBI IP> nagios    com2sec sec_nagiosV2c <common mediation ip> nagios    ... |
| IMS     | 1. 查看PM目录： locate gmoTemp/pm  <br />2. co-lab ips:   <br />HSSVNF( 10.103.200.52)<br /> BM(TIAMS IP: 10.53.32.21, 10.53.32.22<br/>HLR IP:   10.53.32.24)<br />密码：root/rtp99     yt_xk39b<br/>wsuser          wspassword<br />\3. 查看PM数据 etlcolDBInfo.pl -t VNFHSV%RAW<br /><https://confluence.int.net.nokia.com/display/NCEPdev/UDM+Adaptation+Structure><br />4. Troubleshooting:<br />A:CA 查看 确认NetAct和NE的CA信息一致<br />Q:查看 mediation 使用的ＣＡ信息：<br/>[root@clab515node05 omc]# grep SSLCertificateChainFile /etc/httpd/conf/httpd.conf<br/>openssl x509 -text -noout -in /var/opt/oss/certificates/ne3sws-mediation/httpd_caCerts.pem<br/>查看给网元的ＣＡ信息：<br/>openssl x509 -text -noout -in /etc/openldap/cacerts/authconfig_downloaded.pem<br />5. **/tspinst/scripts/**aiParameter.sh 网元配置文件 可以查看HIP<br />/opt/agents/Configurations/Esymac/dynamicData/SW/gmoTemp/registrations.dat<br />strings /opt/agents/Configurations/Esymac/dynamicData/SW/gmoTemp/registrations.dat<br />1). First start the Esymac process with nohup ./StartEsymac.sh –clean-config &<br />2). Then start the tomcat process with nohup ./Tomcat.sh -start & |
|         |                                                              |
|         |                                                              |
|         |                                                              |

**5.工具**

| Name                       | Info                                                         |
| -------------------------- | ------------------------------------------------------------ |
| 本地TAserver               | TA SERVER IP:  135.242.205.43  admin public?123              |
| NetAct 16.5 maintaince lab | omc/0029--User, root//arthur  root SSH 是disabled，  先 omc登陆 然后su - root |

**6.troubleshooting**

1. DA失败，报ERROR: DB_ACTIVATE_FAIL， 根据 DA maintaince <https://confluence.int.net.nokia.com/display/rangers/Maintenance> ，发现/var/log/adap_install-*.log文件里面的错误为：

EXECUTE: D3B version 'IMSHCVCDB_RAW_OSS5.1_01.001' already installed
 NOTE: UMAIMS/IMSHCV - D3B installation succeeded without errors.
 NOTE: UMAIMS/IMSHCV -  Registering ETLoad metadata. 



koala判断当前的包已经安装，不需要做数据库升级。从而导致后面做partion的时候报新的数据库表找不到

这个问题的原因是 /var/opt/nokia/oss/global/rtekoa/work/releases/imshcv 被清理掉了，所以导致koala判断当前版本为第一个 01.001，但是安装的时候发现01.001已经被安装。所以出问题



Fix/workaround：

Please note that the issue is happening due to that some necessary source files related to imshcv that needed by KOARTE are missing in NetAct, thus the upgrade always failed after several trials of DA deployment.

Below is the WA steps based on testbed. The same steps can be applied in customer side if WA is working in TB.

1. Create below folder and grant correct user/group and permissions.

*mkdir /var/opt/nokia/oss/global/rtekoa/work/releases/imshcv*

  *chown omc:sysop /var/opt/nokia/oss/global/rtekoa/work/releases/imshcv*

  *chmod 777 /var/opt/nokia/oss/global/rtekoa/work/releases/imshcv*

1. Copy imshcv to above folder and rename it.

  cp /opt/oss/Nokia-umaims-imshcv/conf/addon/imshcv.model */var/opt/nokia/oss/global/rtekoa/work/releases/imshcv/imshcvMetadata_REL_05.01.001*

  *chown omc:sysop /var/opt/nokia/oss/global/rtekoa/work/releases/imshcv/imshcvMetadata_REL_05.01.001*

  *chmod 644 /var/opt/nokia/oss/global/rtekoa/work/releases/imshcv/imshcvMetadata_REL_05.01.001*

1. Copy repository file to release specifc repository file

  *cp /var/opt/nokia/oss/global/rtekoa/work/repositories/imshcv/imshcv_IDRepository.dat /var/opt/nokia/oss/global/rtekoa/work/repositories/imshcv/imshcv_IDRepository_REL_05.01.001.dat*

  *chown omc:sysop /var/opt/nokia/oss/global/rtekoa/work/repositories/imshcv/imshcv_IDRepository_REL_05.01.001.dat*

  *chmod 755 /var/opt/nokia/oss/global/rtekoa/work/repositories/imshcv/imshcv_IDRepository_REL_05.01.001.dat*

1. Change SS-DB status file **/var/adm/subsystems/SS-UMAIMS-IMSHCV-DB** content like below.

YES::5.0::20.0.3::1::**0**    =>  YES::5.0::20.0.3::1:: **1**

1. Change SS-SW status file /var/adm/subsystems/SS-UMAIMS-IMSHCV content like below.

YES::5.0::20.0.**1**::1::1    =>  YES::5.0::20.0. **3**::1::1

1. Make sure the DA release tag file **/var/opt/nokia/oss/global/NSN-ne3sws_dynamicadaptation/koalafiles/com.nokia.hsscallpvm_REL** content is **NEED**

 

 KOARTE and ITK specification:

<https://sharenet-ims.int.net.nokia.com/livelink/livelink?func=ll&objId=537588111&objAction=browse>



PM Base Supplementary specification:

<https://sharenet-ims.int.net.nokia.com/livelink/livelink?func=ll&objaction=overview&objid=534942549>

  

2. CSD收不到alarm，但是 alarm upload是成功的

首先通过tcpdump抓包：

tcpdump -i any port 162 or 161

09:14:51.980396 IP 10.93.151.49.53209 > 10.91.36.221.snmptrap:  F=ap U="nagiosV3" [!scoped PDU]0d_7e_22_1c_45_92_ff_31_38_1c_56_56_05_34_0d_ad_d4_90_fe_c1_74_c8_7d_c7_5c_5f_5b_29_29_3c_be_36_21_fd_06_df_ 

发现集成ip 和 trap的source ip不同，netact只支持相同ip的情况。

Fix/WA: 网元的同事修改trap ip 或者 换集成ip



3. DA或者部署adaptation后，OIB没有对应的release version

java -jar /opt/oss/NSN-aib_preprocessor/bin/com.nsn.oib.preprocessor-jar-with-dependencies.jar -koala /d/oss/global/var/NSN-aib/OIB_Interface_Data/com.nsn.hssfe/1537341811380/com.nsn.hssfe-19.0VIKOALA.xml -dndb /d/oss/global/var/NSN-aib/OIB_Interface_Data/com.nsn.hssfe/1537341811380/com.nsn.hssfe-19.0VIdnDBDescription.xml -pmb /d/oss/global/var/NSN-aib/OIB_Interface_Data/com.nsn.hssfe/1537341811380/com.nsn.hssfe-19.0VIPMB.xml -suppmentary /d/oss/global/var/NSN-aib/OIB_Interface_Data/com.nsn.hssfe/1537341811380/com.nsn.hssfe.supplementary.xml

查看

原因是因为pmb文件里面没有vender和presentation



\3. CNUM troubleshooting 

--1. 检查oneDS connection，16611时候连接（established） 

root@hssgen809> netstat -anp|grep 16611

 tcp        0      1 10.8.48.78:27539        10.43.198.174:16611     SYN_SENT    -                  

 tcp        0      1 10.8.48.78:27531        10.43.198.174:16611     SYN_SENT    6114/IMS_P_UMS0V   

 tcp        0      1 10.8.48.78:27521        10.43.198.174:16611     SYN_SENT    9888/IMS_P_UMS1R   

 tcp        0      1 10.8.48.78:27537        10.43.198.174:16611     SYN_SENT    -                  

 tcp        0      1 10.8.48.78:27511        10.43.198.174:16611     SYN_SENT    6195/IMS_P_UMS1O   

 tcp        0      1 10.8.48.78:27523        10.43.198.174:16611     SYN_SENT    9906/IMS_P_UMS26   

 tcp        0      1 10.8.48.78:27519        10.43.198.174:16611     SYN_SENT    6038/IMS_P_UMS0G   

 tcp        0      1 10.8.48.78:27527        10.43.198.174:16611     SYN_SENT    9899/IMS_P_UMS1Q   

 tcp        0      1 10.8.48.78:27524        10.43.198.174:16611     SYN_SENT    9897/IMS_P_UMS1U   

 tcp        0      1 10.8.48.78:27535        10.43.198.174:16611     SYN_SENT    6115/IMS_P_UMS0B   

 tcp        0      1 10.8.48.78:27533        10.43.198.174:16611     SYN_SENT    6078/IMS_P_UMS10   

 tcp        0      1 10.8.48.78:27517        10.43.198.174:16611     SYN_SENT    6044/IMS_P_UMS03   

 tcp        0      1 10.8.48.78:27513        10.43.198.174:16611     SYN_SENT    6220/IMS_P_UMS2F   

 tcp        0      1 10.8.48.78:27515        10.43.198.174:16611     SYN_SENT    6075/IMS_P_UMS0U



--2. 检查CM upload 时候可以工作

- [HOME](https://clab615lbwas.netact.nsn-rdnet.net/startpage/#)
- CONFIGURATION、CM OPERATIONS MANAGER

 **UPLOAD CM FILE**