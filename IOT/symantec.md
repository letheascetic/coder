# symantec iot

IoT security can be covered with four cornerstones: 

##### Protecting Communications

* encryption and authentication for devices to know whether or not they can trust a remote system
* elliptic curve cryptography (ECC)
* embedded “device certificate” keys

##### Protecting Devices

* code signing, to be sure all code is authorized to run, it can be done at “application” and “firmware” levels 
* run-time protection, to be sure malicious attacks don’t overwrite code after it is loaded, host based protections

##### Managing Devices

* updates required
* over-the air (OTA) manageability must be built into devices before they ship.

##### Understanding Your System

* an IoT Security Analytics capability that helps you best understand your network


Comprehensive security requires clean integration of the **key management, host-based security, OTA infrastructure, and security analytics**. 


### Strategy

#### Protecting Communications

* Elliptic Curve Cryptography (ECC) has been proven 10x faster and more efficient than traditional encryption in resource constrained chips, such as IoT chips. 

* (a) 224-bit ECC at a minimum for end-entity certificates, with 256-bit and 384-bit preferred; (b) 256-bit ECC at a minimum for root certificates, with 384-bit preferred.

* embed both roots of trust and device certificates into devices

#### Protecting Devices

* Protecting the Code that Drives IoT, code signing
* (a) 224-bit ECC at a minimum for end-entity certificates, with 256-bit and 384-bit preferred; (b) 521-bit ECC at a minimum for root certificates
* Effective Host-Based Protection for IoT
* system hardening, whitelisting, application sandboxing, reputation-based technology, antimalware, and encryption. 


### Managing Devices

• Configuration updates
• Management of security content and security telemetry for security analytics
• Management of telemetry and control for proper system function
• Diagnostics and remediation
• Management of Network Access Control (NAC) credentials
• Management of permissions, and countless other examples






