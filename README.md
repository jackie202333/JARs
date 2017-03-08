java技术相关jar包简介

Dom4j.jar简介	3

antlr-2.7.6.jar简介	3

ejb3-persistence.jar简介	3

hibernate3.jar简介	3

hibernate-annotations.jar简介	4

Hibernate3.3.2的JAR包简介	4

Spring的相关jar包简介	5

Struts2的相关jar包简介	8

jaxen-1.1-beta-6.jar简介	8

commons-digester.jar简介	9

commons-beanutils.jar简介	9

aspectjweaver.jar 简介	9

ognl.jar简介	9

cglib-asm.jar简介	9

odmg.jar简介	9

commons-collections.jar简介	10

commons-beanutils.jar简介	10

Java类库中自带的各个主要包的作用	10


Dom4j.jar简介
dom4j是一个Java的XML API，类似于jdom，用来读写XML文件的。dom4j是一个非常非常优秀的Java XML API，具有性能优异、功能强大和极端易用使用的特点，同时它也是一个开放源代码的软件，可以在SourceForge上找到它。在IBM developerWorks上面可以找到一篇文章，对主流的Java XML API进行的性能、功能和易用性的评测，dom4j无论在那个方面都是非常出色的。我早在将近两年之前就开始使用dom4j，直到现在。如今你可以看到越来越多的Java软件都在使用dom4j来读写XML，特别值得一提的是连Sun的JAXM也在用dom4j。这是必须使用的jar包，Hibernate用它来读写配置文件。 

antlr-2.7.6.jar简介
项目中没有添加antlr-2.7.6.jar,hibernate不会执行hql语句并且会报NoClassDefFoundError: antlr/ANTLRException错误

ejb3-persistence.jar简介
规范内容包括Bean提供者，应用程序装配者，EJB容器，EJB配置工具，EJB服务提供者，系统管理员。这里面，EJB容器是EJB之所以能够运行的核心。EJB容器管理着EJB的创建，撤消，激活，去活，与数据库的连接等等重要的核心工作。

hibernate3.jar简介
Hibernate的库，必须使用的jar包 


hibernate-annotations.jar简介
Hibernate annotation可以减轻我们每一次都需要配置XXX.hbm.xml,可以减轻dba的工作量，使程序从一个数据库移植到另一个数据库更轻松，这些工作都交于hibernate内部自动维护

Hibernate3.3.2的JAR包简介
包名	位置	用途
hibernate3.jar	/hibernate	核心JAR包
antlr.jar	/hibernate/lib/required	Another Tool for Language Recognition，可以构造语言识别器，解析HQL需要
commons-collections.jar	/hibernate/lib/required	包含了一些Apache开发的集合类，功能比java.util.*强大
dom4j.jar	/hibernate/lib/required	越来越多的Java软件都在使用dom4j来操作XML，Hibernate也不例外
javassist.jar	/hibernate/lib/required	操作字节码，跟cglib相关
jta.jar	/hibernate/lib/required	定义JTA规范的JAR包，当Hibernate使用JTA的时候需要
slf4j.jar	/hibernate/lib/required	整合各种日志框架的工具
slf4j-nop.jar	/slf4j	包含了对slf4j.jar的实现类
注意：slf4.jar和slf4j-nop.jar之间的版本需要匹配，如果Hibernate中使用早期的slf4j.jar，可以从slf4j官方网站下载新的JAR包将其置换掉
如果要使用Annotation，还需要下面的JAR包：


包名	位置	用途
hibernate-annotations.jar	/hibernate-annotations	使用Hibernate Annotation的核心JAR包
ejb3-persistence.jar	/hibernate-annotations/lib	实体类中使用的注解都是在这个JAR包中定义的
hibernate-commons-annotations.jar	/hibernate-annotations/lib	
使用javax.persistence下的Annotation可以不依赖Hibernate的JAR包，这样的话可以切换到其他的ORM框架
如果要使用log4j，则需要添加相关的JAR包：
包名	位置	用途
log4j.jar	很多框架中都有	生成用户定制日志
slf4j-log4j.jar	/slf4j	将slf4j和log4j关联起来的JAR包
当然别忘记了在类路径下放log4j的配置文件哦


Spring的相关jar包简介
(1) spring-core.jar
这个jar文件包含Spring框架基本的核心工具类，Spring其它组件要都要使用到这个包里的类，是其它组件的基本核心，当然你也可以在自己的应用系统中使用这些工具类。
(2) spring-beans.jar
这个jar文件是所有应用都要用到的，它包含访问配置文件、创建和管理bean以及进行Inversion of Control / Dependency Injection（IoC/DI）操作相关的所有类。如果应用只需基本的IoC/DI支持，引入spring-core.jar及spring-beans.jar文件就可以了。
(3) spring-aop.jar
这个jar文件包含在应用中使用Spring的AOP特性时所需的类。使用基于AOP的Spring特性，如声明型事务管理（Declarative Transaction Management），也要在应用里包含这个jar包。
(4) spring-context.jar这个jar文件为Spring核心提供了大量扩展。可以找到使用Spring ApplicationContext特性时所需的全部类，JDNI所需的全部类，UI方面的用来与模板（Templating）引擎如Velocity、FreeMarker、JasperReports集成的类，以及校验Validation方面的相关类。
(5) spring-dao.jar这个jar文件包含Spring DAO、Spring Transaction进行数据访问的所有类。为了使用声明型事务支持，还需在自己的应用里包含spring-aop.jar。
(6) spring-hibernate.jar这个jar文件包含Spring对Hibernate 2及Hibernate 3进行封装的所有类。
(7) spring-jdbc.jar这个jar文件包含对Spring对JDBC数据访问进行封装的所有类。
(8) spring-orm.jar这个jar文件包含Spring对DAO特性集进行了扩展，使其支持 iBATIS、JDO、OJB、TopLink，因为Hibernate已经独立成包了，现在不包含在这个包里了。这个jar文件里大部分的类都要依赖spring-dao.jar里的类，用这个包时你需要同时包含spring-dao.jar包。
(9) spring-remoting.jar这个jar文件包含支持EJB、JMS、远程调用Remoting（RMI、Hessian、Burlap、Http Invoker、JAX-RPC）方面的类。
(10) spring-support.jar这个jar文件包含支持缓存Cache（ehcache）、JCA、JMX、邮件服务（Java Mail、COS Mail）、任务计划Scheduling（Timer、Quartz）方面的类。
(11) spring-web.jar这个jar文件包含Web应用开发时，用到Spring框架时所需的核心类，包括自动载入WebApplicationContext特性的类、Struts与JSF集成类、文件上传的支持类、Filter类和大量工具辅助类。
(12) spring-webmvc.jar
这个jar文件包含Spring MVC框架相关的所有类。包含国际化、标签、Theme、视图展现的FreeMarker、JasperReports、Tiles、Velocity、XSLT相关类。当然，如果你的应用使用了独立的MVC框架，则无需这个JAR文件里的任何类。
(13) spring-mock.jar这个jar文件包含Spring一整套mock类来辅助应用的测试。Spring测试套件使用了其中大量mock类，这样测试就更加简单。模拟HttpServletRequest和HttpServletResponse类在Web应用单元测试是很方便的。

Spring包依赖说明:
1) spring-core.jar需commons-collections.jar，spring-core.jar是以下其它各个的基本。
2) spring-beans.jar需spring-core.jar，cglib-nodep-2.1_3.jar
3) spring-aop.jar需spring-core.jar，spring-beans.jar，cglib-nodep-2.1_3.jar，aopalliance.jar
4) spring-context.jar需spring-core.jar，spring-beans.jar，spring-aop.jar，commons-collections.jar，aopalliance.jar
5) spring-dao.jar需spring-core.jar，spring-beans.jar，spring-aop.jar，spring-context.jar
6) spring-jdbc.jar需spring-core.jar，spring-beans.jar，spring-dao.jar
7) spring-web.jar需spring-core.jar，spring-beans.jar，spring-context.jar
8) spring-webmvc.jar需spring-core.jar/spring-beans.jar/spring-context.jar/spring-web.jar
9) spring-hibernate.jar需spring-core.jar，spring- beans.jar，spring-aop.jar，spring-dao.jar，spring-jdbc.jar，spring- orm.jar，spring-web.jar，spring-webmvc.jar
10) spring-orm.jar需spring-core.jar，spring-beans.jar，spring-aop.jar，spring-dao.jar，spring-jdbc.jar，spring-web.jar，spring-webmvc.jar
11) spring-remoting.jar需spring-core.jar，spring-beans.jar，spring- aop.jar，spring-dao.jar，spring-context.jar，spring-web.jar，spring- webmvc.jar
12) spring-support.jar需spring-core.jar，spring-beans.jar，spring-aop.jar，spring-dao.jar，spring-context.jar，spring-jdbc.jar
13) spring-mock.jar需spring-core.jar，spring-beans.jar，spring-dao.jar，spring-context.jar，spring-jdbc.jar

Struts2的相关jar包简介
struts2-core-2.1.6.jar
struts2的核心包
freemarker-2.3.13.jar             
 FreeMarker是一个模板引擎，一个基于模板生成文本输出的通用工具
commons-logging-1.0.4.jar         
 Jakarta的通用日志记录包
ognl-2.6.11.jar        
            支持ognl表达式
xwork-2.1.2.jar              
      xwork的包 由于Struts2是由xwork的延伸 有些类依然关联着 xwork的类 
commons-fileupload-1.2.1.jar , commons-io.jar
 struts的上传下载 两者缺一不可
struts2-spring-plugin-2.1.8.1.jar       
 spring插件
struts2-convention-plugin-2.2.1.1   
零配置实现 省去使用struts.xml进行Action置配的麻烦

jaxen-1.1-beta-6.jar简介
他是是Xpath支持包

commons-digester.jar简介 
Digester基于规则的XML文档解析,主要用于XML到Java对象的映射. 

commons-beanutils.jar简介 
提供对Java 反射和自省API的包装. 

aspectjweaver.jar 简介
用于在Spring 2.0中集成AspectJ AspectJ LTW织入器 

ognl.jar简介 
OGNL是Object-Graph Navigation Language的缩写，它是一种功能强大的表达式语言（Expression Language，简称为EL），通过它简单一致的表达式语法，可以存取对象的任意属性，调用对象的方法，遍历整个对象的结构图，实现字段类型转化等功能。它使用相同的表达式去存取对象的属性。 

cglib-asm.jar简介
CGLIB库，Hibernate用它来实现PO字节码的动态生成，非常核心的库，必须使用的jar包 

odmg.jar简介
ODMG是一个ORM的规范，Hibernate实现了ODMG规范，这是一个核心的库，必须使用的jar包。 

commons-collections.jar简介
Apache Commons包中的一个，包含了一些Apache开发的集合类，功能比java.util.*强大。必须使用的jar包。 

commons-beanutils.jar简介 
Apache Commons包中的一个，包含了一些Bean工具类类。必须使用的jar包。 

Java类库中自带的各个主要包的作用
　　java.util是JAVA的utility工具包，包含一些使用工具类，如定义系统特性、使用与日期日历相关的函数等。
　　java.lang是JAVA的language核心语言包;如String、Math、Integer、System、Thread，提供常用的功能。特殊之处是不需要导入，是作为默认导入的包。
　　java.awt是JAVA的abstractwindow toolkit,抽象窗口工具包;包含了构成抽象窗口共具体的多个类，这些类用于构建和管理应用程序的图形用户(GUI)。
　　java.applet是创建APPLET的必须包;包含applet运行时所需要的一些类。
　　java.net是JAVA有关网络操作的包。
　　java.io是JAVA的输入输出流的包。	
　　java.sql是JAVA的数据库操作包。
　　javax.swing是新的界面包。
　　java.applet 支持小应用程序的结构
　　java.awt 提供图形用户接口的能力
　　java.awt.color 支持颜色空间和外形
　　java.awt.datatransfer 与系统的剪贴板交换数据
　　java.awt.dnd 支持拖拉操作
　　java.awt.event 处理事件
　　java.awt.font 描述多种字体类型
　　java.awt.geom 允许你使用几何形状
　　java.awt.im 允许编辑组件中日文，中文，韩文的的输入
　　java.awt.im.spi 支持二选一的输入设备 (在java 2, v1.3中加入)
　　java.awt.image 处理图像
　　java.awt.image.renderable 支持独立显示图像
　　java.awt.print 支持一般的打印功能
　　java.beans 允许你建立软件组件
　　java.beans.beancontext 为bean 提供可执行环境
　　java.io 输入输出数据
　　java.lang 提供核心功能
　　java.lang.ref 使能与垃圾回收交互
　　java.lang.reflect 运行时分析代码
　　java.math 处理大整数和十进制数
　　java.net 支持网络功能
　　java.rmi 支持远程方法调用
　　java.rmi.activation 激活永久对象
　　java.rmi.dgc 管理分布垃圾回收
　　java.rmi.registry 映射名称到远程对象引用
　　java.rmi.server 支持远程方法调用
　　java.security 处理证书，密钥，摘要，签名和其他安全功能
　　java.security.acl 管理访问控制列表
　　java.security.cert 分析和管理证书
　　java.security.interfaces 为DSA(数字签名算法)定义接口
　　java.security.spec 设定密钥和算法参数
　　java.sql 与SQL(结构化查询语言)数据库交互
　　java.text 格式化，查询和处理文本
　　java.util 包含一般工具
　　java.util.jar 生成和打开JAR文件
　　java.util.zip 读写压缩或解压缩文件
