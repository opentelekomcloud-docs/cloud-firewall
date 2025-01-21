:original_name: cfw_01_0200.html

.. _cfw_01_0200:

Attack Defense Overview
=======================

CFW can defend against network attacks and virus files. You are advised to set **Protection Mode** to **Intercept** in a timely manner.

Prerequisites
-------------

At least one type of traffic protection has been enabled.

-  For details about how to enable EIP traffic protection, see :ref:`Enabling Internet Border Traffic Protection <cfw_01_0031>`.
-  For details about how to enable VPC traffic protection, see :ref:`Enabling VPC Border Traffic Protection <cfw_01_0078>`.

.. _cfw_01_0200__section19642352202214:

Defense Against Network Attacks and Virus Files
-----------------------------------------------

The following methods can be used:

-  IPS provides you with basic protection functions, and, with many years of attack defense experience, it detects and defends against a wide range of common network attacks and effectively protects your assets.

   -  IPS provides four protection modes. For details about how to configure it, see :ref:`Adjusting the IPS Protection Mode to Block Network Attacks <cfw_01_0032__section385820543273>`.

      -  **Observe**: Attacks are detected and recorded in logs but are not intercepted.
      -  **Intercept**: Attacks and abnormal IP address access are automatically intercepted.

         -  **Intercept mode - loose**: The protection granularity is coarse. In this mode, only attacks with high threat and high certainty are blocked.
         -  **Intercept mode - moderate**: The protection granularity is medium. This mode meets protection requirements in most scenarios.
         -  **Intercept mode - strict**: The protection granularity is fine-grained, and all attack requests are intercepted.

   -  IPS provides multiple types of rule libraries. For details, see :ref:`Table 1 <cfw_01_0200__table1655118365215>`. Different rules are enabled for different interception modes. For details, see :ref:`Default Actions of Rule Groups in Different Protection Modes <cfw_01_0168__section875111419156>`.

      .. _cfw_01_0200__table1655118365215:

      .. table:: **Table 1** Intrusion prevention rule libraries

         +-------------------------------------------------------------------+------------------------------------------------------------------------------------------------------------------------------------------------------------------------+----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+-----------------------------------------------------------------------------------------------------------------------------------------------------------+
         | Function                                                          | Description                                                                                                                                                            | Check Type                                                                                                                                                                       | Configuration Method                                                                                                                                      |
         +===================================================================+========================================================================================================================================================================+==================================================================================================================================================================================+===========================================================================================================================================================+
         | Basic defense                                                     | A built-in rule library. It covers common network attacks and provides basic protection capabilities for your assets.                                                  | -  Scan for threats and scan vulnerabilities.                                                                                                                                    | For details about how to view and modify rule library settings, see :ref:`Modifying the Protection Action of an Intrusion Prevention Rule <cfw_01_0168>`. |
         |                                                                   |                                                                                                                                                                        | -  Check whether traffic contains phishing, Trojans, worms, hacker tools, spyware, password attacks, vulnerability attacks, SQL injection attacks, XSS attacks, and web attacks. |                                                                                                                                                           |
         |                                                                   |                                                                                                                                                                        | -  Checks whether there are protocol anomalies, buffer overflow, access control, suspicious DNS activities, and other suspicious behaviors in traffic.                           |                                                                                                                                                           |
         +-------------------------------------------------------------------+------------------------------------------------------------------------------------------------------------------------------------------------------------------------+----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+-----------------------------------------------------------------------------------------------------------------------------------------------------------+
         | Virtual patch                                                     | Hot patches are provided for IPS at the network layer to intercept high-risk remote attacks in real time and prevent service interruption during vulnerability fixing. |                                                                                                                                                                                  |                                                                                                                                                           |
         |                                                                   |                                                                                                                                                                        |                                                                                                                                                                                  |                                                                                                                                                           |
         |                                                                   | Updated rules are added to the virtual patch library first. You can determine whether to add the rules to the basic defense library.                                   |                                                                                                                                                                                  |                                                                                                                                                           |
         |                                                                   |                                                                                                                                                                        |                                                                                                                                                                                  |                                                                                                                                                           |
         |                                                                   | To add defense rules, enable this function to apply virtual patch rules. The protection action can be manually modified.                                               |                                                                                                                                                                                  |                                                                                                                                                           |
         +-------------------------------------------------------------------+------------------------------------------------------------------------------------------------------------------------------------------------------------------------+----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+-----------------------------------------------------------------------------------------------------------------------------------------------------------+
         | Custom IPS signature (supported only by the professional edition) | If the built-in rule library cannot meet your requirements, you can customize signature rules.                                                                         | The check types are the same as those of **Basic defense**.                                                                                                                      | For details, see :ref:`Customizing IPS Signatures <cfw_01_0188>`.                                                                                         |
         |                                                                   |                                                                                                                                                                        |                                                                                                                                                                                  |                                                                                                                                                           |
         |                                                                   |                                                                                                                                                                        | Signature rules of the HTTP, TCP, UDP, POP3, SMTP and FTP protocols can be added.                                                                                                |                                                                                                                                                           |
         +-------------------------------------------------------------------+------------------------------------------------------------------------------------------------------------------------------------------------------------------------+----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+-----------------------------------------------------------------------------------------------------------------------------------------------------------+

-  Sensitive directory scan can defend against scanning attacks on sensitive directories on cloud servers. For details, see :ref:`Enabling Sensitive Directory Scan Defense <cfw_01_0032__section61321527141315>`.

-  Reverse shell detection can defend against network attacks in reverse shell mode. For details, see :ref:`Enabling Reverse Shell Defense <cfw_01_0032__section17909527114711>`.

-  Antivirus can identify and process virus-infected files through virus feature detection to prevent data damage, permission change, and system breakdown caused by virus-infected files. HTTP, SMTP, POP3, FTP, IMAP4 and SMB protocols can be checked.

   For details about antivirus, see :ref:`Blocking Virus-infected Files <cfw_01_0195>`.

Protection Actions
------------------

-  **Observe**: The firewall records the traffic that matches the current rule in :ref:`Attack Event Logs <cfw_01_0139__section1131659192010>` and does not block the traffic.
-  **Intercept**: The firewall records the traffic that matches the current rule in :ref:`Attack Event Logs <cfw_01_0139__section1131659192010>` and blocks it.
-  **Disable**: The firewall does not log or block the traffic that matches the current rule.

References
----------

For details about the protection overview, see :ref:`Viewing Attack Defense Information on the Dashboard <cfw_01_0228>`. For details about logs, see :ref:`Attack Event Logs <cfw_01_0139__section1131659192010>`.
