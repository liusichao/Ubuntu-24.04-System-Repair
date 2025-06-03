# Ubuntu-24.04-System-Repair
如何测试Ubuntu24.04系统网络是否正常？
测试Ubuntu 24.04系统网络是否正常，可以按照以下步骤逐步排查：

1.检查物理连接
确认网线已插好，或无线网络已连接。

2.查看网络连接状态
打开终端，输入以下命令查看网卡状态及IP分配情况：
bash
ip addr
或
bash
ifconfig   # 需要安装 net-tools: sudo apt install net-tools
3.测试本地网络协议栈
测试本机回环接口：
bash
ping 127.0.0.1
如果能ping通，说明本机网络协议栈正常。
4.测试网关连通性
获取网关地址：
bash
ip route
找到如 default via 192.168.x.x 字样，ping一下网关：
bash
ping <网关地址>
5.测试外网连通性
尝试ping公共DNS服务器：
bash
ping 8.8.8.8
