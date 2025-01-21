:original_name: cfw_01_0139.html

.. _cfw_01_0139:

Querying Logs
=============

CFW allows you to query logs generated within the last seven days. The following types of logs are available:

-  Attack event log: Events detected by attack defense functions, such as IPS, are recorded. You can modify the protection action if traffic is improperly blocked. For details, see :ref:`Modifying the Protection Action of an Intrusion Prevention Rule <cfw_01_0168>`. For details about how to modify the protection action of antivirus, see :ref:`Modifying the Virus Defense Action for Better Protection Effect <cfw_01_0195__section115051117231>`.
-  Access control logs: All traffic that matches the access control policies are recorded. For details about how to modify a protection rule, see :ref:`Managing Protection Rules <cfw_01_0061>`. For details about how to modify the blacklist or whitelist, see :ref:`Editing the Blacklist or Whitelist <cfw_01_0035__section510452611127>`.
-  Traffic logs: All traffic passing through the firewall is recorded.

Constraints
-----------

-  Logs can be stored for up to seven days.
-  For each type of logs, up to 1000 records can be viewed, and up to 100,000 records can be exported.
-  Traffic logs are collected based on sessions. Data about a connection is not reported until connection is terminated.

.. _cfw_01_0139__section1131659192010:

Attack Event Logs
-----------------

#. Log in to the management console.

#. In the navigation pane on the left, click |image1| and choose **Security** > **Cloud Firewall**. The **Dashboard** page will be displayed.

#. (Optional) Switch to another firewall instance: Select a firewall from the drop-down list in the upper left corner of the page.

#. In the navigation pane, choose **Log Audit** > **Log Query**. The **Attack Event Logs** tab page is displayed. You can view details about attack events in the past week.

   .. _cfw_01_0139__table1131654116506:

   .. table:: **Table 1** Attack event log parameters

      +-----------------------------------+----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
      | Parameter                         | Description                                                                                                                                                                                                                      |
      +===================================+==================================================================================================================================================================================================================================+
      | Time                              | Time when an attack occurred.                                                                                                                                                                                                    |
      +-----------------------------------+----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
      | Attack Type                       | Type of the attack event, including IMAP, DNS, FTP, HTTP, POP3, TCP, and UDP.                                                                                                                                                    |
      +-----------------------------------+----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
      | Risk Level                        | It can be **Critical**, **High**, **Medium**, or **Low**.                                                                                                                                                                        |
      +-----------------------------------+----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
      | Rule ID                           | Rule ID                                                                                                                                                                                                                          |
      +-----------------------------------+----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
      | Rule Name                         | Matched rule in the library.                                                                                                                                                                                                     |
      +-----------------------------------+----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
      | Source IP Address                 | Source IP address of an attack event.                                                                                                                                                                                            |
      +-----------------------------------+----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
      | Tags                              | IP address type identifier.                                                                                                                                                                                                      |
      |                                   |                                                                                                                                                                                                                                  |
      |                                   | -  Other tags: IP addresses that are not WAF back-to-source IP addresses. No special actions required.                                                                                                                           |
      |                                   |                                                                                                                                                                                                                                  |
      |                                   | -  **WAF back-to-source IP addresses**: **Source IP Address** is a WAF back-to-source IP address. If the **Action** of this record is **Block**, **Block IP**, or **Discard**, you need to manually set the action to **Allow**. |
      |                                   |                                                                                                                                                                                                                                  |
      |                                   |    Operation: Find the rule based on its ID. In the **Operation** column of the rule, click **Observe**.                                                                                                                         |
      +-----------------------------------+----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
      | Source Country/Region             | Geographical location of the attack source IP address.                                                                                                                                                                           |
      +-----------------------------------+----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
      | Source Port                       | Source port of an attack.                                                                                                                                                                                                        |
      +-----------------------------------+----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
      | Destination IP Address            | Attacked IP address.                                                                                                                                                                                                             |
      +-----------------------------------+----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
      | Destination Country/Region        | Geographical location of the attack target IP address.                                                                                                                                                                           |
      +-----------------------------------+----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
      | Destination Port                  | Destination port of an attack.                                                                                                                                                                                                   |
      +-----------------------------------+----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
      | Protocol                          | Protocol type of an attack.                                                                                                                                                                                                      |
      +-----------------------------------+----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
      | Application                       | Application type of an attack.                                                                                                                                                                                                   |
      +-----------------------------------+----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
      | Direction                         | It can be outbound or inbound.                                                                                                                                                                                                   |
      +-----------------------------------+----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
      | Action                            | Action of the firewall. It can be:                                                                                                                                                                                               |
      |                                   |                                                                                                                                                                                                                                  |
      |                                   | -  **Allow**                                                                                                                                                                                                                     |
      |                                   | -  **Block**                                                                                                                                                                                                                     |
      |                                   | -  **Block IP**                                                                                                                                                                                                                  |
      |                                   | -  **Discard**                                                                                                                                                                                                                   |
      +-----------------------------------+----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
      | Operation                         | You can click **View** to view the basic information and attack payload of an event.                                                                                                                                             |
      +-----------------------------------+----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+

.. _cfw_01_0139__section8485135919336:

Access Control Logs
-------------------

#. Log in to the management console.

#. In the navigation pane on the left, click |image2| and choose **Security** > **Cloud Firewall**. The **Dashboard** page will be displayed.

#. (Optional) Switch to another firewall instance: Select a firewall from the drop-down list in the upper left corner of the page.

#. In the navigation pane, choose **Log Audit** > **Log Query**. Click the **Access Control Logs** tab and check the traffic details in the past week. For details about how to modify the action taken on an IP address, see :ref:`Adding Protection Rules to Block or Allow Traffic <cfw_01_0030>` or :ref:`Adding Blacklist or Whitelist Items to Block or Allow Traffic <cfw_01_0065>`.

   .. _cfw_01_0139__table099515711343:

   .. table:: **Table 2** Access control log parameters

      +----------------------------+----------------------------------------------------------------------------------------------------------------+
      | Parameter                  | Description                                                                                                    |
      +============================+================================================================================================================+
      | Hit Time                   | Time of access.                                                                                                |
      +----------------------------+----------------------------------------------------------------------------------------------------------------+
      | Source IP Address          | Source IP address of the access.                                                                               |
      +----------------------------+----------------------------------------------------------------------------------------------------------------+
      | Source Country/Region      | Geographical location of the source IP address.                                                                |
      +----------------------------+----------------------------------------------------------------------------------------------------------------+
      | Source Port                | Source port for access control. It can be a single port or consecutive port groups (example: **80-443**).      |
      +----------------------------+----------------------------------------------------------------------------------------------------------------+
      | Destination IP Address     | Destination IP address.                                                                                        |
      +----------------------------+----------------------------------------------------------------------------------------------------------------+
      | Destination Host           | Destination domain name                                                                                        |
      +----------------------------+----------------------------------------------------------------------------------------------------------------+
      | Destination Country/Region | Geographical location of the destination IP address.                                                           |
      +----------------------------+----------------------------------------------------------------------------------------------------------------+
      | Destination Port           | Destination port for access control. It can be a single port or consecutive port groups (example: **80-443**). |
      +----------------------------+----------------------------------------------------------------------------------------------------------------+
      | Protocol                   | Protocol type for access control.                                                                              |
      +----------------------------+----------------------------------------------------------------------------------------------------------------+
      | Action                     | Action taken on an event. It can be **Observe**, **Block**, or **Allow**.                                      |
      +----------------------------+----------------------------------------------------------------------------------------------------------------+
      | Rule                       | Type of an access control rule. It can be a blacklist or whitelist.                                            |
      +----------------------------+----------------------------------------------------------------------------------------------------------------+

.. _cfw_01_0139__section8581131111344:

Traffic Logs
------------

#. Log in to the management console.
#. In the navigation pane on the left, click |image3| and choose **Security** > **Cloud Firewall**. The **Dashboard** page will be displayed.
#. (Optional) Switch to another firewall instance: Select a firewall from the drop-down list in the upper left corner of the page.
#. In the navigation pane, choose **Log Audit** > **Log Query**. Click the **Traffic Log** tab to view the number of traffic bytes and packets in the past week.

   .. table:: **Table 3** Traffic log parameters

      +----------------------------+--------------------------------------------------------+
      | Parameter                  | Description                                            |
      +============================+========================================================+
      | Start Time                 | Time when traffic protection started.                  |
      +----------------------------+--------------------------------------------------------+
      | End Time                   | Time when traffic protection ended.                    |
      +----------------------------+--------------------------------------------------------+
      | Source IP Address          | Source IP address of the traffic                       |
      +----------------------------+--------------------------------------------------------+
      | Source Country/Region      | Geographical location of the access source IP address. |
      +----------------------------+--------------------------------------------------------+
      | Source Port                | Source port of the traffic.                            |
      +----------------------------+--------------------------------------------------------+
      | Destination IP Address     | Destination IP address.                                |
      +----------------------------+--------------------------------------------------------+
      | Destination Country/Region | Geographical location of the destination IP address.   |
      +----------------------------+--------------------------------------------------------+
      | Destination Port           | Destination port of the traffic.                       |
      +----------------------------+--------------------------------------------------------+
      | Protocol                   | Protocol type of the traffic.                          |
      +----------------------------+--------------------------------------------------------+
      | Stream Size                | Total number of bytes of protected traffic.            |
      +----------------------------+--------------------------------------------------------+
      | Stream Packets             | Total number of protected packets.                     |
      +----------------------------+--------------------------------------------------------+

Related Operations
------------------

Exporting logs: Click |image4| in the upper right corner to export the logs in the list.

Follow-up Operations
--------------------

-  If improper blocking is recorded in access control logs, check whether your protection rules, blacklist, and whitelist configurations are correct.
-  If improper blocking is recorded in attack event logs, your normal workloads may be blocked by IPS.

   -  If the traffic from an IP address is improperly blocked, add it to the whitelist.
   -  If the traffic from multiple IP addresses is blocked, check logs to see whether it is blocked by a single rule or multiple rules.

      -  Blocked by a single rule: Modify the protection action of the rule. For details, see :ref:`Modifying the Action of a Basic Protection Rule <cfw_01_0168__section204771329204015>`.
      -  Blocked by multiple rules: Modify the protection mode. For details, see :ref:`Adjusting the IPS Protection Mode to Block Network Attacks <cfw_01_0032__section385820543273>`.

.. |image1| image:: /_static/images/en-us_image_0000001259322747.png
.. |image2| image:: /_static/images/en-us_image_0000001259322747.png
.. |image3| image:: /_static/images/en-us_image_0000001259322747.png
.. |image4| image:: /_static/images/en-us_image_0000001889194328.png
