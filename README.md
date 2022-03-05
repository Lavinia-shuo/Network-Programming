## Network-Programming

Linux下Socket网络通信实践

------

### Introduction

基于 *Linux* 平台运行的简易 *web* 服务器，支持 *GET* 请求获取静态资源

------

### Environment

Server: Ali Cloud

Editor:  VScode

OS: Ubuntu

------

### Run 

```
g++ *.cpp -pthread

./a.out 10000
```

------

### Highlights

:white_check_mark: 使用 Epoll 作为 IO 多路复用的实现方式，提高程序性能；

:white_check_mark: 使用同步事件循环 + 非阻塞 I/O + 线程池的 Reactor 模型；

:white_check_mark: 设置 Epoll 为边沿触发模式 (ET)，实现 HTTP 长连接传输数据；

:white_check_mark: 使用多线程充分利用多核 CPU 处理 IO 密集型请求，使用线程池降低频繁创建线程的开销；

:white_check_mark: 运用单例模式与阻塞队列实现异步的日志系统，对服务器运行状态、错误信息和访问数据进行记录；
