title: 夸夸Ofbiz_2
date: 2014-11-16 17:00:00
category: 工作积累
tags: ofbiz
description: 上一篇夸的不好，老板不满意，继续夸。

---


## 关于Ofbiz ##

OFBiz是一个非常著名的开源电子商务平台，提供了创建基于J2EE/XML规范和技术标准，构建大中型企业级、跨平台、跨数据库、跨应用服务器的多层、分布式电子商务类WEB应用系统的框架。

OFBiz最主要的特点是OFBiz提供了一整套的开发基于Java的web应用程序的组件和工具。包括实体引擎, 服务引擎, 消息引擎, 工作流引擎, 规则引擎等。

OFBiz已经正式成为 Apache 的顶级项目: Apache OFBiz。

## Ofbiz愿景及架构##

- 五个‘E’
	1. Ease of Cost: 减轻成本
	2. Ease of Installation: 易于安装
	3. Ease of Customization: 方便自定义
	4. Ease of Integration: 易于集成
	5. Ease of Use: 容易使用

- 三个设计目标
	1. 使用自然语言或XML文档来定义业务逻辑、规则及数据模型。
	2. 用最少的代码来实现一个功能。
	3. 最大化地重用现有组件。


### Ofbiz架构图 ###

![OFBiz Architecture](http://oss.org.cn/ossdocs/applications/ofbiz/ofbiz-2.1.1-docs/website/presentation/img5.gif)

## OFBiz特性 ##

Ofbiz最大的价值，也许就是它不仅仅是一个**技术框架**，更是一个实现企业应用得很好的**业务框架**。它的MVC模式不仅仅是Web层，而是贯穿于业务层和数据层，每一层都有出色的控制器。 

两大核心组件(Service Engine和Entity Engine)使obfiz的framework成为目前最有效和易用的framework, 给企业应用系统的开发带来了极大的方便。

OFBiz通过Workflow Engine和Message Engine来管理业务过程，通过SOAP,RMI,EJB Session Bean等技术来调用 Service Engine提供的服务, 这使得多年来业界为之努力的业务与技术的分离梦想成真.

### 完善的实体引擎 ###

实体引擎是Ofbiz最有价值、最核心的、也是最稳定的一个数据层控制器，通过它基本不用编码或很少编码就可以访问数据层。Ofbiz提供了用XML些配置文件的方法来操纵数据。

实体引擎的功能类似于CICS、实体EJB、以及其他O-R Mapper。但是，Ofbiz的实体引擎不仅强大、而且灵活，程序员不需要JDBC知识，不用写SQL代码。基本上，实体引擎的封装能够解决绝大部分的数据库操作，同时，也提供了给你写SQL代码，实现复杂SQL查询的空间。

实体引擎采用了不少核心J2EE设计模式，如值对象、代表、助手等模式，用户的API接口比较友好。

![Entity Engine Components](http://oss.org.cn/ossdocs/applications/ofbiz/ofbiz-2.1.1-docs/website/presentation/img14.gif)

- 提供简单的模型来使用关系数据库。
- 不用编写或维护数据实体的持久化代码。
- 实体定义在简单的XML文件中。
- 实体可以通过API来创建、存储、删除、查找、排序、缓存等。
- 支持基于JDBC驱动的任意数据库。
- 支持分布式事务。
- 对数据源透明，为跨平台服务，方便移植。
- 可以通过配置代理来使用多个数据源。
- 自动检查实体定义，并将差别同步到数据库中
- 在有些情况下，使用实体引擎可能不合适，你可以使用JDBC、SQLJ来绕过实体引擎。

![Entity Engine Efficiency](http://oss.org.cn/ossdocs/applications/ofbiz/ofbiz-2.1.1-docs/website/presentation/img16.gif)


### 强大的服务引擎 ###

服务引擎是Ofbiz的另一个核心组件。Ofbiz只有这两个核心组件。实体引擎代表业务数据，而服务引擎代表了业务逻辑。

引入服务引擎的另一个价值是，它使得Ofbiz业务框架不限于Web应用。非Web的客户端包括java 应用、EJB、甚至SOAP都可以直接调用，这样，框架的可扩展性非常好。

服务引擎的服务可以分为同步、异步（关心还是忽略结果），支持JMS。具体实现方式可以是一个java 静态方法、工作流、Bean Shell脚本等。如下图：

![Service Engine Component](http://oss.org.cn/ossdocs/applications/ofbiz/ofbiz-2.1.1-docs/website/presentation/img12.gif)

- 多服务类型：Java，BeanShell，WorkFlow，Rules，SOAP
- 目标的触发是通过定义XML配置文件，而不是代码。
- 方法参数和返回值定义在XML里
- 服务可以通过Web来获取（SOAP Server）
- 服务可以使Web服务（SOAP Client）
- 服务可以同步调用，也可异步调用。
- 服务可以是定时任务。
- 服务引擎可以通过SOAP,RMI或者EJB Session Bean等方式来触发。

### 工作流引擎 ###

OFBiz工作流引擎是基于WfMC和OMG规范的, 工作流引擎是一组服务框架（EDA架构）.它和Entity Engine紧密集成在一起.

一个过程或者活动的所有改变都是实时的.所以工作流引擎不在一个线程里运行,它只是一组处理流程的通用对象和API.

OFBiz工作流使用XPDL作为它的过程定义语言. Xpdl制定了一个公用的转换标准，可以实现内部转换格式和公共转换相互衍射的标准,而且非常灵活.

- XPDL Extensions：工作流是用一种叫做XPDL的过程定义语言来设计的.该文档不对XPDL进行细节说明.
- Client API：工作流引擎的客户端API包含一套全局服务和一个工厂类.
- 工作流活动：手工和自动化活动的结合使得工作流强大.当前的工作流引擎实现了NO,ROUTE,TOOL:Application、Procedure和SUB-FLOW类型活动.
	- NO：也就没有活动,它描述了一个手工活动
	- ROUTE：路线活动,通过转换用来简单过渡到其他活动.
	- TOOL:Application：外部程序被调用.
	- TOOL:Procedure：OFBiz工作引擎将过程作为内部服务调用来实现.
	- TOOL:SUB-FLOW：一个子工作流被创建和运行.可以被定义成同步或者不同步.

### 消息引擎 ###

- 消息引擎基于BPMI的BPML标准
- 使用已有的成熟消息技术JMS等。
- 遵循现有的开源标准XML,XPath以及在BPML中使用的其他相关的XML标准。

### 规则引擎 ###

规则引擎也是OFBiz很重要的一个组成部分，它主要是采用了Prolog这种人工智能领域的编程语言的精髓部分和流行的规则语言RuleML。ofbiz完整地实现了抽象的逻辑规则到具象的程序流程控制的映射。

OFBiz规则引擎和人类思维相对应，存在两种推理方式：演绎法（Forward-Chaining）、归纳法（Backward-Chaining）。演绎法从一个初始的事实出发，不断地应用规则得出结论（或执行指定的动作）。而归纳法则是从假设出发，不断地寻找符合假设的事实。

### 控制层Servlet ###

Web层控制器的核心是Control Servlet。和Struts一样，Web层的流控制器的配置文件也是基于XML文件。

与Struts不同，View不仅仅只有Jsp，还有velocity、jpublish等。

### 报表与分析功能 ###

OFBiz具备的工具包可以建立用户界面，这些工具包同样也能建立报表。

OFBiz还包括一些商业智能的基本架构，能支持星型模式的定义，该模式可用于预先准备好的报表中。

### 扩展性和可移植性 ###

OFBiz提供一个基于纯Java应用程序的系统框架，在具体实现中大量采用了各种设计系统模式，完全符合面向对象的设计原则中绝大部分要求，除采用J2EE核心设计模式、数据库设计模式外，在实现代码中大量引入Java设计，成为系统扩展性和可移植性的基础。

OFBiz目前兼容Weblogic，Tomcat，Jboss，Resin，Orion等厂商的应用服务器，兼容Oracle，MySQL，Sybase，PostgreSQL，Hsql等数据库产品，可以在Unix和Windows两大操作系统上进行开发和测试，具备Java应用系统的所有跨平台特点。


## 相关技术及标准 ##

OFBiz的框架中引入了当前最先进的主流开发Web应用系统构建技术

- 与OFBiz相关的开源项目有： FreeMarker 、BeanShell 、Tomcat、 Jetty 、JOTM 、XAPool 、Javolution 、JPublish、 DataVision、 JasperReports、 WEKA、 Xerces、 Xalan 、Axis、 FOP、 Batik、Ant、 BSF 、Commons 、Log4J、 Lucene 、ORO 、POI、 OpenJMS 、PostgreSQL 、MySQL、MaxDB by MySQL、 Hypersonic SQL Derby等 。

- 与OFBiz相关的技术标准有：XML 、SOAP、 HTML 、Java、J2EE、 RuleML、XPDL、BPML、UNSPSC 、ebXML 、FASB 、Workflow、GL & Party 、Product 、qbXML、 OAGIS 、UBL等 。

### 主要使用的技术 ###

- XML：可扩展标记语言，它可以用来标记数据、定义数据类型，是一种允许用户对自己的标记语言进行定义的源语言。 它非常适合万维网传输，提供统一的方法来描述和交换独立于应用程序或供应商的结构化数据。OFBiz框架各个层次、模块均会涉及到的标记语言。
- SOAP：简单对象访问协议是在分散或分布式的环境中交换信息的简单的协议，是一个基于XML的协议。OFBiz使用该协议完成远程方法调用（RMI）的处理。
- RuleML：规则标记语言，OFBiz用来规则引擎开发。
- BPML：是业务流程建模的元语言，就像XML是业务数据建模的元语言一样。OFBiz用来定义工作流。
- FreeMarker:是一个用Java语言编写的模板引擎，它基于模板来生成文本输出。它不仅可以用作表现层的实现技术，而且还可以用于生成XML，JSP或Java等。OFBiz可以使用FreeMarker作为表示层语言。


## Ofbiz的好处 ##

Ofbiz的优势可以从几方面来体会：

- 缩短开发周期，降低成本

	据称，很多基于J2EE的失败实践，都可以归结于拙劣的设计。J2EE规范并不复杂，但是如何遵照J2EE规范，根据自己的业务需求，做一个合适的、高效的、可扩展的设计，是需要实际经验和智慧的。国外的大中型系统基于J2EE的早就很多了，国内近几年也多了起来，但是优秀的设计人员不是很多。

	Ofbiz的价值在于它的架构非常好，不仅用到了几乎所有的J2EE核心设计模式（Sun公司推荐的），而且还实现了工作流、业务规则引擎，以处理灵活的与变更。这样，就避免了缺少优秀设计人员所造成的拙劣设计。

	基于Ofbiz开发，无疑会缩短开发周期，好的设计以及工作流和业务规则引擎的引入，也最大程度的降低了系统的维护成本。 

- 用很少的 Code 完成复杂的处理

	这是Ofbiz 宣称的优点之一。如果把Ofbiz消化了，则基于Ofbiz开发一个CRM和ERP系统会大大缩短开发周期，由于Ofbiz优良的设计，维护的成本应该比较小。 

	Ofbiz 已经完成了大部分业务类软件系统都需要的部件，像用户认证、工作流、业务规则处理等，很多业务需求都可以通过写XML配置文件，以及很少的java代码来完成。代码量不大，但知道怎么写会比较费时。弄懂Ofbiz以后，写实现代码通常会比较简单，只需要按照它的开发机制度就是了。

- 扩展性和移植性好

	OFBIZ所提供的系统框架，是一个纯Java的应用程序。框架提供的接口十分的完备，例如核心部件实体引擎，早期版本就有，已经十分的成熟。通过实体引擎，用户不用直接操纵数据库，建立库表、查询、视图、触发器等都可以通过写XML配置文件来完成。也有人提出，实体引擎不能够处理复杂的SQL查询，实际上，一方面这种复杂的SQL查询很少遇到，另一方面实体引擎也同样允许你用SQL代码来操纵这种复杂的查询。 

	OFBIZ开发者同时维护和Weblogic，Tomcat，Jboss，Resin，Orion等16个厂商的Web和App应用服务器的兼容版本. 

	OFBIZ开发者同时维护和Oracle，MySql，Sybase，PostgreSQL，Hsql等数据库产品的兼容支持，包括编译、打包、部署到这些数据库产品或应用服务器产品的运行环境下。

	OFBIZ开发者同时在Unix和Windows两大操作系统上进行开发和测试，而且具备Java应用系统的所有跨平台的特点。 

	有了这些，对于大型企业级应用系统的具体、特定实现来说，你有信心实现所谓的“一次开发，到处运行”。

- 没有版权问题 

	免费的，可以用于商业目的，可以分发。

## 成功案例 ##

- [百货购](http://www.100hg.com/)
- [美陶家](http://www.meitaojia.com/)
- [gorun8](http://www.gorun8.cn/dyn/main)
