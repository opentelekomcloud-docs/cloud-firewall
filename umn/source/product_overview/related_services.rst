:original_name: cfw_01_0007.html

.. _cfw_01_0007:

Related Services
================

IAM
---

`Identity and Access Management (IAM) <https://docs.otc.t-systems.com/identity-access-management/umn/service_overview/what_is_iam.html#iam-01-0026>`__ provides the permission management function for CFW. Only users who have Tenant Administrator permissions can perform operations such as authorizing, managing, and detect cloud assets using CFW. To obtain the permissions, contact the users who have the Security Administrator permissions.

EIP
---

`Elastic IP (EIP) <https://docs.otc.t-systems.com/elastic-ip/umn/service_overview/what_is_elastic_ip.html>`__ provides independent public IP addresses and bandwidth for Internet access.

CFW protects Internet border traffic by protecting EIPs.

VPC
---

`Virtual Private Cloud (VPC) <https://docs.otc.t-systems.com/virtual-private-cloud/umn/service_overview/what_is_virtual_private_cloud.html#en-us-topic-0013748729>`__ enables you to provision an isolated, private virtual network for cloud resources, such as cloud servers, containers, and databases.

CFW can protect traffic at VPC borders, such as between VPCs, or between a VPC on the cloud and an on-premises data center.

NAT Gateway
-----------

NAT Gateway provides public and private NAT gateways. A public NAT gateway provides SNAT and DNAT to let cloud servers in a VPC use an EIP to communicate with the Internet.

CFW protects the NAT gateway traffic by protecting the VPC where the NAT gateway resides.

Enterprise Router
-----------------

Enterprise Router provides inter-VPC traffic diversion for CFW. If you purchase the professional edition to protect inter-VPC traffic or Direct Connect traffic, you need to use Enterprise Router to divert traffic.

CTS
---

`Cloud Trace Service (CTS) <https://docs.otc.t-systems.com/cloud-trace-service/umn/service_overview/what_is_cloud_trace_service.html#en-us-topic-0030594187>`__ generates traces to enable you to get a history of operations performed on CFW, allowing you to query, audit, and backtrack resource operation requests initiated from the management console as well as the responses to those requests.

CTS records operations related to CFW, facilitating your further queries, audits, and retrievals.

Cloud Eye
---------

`Cloud Eye <https://docs.otc.t-systems.com/cloud-eye/umn/product_introduction/what_is_cloud_eye.html#en-us-topic-0015479882>`__ provides a comprehensive monitoring platform for resources such as the ECS and bandwidth. Cloud Eye monitors the metrics of CFW, so that you can understand the protection status of the service in a timely manner, and set protection policies accordingly.

LTS
---

`Log Tank Service (LTS) <https://docs.otc.t-systems.com/log-tank-service/umn/service_overview/introduction.html#lts-01-0002>`__ collects log data from servers and cloud services. CFW can record attack event logs, access control logs, and traffic logs to LTS, enabling real-time, efficient, and secure log processing.

Differences from WAF
--------------------

CFW and WAF are two different products that can be used to protect your Internet borders, VPC borders, and web services.

The following table describes the differences between CFW and WAF.

.. table:: **Table 1** Differences between CFW and WAF

   +-----------------------+---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
   | Item                  | CFW                                                                                                                                                                                                                                                                                                                                                                                                                                                                                   | WAF                                                                                                                                                                                                                                                                                                                                                                                                                  |
   +=======================+=======================================================================================================================================================================================================================================================================================================================================================================================================================================================================================+======================================================================================================================================================================================================================================================================================================================================================================================================================+
   | Definition            | Cloud Firewall (CFW) is a next-generation cloud-native firewall. It protects the Internet border and VPC border on the cloud by real-time intrusion detection and prevention, global unified access control, full traffic analysis, log audit, and tracing. It employs AI for intelligent defense, and can meet changing business needs, helping you easily handle security threats. CFW is a basic service that provides network security protection for user services on the cloud. | WAF keeps web services stable and secure. It examines all HTTP and HTTPS requests to detect and block the following attacks: Structured Query Language (SQL) injection, cross-site scripting (XSS), web shells, command and code injections, file inclusion, sensitive file access, third-party vulnerability exploits, Challenge Collapsar (CC) attacks, malicious crawlers, and cross-site request forgery (CSRF). |
   +-----------------------+---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
   | Protection            | -  EIP border and VPC border                                                                                                                                                                                                                                                                                                                                                                                                                                                          | -  Applicable to domain names, IP addresses, and web services on and off the cloud                                                                                                                                                                                                                                                                                                                                   |
   |                       | -  Basic protection against web attacks                                                                                                                                                                                                                                                                                                                                                                                                                                               | -  Comprehensive protection against web attacks                                                                                                                                                                                                                                                                                                                                                                      |
   |                       | -  Defense against external intrusions and protection of proactive connections to external systems                                                                                                                                                                                                                                                                                                                                                                                    |                                                                                                                                                                                                                                                                                                                                                                                                                      |
   +-----------------------+---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
   | Features              | -  Asset management and intrusion defense: It detects and defends against intrusions into cloud assets that are accessible over the Internet in real time.                                                                                                                                                                                                                                                                                                                            | WAF identifies and blocks a wide range of suspicious attacks, such as SQL injections, XSS attacks, web shell upload, command or code injections, file inclusion, unauthorized sensitive file access, third-party vulnerability exploits, CC attacks, malicious crawlers, and CSRF.                                                                                                                                   |
   |                       | -  Access control: You can control access at Internet borders.                                                                                                                                                                                                                                                                                                                                                                                                                        |                                                                                                                                                                                                                                                                                                                                                                                                                      |
   |                       | -  Traffic Analysis and log audit: CFW controls, analyzes, and visualizes VPC traffic, audits logs, and traces traffic sources.                                                                                                                                                                                                                                                                                                                                                       |                                                                                                                                                                                                                                                                                                                                                                                                                      |
   +-----------------------+---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
