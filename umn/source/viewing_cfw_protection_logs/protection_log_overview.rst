:original_name: cfw_01_0278.html

.. _cfw_01_0278:

Protection Log Overview
=======================

This section describes the following content:

-  The two log storage modes provided by CFW. For details, see :ref:`Log Storage Mode <cfw_01_0278__section863819309356>`.
-  Supported log types. For details, see :ref:`Log Types <cfw_01_0278__section157305387362>`.
-  How to handle improper blocking recorded in logs. For details, see :ref:`Handling Improper Blocking <cfw_01_0278__section6537461243>`.
-  For details about how to dump logs to LTS, see :ref:`Log Management Description <cfw_01_0278__section757611445583>`.

.. _cfw_01_0278__section863819309356:

Log Storage Mode
----------------

+----------------+------------------+-----------------------------+------------------------------------------------------------------------------------------------------------------------------+--------------------------------------------+
| Function       | Storage Duration | Billing Mode                | Access Mode                                                                                                                  | Log Field Description                      |
+================+==================+=============================+==============================================================================================================================+============================================+
| Log query      | 7 days           | Free                        | Automatic access                                                                                                             | :ref:`Querying Logs <cfw_01_0139>`         |
+----------------+------------------+-----------------------------+------------------------------------------------------------------------------------------------------------------------------+--------------------------------------------+
| Log management | 1 to 365 days    | Separate billing by traffic | You need to manually connect to LTS. For details, see :ref:`Configuring Logs <cfw_01_0141>`.                                 | :ref:`Log Field Description <cfw_01_0147>` |
|                |                  |                             |                                                                                                                              |                                            |
|                |                  |                             | For details about how to use the LTS log function, see :ref:`Log Management Description <cfw_01_0278__section757611445583>`. |                                            |
+----------------+------------------+-----------------------------+------------------------------------------------------------------------------------------------------------------------------+--------------------------------------------+

.. _cfw_01_0278__section157305387362:

Log Types
---------

The following types of logs are provided:

-  Attack event log: Events detected by attack defense functions, such as IPS, are recorded. You can modify the protection action if traffic is improperly blocked. For details, see :ref:`Modifying the Protection Action of an Intrusion Prevention Rule <cfw_01_0168>`. For details about how to modify the protection action of antivirus, see :ref:`Modifying the Virus Defense Action for Better Protection Effect <cfw_01_0195__section115051117231>`.
-  Access control logs: All traffic that matches the access control policies are recorded. For details about how to modify a protection rule, see :ref:`Managing Protection Rules <cfw_01_0061>`. For details about how to modify the blacklist or whitelist, see :ref:`Editing the Blacklist or Whitelist <cfw_01_0035__section510452611127>`.
-  Traffic logs: All traffic passing through the firewall is recorded.

.. _cfw_01_0278__section6537461243:

Handling Improper Blocking
--------------------------

-  If improper blocking is recorded in access control logs, check whether your protection rules, blacklist, and whitelist configurations are correct.
-  If improper blocking is recorded in attack event logs, your normal workloads may be blocked by IPS.

   -  If the traffic from an IP address is improperly blocked, add it to the whitelist.
   -  If the traffic from multiple IP addresses is blocked, check logs to see whether it is blocked by a single rule or multiple rules.

      -  Blocked by a single rule: Modify the protection action of the rule. For details, see :ref:`Modifying the Action of a Basic Protection Rule <cfw_01_0168__section204771329204015>`.
      -  Blocked by multiple rules: Modify the protection mode. For details, see :ref:`Adjusting the IPS Protection Mode to Block Network Attacks <cfw_01_0032__section385820543273>`.

.. _cfw_01_0278__section757611445583:

Log Management Description
--------------------------

+--------------------------------+---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+--------------------------------------------------------------------------------------------------------------------------------+
| Function                       | Description                                                                                                                                                                                             | Configuration Method                                                                                                           |
+================================+=========================================================================================================================================================================================================+================================================================================================================================+
| Configuring logs               | Interconnect logs with LTS and create a log group and a log stream.                                                                                                                                     | :ref:`Configuring Logs <cfw_01_0141>`                                                                                          |
+--------------------------------+---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+--------------------------------------------------------------------------------------------------------------------------------+
| Modifying log storage duration | (Optional) By default, logs are stored for seven days. You can set the storage duration in the range 1 to 365 days.                                                                                     | :ref:`Changing the Log Storage Duration <cfw_01_0142>`                                                                         |
+--------------------------------+---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+--------------------------------------------------------------------------------------------------------------------------------+
| Log search and analysis        | (Optional) Use proper log collection functions, efficient search methods, and professional analysis tools to implement comprehensive monitoring and refined management of your system and applications. | For details, see `Log Search and View <https://docs.otc.t-systems.com/log-tank-service/umn/log_search_and_view/index.html>`__. |
+--------------------------------+---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+--------------------------------------------------------------------------------------------------------------------------------+
| Viewing log fields             | Learn the meaning of fields in a log.                                                                                                                                                                   | :ref:`Log Field Description <cfw_01_0147>`                                                                                     |
+--------------------------------+---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+--------------------------------------------------------------------------------------------------------------------------------+

References
----------

-  For details about the protection overview of access control policies, see :ref:`Viewing Protection Information Using the Policy Assistant <cfw_01_0226>`.
-  For details about the traffic defense overview and trend, see :ref:`Viewing Traffic Statistics <cfw_01_0011>`.
-  For details about the overall network attack defense, see :ref:`Viewing Attack Defense Information on the Dashboard <cfw_01_0228>`.
