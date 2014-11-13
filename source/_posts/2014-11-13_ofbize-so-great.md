title: 夸夸Ofbiz
date: 2014-11-13 17:47:00
category: 工作积累
tags: ofbiz
description: 方便自己

---


## 需求描述 ##

开发思想和技术成熟、领先

缩短开发企业级WEB应用系统的进度和成本

开源

OFBiz把PHP世界编程里的方便快捷与Java世界编程里的层次分明给很好地结合了起来


Ofbiz 宣称的优点之一是用很少的 Code 完成复杂的处理。 

### 缺点 ###

文献资料

开发技术相当多，系统结构也十分复杂


## 原始文档 ##

2.1  Apache OFBiz概述
2.1.1  Apache License许可证
OFBiz目前得到Apache License（Version 2.0）——开源软件最灵活的许可证之一。该许可证授予您自由使用任何期望的技术、构建派生的作品进行发行、然后将代码贡献回社区[5]。详细证书内容可以查看http://www.apache.org/licenses/LICENSE-2.0。
与其他许可证相比，Apache License的自由在于它强调使用源代码的人不需要公开自己的源代码（修改后的源代码），在这种情况下，不管是编程爱好者还是商业公司，从免费获取OFBiz的源代码开始，就可以自由地定制自己所想要的OFBiz，而这并不需要向任何一家公司支付所谓的专利费用。
2.1.2  Apache OFBiz功能模块
Apache OFBiz提供大量功能模块，包括有：
(1) 高级电子商务；
(2) 目录管理；
(3) 促销及定价管理；
(4) 定单管理（销售与供应）；
(5) 客户管理；
(6) 仓库管理；
(7) 工作流程；
(8) 账户管理；
(9) 生产管理；
(10)  绩效管理；
(11)  内容管理。
虽然当中的某些模块还不太完善，但总体上来看，Apache OFBiz的目标是提供一个能应用于企业信息化的一个成熟的软件框架。

2.1.3  完善的实体引擎
OFBiz的核心技术在于实体引擎Entity Engine。OFBiz实体引擎提供了一组工具和设计模式来对现实世界中特定的实体（数据对象）进行建模和管理[6]。简言之，实体引擎的主要功能是将数据库表创建、对象与数据表的映射、对象的查询等强大的封装，这样就可以在一个简单的XML文件中定义数据库表结构，OFBiz会自动在数据库中建表，并动态生成映射对象，开发者在程序中可以只考虑对对象的处理，OFBiz会自动通过事务逻辑更新到数据库中。
实体引擎的目标是简化企业级应用中对实体数据（对应关系型数据库表）的大量操作，包括定义、维护、通用操作（增、删、改、查实体和实体之间的关系）的开发工作。

2.1.4  扩展性和可移植性
OFBiz提供一个基于纯Java应用程序的系统框架，在具体实现中大量采用了各种设计系统模式，完全符合面向对象的设计原则中绝大部分要求，除采用J2EE核心设计模式、数据库设计模式外，在实现代码中大量引入Java设计，成为系统扩展性和可移植性的基础。
OFBiz目前兼容Weblogic，Tomcat，Jboss，Resin，Orion等厂商的应用服务器，兼容Oracle，MySQL，Sybase，PostgreSQL，Hsql等数据库产品，可以在Unix和Windows两大操作系统上进行开发和测试，具备Java应用系统的所有跨平台特点[7]。

2.1.5  开源社区支持
开源软件的参与者一般是高热情的志愿者，他们出于兴趣而不是具体的报酬参与其中，自由地贡献各方面的技术和想法，帮助发现潜在的错误，复用已有的代码，避免不必要的重复开发[3]。
Apache OFBiz显然也继承了开源软件这一共性。Apache 组织专门为OFBiz建立的网上社区为爱好者们提供了良好的信息交流平台。来自众多专家和支持者的观点及更新为OFBiz的发展增添了无尽的生命力。

2.2  相关技术及标准
OFBiz的框架中引入了当前最先进的主流开发Web应用系统构建技术，正是有这些技术的支撑，整个系统在原来的基础上不断被重构和修订，也吸引了众多对最新技术敏感的编程爱好者。
与OFBiz相关的开源项目有： FreeMarker 、BeanShell 、Tomcat、 Jetty 、JOTM 、XAPool 、Javolution 、JPublish、 DataVision、 JasperReports、 WEKA、 Xerces、 Xalan 、Axis、 FOP、 Batik、Ant、 BSF 、Commons 、Log4J、 Lucene 、ORO 、POI、 OpenJMS 、PostgreSQL 、MySQL、MaxDB by MySQL、 Hypersonic SQL Derby等 。
与OFBiz相关的技术标准有：XML 、SOAP、 HTML 、Java、J2EE、 RuleML、XPDL、BPML、UNSPSC 、ebXML 、FASB 、Workflow、GL & Party 、Product 、qbXML、 OAGIS 、UBL等 。

2.3  二次开发方法论
Apache创始人Brian Behlendorf先生曾总结开源项目开发方法论最重要的特点是：“它的组织者不是‘管理’开发者，而是‘带领’他们充分发挥开发者的主观能动性”[10]。
开源软件的二次开发方法也因为这个特点与众不同。首先，以最自由的方式修改现有模块，甚至突破原有框架扩展功能；第二，免费得到最新技术支持，这要得益于开源社区的贡献；第三，没有固定不变的开发模式，完全由用户需求决定，大大节省成本。










首先，研究过Apache OFBiz的人都会被其成熟、领先的开发思想和技术所吸引。Apache OFBiz完全具备大型复杂的电子商务平台的框架特性，必将成为未来优秀的电子商务解决方案。

另一方面，使用Apache OFBiz的框架和组件，可以大大缩短开发企业级WEB应用系统的进度和成本。当然，前提是要有扎实的编程基础和敏感的技术嗅觉，因为这个项目涉及的技术范畴十分广。要想完全透彻地理解，并熟练地应用到实际中去，确实需要大量的努力和研究。

当前，国内的企业电子商务应用水平参差不齐，缺乏成熟的电子商务软件平台是其中一个重要原因。从开发成本的角度看，国内大多数企业，特别是对电子商务需求正不断增长的中小型企业难以负担得起成熟软件平台的开发及维护费用。开源提供了另外一种可能的解决方案。

只要对Apache OFBiz研究透彻，既可以吸收开源软件公开的优秀技术，又能在其框架上开发、定制所需的应用模块，无论从技术更新还是投入成本讲，Apache OFBiz不失为一种即经济又有效的电子商务解决方案。

在文献资料方面，由于OFBiz的中文官方站点还没有开通，网络上并没有相关的中文权威资料库。虽然国内也有不少人开始研究OFBiz，研究心得之类的文献资源较零散。OFBiz的英文技术文档大部分可以从其英文官方网站获取，从这一点来看，多数开源项目由国外发起，因此一定的英文材料阅读能力是必需的。

OFBiz基于大型电子商务应用构建，因此涉及的开发技术相当多，系统结构也十分复杂。对技术的学习能力和合理选择研究方向是对这个项目进行二次开发的关键前提。OFBiz是由世界各地的技术高手共同维护的项目，一个人并不可能完全掌握其中所有技术要点。


http://blog.sina.com.cn/s/blog_976e49570100ycwe.html



Spring:
- I dont see any existing entities there. Its just a framework! OfBIZ has
600 plus well-thought entities ready to be used and aggreed upon!
- I dont see standard components with business functionality. There might
be apps out there but you got to merge them yourself!
+ it seems they have a better marketing department!
So Spring just has a different approach and can not be compared to ofbiz
which is an erp-system with a nice framwork! Spring is just a framework! So
there are years until spring could reach ofbiz level !?


http://www.360doc.com/content/07/0529/16/11586_527277.shtml

http://www.blogjava.net/wealupa/archive/2007/04/19/111971.html




http://dagmom.iteye.com/blog/1625642

http://wang-guo-qiang.iteye.com/blog/106090/

http://wang-guo-qiang.iteye.com/blog/106088