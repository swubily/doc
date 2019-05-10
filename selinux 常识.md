secure linux： 

 

```
/etc/selinux/config
```

:



查看selinux默认配置：

getsebool -a | grep ssh

getsebool -a | grep httpd



可以通过两种途径解决

1.解决方案：

\#setsebool httpd_can_network_connect 1

\2. restorecon -r /root/.ssh