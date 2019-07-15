wireshark的下载及安装
===========================

# 下载
官网下载页面
https://www.wireshark.org/#download
可以根据自己的系统参数来选择下载

# 安装
可以根据百度经验来安装,一般按默认设置来即可,没有特别的点
https://jingyan.baidu.com/article/656db918834874e381249cae.html

# 理解

## Wireshark 窗口介绍
![此处输入图片的描述][1]


  WireShark 主要分为这几个界面

1. Display Filter(显示过滤器)，  用于过滤

2. Packet List Pane(封包列表)， 显示捕获到的封包， 有源地址和目标地址，端口号。 颜色不同，代表

3. Packet Details Pane(封包详细信息), 显示封包中的字段

4. Dissector Pane(16进制数据)

5. Miscellanous(地址栏，杂项)

![此处输入图片的描述][2]


  使用过滤是非常重要的， 初学者使用wireshark时，将会得到大量的冗余信息，在几千甚至几万条记录中，以至于很难找到自己需要的部分。搞得晕头转向。

过滤器会帮助我们在大量的数据中迅速找到我们需要的信息.

## 过滤器有两种:

一种是显示过滤器，就是主界面上那个，用来在捕获的记录中找到所需要的记录

一种是捕获过滤器，用来过滤捕获的封包，以免捕获太多的记录。 在Capture -> Capture Filters 中设置

## 过滤表达式的规则

1. 协议过滤
比如TCP，只显示TCP协议。

2. IP 过滤
比如 ip.src ==192.168.1.102 显示源地址为192.168.1.102，
ip.dst==192.168.1.102, 目标地址为192.168.1.102

3. 端口过滤
tcp.port ==80,  端口为80的
tcp.srcport == 80,  只显示TCP协议的愿端口为80的。

4. Http模式过滤
http.request.method=="GET",   只显示HTTP GET方法的。

5. 逻辑运算符为 AND/ OR

6. http
只查看HTTP协议的记录

## 封包列表(Packet List Pane)

封包列表的面板中显示，编号，时间戳，源地址，目标地址，协议，长度，以及封包信息。 你可以看到不同的协议用了不同的颜色显示。
你也可以修改这些显示颜色的规则，  View ->Coloring Rules.

![此处输入图片的描述][3]


## 封包详细信息 (Packet Details Pane)

这个面板是我们最重要的，用来查看协议中的每一个字段。

各行信息分别为

Frame:   物理层的数据帧概况

Ethernet II: 数据链路层以太网帧头部信息

Internet Protocol Version 4: 互联网层IP包头部信息

Transmission Control Protocol:  传输层T的数据段头部信息，此处是TCP

Hypertext Transfer Protocol:  应用层的信息，此处是HTTP协议

![此处输入图片的描述][4]


### TCP包的具体内容

 从下图可以看到wireshark捕获到的TCP包中的每个字段
 
 ![此处输入图片的描述][5]


  [1]: http://www.cr173.com/up/2013-5/2013050217125642416.png
  [2]: http://www.cr173.com/up/2013-5/2013050217125625854.png
  [3]: http://www.cr173.com/up/2013-5/2013050217125720773.png
  [4]: http://www.cr173.com/up/2013-5/2013050217125736394.png
  [5]: http://www.cr173.com/up/2013-5/2013050217125787134.pnghttp://www.cr173.com/up/2013-5/2013050217125787134.png
  