# weave

物联网通信框架，不依赖于任何底层的通信协议，它可以运行在任何常见的物联网通信协议之上，包括WiFi，BLE，Zigbee等等

## 特点

### 可移植性：

操作系统无关，可以移植到任意操作系统上，只要底层操作系统能够提供Weave需要的最基本函数接口。

### 标准化和通用性： 

不依赖于任何通信协议，可以运行在Wi-Fi，BLE，Zigbee等常见的通信协议之上。
Weave提供了一套标准的设备操作命令（叫做Schema），以及对应的认证机制。

### 可扩展性：

不在标准schema框架内的设备及操作，可以经过Google的认证后，添加到标准schema中。

## weave 组成

![](https://github.com/letheascetic/coder/blob/master/IOT/pic/weave.png "weave-architecture")

### 三大组件

* 云端组件（WeaveCloud）
* 智能手机段组件: Android & IOS lib/api 
* 设备端组件（LibWeave和uWeave）

> LibWeave: 适应于具备复杂计算能力的设备
> uWeave: 运行在资源受限的嵌入式设备上

### 两类API

* Weave Local API
* WeaveCloud API


## 参考
http://blog.csdn.net/hellochina15/article/details/51969995
http://www.infoq.com/cn/news/2015/10/nest-weave