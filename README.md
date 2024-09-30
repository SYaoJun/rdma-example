# RDMA使用教程
- 基于RDMACM的连接
- 没有RDMA网卡可以参考这个[教程](https://github.com/animeshtrivedi/blog/blob/master/post/2019-06-26-siw.md)。

## 在Ubuntu 22.04及以上安装软件模拟的RDMA
- 本人在ubuntu 24.04上测试过，能够正常运行。
- 查看RDMA网卡是否支持，通过命令
```
# 要安装rdma-core之后才有这个二进制
ibv_devices
ibv_devinfo -d siw0
```
## 依赖库

- rdma-core 源码编译安装即可
- libibverbs 基于包安装

```
apt install libibverbs-dev -y
```

## 编译

```
cd src
make
```

## 运行

```c

# 服务端
./server -a 10.0.4.7
# 客户端
./client -a 10.0.4.7 -s textstring 
```

## 感谢

感谢大佬开源的[项目](https://github.com/animeshtrivedi/rdma-example)
