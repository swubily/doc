之前一直没搞清楚

synchronized

的用法和意识：



**synchronized**修饰成员方法时，会获取当前对象的锁（synchronized state）和**synchronized（this）**一个效果，所以他们之间是互斥关系，而与其他如static synchronized 或者synchronized（otherObj）不互斥，与在不在一个类里还是多个类里没有关系；



**synchronized**修饰静态（static）方法时，会获这个类（class）的锁（synchronized state）和**synchronized（class）**一个效果，所以他们之间是互斥关系；



**synchronized**修饰代码块（block）时，会获这个括号里对象或者类的锁（synchronized state），会与对应的同步方法或同步块互斥；

