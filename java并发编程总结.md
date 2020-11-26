之前一直没搞清楚

1. **synchronized**的用法和意识：

   synchronized**修饰成员方法时，会获取当前对象的锁（synchronized state）和**synchronized（this）**一个效果，所以他们之间是互斥关系，而与其他如static synchronized 或者synchronized（otherObj）不互斥，与在不在一个类里还是多个类里没有关系；**

   synchronized**修饰静态（static）方法时，会获这个类（class）的锁（synchronized state）和**synchronized（class）**一个效果，所以他们之间是互斥关系；**

   synchronized**修饰代码块（block）时，会获这个括号里对象或者类的锁（synchronized state），会与对应的同步方法或同步块互斥；

2. **volatile**关键字：

   适用于一次写，多次读操作。不保证原子操作，只保证可见性

3. **ThreadLocal**

   保存每个线程自己本身的拷贝，线程间不会影响，使用于小的内存保存。大的内存对象用原子操作Atomic

4. **wait、notify、notifyAll **

   这三个方法都是在object上的，都需要放到同步方法或者同步块里，wait最好放到while循环里。尽量使用notifyAll。wait会释放锁，notify notifyAll不会。所谓锁就是在对象上设置

5. **Join、yield、sleep**

6. 这两个方式是Thread方法，yield、sleep不会释放锁

CBRS

cbrs

NCDP19B



* %WIP FC:OSS_FC_017838 add im fragment

OSS_FC_017838 NE_Radio_LTE_fp

 LTE 19B Flexi Zone Management Functionality