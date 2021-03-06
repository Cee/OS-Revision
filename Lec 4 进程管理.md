# Lec 4 进程管理

### 什么是进程

> 进程是一个具有一定独立功能的程序关于某个数据集合的一次运行活动

+ 引入进程

	- 刻画系统动态性
	
	- 解决系统共享性
	
		+ 可再用
		
		+ 可再入
	
+ 状态

	- 运行态
	
	- 就绪态
	
	- 阻塞态

### 进程的状态

+ 两状态模型

	- 运行态

	- 非运行态

+ 三状态模型

	- 运行态

	- 阻塞态

	- 就绪态

+ 五状态模型	

	- 新建态
	
	- 运行态

	- 阻塞态

	- 就绪态

	- 终止态
	
### 进程的描述与管理

+ 操作系统的控制结构

	- 必须掌握关于每个进程和资源当前状态的信息
	
	- 操作系统构造并维护它所管理的每个实体的信息表

	- 包括内存表,I/O表,文件表,进程表

+ 进程的控制结构

	- 进程
	
		+ 程序
		
		+ 数据
		
		+ 系统栈
		
		+ 进程控制块(PCB, Process Control Block)

			+ 标识:此进程的标识号,父进程的标识号,用户标识号

			+ 处理器状态信息:用户可见寄存器,控制和状态寄存器,栈指针

			+ 进程控制信息:调度和状态信息,数据结构,进程通信,进程特权,存储管理,使用权和使用情况
		
	- 进程映像

		+ 包括程序,数据,栈和属性的集合

	- 进程属性

	- 处理器状态信息

+ 执行模式

	- 处理器状态信息
	
		+ 处理器寄存器

		+ 程序状态字

	- 进程上下文
		
		+ 用户级上下文:进程正文,共享内存区

		+ 寄存器上下文:PSW,栈指针,通用寄存器

		+ 系统及上下文:PCB,内存区表,内核栈

	- 用户模式(非特权模式)

	- 系统模式,控制模式和内核模式(特权模式)
	
+ 内核功能

	- 进程管理
	
	- 内存管理
	
	- I/O管理
	
+ 进程创建

	- 分配唯一进程标识号
	
	- 分配空间
	
	- 初始化进程控制块
	
	- 设置正确的链接
	
	- 创建扩充其他数据结构
	
+ 进程撤销

	- 通过进程标识号找到进程
	
	- 释放进程资源
	
	- 撤销子进程
	
	- PCB返还
	
+ 进程切换

	> 保存现场后,将PC置成中断处理程序的开始地址,由用户模式切换到内核模式

	- 中断:时钟中断(超时),I/O中断
	
	- 内存失效
	
	- 陷阱
	
	- 系统调用
	
+ OS的执行方式

	- 无进程的内核:操作系统是一个在特权模式下工作的独立体
	
	- 在用户进程中执行:上下文执行操作系统软件,发生中断时,处理器置于内核模式
	
	- 基于进程的操作系统:操作系统作为一组进程实现