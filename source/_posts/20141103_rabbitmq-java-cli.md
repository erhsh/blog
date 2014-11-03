title: RabbitMq之java实战
date: 2014-11-03 22:55:16 
category: 工作积累
tags: RabbitMq
description: 曾经以为理解了RabbitMq，今天应对新需求，发现理解还是不到位。

---

## RabbitMq之java实战 ##

### 消费者 ###
	public static void main(String[] args) throws Exception {
		// 建立连接，得到channel：
		ConnectionFactory factory = new ConnectionFactory();
		factory.setHost("127.0.0.1");
		factory.setPort(5672);
		factory.setUsername("guest");
		factory.setPassword("guest");
	
	
		Connection connection = factory.newConnection();
		Channel channel = connection.createChannel();
	
		// 构建消费者：
		QueueingConsumer consumer = new QueueingConsumer(channel);

		// 声明交换机，有则用，无则创建：
		channel.exchangeDeclare("MsgTopic1", "topic", false, true, false, null);

		// 声明消息队列，有则用，无则创建：
		channel.queueDeclare("queueAlarm", false, false, true, null);

		// 队列绑定，指定该队列接收来自哪个交换机下哪条路由的消息：
		channel.queueBind("queueAlarm", "MsgTopic1", "rout1_1");
		channel.queueBind("queueAlarm", "MsgTopic1", "rout1_2");

		// 指定消费者
		channel.basicConsume("queueAlarm", true, consumer);

		// 可绑定多个关系
		channel.exchangeDeclare("MsgTopic2", "topic", true, false, false, null);
		channel.queueDeclare("updateQueue", false, false, true, null);
		channel.queueBind("updateQueue", "MsgTopic2", "#");
		channel.queueBind("updateQueue", "MsgTopic2", "rout2_2");
		channel.basicConsume("updateQueue", true, consumer);

		// 消费者消费消息
		while (true) {
			QueueingConsumer.Delivery delivery = consumer.nextDelivery();
			String message = new String(delivery.getBody());
			String routingKey = delivery.getEnvelope().getRoutingKey();

			System.out.println(" [x] Received '" + routingKey + "':'" + message
					+ "'");
		}
	}

### 生产者 ###

	public static void main(String[] args) throws Exception {
		ConnectionFactory factory = new ConnectionFactory();
		factory.setHost("127.0.0.1");
		factory.setPort(5672);
		factory.setUsername("guest");
		factory.setPassword("guest");
		
		Connection connection = factory.newConnection();
		Channel channel = connection.createChannel();

		// 声明消息队列
		channel.queueDeclare("MsgTopic1", false, false, false, null);

		// 发布消息
		channel.basicPublish("MsgTopic", "8", null, "Hello World!".getBytes());
		System.out.println(" [x] Sent '" + message + "'");

		channel.close();
		connection.close();
	}


### 可配置的消费者 ###

配置文件：

	<?xml version="1.0" encoding="UTF-8"?>
	<rmqReceiveCfg>
		<recevieQueue>
			<exchangeName>MsgTopic</exchangeName>
			<queueName>alarmQueue</queueName>
			<msgParser>com.erhsh.push.parser.impl.AlarmMsgParser</msgParser>
			<routeKey>8</routeKey>
		</recevieQueue>
		<recevieQueue>
			<exchangeName>MsgTopic</exchangeName>
			<queueName>upgradeQueue</queueName>
			<msgParser>com.erhsh.push.parser.impl.UpgradeMsgParser</msgParser>
			<routeKey>9</routeKey>
			<routeKey>10</routeKey>
		</recevieQueue>
		<recevieQueue>
			<exchangeName>MsgTopic</exchangeName>
			<queueName>allQueue</queueName>
			<msgParser>com.erhsh.push.parser.impl.UpgradeMsgParser</msgParser>
			<routeKey>#</routeKey>
		</recevieQueue>
	</rmqReceiveCfg>

对应的配置类：

	package com.erhsh.push.test;
	
	import java.io.InputStream;
	import java.util.List;
	
	import javax.xml.bind.JAXB;
	
	public class RmqReceiveCfg {
	
		private static RmqReceiveCfg instance;
		private List<RecevieQueue> recevieQueue;
	
		public static RmqReceiveCfg getInstance() {
			if (null != instance) {
				return instance;
			}
	
			return createRmqReceiveCfg();
		}
	
		private static synchronized RmqReceiveCfg createRmqReceiveCfg() {
	
			if (instance != null) {
				return instance;
			}
	
			InputStream is = ClassLoader.getSystemResourceAsStream("tmp2.xml");
			instance = JAXB.unmarshal(is, RmqReceiveCfg.class);
			return instance;
		}
	
		public List<RecevieQueue> getRecevieQueue() {
			return recevieQueue;
		}
	
		public void setRecevieQueue(List<RecevieQueue> recevieQueue) {
			this.recevieQueue = recevieQueue;
		}
	
		static class RecevieQueue {
			private String exchangeName;
	
			private String queueName;
	
			private String msgParser;
	
			private List<String> routeKey;
	
			public String getExchangeName() {
				return exchangeName;
			}
	
			public void setExchangeName(String exchangeName) {
				this.exchangeName = exchangeName;
			}
	
			public String getQueueName() {
				return queueName;
			}
	
			public void setQueueName(String queueName) {
				this.queueName = queueName;
			}
	
			public String getMsgParser() {
				return msgParser;
			}
	
			public void setMsgParser(String msgParser) {
				this.msgParser = msgParser;
			}
	
			public List<String> getRouteKey() {
				return routeKey;
			}
	
			public void setRouteKey(List<String> routeKey) {
				this.routeKey = routeKey;
			}
	
		}
	
		public static void main(String[] args) {
			RmqReceiveCfg cfg = RmqReceiveCfg.getInstance();
			System.out.println(cfg);
		}
	}
