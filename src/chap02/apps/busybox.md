
# Busybox

RuxOS 支持在 Qemu 上运行动态链接的 [busybox](https://www.busybox.net/).

## 快速开始

1. 获取 busybox 二进制文件.

目前仅支持 musl 作为 libc 的动态链接版本. 可以自行编译, 或者从网上获取预编译的二进制文件.

2. 获取其依赖的动态库. 

3. 使用 ELF-loader 运行 busybox. 

> 关于 ELF-loader, 详情参见 [ELF-loader 一节](../ELF-loader.md).

此处给出 `axbuild.mk` 的例子:

```makefile
app-objs=main.o

# 参数
ARGS = /bin/busybox  # 实际路径为 rootfs/bin/busybox
# 环境变量
ENVS = 
# 9pfs 根文件系统路径
V9P_PATH=${APP}/rootfs
```

