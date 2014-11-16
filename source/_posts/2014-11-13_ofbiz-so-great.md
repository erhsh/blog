title: 夸夸Ofbiz
date: 2014-11-13 17:47:00
category: 工作积累
tags: ofbiz
description: 方便自己

---


### Ofbiz是什么？ ###
OFBiz是一个非常著名的开源电子商务平台，提供了创建基于最新J2EE/XML规范和技术标准，构建大中型企业级、跨平台、跨数据库、跨应用服务器的多层、分布式电子商务类WEB应用系统的框架。 OFBiz最主要的特点是OFBiz提供了一整套的开发基于Java的web应用程序的组件和工具。包括实体引擎, 服务引擎, 消息引擎, 工作流引擎, 规则引擎等。

OFBiz 已经正式成为 Apache 的顶级项目: Apache OFBiz。


### 自身有什么优点 ###

#### 大量功能模块 ####

Apache OFBiz提供大量功能模块，有：

- 高级电子商务；
- 目录管理；
- 促销及定价管理；
- 定单管理（销售与供应）；
- 客户管理；
- 仓库管理；
- 工作流程；
- 账户管理；
- 生产管理；
- 绩效管理；
- 内容管理。


#### 完善的实体引擎 ####

OFBiz的核心技术在于实体引擎Entity Engine。OFBiz实体引擎提供了一组工具和设计模式来对现实世界中特定的实体（数据对象）进行建模和管理[6]。简言之，实体引擎的主要功能是将数据库表创建、对象与数据表的映射、对象的查询等强大的封装，这样就可以在一个简单的XML文件中定义数据库表结构，OFBiz会自动在数据库中建表，并动态生成映射对象，开发者在程序中可以只考虑对对象的处理，OFBiz会自动通过事务逻辑更新到数据库中。
实体引擎的目标是简化企业级应用中对实体数据（对应关系型数据库表）的大量操作，包括定义、维护、通用操作（增、删、改、查实体和实体之间的关系）的开发工作。

#### 扩展性和可移植性 ####

OFBiz提供一个基于纯Java应用程序的系统框架，在具体实现中大量采用了各种设计系统模式，完全符合面向对象的设计原则中绝大部分要求，除采用J2EE核心设计模式、数据库设计模式外，在实现代码中大量引入Java设计，成为系统扩展性和可移植性的基础。
OFBiz目前兼容Weblogic，Tomcat，Jboss，Resin，Orion等厂商的应用服务器，兼容Oracle，MySQL，Sybase，PostgreSQL，Hsql等数据库产品，可以在Unix和Windows两大操作系统上进行开发和测试，具备Java应用系统的所有跨平台特点[7]。

#### 开源社区支持 ####

开源软件的参与者一般是高热情的志愿者，他们出于兴趣而不是具体的报酬参与其中，自由地贡献各方面的技术和想法，帮助发现潜在的错误，复用已有的代码，避免不必要的重复开发[3]。
Apache OFBiz显然也继承了开源软件这一共性。Apache 组织专门为OFBiz建立的网上社区为爱好者们提供了良好的信息交流平台。来自众多专家和支持者的观点及更新为OFBiz的发展增添了无尽的生命力。

#### Ofbiz缺点 ####

其缺点也是显而易见的：

1. 文献资料少；
2. 开发技术相当多，系统结构也十分复杂

### 相关技术及标准 ###

OFBiz的框架中引入了当前最先进的主流开发Web应用系统构建技术，正是有这些技术的支撑，整个系统在原来的基础上不断被重构和修订，也吸引了众多对最新技术敏感的编程爱好者。

- 与OFBiz相关的开源项目有： FreeMarker 、BeanShell 、Tomcat、 Jetty 、JOTM 、XAPool 、Javolution 、JPublish、 DataVision、 JasperReports、 WEKA、 Xerces、 Xalan 、Axis、 FOP、 Batik、Ant、 BSF 、Commons 、Log4J、 Lucene 、ORO 、POI、 OpenJMS 、PostgreSQL 、MySQL、MaxDB by MySQL、 Hypersonic SQL Derby等 。

- 与OFBiz相关的技术标准有：XML 、SOAP、 HTML 、Java、J2EE、 RuleML、XPDL、BPML、UNSPSC 、ebXML 、FASB 、Workflow、GL & Party 、Product 、qbXML、 OAGIS 、UBL等 。

### 选择Ofbiz有什么好处？ ###

Ofbiz的具体功能优势可以从几大方面来体会。
1. 开源，OFBiz目前得到Apache License（Version 2.0）——开源软件最灵活的许可证之一。该许可证授予您自由使用任何期望的技术、构建派生的作品进行发行、然后将代码贡献回社区[5]。详细证书内容可以查看http://www.apache.org/licenses/LICENSE-2.0。与其他许可证相比，Apache License的自由在于它强调使用源代码的人不需要公开自己的源代码（修改后的源代码），在这种情况下，不管是编程爱好者还是商业公司，从免费获取OFBiz的源代码开始，就可以自由地定制自己所想要的OFBiz，而这并不需要向任何一家公司支付所谓的专利费用。
2. 功能强大，已经拥有了已经开发好，并且稳定的常用业务。
3. 功能扩展方案。Ofbiz提供了一套基于JAVA的功能扩展方案，可以在目前最基本的功能上添加新的功能。并且基于Component组件开发，对于不需要的功能可以将相应Component去除掉。
4. 面向企业应用而设计，Ofbiz不是纯技术框架，是面向业务的（SOA）
5. 用很少的 Code 完成复杂的处理。Ofbiz自身实现了MVC框架、ORM。通过 XML 对系统进行建模，以 XML 来定义系统中不同的层次关系，尽量减少写 Java 代码的数量
6. 缩短开发企业级WEB应用系统的进度和成本
7. OFBiz从技术架构上来说是SOA (Service Oriented Architecture)
8. OFBiz和其他架构最大的不同在于它不仅仅是一个优秀的技术架构，还是一个优秀的业务架构.在应用软件开发领域，单纯的技术框架是没有多少价值的，因为IT行业已经过了泡沫时期，现在要赚钱，是那些面向行业的的业务框架。不过业务框架相对于技术框架来说，更加难以成功，因为技术框架解决的问题相对明确和简单，而业务框架要解决的商务问题实在太灵活多变了，也许Ofbiz算是一个成功的业务框架，如果你能够做出一个很好的某行业的业务框架，赚钱是一定的了。 


为什么不使用SSH

1. Ofbiz是业务框架，SSH属于技术框架，并非一个层次。
2. 就好比你可以买下零件自己组装汽车，但是 Oracle 是组装整车的公司，某一部分不一定是最好的，但是它们组合在一起是最有效率的，每一部分都可以很好地发挥作用。 现在的 Open Source 世界所提供的就是这样的一些汽车零件。把这些零件拼装起来就可以生产整车了，但是你不能简单地拼凑起来，那样是跑不过别人的车的，从 DIY 到提供真正的商业价值的道路还是很远的。

### 类似框架 ###
解决业务问题的业务框架有很多，IBM 兜售的解决方案中就有面向业务的框架，比如以前的[NetSuite E-Commerce](http://www.netsuite.com/portal/home.shtml)。开源的业务框架只用过Ofbiz。


### 有哪些成功案例？ ###

[百货购](http://www.100hg.com/)

[美陶家](http://www.meitaojia.com/)

[gorun8](http://www.gorun8.cn/dyn/main)



## 参考资料 ##

http://blog.sina.com.cn/s/blog_976e49570100ycwe.html

http://www.360doc.com/content/07/0529/16/11586_527277.shtml

http://www.blogjava.net/wealupa/archive/2007/04/19/111971.html

http://dagmom.iteye.com/blog/1625642

http://wang-guo-qiang.iteye.com/blog/106090/

http://wang-guo-qiang.iteye.com/blog/106088

http://wenku.baidu.com/view/792757a0f524ccbff1218440.html

http://www.iteye.com/topic/1032