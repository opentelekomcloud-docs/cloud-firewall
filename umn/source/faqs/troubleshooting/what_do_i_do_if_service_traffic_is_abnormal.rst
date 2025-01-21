:original_name: cfw_01_0248.html

.. _cfw_01_0248:

What Do I Do If Service Traffic is Abnormal?
============================================

This section describes how to rectify the fault if your service traffic is abnormal and may be interrupted by CFW.

Symptom
-------

Service traffic is abnormal. For example:

-  An EIP cannot access the Internet.
-  A server cannot be accessed.

Troubleshooting Methods
-----------------------


.. figure:: /_static/images/en-us_image_0000001922057320.png
   :alt: **Figure 1** Procedure of checking traffic exceptions

   **Figure 1** Procedure of checking traffic exceptions

.. _cfw_01_0248__table141256121471:

.. table:: **Table 1** Procedure of checking traffic exceptions

   +-----+-----------------------------------------+----------------------------------------------------------------------------------------------------+
   | No. | Possible Cause                          | Solution                                                                                           |
   +=====+=========================================+====================================================================================================+
   | 1   | Traffic interruption not caused by CFW  | See :ref:`Cause 1: Traffic Interruption Not Caused by CFW <cfw_01_0248__section14214829162714>`.   |
   +-----+-----------------------------------------+----------------------------------------------------------------------------------------------------+
   | 2   | Traffic blocked by protection policies  | See :ref:`Cause 2: Traffic Blocked by Protection Policies <cfw_01_0248__section1085613222011>`.    |
   +-----+-----------------------------------------+----------------------------------------------------------------------------------------------------+
   | 3   | Traffic blocked by intrusion prevention | See :ref:`Cause 3: Traffic Blocked by Intrusion Prevention <cfw_01_0248__section113161327123210>`. |
   +-----+-----------------------------------------+----------------------------------------------------------------------------------------------------+

.. _cfw_01_0248__section14214829162714:

Cause 1: Traffic Interruption Not Caused by CFW
-----------------------------------------------

You can disable protection on the CFW console and observe the service status. If the service does not recover, it indicates the traffic interruption was not caused by CFW.

To disable protection, perform the following steps:

-  EIP traffic fault: Disable the CFW protection in EIPs whose services are interrupted. For details, see :ref:`Disabling EIP Protection <cfw_01_0031__section559382018485>`.
-  SNAT or inter-VPC access failure: Disable the VPC border firewall. For details, see :ref:`Enabling or Disabling a VPC Border Firewall <cfw_01_0205>`.

If problem persists, refer to the following common fault causes:

-  Network fault: The route configuration is incorrect, or the NE is faulty.
-  Policy-based interception: Interception caused by incorrect configurations of other security services, network ACLs, or security groups.

.. _cfw_01_0248__section1085613222011:

Cause 2: Traffic Blocked by Protection Policies
-----------------------------------------------

Traffic is blocked probably because a blocking rule is configured in the access control policy, or the normal services are blacklisted. In this case, CFW blocks related sessions, causing service loss.

You can take the following measures:

In the :ref:`Access Control Logs <cfw_01_0139__section8485135919336>` tab, search for logs about the blocked IP address or domain name.

-  If no records are found, see cause 3 in :ref:`Table 1 <cfw_01_0248__table141256121471>`.
-  If a record is found, click the **Rule** column to go to the matched blocking policy.

   -  If normal services are blacklisted, you can:

      -  Delete the blacklist policy.
      -  Add a whitelist policy for the IP address/domain name. (The whitelist takes precedence over the blacklist. After the whitelist policy is added, the blacklist policy becomes invalid and the traffic is directly permitted.)

   -  If the traffic is blocked by a blocking rule, you can:

      -  Find the blocking rule of the IP address or domain name in the access control rule list and disable the policy.
      -  Modify the matching condition of the blocking policy and remove the IP address or domain name information.
      -  Add a protection rule whose **Action** is **Allow** and **Priority** is **Pin on top**. For details, see :ref:`Adding Protection Rules to Block or Allow Traffic <cfw_01_0030>`.

**Case**

Handling process: Detect a fault -> Disable protection -> View logs -> Modify a policy -> Restore protection -> Confirm logs

The network O&M personnel of a company found that an ECS cannot access the Internet through the bound EIP **xx.xx.xx.126**.

The firewall administrator took the following measures:

#. To ensure that the IP address can be used for external communication during fault locating, the firewall administrator logged in to the CFW console, and chose **Assets** > **EIPs**, and disables protection for the EIP.

   During the firewall is disabled, the traffic of the EIP is not processed and related logs are not displayed.


   .. figure:: /_static/images/en-us_image_0000001922291358.png
      :alt: **Figure 2** EIPs

      **Figure 2** EIPs

#. The administrator chose **Log Audit** > **Log Query** and clicked the **Access Control Logs** tab. He searched for the blocking logs of the access source IP address **xx.xx.xx.126**. A blocking rule named **Block-Malicious-Outreach** was found, and this rule blocked the traffic from the attack source IP address to the Internet.


   .. figure:: /_static/images/en-us_image_0000001950170221.png
      :alt: **Figure 3** Filtering access control logs

      **Figure 3** Filtering access control logs

#. The administrator searched for "Source: xx.xx.xx.126; Action: Block; Direction: Outbound; Status: Enabled" in the access control policy list. Three available policies that contain the IP address were found.

   The policy contained the **Block-Malicious-Outreach** blocking rule. According to the value of the **Hits** column, a large number of sessions have been blocked.

   .. _cfw_01_0248__fig886815536237:

   .. figure:: /_static/images/en-us_image_0000001922451014.png
      :alt: **Figure 4** Searching for a protection rule

      **Figure 4** Searching for a protection rule

   .. caution::

      According to :ref:`Figure 4 <cfw_01_0248__fig886815536237>`, there were three valid rules whose source IP addresses contain **xx.xx.xx.126**, including **Block-xxx-com** (with the highest priority), **Block-Malicious-Outreach**, and **Allow-Asia** (with the lowest priority). Besides the blocking rule **Block-Malicious-Outreach**, the administrator checked whether the two other two rules may intercept normal services.

   Finally, it is found that the EIP accessed suspicious IP addresses so that an administrator configured a blocking rule it, but the configured destination was incorrect. As a result, all external traffic is blocked by mistake (see the second protection rule in :ref:`Figure 4 <cfw_01_0248__fig886815536237>`).

#. The administrator changed the destination address to a specific IP address that needs to be blocked, and enabled protection for the EIP on the **Assets** > **EIPs** page of the CFW console. After protection was restored, the traffic of the EIP was normally forwarded by CFW.

#. The administrator viewed the external connection logs related to the IP address in the traffic logs and confirmed that the service was restored.

.. _cfw_01_0248__section113161327123210:

Cause 3: Traffic Blocked by Intrusion Prevention
------------------------------------------------

The protection mode of intrusion prevention functions, such as IPS, is too strict, blocking normal traffic.

You can take the following measures:

In the :ref:`Attack Event Logs <cfw_01_0139__section1131659192010>` tab, search for logs about the blocked IP address or domain name.

-  If no records are found, .
-  If a record is found, perform either of the following operations:

   -  Copy the rule ID. In the corresponding module (such as IPS), set the protection mode of the rule with that ID to **Observe**. For details about the intrusion prevention module, see :ref:`Blocking Network Attacks <cfw_01_0032>`.
   -  Add the IP addresses that do not need to be protected by CFW to the whitelist. For details about how to configure the whitelist, see :ref:`Managing the Blacklist and the Whitelist <cfw_01_0035>`.

**Case**

Handling process: Detect a fault -> Change the protection status -> View logs -> Confirm services -> Modify the policy -> Restore the protection status -> Confirm logs

The O&M personnel of a company found that a service on the server whose IP address was **xx.xx.xx.99** cannot be accessed. It was suspected that the service was blocked by the firewall.

The firewall administrator took the following measures:

#. To quickly recover the service, the administrator logged in to the CFW console, choose **Attack Defense** > **Intrusion Prevention**, and changed the protection mode from **Intercept mode - strict** to **Observe**.

   During this period, the firewall did not intercept attack traffic but only logged the attack traffic.

#. The administrator chose **Log Audit** > **Log Query** and clicked the **Attack Event Logs** tab. The logs about the access to the destination IP address **xx.xx.xx.99** were displayed. The IPS rule whose ID was 334841 blocked the traffic.


   .. figure:: /_static/images/en-us_image_0000001922291366.png
      :alt: **Figure 5** Filtering attack event logs

      **Figure 5** Filtering attack event logs

#. The administrator clicked **Details** in the **Operation** column, clicked **Payload Content** in the display page, and created a packet capture task to verify that the service is normal. The administrator searched for the rule whose ID is 334841 from the list on the **Basic Protection** tab page by referring to :ref:`Modifying the Protection Action of an Intrusion Prevention Rule <cfw_01_0168>`.


   .. figure:: /_static/images/en-us_image_0000001950170229.png
      :alt: **Figure 6** Rule 334841

      **Figure 6** Rule 334841

#. The administrator clicked **Observe** in the **Operation** column. This rule did not block the traffic matching the signature but only logged the traffic.

#. The administrator set the protection mode to **Intercept mode - strict** and went to the **Basic Protection** tab to confirm that the **Current Status** of the rule 334841 was still **Observe**.

#. In the **Attack Event Logs** tab, after the service session matched the rule, the **Action** of the log was **Allow**. The service was restored.

Submitting a Service Ticket
---------------------------

If the preceding methods cannot solve your problem, .
