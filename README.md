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

### Stress testing

```
webbench -c 1000 -t 30 http://139.155.69.105:10000/index.html
```

------

### Highlights

:white_check_mark: 使用 Epoll 作为 IO 多路复用的实现方式，实现单线程监听多个网络连接;

:white_check_mark: 使用同步 I/O 实现了 Reactor 模式；

:white_check_mark: 设置 Epoll 为边沿触发模式 (ET)，提高事件处理效率；

:white_check_mark: 使用线程池提高并发度，并降低频繁创建销毁线程的开销；

:white_check_mark: 使用互斥锁实现线程同步机制，保证对共享资源的原子访问;

:white_check_mark: 运用生产者消费者模型，使用信号量唤醒工作线程;

:white_check_mark: 利用状态机解析 HTTP 请求报文，目前仅支持 GET 方法，实现对静态资源的请求