1. SSH 为 Secure Shell 的缩写， 是目前较可靠，专为远程登录会话和其他网络服务提供安全性的协议。

  **SSH密钥验证的机制：**

​    a. 生成本机的公钥，私钥

​    b. 上传公钥到远程主机,并将公钥加入到远程主机的授权列表（.ssh/authorized_keys）

​    c. 发起远程登录请求，远程主机生成一个随机字符串并用本地主机的公钥加密，然后发送给本地主机

​    d. 本地主机用私钥解密字符串，然后发送给远程主机

​    e. 远程主机对比发送过来的字符串是否和生成的字符串一致，一致登录成功

​    **SSH无密码（密钥验证）登录的配置**

   a. #进入到我的home目录  cd ~/.ssh

　　b. ssh-keygen -t rsa （四个回车）  

　　c. 执行完这个命令后，会生成两个文件id_rsa（私钥）、id_rsa.pub（公钥）  

　　d. 将公钥拷贝到要免登陆的机器上：  ssh-copy-id <user>@<remote host>



2. rpm 命令详解

​    rpm -qa 查看所有的rpm包

​    rpm -ql 《rpm package》 查看该包的文件list



3. linux 运维一个中高级技巧

创建独立的 screen 命令如下：

```
screen -dmS elkscreen_1
```

接管连入创建的 `elkscreen_1` 命令如下：

```
screen -r elkscreen_1
```

然后你可以看到一个一模一样的终端，运行 logstash 之后，不要按 Ctrl+C，而是按 Ctrl+A+D 键，断开环境。想重新接管，依然 `screen -r elkscreen_1` 即可。

如果创建了多个 screen，查看列表命令如下：

```
screen -list
```