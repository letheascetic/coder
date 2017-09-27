# weave

* 物联网通信框架，不依赖于任何底层的通信协
* 它可以运行在任何常见的物联网通信协议之上，包括WiFi，BLE，Zigbee等等
* 低功耗、低带宽、低延迟、安全

## 特点

### 可移植性：

操作系统无关，可以移植到任意操作系统上，只要底层操作系统能够提供Weave需要的最基本函数接口。

### 标准化和通用性： 

不依赖于任何通信协议，可以运行在Wi-Fi，BLE，Zigbee等常见的通信协议之上。
Weave提供了一套标准的设备操作命令（叫做Schema），以及对应的认证机制。

### 可扩展性：

不在标准schema框架内的设备及操作，可以经过Google的认证后，添加到标准schema中。

## weave 组成

### 三大组件

![](https://github.com/letheascetic/coder/blob/master/IOT/pic/weave.png "weave-architecture")

* 云端组件（WeaveCloud）：提供所有的云化基础环境
* 智能手机端组件: Android & IOS lib/api 
* 设备端组件（LibWeave和uWeave）

> LibWeave: 适应于具备复杂计算能力的设备, 设备连接Cloud
> uWeave: 运行在资源受限的嵌入式设备上，设备不连接Cloud，只接收手机端管理

### 两类API

![](https://github.com/letheascetic/coder/blob/master/IOT/pic/weave-api.png "weave-api")

* Weave Local API:  mDNS, HTTPS, BLE
* Weave Cloud API:  DNS, HTTPS, XMPP(星形通信)

## 技术

### 标准的命令和状态Schema

* 传递的数据无非分为两类：命令（command）和状态（state）
* 设备分类，每类设备赋予一个标准的类别编码
* 定义每种类别的设备的标准命令和状态，用JSON格式进行表示
* 采用全球唯一ID(GUID)来标识每个设备
* 设备厂商可以自己定义，然后向Google申请认证

> 
{
    “deviceId”: “52c867ca-17d5-f422-a2c8-b31c4e02743e”,
    “name”: “onOff.setConfig”,
    “parameters”: {
       “state” : “on”
     }
}

### 用户权限管理

* Owner：是设备的所有者，拥有最高权限。Owner可以设定其它的用户角色；
* Manager，具备对其它（除Owner和Manager之外）用户角色的管理职责，可以给用户分配角色；
* User：设备的使用者，具备对设备执行命令（commands）的权限；
* Viewer：设备的查看者，可以对设备的状态（state）进行查询，但是不能对设备进行命令操作；
* Unspecified/anonymous：没有被授予任何权限的角色。

### 低功耗蓝牙的深度优化

* CBOR编码格式代替JSON
* 短周期连接

### 资源受限系统的专门优化

## 不足

* 没有实现物联网设备与设备之间的协同
* 基于Weave的物联网设备，只能在用户的Google账号范围内可以唯一识别，一旦超出了Google账号的范围，则无法识别
* 针对Zigbee以及LoRa等无线通信技术，Weave还没有对应的解决方案
* Weave Cloud没有开源
* Google的服务器并不是每个地方都能访问到，对于一些无法访问Google服务的地方，则Weave几乎无法使用

## 现状

三星电子的SmartThings智能硬件，以及Philips Hue等产品已经在使用Weave通信协议

一些其他的产品如Belking WeMo,LiFX,Honeywell,Wink，TP-Link和First Alert也正在整合实施当中。

## 参考
http://blog.csdn.net/hellochina15/article/details/51969995
http://www.infoq.com/cn/news/2015/10/nest-weave
http://news.zol.com.cn/619/6193924.html

