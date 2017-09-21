# symantec iot

IoT security can be covered with four cornerstones: 

## Protecting Communications

* encryption and authentication for devices to know whether or not they can trust a remote system
* elliptic curve cryptography (ECC)
* embedded “device certificate” keys

## Protecting Devices

* code signing, to be sure all code is authorized to run, it can be done at “application” and “firmware” levels 
* run-time protection, to be sure malicious attacks don’t overwrite code after it is loaded, host based protections

## Managing Devices

* updates required
* over-the air (OTA) manageability must be built into devices before they ship.

## Understanding Your System

* an IoT Security Analytics capability that helps you best understand your network


Comprehensive security requires clean integration of the **key management, host-based security, OTA infrastructure, and security analytics**. 


## Strategy

### Protecting Communications

* Elliptic Curve Cryptography (ECC) has been proven 10x faster and more efficient than traditional encryption in resource constrained chips, such as IoT chips. 

* (a) 224-bit ECC at a minimum for end-entity certificates, with 256-bit and 384-bit preferred; (b) 256-bit ECC at a minimum for root certificates, with 384-bit preferred.

* embed both roots of trust and device certificates into devices

### Protecting Devices

* Protecting the Code that Drives IoT, code signing
* (a) 224-bit ECC at a minimum for end-entity certificates, with 256-bit and 384-bit preferred; (b) 521-bit ECC at a minimum for root certificates
* Effective Host-Based Protection for IoT
* system hardening, whitelisting, application sandboxing, reputation-based technology, antimalware, and encryption. 


### Managing Devices

IoT systems must have OTA update capabilities built into them from the beginning.

* Configuration updates
* Management of security content and security telemetry for security analytics
* Management of telemetry and control for proper system function
* Diagnostics and remediation
* Management of Network Access Control (NAC) credentials
* Management of permissions, and countless other examples

### Understanding Your System

Security Analytics to Address Threats Beyond the Above Countermeasures


## products

### 嵌入式 Critical System Protection

> 一款轻量型安全防护客户端，旨在通过保护端点和嵌入式设备来确保物联网(IoT) 安全。 
> 为嵌入式系统生产商和资产所有人提供了无特征、基于主机的强大安全防护，可用于托管场景和非托管场景，且不影响设备性能。

### 设备证书实现强认证功能

对物联网设备进行身份验证，并对通过物联网系统和网络进行传输的数据予以加密。

> 椭圆曲线加密技术 (ECC) 适用于极度受限的设备、低兆赫、容量超低的存储器
> 验证分布式硬件身份的统包式解决方案
> 基于公共密钥基础设施 (PKI) 的解决方案特别适用于分布式硬件设备，是验证其身份的最合适方法。
> 赛门铁克推出的这款大容量和高性能的解决方案可帮助厂商或生态系统将证书嵌入到硬件中，同时为颁发的证书实时提供生命周期管理。
> 一个统包式解决方案，可通过易于使用的 Web 界面生成批量数字证书。
> 无需掌握 PKI 的技术知识，也不需要投资购买昂贵的基础架构即可管理身份验证服务。
> PKI 环境完全托管在一个 24 x 7 x 365 全天候运行的军用级别的安全设备中，由赛门铁克一手管理

### 代码签名证书

控制在设备上运行的代码权限

> 支持 ELF 和 Java 等格式文件的云签名和控制。
> 支持作者与出版商之间复杂的关系。
> 帮助管理层级式供应商之间的复杂生态系统。

确保设备上运行的代码经过授权，而非攻击者上传的代码。

* 大多数芯片组，包括随附专属工具的安全启动芯片组，同时需要支持算法。
* 应用程序级别代码签名和验证，只需借助 OpenSSL 和 Micro-ECC 等广受欢迎的开源加密库。

帮助管理内部和合作伙伴软件开发人员的签名权限

* 确保您能控制有权在您所分发系统中运行的供应商。
* 在员工和合作伙伴发生变动时，保护代码签名密匙

## references

* https://www.symantec.com/content/dam/symantec/docs/white-papers/iot-security-reference-architecture-en.pdf
* https://www.symantec.com/content/dam/symantec/docs/data-sheets/embedded-security-critical-system-protection-en.pdf
* https://www.websecurity.symantec.com/code-signing






