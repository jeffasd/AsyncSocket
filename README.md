# 原作者写的挺用心的 着这里标记一下 
AsyncSocket
我在工作中用GCDAsyncSocket封装的一套TCP网络服务框架，用在公司的股票产品上

股票场景有实时性，所以通讯协议必须走socket，股票数据量大，传输协议用谷歌的ProtoBuffer，序列化速度快，数据压缩比高，省流量

因为是公司的产品用的，我删掉了相关的账号和公司内部的ip，所以能看到程序实现思路，而不能运行了


文件说明

ViewController.h        测试的界面

TCPAPI.h                这个类负责tcp请求封装，心跳机制，tcp打包拆包，自动重登录，数据序列化

SocketManager.h         这个类负责socket状态管理，掉线重连

SpeedDectectManager.h   这个类负责客户端的负载均衡，测速服务

NetWorkManager.h        判断网络状态


我把有状态的socket封装成了对应用层来说是无状态的，就像使用HTTP请求那样简单，它能够处理自动重连，自动TCP层的重登录，自动测速和负载均衡，包括一些缓存，能适应网络频繁断开连上的情况，具体细节写在注释中了，有兴趣的可以看看

整个TCP网络服务层逻辑，图片可能太小，建议从代码库中下载到本地查看

![](https://github.com/hehe520/AsyncSocket/blob/master/TCP%E7%BD%91%E7%BB%9C%E6%9C%8D%E5%8A%A1%E5%B1%82%E9%80%BB%E8%BE%91.png)


如果您发现程序有问题，欢迎反馈，谢谢，我的QQ:657668857，或者邮箱657668857@qq.com
