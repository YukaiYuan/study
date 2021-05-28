谈谈你对java的理解
1.平台无关性
  编译器(javac指令)编译成字节码,放在class文件,通过java虚拟机进行字节码解析成系统能执行的机器码(一次编译,到处运行)
  javap -c 指令进行反汇编,查看字节码
2.GC(与C++比较)
3.语言特性(放射、泛型、lamda等)
4.面向对象(封装、继承、多态)
5.类库
6.异常处理

反射
Java反射机制是在运行状态中,对于任意一个类都能够知道这个类的所有属性和方法;对于任意一个对象,都能调用它的任意方法和属性;这种动态获取信息以及动态调用对象方法的功能称为java语言的反射机制;
优点:使代码更加灵活
缺点:安全隐患,比如可以无视泛型的安全检查(泛型的安全检查发生在编译时);性能较差(实际影响不大)
获取class的四种方式
1.Class c = Object.class; //不会初始化
2.Class.forName("com.yyk.iv.xxx"); //对class进行了初始化静态代码块会被执行,静态变量会进行初始化
3.Class c = ClassLoader.loadCla("com.yyk.iv.xxx"); //不会初始化
4.Object o = new Object();
  o.getClass;
框架中的动态代理也是依赖反射来实现的;

ClassLoader
主要工作在Class装载的加载阶段,主要作用是从系统外部获得Class二进制数据流.它是Java的核心组件,所有的Class都是由ClassLoader进行加载的,ClassLoader负责通过将class文件的二进制数据流装载进系统,然后交给虚拟机进行连接、初始化等操作.
主要方法 loadClass();
ClassLoader的种类
BootStrapClassLoader: c++编写,加载核心库java.*
ExtClassLoader:Java编写,加载扩展库javax.*
AppClassLoader:Java编写,加载程序所在目录
自定义ClassLoader的实现
关键函数 findClass()  defineClass();

类加载器的双亲委派机制
1.自下而上检查类加载器是否已经加载
2.自上而下尝试加载类(在指定目录寻找是否有对应Class)
查看classLoader -> loadClass()源码

为什么要使用双亲委派机制去加载类
避免多份同样字节码加载

类的加载方式
隐式加载:new  //不需要newInstance()即可获得对象
显式加载:loadClass,forName等

类的装载过程
1.加载 ClassLoader加载class字节码,生成Class对象
2.链接 校验:检查加载的class的正确性和安全性 准备:为类变量分配存储空间并设置类变量初始值 解析:JVM将常量池内的符号引用转换为直接引用
3.初始化 执行类变量赋值和静态代码块

