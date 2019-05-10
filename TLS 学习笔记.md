\1. IMS TLS WIKI: 

https://confluence.int.net.nokia.com/pages/viewpage.action?pageId=688611136

\2. RSA加密解密，数字签名及证书： <https://blog.csdn.net/junehappylove/article/details/52288796>

​     公钥加密，私钥解密。

​    私钥数字签名，公钥验证。

\3. TLS 概念：



pem 证书文件
 csr 证书请求文件,去证书中心获取证书文件，---》生成CA pem

 CA文件内容编码格式 PEM（base64） DER(二进制) crt（Unix）cer(windows) pem der 都是值证书文件
 key就是指公钥私钥

 crl 证书吊销列表

 JKS
 keystore.jks 私钥 证书连
 truststore。jsk 客户端证书

 导证书 就是把server的证书导入到truststore， server会把keystone的信息返回给client

 \1. client hello( TLS版本 支持的算法)--》 server hello（TLS 版本 选择一个算法 返回server的证书）
 \2. client

 证书（公钥，）