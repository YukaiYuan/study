JVM如何加载.class文件
class Loader加载class文件,Execution Engine进行解析

JVM三大性能调优参数 -Xms -Xmx -Xss的含义
java -Xms128m -Xmx128m -Xss256k -jar xxx.jar
-Xss:规定了每个线程虚拟机栈的大小
-Xms:堆的初始值(不够时扩容)
-Xmx:堆能达到的最大值 (-Xms -Xmx一般设置为一样,堆扩容时会影响程序稳定性)


