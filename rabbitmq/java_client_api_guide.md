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

##### 方法二

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

> a durable, non-autodelete exchange of "direct" type
> a non-durable, exclusive, autodelete queue with a generated name






