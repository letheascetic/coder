# Java Client API Guide

# Overview

### 主要类和接口

* Channel
* Connection
* ConnectionFactory
* Consumer

### 连接broker

#### 方法一

    ConnectionFactory factory = new ConnectionFactory();
    factory.setUsername(userName);
    factory.setPassword(password);
    factory.setVirtualHost(virtualHost);
    factory.setHost(hostName);
    factory.setPort(portNumber);
    Connection conn = factory.newConnection();

#### 方法二

    ConnectionFactory factory = new ConnectionFactory();
    factory.setUri("amqp://userName:password@hostName:portNumber/virtualHost");
    Connection conn = factory.newConnection();


