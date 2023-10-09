# 随笔
## socat 创建虚拟连接并进行转发
### 创建串口转发 
socat -d -d pty,b115200 pty,b115200
### 创建串口与网络数据
socat -d -d /dev/pts/2,raw,nonblock,ignoreeof,cr,echo=0 tcp-listen:5555,reuseaddr


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
