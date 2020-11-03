
##### 程序状态字
程序状态字（Program Status Word, PSW）又称状态寄存器，主要用于反映处理器的状态及某些计算结果以及控制指令的执行。用一个专门的寄存器来指示处理器状态。

程序状态字通常包括以下状态代码：
CPU的工作状态码——指明管态还是目态，用来说明当前在CPU上执行的是操作系统还是一般用户，从而决定其是否可以使用特权指令或拥有其它的特殊权力

条件码——反映指令执行后的结果特征
[image](https://img-blog.csdn.net/20140325105401500)
中断屏蔽码——指出是否允许中断

##### CPU管态和目态
  CPU有两个状态，分别是管态和目态。
  
  管态，即操作系统的管理程序运行时的状态，具有较高的特权级别，也称为特权态、系统态、内核态或者核心态。当处理器处于管态时，可以执行所有的指令，包括各种特权指令，也可以使用所有的资源，并且具有改变处理器状态的能力。
  
  目态，即用户程序运行时的状态，具有较低的特权级别，又称为普通态或用户态。在这种状态下不能使用特权指令，不能直接使用系统资源，也不能改变CPU的工作状态，并且只能访问这个用户程序自己的存储空间。
  
  从目态转换为管态的唯一途径是中断(访管指令或系统调用)。
  
  访管指令:用于实现在用户态下运行的进程调用操作系统内核程序，即当运行的用户进程或系统实用进程欲请求操作系统内核为其服务时，可以安排执行一条陷入指令引起一次特殊异常。
  
##### intel超线程技术
每个IA core模拟两个逻辑核心，共用缓存、执行单元、总线，每个逻辑核心都有通用寄存器和控制寄存器。

##### 特权指令
如：清内存、置时钟、分配系统资源、修改虚存的段表和页表，修改用户的访问权限等