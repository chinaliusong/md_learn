# linux指令
## echo 输入16进制数
echo 001122334455 | xxd -r -ps > test            // 6 个字节
xxd // xxd 命令用于用二进制或十六进制显示文件的内容
-r  // 把xxd的十六进制输出内容转换回原文件的二进制内容
-ps // 以 postscript的连续十六进制转储输出，这也叫做纯十六进制转储

## grep
grep -E "a|b"