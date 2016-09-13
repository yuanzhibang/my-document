## 进程

##  什么是进程
进程是一个程序执行时的实例，是处于执行期的程序以及相关资源的总称。

* 一个程序可以对应多个进程。
* Linux内核通常把进程称为“任务(Task)”或“线程(thread)”：Task是从内核的角度看到的进程。

> ()产生一个新进程。调用fork()称为父进程，新产生的进程称为子进程。fork()从内核返回两次：一次回到父进程，另一次回到新产生的子进程。fork()其实是由系统调用clone()实现的。

>exec()函数可以创建新的地址空间，并把新的程序载入。

>exit() 退出执行。

> wait4()查询子进程是否终结。

## 进程描述符
作用：为了进程管理，内核必须对进程进行明确的描述,如进程优先级，运行状态，地址空间等。

进程描述符使用task_struct。

slab分配器分配task_struct结构，可以达到对象复用和缓存着色(cache coloring)的目的。

## 进程，线程和轻量级进程
POSIX兼容的pthread库有三种方式：
* LinuxThreads
* Native Posix Thread Library(NPTL)
* Next Generation Posix Threading Package(NGPT)
