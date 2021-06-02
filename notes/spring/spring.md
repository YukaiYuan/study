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
  
 



