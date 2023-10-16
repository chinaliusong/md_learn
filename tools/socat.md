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

socat -dd pty,link=/dev/virtualcom0,raw,echo=0 TCP-LISTEN:7890,fork,reuseaddr

socat -dd pty,link=/dev/virtualcom1,raw,echo=0 TCP-LISTEN:5555,fork,reuseaddr

`socat pty,link=/dev/virtualcom0,raw,echo=0 TCP-LISTEN:5678`

文本模式(Text)会自动添加0D, 改成二进制(Binary)模式.


### 删除虚拟串口对
/dev/pts# ls
列出socat所有串口
fuser -k /dev/pts/xx
此处xx替换要删除的串口名称