:original_name: cfw_01_0262.html

.. _cfw_01_0262:

Access Control Policy Overview
==============================

After protection is enabled, CFW access control policies allow all traffic by default. Proper access control policies help you implement refined management and control on traffic between internal servers and the Internet, prevent internal threats from spreading, and enhance in-depth security.

Access Control Policy Types
---------------------------

Access control policies are classified into protection rules and blacklist/whitelist. :ref:`Differences between protection rules and blacklist/whitelist <cfw_01_0262__table1185931821515>` shows more details. If traffic hits a policy, the action of the policy will be taken.

.. _cfw_01_0262__table1185931821515:

.. table:: **Table 1** Differences between protection rules and blacklist/whitelist

   +------------------+----------------------------------------+-----------------------+-------------------------------------------------------------------------------------------------------------------------------------+------------------------------------------------------------------------------------+
   | Type             | Protected Object                       | Network Type          | Action                                                                                                                              | Configuration Method                                                               |
   +==================+========================================+=======================+=====================================================================================================================================+====================================================================================+
   | Protection rules | -  5-tuple                             | -  EIP                | -  If **Block** is selected, traffic will be blocked.                                                                               | :ref:`Adding Protection Rules to Block or Allow Traffic <cfw_01_0030>`             |
   |                  | -  IP address groups                   | -  Private IP address | -  If **Allow** is selected, traffic will be allowed by protection rules and then checked by the intrusion prevention system (IPS). |                                                                                    |
   |                  | -  Geographical locations              |                       |                                                                                                                                     |                                                                                    |
   |                  | -  Domain names and domain name groups |                       |                                                                                                                                     |                                                                                    |
   +------------------+----------------------------------------+-----------------------+-------------------------------------------------------------------------------------------------------------------------------------+------------------------------------------------------------------------------------+
   | Blacklist        | -  5-tuple                             |                       | Traffic is blocked directly.                                                                                                        | :ref:`Adding Blacklist or Whitelist Items to Block or Allow Traffic <cfw_01_0065>` |
   |                  | -  IP address groups                   |                       |                                                                                                                                     |                                                                                    |
   +------------------+----------------------------------------+-----------------------+-------------------------------------------------------------------------------------------------------------------------------------+------------------------------------------------------------------------------------+
   | Whitelist        |                                        |                       | Traffic is allowed by CFW and not checked by other functions.                                                                       |                                                                                    |
   +------------------+----------------------------------------+-----------------------+-------------------------------------------------------------------------------------------------------------------------------------+------------------------------------------------------------------------------------+

Specification Limitations
-------------------------

To enable VPC border protection and NAT protection, use the CFW professional edition and enable :ref:`VPC firewall <cfw_01_0078>` protection.

Precautions for Configuring a Blocking Policy
---------------------------------------------

The precautions for configuring a protection rule or a blacklist item for blocking IP addresses are as follows:

#. You are advised to preferentially configure specific IP addresses (for example, 192.168.10.5) to reduce network segment configurations and avoid improper blocking.
#. Exercise caution when configuring protection rules to block reverse proxy IP addresses, such as the WAF back-to-source IP addresses. You are advised to configure protection rules or whitelist to permit reverse proxy IP addresses.
#. Blocking forward proxy IP addresses (such as company egress IP addresses) can have a large impact. Exercise caution when configuring protection rules to block forward proxy IP addresses.
#. When configuring region protection, take possible EIP changes into consideration.

Wildcard Rule
-------------

+-------------------------------------------+-----------------------+---------------------------------------------------------------------------------+
| Parameter                                 | Input                 | Description                                                                     |
+===========================================+=======================+=================================================================================+
| Source/Destination                        | 0.0.0.0/0             | All IP addresses                                                                |
+-------------------------------------------+-----------------------+---------------------------------------------------------------------------------+
| Domain name                               | www.example.com       | Domain name www.example.com                                                     |
+-------------------------------------------+-----------------------+---------------------------------------------------------------------------------+
| Domain name                               | \*.example.com        | All domain names ending with **example.com**, for example, **test.example.com** |
+-------------------------------------------+-----------------------+---------------------------------------------------------------------------------+
| Service - Source port or destination port | 1-65535               | All ports                                                                       |
+-------------------------------------------+-----------------------+---------------------------------------------------------------------------------+
| Service - Source port or destination port | 80-443                | All ports in the range 80 to 443                                                |
+-------------------------------------------+-----------------------+---------------------------------------------------------------------------------+
| Service - Source port or destination port | -  80                 | Ports 80 and 443                                                                |
|                                           | -  443                |                                                                                 |
+-------------------------------------------+-----------------------+---------------------------------------------------------------------------------+

References
----------

-  For details about how to add a single rule to protect traffic, see :ref:`Adding Protection Rules to Block or Allow Traffic <cfw_01_0030>`. For details about how to add a single blacklist or whitelist item to protect traffic, see :ref:`Adding Blacklist or Whitelist Items to Block or Allow Traffic <cfw_01_0065>`.
-  For details about how to add protection policies in batches, see :ref:`Importing and Exporting Protection Policies <cfw_01_0129>`.
-  Follow-up operations after adding a policy:

   -  Policy hits: For details about the protection overview, see :ref:`Viewing Protection Information Using the Policy Assistant <cfw_01_0226>`. For details about logs, see :ref:`Access Control Logs <cfw_01_0139__section8485135919336>`.
   -  For details about the traffic trend and statistics, see :ref:`Viewing Traffic Statistics <cfw_01_0011>`. For details about traffic records, see :ref:`Traffic Logs <cfw_01_0139__section8581131111344>`.
