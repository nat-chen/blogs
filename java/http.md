Web前后端基础架构原理

计算机⽹络是如何⼯作的
ip 全程 internet protocol
ipv4 32位地址，4 个字节 （internet protocol version 4）
ipv6 128位地址, 16 个字节

域名与DNS
DNS (domain name service，域名服务器)
每当输入一个网址时，向 DNS 查询 ip 地址，对应于请求 headers 中 general 区域的 remote address
/etc/hosts 设置 ip 与地址的映射

端口
又称为连接或协议端口（protocol port），每个端口都会与主机的 ip 地址及通信协议关联
0~65536 个端口：
1. 0 端口为保留，不可使用。
2. 1-1023 系统保留，只能 root 用户使用。
3. 1024-4999 客户端程序自由分配。
4. 5000-65535 由服务器端程序自由分配在UDP协议中
在操作系统中，一个行程可以通过网络套接字将它的输入与输出与一个特定的传输协议、一个端口、一个IP地址关系起来。这个关系动作，称为綁定（binding），在这之后，就可以通过网络提交与接收资料。
当使用同样协议的多个程序，尝试着綁定在同一个IP地址下的相同端口，就会产生一个常见的应用程序错误，这个错误有时候被称为端口冲突（port conflicts）。
HTTPS 协议的默认端⼝是 443，HTTP 协议的默认端⼝是 80

TCP 协议
传输控制协议（transmission control protocol）是一种面向连接的、可靠的、基于字节流的传输层通信协议。全双工通信即为双方都能同时发送及接收数据
HTTP 协议
基于TCP/IP 协议的一种更上层协议
TCP是底层通讯协议，定义的是数据传输和连接方式的规范
HTTP是应用层协议，定义的是传输数据的内容的规范
HTTP协议中的数据是利用TCP协议传输的，所以支持HTTP也就一定支持TCP
HTTP是要基于TCP连接基础上的，简单的说，TCP就是单纯建立连接，不涉及任何我们需要请求的实际数据，简单的传输。HTTP是用来收发数据，即实际应用上来的。

浏览器的控制台的 network
request headers 对应请求的数据 (view source 查看未被解析过的数据)
response headers 对应发送的数据

localhost 等同于 ipv6 127.0.0.1 及 ipv4 127.0.0.0/8

referrer 图片的防盗链

⼆进制（图⽚/下载⽂件）

HTTP协议是⽆状态的


