title: 这里是文章标题
date: 1970-01-01 00:00:00 
category: 教程技术
tags: 涨技能
description: 方便自己

---

# Netty学习 #
Netty提供异步的、事件驱动的网络应用程序框架和工具，用以快速开发高性能、高可靠性的网络服务器和客户端程序


Netty整体架构很清晰的分成2个部分，ChannelFactory和
ChannelPipelineFactory,前者主要生产网络通信相关的Channel实例和
ChannelSink实例，Netty提供的ChannelFactory实现基本能够满足绝大部分用户的需求，当然你也可以定制自己的ChannelFactory,后者主要关注于具体传输数据的处理，同时也包括其他方面的内容，比如异常处理等等，只要是你希望的，你都可以往里添加相应的handler,一般ChannelPipelineFactory由用户自己实现，因为传输数据的处理及其他操作和业务关联比较紧密，需要自定义处理的handler。

现在，使用Netty的步骤实际上已经非常明确了，比如面向连接的Netty服务端客户端使用，第一步：实例化一个BootStrap,并且通过构造方法指定一个ChannelFactory实现，第二步：向bootstrap实例注册一个自己实现的ChannelPipelineFactory,第三步：如果是服务器端，bootstrap.bind(newInetSocketAddress(port))，然后等待客户端来连接,如果是客户端，
bootstrap.connect(newInetSocketAddress(host,port))取得一个future,这个时候Netty会去连接远程主机，在连接完成后，会发起类型为CONNECTED的ChannelStateEvent，并且开始在你自定义的Pipeline里面流转，如果你注册的handler有这个事件的响应方法的话那么就会调用到这个方法。在此之后就是数据的传输了。


现在，使用Netty的步骤实际上已经非常明确了，比如面向连接的Netty服务端客户端使用，第一步：实例化一个BootStrap,并且通过构造方法指定一个ChannelFactory实现，第二步：向bootstrap实例注册一个自己实现的ChannelPipelineFactory,第三步：如果是服务器端，bootstrap.bind(newInetSocketAddress(port))，然后等待客户端来连接,如果是客户端，
bootstrap.connect(newInetSocketAddress(host,port))取得一个future,这个时候Netty会去连接远程主机，在连接完成后，会发起类型为CONNECTED的ChannelStateEvent，并且开始在你自定义的Pipeline里面流转，如果你注册的handler有这个事件的响应方法的话那么就会调用到这个方法。在此之后就是数据的传输了。

网络动作归结到最简单就是服务器端bind->accept->read->write,客户端 connect->read->write,一般bind或者connect后会有多次read、write。这种特性导致，bind,accept与read,write的线程分离，connect与read、write线程分离，这样做的好处就是无论是服务器端还是客户端吞吐量将有效增大，以便充分利用机器的处理能力，而不是卡在网络连接上，不过一旦机器处理能力充分利用后，这种方式反而可能会因为过于频繁的线程切换导致性能损失而得不偿失，并且这种处理模型复杂度比较高。

采用什么样的网络事件响应处理机制对于网络吞吐量是非常重要的，Netty采用的是标准的SEDA（StagedEvent-DrivenArchitecture）架构
[http://en.wikipedia.org/wiki/Staged_event-driven_architecture]，其所设计的事件类型，代表了网络交互的各个阶段，并且在每个阶段发生时，触发相应事件交给初始化时生成的pipeline实例进行处理。事件处理都是通过
Channels类的静态方法调用开始的，将事件、channel传递给channel持有的Pipeline进行处理，Channels类几乎所有方法都为静态，提供一种Proxy的效果(整个工程里无论何时何地都可以调用其静态方法触发固定的事件流转,但其本身并不关注具体的处理流程)。


Channels部分事件流转静态方法
1．fireChannelOpen2．fireChannelBound3．fireChannelConnected4．fireMessageReceived5．fireWriteComplete6．fireChannelInterestChanged7．fireChannelDisconnected8．fireChannelUnbound9．fireChannelClosed10.fireExceptionCaught11.fireChildChannelStateChanged



http://wenku.baidu.com/view/e9638e25ccbff121dd3683c2.html
## 前言 ##

## 分析 ##

## 总结 ##

