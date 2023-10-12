# cmake
## 函数
### add_executable
该命令会查找指定目录下的所有源文件，然后将结果存进指定变量名
`aux_source_directory(<dir> <variable>)`
## 示例
### 示例一 
``` cmake
#CMake 最低示例号要求
cmake_minimum_required (VERSION 2.8)
#项目信息
project (Demo1)
#指定生成目标
add_executable(Demo main.cc)
```

### 示例二
``` cmake
# CMake 最低示例号要求
cmake_minimum_required (VERSION 2.8)

# 项目信息
project (Demo2)

# 指定生成目标
add_executable(Demo main.cc MathFunctions.cc)
```

### 示例三
```cmake
# CMake 最低示例号要求
cmake_minimum_required (VERSION 2.8)

# 项目信息
project (Demo2)

# 查找当前目录下的所有源文件
# 并将名称保存到 DIR_SRCS 变量
aux_source_directory(. DIR_SRCS)

# 指定生成目标
add_executable(Demo ${DIR_SRCS})
```

### 示例四
```cmake
# CMake 最低版本号要求
cmake_minimum_required (VERSION 2.8)

# 项目信息
project (Demo3)

# 查找当前目录下的所有源文件
# 并将名称保存到 DIR_SRCS 变量
aux_source_directory(. DIR_SRCS)

# 添加 math 子目录
add_subdirectory(math)

# 指定生成目标 
add_executable(Demo main.cc)

# 添加链接库
target_link_libraries(Demo MathFunctions)
```