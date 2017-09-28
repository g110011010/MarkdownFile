---
title: 2017-9-26 
tags: 计算机网络
author:sf
grammar_cjkRuby: true
---
<!--teacher info-->
<!--Name:雷友珣-->

## Course 1
1. Computer Networks:
	* a collection of autonomous computers interconnected by a single technology
	* Users are exposed to the atual machines
	* If the machine have different hardware or

2. distributed system:


3. Components of CN:
	* Computers/Hosts/End Systems
	* Communication Links
	* Switches/Routers
4. Business Application
5. Home Apllication
> IETF:互联网标准提出公司

### Network hardware
1. end systems(hosts):run application programs
2. client/server model:client
3. mesh of interconnected routers
	* circuit switching:dedicated circuit per call:telephone net(数据传输一旦联通，网路就被独占，直到本次交互停止)
	* packet-switching:data sent thru net in discrete "chunks"(数据包前面有目标的地址，由数据包自动寻找目标地址)

4. broadcast networks(广播通信):Sending a packet to all destinations,each machine checks the address field.
5. ponint-to-point networks:
6. 体域网（personal area network）:

网络|距离|描述
--|---|--
personal area network|1m|蓝牙通讯，红外通讯，智能手表
Local area network|1Km|
MAN|10KM|城域网
WAN||广域网,提供从LAN(local area network局域网)到互联网的连接,采用电信网络,传输范围更远

7. Chnnel allocation

	* 静态分配：使用时间片轮寻算法，允许每一个用户在轮寻到其位置的时候连接到网络
	* 动态分配

8. MAN & WAN

#### 计算机网络与分布式系统
描述|计算机网络|分布式系统
--|---|--
不同点|在计算机网络中，不存在一致性，模式和软件。用户暴露于真实的机器
1. 传输子网(communication subnet)
	* 传输线
	* 交换设备(路由器
		* 存储和发送
		* 重新组装
		* 路由描述,路由算法

### 无线网(wireless network)
1. 无线网实例:
	* 无线局域网:IEEE 802.11 a/b/c....
	* 系统连接:NFC,蓝牙,"ZigBee BLE"
	* 无线城域网&广域网:IEEE 802.16 WiMAX,Radio networks  used for Cellular telephones(1G 2G 3G 4G 5G....)

2. 无线网连接方式:

	* 通过蓝牙
	* 无线局域网

3. 无线网架构
	* SGSN:serving GPRS support network
	* 基站:BSC(2G) RNC(3G) eNockB(4G 不再需要SGSN)

#### Internetworks
1. Internet:一个内部互联的网络的集合叫做Internetwork或者Internet
2. Gateway(网关):提供硬件和软件上必要的传输
3. ISP:Internet server provider,互联网服务提供商 
4. subnet(子网):连接到路由器上的网络等
5. network:子网和它上面主机的集合
6. miss
7. 网络结构:network of networks
8. CNGI

### 网络软件
1. 协议分层:为了减低设计复杂度,大多数网络是使用栈来分层设计的,每一层都建立在它下面一层的基础之上.
2. 一个机器上的第n层与另一个机器上的第n层进行通讯
3. 协议是两个通讯部分之间关于如何进行通讯的规则 
4. peers:不同机器上对等层上的实体
5. innterface:层栈相邻层之间的接口
6. protocal  stack:每一个对应层之间都有相应的协议
7. network architecture
	1. 网络是由层栈组织起来的
			* 每一层将自己的实现细节隐藏起来而向上向下提供相应的功能
			* 每一层都是一种虚拟机
	2. miss

8.  交换机只检查到数据链路层协议,路由器检查到网络层协议
9.  分层的设计问题
	1.  可靠性
		* 差错控制:能查错和纠错
		* 路由:查找网络上一个合理的路径 

	2. 网络演变

		* 协议分层
		* 寻址或命名:区分发送者和接收者
		* 网络互通性
		* 可扩展性
	3. 资源分配
		* 统计复用,按需分配
		* 流量控制
	4. QoS(服务质量)
	5. Security(安全)

10. 错误控制
	1. 物理线路不够完善
		* 错误校验和错误纠正
		* 接收者如何告诉发送者发送的那些数据是正确的哪些是错误的.
	2. 信息可能是顺序错乱的
		*发送者如何给消息编号
		接收者如何确定哪些消息的顺序是错误的
11. 寻址:每一层需要一种机制来确定发送者和接收者,发送者和接收者是不同机器上的进程
12. 流控制:一个高速的发送者可能使得一个低速的接收者无法正确处理
13. 路由:当多个路线存在的时候,必须选择一条最好的通路.
14. 面向连接和面向非连接
	1. 面向连接:必须首先建立连接,使用连接,最后释放连接
	2. 面向非连接:每一个信息带有完全的地址,并且可以通过这些方式独立的发送到接收者. 