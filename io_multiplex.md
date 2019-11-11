# I/O多路复用
```text
场景：C/S架构（网络请求）
解决方案：单线程处理大量的Client Request(文件描述符)
内核（kernel）利用文件描述符（file descriptor）来访问文件。文件描述符是非负整数。打开现存文件或新建文件时，内核会返回一个文件描述符。读写文件也需要使用文件描述符来指定待读写的文件。
应用产品：Redis、Nginx、JavaNIO
```
## select 
格式
while
int select(int nfds, fd_set *readfds, fd_set *writefds, fd_set *exceptfds, struct timeval *timeout);
功能：
0、用户态数据拷贝到内核处理，没有数据阻塞
1、fds置位 (不可重用)
2、select返回
3、存储1024位

执行流程：
当用户process调用select的时候，select会将需要监控的readfds集合拷贝到内核空间（假设监控的仅仅是socket可读），然后遍历自己监控的socket sk，挨个调用sk的poll逻辑以便检查该sk是否有可读事件，遍历完所有的sk后，如果没有任何一个sk可读，那么select会调用schedule_timeout进入schedule循环，使得process进入睡眠。如果在timeout时间内某个sk上有数据可读了，或者等待timeout了，则调用select的process会被唤醒，接下来select就是遍历监控的sk集合，挨个收集可读事件并返回给用户了，
要解决的问题：
（1）被监控的fds集合限制为1024，1024太小了，我们希望能够有个比较大的可监控fds集合
（2）fds集合需要从用户空间拷贝到内核空间的问题，我们希望不需要拷贝
（3）当被监控的fds中某些有数据可读的时候，我们希望通知更加精细一点，就是我们希望能够从通知中得到有可读事件的fds列表，而不是需要遍历整个fds来收集。


## poll 阻塞
格式：
poll(pollfds,5,5000)
流程:
1、置位revents(可重用)
2、结构体

## epoll 阻塞
格式：
epoll_wait(epdf,events,5,10000)
1、存储：白板
fd-events(poll)
2、共享存储
3、置位（重排）返回总数，前三个处理


