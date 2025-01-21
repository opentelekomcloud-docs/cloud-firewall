:original_name: cfw_01_0057.html

.. _cfw_01_0057:

Basic Concepts
==============

5-tuple
-------

A 5-tuple (or quintuple) consists of a source IP address, a destination IP address, a protocol, a source port, and a destination port.

Protected Traffic
-----------------

Inbound traffic is the traffic transferred from the Internet to CFW. For example, the traffic for downloading resources from the public network to servers in the cloud is the inbound traffic.

Outbound traffic is the traffic transferred from CFW to the Internet. For example, servers on the cloud provide services for external users, the traffic used by external users for downloading resources from the cloud is outbound traffic.

Protection bandwidth: bandwidth of all services protected by CFW.

Protected bandwidth at the Internet border: the maximum inbound or outbound traffic of all EIPs protected by CFW.

Protected bandwidth at the VPC border: the maximum total traffic of all VPCs protected by CFW.

Internet Border Firewall
------------------------

An Internet border firewall is used to detect north-south traffic. It supports intrusion detection and prevention (IPS) and network antivirus based on EIPs.

VPC Border Firewall
-------------------

A VPC border firewall is used to detect communication traffic between two VPCs (east-west traffic), visualizing and protecting internal access activities.

IPS
---

An intrusion prevention system (IPS) is located between a firewall and a network device. It blocks attacks from suspicious communications before they are spread to other network devices.

Antivirus
---------

The anti-virus function identifies and processes virus files through virus feature detection to prevent data damage, permission change, and system breakdown.

Internet Access
---------------

Internet access refers to the access from Internet IP addresses to cloud servers. Internet access protection helps you defend against intrusions from the outside in a timely manner.

Server Originated Access
------------------------

Server originated access refers to the behavior that a cloud server proactively accesses an external IP address. Server originated access protection helps you manage and control outbound access behaviors.

VPC Peering Connection
----------------------

A VPC peering connection is a networking connection between two VPCs using private IP addresses as if they were in the same VPC. In the same resource pool, you can create a VPC peering connection between your own VPCs, or with a VPC of another tenant. However, you cannot create a VPC peering connection between VPCs in different resource pools.

Enterprise Router
-----------------

An enterprise router is a central router that interconnects all of your VPCs and on-premises networks.

CFW-associated Subnet
---------------------

This is a parameter that can be configured for a VPC border firewall. After a CIDR block is configured, a CFW-associated subnet is automatically allocated to forward traffic from the firewall to an enterprise router.

CVE ID
------

A Common Vulnerabilities and Exposures (CVE) ID is the unique identifier of a vulnerability.

CVE is a list of security vulnerabilities. Each entry in the list has a unique CVE ID.

Inspection VPC
--------------

An inspection VPC is used for a VPC border firewall to divert traffic. After a CIDR block is configured, CFW creates an inspection VPC by default. In VPC mode, the traffic destined for a service VPC is diverted by the inspection VPC to the firewall. In enterprise router mode, the inspection VPC diverts traffic between the enterprise router and the firewall.
