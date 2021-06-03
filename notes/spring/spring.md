spring家族体系

IOC:控制反转
springCore最核心的部分

实现方法
DI(依赖注入):
1.Setter
2.Interface
3.Constructor
4.Annotation

IOC容器的优势:
避免在各处使用new来创建类,并且可以做到统一维护
创建实例时不需要了解其中的细节

spring IOC
Spring启动时去读取应用程序Bean的配置信息,在spring容器中生成一份相应的Bean注册表,根据Bean注册表去实例化Bean(利用反射区实例化Bean,建立Bean之间的依赖关系),将Bean实例放入Spring容器中

支持的功能
依赖注入
依赖检查
自动装配
支持集合
指定初始化和销毁方法
支持回调(带有侵入性,谨慎使用)

核心接口
BeanFactory:spring框架最核心的接口
  提供IOC的配置机制
  包含Bean的各种定义,便于实例化Bean
  建立Bean之间的依赖关系
  Bean生命周期的控制
ApplicationContext(继承多个接口)
  BeanFactory:能够管理、装配Bean
  ResourcePatternResolve:能够加载资源
  MessageSource:能够实现国际化等功能
  ApplicationEventPublisher:能够注册监听器,实现监听机制
  
  

BeanFactory与ApplicationContext的比较
  BeanFactory是spring框架的基础设施,面向spring
  ApplicationContext面向使用Spring框架的开发者
  

BeanDefinition
  主要用来描述Bean的定义
BeanDefinitionRegistry
  提供向容器注册BeanDefinition对象的方法(看源码)
  
getBean方法的代码逻辑
  1.转换BeanName
  2.从缓存中加载实例
  3.实例化Bean
  4.检测parentBeanFactory
  5.初始化依赖的Bean
  6.创建Bean

Spring Bean的作用域
singleton:Spring的默认作用域,容器里拥有唯一的Bean实例
prototype:针对每个getBean请求,容器都会创建一个Bean实例
request:会为每个Http请求创建一个Bean实例
session:会为每个session创建一个Bean实例
globalSession:会为每个全局HttpSession创建一个Bean实例,该作用域仅对Portlet有效

SpringBean的生命周期
创建过程


关注点的分离:不同的问题交给不同的部分去解决
面向切面编程AOP正是此技术的体现
通用化功能代码的实现,对应的就是所谓的切面
业务功能代码和切面代码分开后,架构将变的高内聚低耦合
确保功能的完整性:切面最终要被合并到业务中

AOP的三种织入方式:
编译时织入:需要特殊的Java编译器,如AspectJ
类加载时织入:需要特殊的Java编译器,如AspectJ和AspectWerkz
运行时织入:Spring采用的方式,通过动态代理的方式,实现简单

AOP的主要名词概念
Aspect:通用功能的代码实现
Target:

Spring事务
ACID:
隔离级别:
事务传播:

