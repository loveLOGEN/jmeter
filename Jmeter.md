

# Jmeter简介

Apache JMeter是Apache组织开发的基于Java的压力测试工具。可以用于对静态的和动态的资源（文件，Servlet，Perl脚本，java 对象，数据库和查询，[FTP服务器](https://baike.baidu.com/item/FTP服务器)等等）的性能进行测试。它可以用于对服务器、网络或对象模拟繁重的负载来测试它们的强度或分析不同压力类型下的整体性能。为了最大限度的灵活性，JMeter允许[使用正则表达式](https://baike.baidu.com/item/使用正则表达式/6555484)创建断言。



# Jmeter的作用

1. 能够对HTTP和FTP服务器进行压力和[性能测试](https://baike.baidu.com/item/性能测试)， 也可以对任何数据库进行同样的测试（通过JDBC）。 
2.  完全的可移植性和100% 纯java。 
3.  完全 Swing 和轻量组件支持（[预编译](https://baike.baidu.com/item/预编译)的JAR使用 javax.swing.*)包。 
4.  完全多线程 框架允许通过多个线程并发取样和 通过单独的[线程组](https://baike.baidu.com/item/线程组)对不同的功能同时取样。 
5.  精心的GUI设计允许快速操作和更精确的计时。 
6.  缓存和离线分析/回放测试结果。 



# Jmeter下载与安装

**官方网站：** http://jmeter.apache.org/download_jmeter.cgi 

**下载：**  [apache-jmeter-5.3.zip](https://mirrors.bfsu.edu.cn/apache//jmeter/binaries/apache-jmeter-5.3.zip) 

![1600911990254](https://raw.githubusercontent.com/loveLOGEN/jmeter/master/img/1600911990254.png)



#### 解压到无中文目录

![](https://raw.githubusercontent.com/loveLOGEN/jmeter/master/img/1600912751466.png)



#### Jmeter目录

![1601006110048](https://raw.githubusercontent.com/loveLOGEN/jmeter/master/img/1601006110048.png)

1. backups（备份）：顾名思义，该目录是个备份目录，是将自己的各个Jmx脚本进行备份，所谓备份便是每次保存都会将该脚本进行保存到该目录下，如果保存多次便会保存多个同样的文件，文件名进行默认递增更改。

   <!-- 此文件会在运行保存之后存在 -->

2. bin：

​		（1）examples（例子）：该目录下存放Jmeter官方给的请求模板

​		（2）report-template（报告模板）：该目录下存放Jmeter的报告模板（Jmeter是有自己的报告的）

​		（3）templates（模板）：该目录下存放Jmeter的各类配置模板，例如：JDBC、Beanshell、ThinkTime等

​		（4）Beanshell----：Beanshell请求、监听、断言、函数等

​		（5）**jmeter.bat**：启动文件

​		（6）jmeter.properties：配置文件（属性在官方文档中有解释）

​		（7）jmeter-server.bat：用于分布式

​		（8）shutdown.cmd：硬停止

​		（9）stoptest.cmd：软停止

​		（10）jmeter.sh：Linux下运行

​		（11）user.properties：用户配置i文件（同上）

3. docs：

   （1）api：前面谈到Jmeter是开源的，此处便是它的API文档

   （2）css：xxxx

   （3）Image：部分图片资源

4. extras：存放Build等配置，用于第三方集成构建

5. lib：存放各类jar包，组件类函数类等

6. licenses：许可证等

7. **printable_docs**：用户手册（ apache-jmeter-5.3/printable_docs/usermanual/component_reference.html ）



# Jmeter环境配置与启动

#### **JDK环境（>=1.8）  Windows + R --> cmd --> java -version**

![1600912539121](https://raw.githubusercontent.com/loveLOGEN/jmeter/master/img/1600912539121.png)

1. 双击jmeter.bat启动Jemter

![1600913653795](https://raw.githubusercontent.com/loveLOGEN/jmeter/master/img/1600913653795.png)

1. Jmeter配置

![1600913961960](https://raw.githubusercontent.com/loveLOGEN/jmeter/master/img/1600913961960.png)

2. 复制粘贴到系统变量CLASSPATH -->  **%JMETER_HOME%\lib\ext\ApacheJMeter_core.jar; %JMETER_HOME%\lib\jorphan.jar;** 

![1600914107022](https://raw.githubusercontent.com/loveLOGEN/jmeter/master/img/1600914107022.png)

3. 复制粘贴到系统变量path -->  %JMETER_HOME%\bin

![1600914362806](https://raw.githubusercontent.com/loveLOGEN/jmeter/master/img/1600914362806.png)

4. 启动Jmeter   Windows + R --> cmd --> jmeter  <!-- 此启动命令会与Oracle设置的client端编码NLS_LANG系统变量冲突 -->

   ![1600914978039](https://raw.githubusercontent.com/loveLOGEN/jmeter/master/img/1600914978039.png)



# Jmeter设置中英文

1. 在这里设置下次打开依然是JVM默认语言（ENGLISH）

![](https://raw.githubusercontent.com/loveLOGEN/jmeter/master/img/1600915260173.png)

2. 在Jmeter配置文件中修改，永久保存

![1601022416690](https://raw.githubusercontent.com/loveLOGEN/jmeter/master/img/1601022416690.png)

![1601022591938](https://raw.githubusercontent.com/loveLOGEN/jmeter/master/img/1601022591938.png)



# Jmeter界面介绍

![1600917884549](https://raw.githubusercontent.com/loveLOGEN/jmeter/master/img/1600917884549.png)



# Jmeter使用

<!-- 在线程组下创建的仅为当前线程组使用，在测试计划下创建的为所有线程组使用（父子关系） -->

#### 创建线程组

1. 右键百度计划 --> 添加 --> 线程（用户） --> 线程组

![1600918823581](https://raw.githubusercontent.com/loveLOGEN/jmeter/master/img/1600918823581.png)

2. 线程组介绍

![1600919030655](https://raw.githubusercontent.com/loveLOGEN/jmeter/master/img/1600919030655.png)

#### 创建HTTP请求

1. 右键线程组 --> 添加 --> 取样器 --> HTTP请求

![1600919219336](https://raw.githubusercontent.com/loveLOGEN/jmeter/master/img/1600919219336.png)

2. HTTP请求介绍

![1600919969209](https://raw.githubusercontent.com/loveLOGEN/jmeter/master/img/1600919969209.png)

#### 用户参数

1. 右键线程组 --> 添加 --> 前置处理器 --> 用户参数

![1600929214088](https://raw.githubusercontent.com/loveLOGEN/jmeter/master/img/1600929214088.png)

2. 用户参数介绍

![1600929374025](https://raw.githubusercontent.com/loveLOGEN/jmeter/master/img/1600929374025.png)

![1600931319493](https://raw.githubusercontent.com/loveLOGEN/jmeter/master/img/1600931319493.png)

#### 用函数传参时间戳

![1600931634378](https://raw.githubusercontent.com/loveLOGEN/jmeter/master/img/1600931634378.png)

#### HTTP信息头管理器

1. 右键线程组 --> 添加 --> 配置元件 --> HTTP信息头管理器

![1600929461390](https://raw.githubusercontent.com/loveLOGEN/jmeter/master/img/1600929461390.png)

2. HTTP信息头管理器介绍

![1600931187733](https://raw.githubusercontent.com/loveLOGEN/jmeter/master/img/1600931187733.png)

#### 察看结果树 与 用表格察看结果

1. 右键线程组 --> 添加 --> 监听器 --> 察看结果树

![1600925596295](https://raw.githubusercontent.com/loveLOGEN/jmeter/master/img/1600925596295.png)

2. 察看结果树介绍

![1600926258234](https://raw.githubusercontent.com/loveLOGEN/jmeter/master/img/1600926258234.png)

![1600926410293](https://raw.githubusercontent.com/loveLOGEN/jmeter/master/img/1600926410293.png)

<!--点击open报错是因为之前没有此文件，直接点击ok继续即可-->

3. 右键线程组 --> 添加 --> 监听器 --> 用表格察看结果

![1600925646837](https://raw.githubusercontent.com/loveLOGEN/jmeter/master/img/1600925646837.png)

4. 用表格查看结果介绍

![1600927427535](https://raw.githubusercontent.com/loveLOGEN/jmeter/master/img/1600927427535.png)





#### 启动测试计划

![1600927149964](https://raw.githubusercontent.com/loveLOGEN/jmeter/master/img/1600927149964.png)



1. 每次启动出现的这个警告弹窗可通过在   [apache-jmeter-5.3\bin\jmeter.properties]()   文件修改

![1600928046021](https://raw.githubusercontent.com/loveLOGEN/jmeter/master/img/1600928046021.png)

2.  此操作会覆盖上一次测试计划

![1600928263859](https://raw.githubusercontent.com/loveLOGEN/jmeter/master/img/1600928263859.png)

3. 设置完之后需重启Jmeter

![1600928795024](https://raw.githubusercontent.com/loveLOGEN/jmeter/master/img/1600928795024.png)



java中常见数据库字段类型与java.sql.Types的对应

# Jmeter连接mysql之跨线程组取值

#### 线程组独立运行

![1601169814204](https://raw.githubusercontent.com/loveLOGEN/jmeter/master/img/1601169814204.png)



#### JSON提取器

![1601177721676](https://raw.githubusercontent.com/loveLOGEN/jmeter/master/img/1601177721676.png)

![1601177996428](https://raw.githubusercontent.com/loveLOGEN/jmeter/master/img/1601177996428.png)



#### 调试后置处理器

<!-- 此处理器用来查看JSON处理器（或正则提取器等）是否提取到值 -->

![1601178122825](https://raw.githubusercontent.com/loveLOGEN/jmeter/master/img/1601178122825.png)

![1601178232753](https://raw.githubusercontent.com/loveLOGEN/jmeter/master/img/1601178232753.png)



#### 连接mysql配置

![1601169966899](https://raw.githubusercontent.com/loveLOGEN/jmeter/master/img/1601169966899.png)

![1601177526727](https://raw.githubusercontent.com/loveLOGEN/jmeter/master/img/1601177526727.png)



#### JDBC Request（请求DB）

![1601178296868](https://raw.githubusercontent.com/loveLOGEN/jmeter/master/img/1601178296868.png)

![1601178652539](https://raw.githubusercontent.com/loveLOGEN/jmeter/master/img/1601178652539.png)

> Parameter types数据类型：
>
> bigint            -->        bigint                                              tinyblob                    -->        binary
>
> bit                  -->        bit                                                   enum,set,char         -->        char
>
> date,year      -->        date                                                decimal,numeric     -->        decimal
>
> double,real   -->        double                                           mediumint,int          -->        integer
>
> blob,mediumblob   -->   blob                                         longblob,float           -->       real
>
> smallint         -->        smallint                                          time                           -->        time
>
> timestamp,datetime    -->    timestamp                        tinyint                        -->        tinyint
>
> varbinary,binary     -->     varbinary                                varchar,tinytext,text    -->    varchar  
>
>  https://blog.csdn.net/hemeinvyiqiluoben/article/details/78133544 



#### BeanShell取样器

![1601178821538](https://raw.githubusercontent.com/loveLOGEN/jmeter/master/img/1601178821538.png)

![1601179162173](https://raw.githubusercontent.com/loveLOGEN/jmeter/master/img/1601179162173.png)

#### 跨线程组取值传参

![1601184952649](https://raw.githubusercontent.com/loveLOGEN/jmeter/master/img/1601184952649.png)

#### 运行结果

![1601185184285](https://raw.githubusercontent.com/loveLOGEN/jmeter/master/img/1601185184285.png)

![1601185250683](https://raw.githubusercontent.com/loveLOGEN/jmeter/master/img/1601185250683.png)



# Jmeter元件之逻辑控制器

#### switch控制器

 Jmeter元件Switch控制器一般可以用在模拟多线程同时操作不同请求的测试场景。 

![1603677763793](https://raw.githubusercontent.com/loveLOGEN/jmeter/master/img/1603677763793.png)

#### 如果（if）控制器

![1603682837965](https://raw.githubusercontent.com/loveLOGEN/jmeter/master/img/1603682837965.png)

#### 吞吐量控制器

![1603690427911](https://raw.githubusercontent.com/loveLOGEN/jmeter/master/img/1603690427911.png)



# Jmeter元件之断言

#### 响应断言

<!-- 线程组中设置 在取样器错误后要执行的动作 ，不能设置为继续，否则断言不起作用 -->

![1603697135108](https://raw.githubusercontent.com/loveLOGEN/jmeter/master/img/1603697135108.png)

<!-- 断言执行则请求成功的接口依然标红 -->

![1603697223063](https://raw.githubusercontent.com/loveLOGEN/jmeter/master/img/1603697223063.png)

![1603697445603](https://raw.githubusercontent.com/loveLOGEN/jmeter/master/img/1603697445603.png)