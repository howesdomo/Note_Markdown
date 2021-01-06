# telnet能连通，但ping失败解决方法

低级的做法， 将防火墙关闭， 关闭后就能ping通了。

**正确的做法时，在防火墙中启用对应的 ICMP**



使用ipv4的可以参考下图

![ipv4]()

### ping的本质ICMP(Intent Control Message Protocol 互联网控制报文协议)

> ping是一种计算机网络工具，用来测试数据包能否透过**IP协议**到达特定主机。ping的运作原理是向目标主机传出一个 **ICMP** echo@要求数据包，并等待接收echo回应数据包。程序会按时间和成功响应的次数估算丢失数据包率（丢包率）和数据包往返时间（网络时延，Round-trip delay time）。———— 维基百科



ping这个网络工具利用的时ICMP，[详细了解ICMP](https://www.jianshu.com/p/e1795962ad76) 请浏览此文章



telnet能连通就是能连通了。

