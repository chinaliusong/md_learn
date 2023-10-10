# 随笔
## socat 创建虚拟连接并进行转发

TCP、UDP：传输层协议，用于网络通信。

SSL、TLS：安全传输协议，用于加密数据传输。

HTTP、HTTPS：应用层协议，用于 Web 服务。

SSH：安全 Shell 协议，用于远程登录和文件传输。

FTP、FTPS：文件传输协议，用于文件传输。

SCTP：传输层协议，用于流控制和数据传输。

ICMP：网络层协议，用于网络诊断和错误报告。

IPv4、IPv6：网络层协议，用于 IP 数据包的传输。

Unix 域套接字：本地通信协议，用于进程间通信。

Serial：串口通信协议，用于串口设备的数据传输。

### 创建串口转发 
socat -d -d pty,b115200 pty,b115200
### 创建串口与网络数据
socat -d -d /dev/pts/2,raw,nonblock,ignoreeof,cr,echo=0 tcp-listen:5555,reuseaddr

### TCP
socat - TCP-LISTEN:8080         服务端
socat - TCP-LISTEN:8080,fork,reuseaddr  
- 标准输入输出
fork 每个连接fork一个分支
reuseaddr
socat - TCP:localhost:8080      客户端

#### 端口转发
socat TCP-LISTEN:8080,fork,reuseaddr  TCP:192.168.1.3:80

#### 远程登陆
socat TCP-LISTEN:8080,fork,reuseaddr  EXEC:/usr/bin/bash

### UDP
socat - UDP-LISTEN:8080
socat - UDP:localhost:8080  

`socat PTY,link=/dev/virtualcom0,raw,echo=0 TCP-LISTEN:5678`

文本模式(Text)会自动添加0D, 改成二进制(Binary)模式.


### 删除虚拟串口对
/dev/pts# ls
列出socat所有串口
fuser -k /dev/pts/xx
此处xx替换要删除的串口名称

## echo 输入16进制数
echo 001122334455 | xxd -r -ps > test            // 6 个字节
xxd // xxd 命令用于用二进制或十六进制显示文件的内容
-r  // 把xxd的十六进制输出内容转换回原文件的二进制内容
-ps // 以 postscript的连续十六进制转储输出，这也叫做纯十六进制转储

## minicom
`minicom -D /dev/tty -b115200 -H`
-D 设备名
-H 16进制
-b 波特率
`Ctrl+A Z`  帮助
