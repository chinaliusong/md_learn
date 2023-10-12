# makefile 

## 函数
1. wildcard
    eg: SRC = $(wildcard ./*.c)
2. patsubst
    eg: OBJ = $(patsubst %.c, %.o, $(SRC))
3. addprefix 添加头
    eg: OBJS:=$(addprefix $(DIR_OBJS)/, $(OBJS)
## 创建文件夹
``` makefile
.PHONY:all
MKDIR=mkdir
DIRS=objs exes
all:$(DIRS)
$(DIRS):
	$(MKDIR) $@
```

