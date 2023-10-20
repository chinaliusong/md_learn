# makefile 

## 函数
1. wildcard 匹配目录下所有的.c文件
    `eg: SRC = $(wildcard ./*.c)`
2. patsubst 替换，将SRC中的.c替换为.o
    `eg: OBJ = $(patsubst %.c, %.o, $(SRC))`
3. addprefix 添加头
    `eg: OBJS:=$(addprefix $(DIR_OBJS)/, $(OBJS)`

## 创建文件夹
``` makefile
.PHONY:all
MKDIR=mkdir
DIRS=objs exes
all:$(DIRS)
$(DIRS):
	$(MKDIR) $@
```

## 进入子文件夹make
```makefile
subsystem:
    cd subdir && $(MAKE)
```
等价于
    `$(MAKE) -C subdir`
## 变量传递到子文件夹makefile
export Variable

## 基础make单元
目标前面的路径，意思是将目标生成到指定的目录下
```makefile
$(OBJ_DIR)/%.o : %.c 
	$(CC) $(CFLAGS) -c $< -o $@
$< 第一个依赖文件
$@ 生成的目标文件
$^ 所有的依赖文件
```


