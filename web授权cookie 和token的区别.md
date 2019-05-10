http://www.slideshare.net/derekperkins/authentication-cookies-vs-jwts-and-why-youre-doing-it-wrong



1.传统session，cookie的授权机制的问题，如何扩展，处理集群？

1）node之间同步session-->浪费内存，且有时间延迟问题

2）共享session -->需要实现把所有session放到一个共同存储的地方 如缓存

3）load balance实现路由，通过sessionId的hash路由，可以确保没吃访问同一个node -->需要load balance支持

