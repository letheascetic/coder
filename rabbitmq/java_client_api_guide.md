# Java Client API Guide

## Overview

### 主要类和接口

* Channel
* Connection
* ConnectionFactory
* Consumer

## 使用connection和channel

### 连接broker

##### 方法一

    ConnectionFactory factory = new ConnectionFactory();
    factory.setUsername(userName);
    factory.setPassword(password);
    factory.setVirtualHost(virtualHost);
    factory.setHost(hostName);
    factory.setPort(portNumber);
    Connection conn = factory.newConnection();

##### 方法二：使用连接字符串

    ConnectionFactory factory = new ConnectionFactory();
    factory.setUri("amqp://userName:password@hostName:portNumber/virtualHost");
    Connection conn = factory.newConnection();

### 使用connection创建channel
    
    Channel channel = conn.createChannel();

### 断开连接

    channel.close();
    conn.close();

## 使用Exchanges和Queue

### 声明exchange和queue，并绑定

##### 方法一

    channel.exchangeDeclare(exchangeName, "direct", true);
    String queueName = channel.queueDeclare().getQueue();
    channel.queueBind(queueName, exchangeName, routingKey);

> a **durable**, non-autodelete exchange of "direct" type
> a non-durable, exclusive, **autodelete** queue with a generated name
> 声明了一个用后即删的queue,不需要给出名字

##### 方法二

    channel.exchangeDeclare(exchangeName, "direct", true);
    channel.queueDeclare(queueName, true, false, false, null);
    channel.queueBind(queueName, exchangeName, routingKey);

> a durable, non-autodelete exchange of "direct" type
> a **durable**, non-exclusive, non-autodelete queue with a **well-known name**
> 声明了一个给定名字的queue，适合于多个clients共享同一个queue。

## 发布消息

##### 方法一

    byte[] messageBodyBytes = "Hello, world!".getBytes();
    channel.basicPublish(exchangeName, routingKey, null, messageBodyBytes);

##### 方法二：添加Message属性

    channel.basicPublish(exchangeName, routingKey, mandatory,
                         MessageProperties.PERSISTENT_TEXT_PLAIN,
                         messageBodyBytes);

> 发送persistent的message,内容类型为“text/plain”

##### 方法三：使用Builder构建Message属性

    channel.basicPublish(exchangeName, routingKey,
                 new AMQP.BasicProperties.Builder()
                   .contentType("text/plain")
                   .deliveryMode(2)
                   .priority(1)
                   .userId("bob")
                   .build()),
                   messageBodyBytes);

##### 方法四：Message添加headers

    Map<String, Object> headers = new HashMap<String, Object>();
    headers.put("latitude",  51.5252949);
    headers.put("longitude", -0.0905493);

    channel.basicPublish(exchangeName, routingKey,
                 new AMQP.BasicProperties.Builder()
                   .headers(headers)
                   .build()),
                   messageBodyBytes);

##### 方法五：Message添加expiration

    channel.basicPublish(exchangeName, routingKey,
                 new AMQP.BasicProperties.Builder()
                   .expiration("60000")
                   .build()),
                   messageBodyBytes);

















