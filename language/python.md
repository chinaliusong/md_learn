#learn #computer #python
# python

## 目前使用场景

开发速度快，可作为测试工具使用

### tcp

```python
#set the timeout period
socket.setdefaulttimeout(2)
# create tcp socket
tcp_socket = socket.socket(socket.AF_INET, socket.SOCK_STREAM)
# connect server
tcp_socket.connect(('172.29.94.115', 7890))
#convert string to bytes
data = bytes.fromhex(dic[key][0])
#tcp send data
tcp_socket.send(data)
#tcp receive data
recv_data = tcp_socket.recv(1024)
#print in hexadecimal
print(recv_data.hex())
#close tcp socket
tcp_socket.close()
```

### 串口

```python
#create serial
com = serial.Serial(port="COM6",baudrate=115200, bytesize=serial.EIGHTBITS, parity=serial.PARITY_ODD, stopbits=serial.STOPBITS_ONE)
#get bytes from string
data = bytes.fromhex("55AA0300EB90F3")
#send data to serial
com.write(data)
#receive data from serial
data = serial.read_all()
```

## 数据类型

### 字典

```python
myMap = {1:1,2:2}
```
### list
```
list1 = ['Google', 'Runoob', 1997, 2000]
```
### tuple
```
tup1 = ('Google', 'Runoob', 1997, 2000)
```
### 