:original_name: cfw_01_0031.html

.. _cfw_01_0031:

Enabling Internet Border Traffic Protection
===========================================

CFW protects Internet border traffic by protecting EIPs. After EIP protection is enabled, your service traffic will pass through CFW. By default, all traffic is allowed.

To use CFW to protect traffic, you also need to configure access control policies or enable IPS. For details about how to configure access control policies, see :ref:`Adding a Protection Rule <cfw_01_0030>`. For details about IPS, see :ref:`Configuring Intrusion Prevention Policies <cfw_01_0032>`.

Constraints
-----------

-  Currently, IPv6 addresses cannot be protected.
-  An EIP can only be protected by one firewall.
-  Only EIPs in the enterprise project to which the current account belongs can be protected.

Impacts on Services
-------------------

Enabling or disabling EIP protection does not interrupt services, ensuring smooth traffic switchover.

.. important::

   If a protection rule or blacklist has been configured to block all traffic before an EIP is protected, the rule or blacklist will take effect for the EIP when protection is enabled for it.

   -  For details about how to edit a protection rule, see :ref:`Managing Protection Rules <cfw_01_0061>`.
   -  For details about how to edit a blacklist, see :ref:`Managing the Blacklist and the Whitelist <cfw_01_0035>`.


Enabling Internet Border Traffic Protection
-------------------------------------------

#. Log in to the management console.
#. In the navigation pane on the left, click |image1| and choose **Security** > **Cloud Firewall**. The **Dashboard** page will be displayed.
#. (Optional) Switch to another firewall instance: Select a firewall from the drop-down list in the upper left corner of the page.
#. In the navigation pane, choose **Assets** > **EIPs**. The EIPs page is displayed. The EIP information is automatically updated to the list.

5. Enable EIP protection.

   -  Enable protection for a single EIP: In the row of the EIP, click **Enable Protection** in the **Operation** column.
   -  Enable protection for multiple EIPs: Select the EIPs that you want to enable protection and click **Enable Protection** above the list.

   .. important::

      -  Currently, IPv6 addresses cannot be protected.
      -  An EIP can only be protected by one firewall.
      -  Only EIPs in the enterprise project to which the current account belongs can be protected.

6. On the page that is displayed, check the information and click **Bind and Enable**. Then the **Protection Status** changes to **Protected**.

   .. note::

      After EIP protection is enabled, the default action of the access control policy is **Allow**.

.. _cfw_01_0031__section559382018485:

Related Operations
------------------

-  Disabling EIP protection

   -  To disable an EIP, click **Disable Protection** in the **Operation** column of the EIP.
   -  To disable multiple EIPs, select them and click **Disable Protection** above the table.

-  Enabling automatic protection for new EIPs: Enable **Auto Protect New EIP** above the list. Protection will be automatically enabled for new EIPs, and EIP traffic will pass through and be protected by the firewall.

Follow-up Operations
--------------------

After protection is enabled, all traffic is allowed by default. CFW will block traffic based on the policies you configure.

-  To implement traffic control, configure a protection policy. For details, see :ref:`Adding an Internet Boundary Protection Rule <cfw_01_0030__section8135741192619>` or :ref:`Adding Blacklist or Whitelist Items to Block or Allow Traffic <cfw_01_0065>`.

   -  Allow or block traffic based on protection rules.

      -  Traffic allowing rule: The allowed traffic will be checked by functions such as intrusion prevention system (IPS) and antivirus.
      -  Traffic blocking rule: Traffic will be directly blocked.

   -  Allow or block traffic based on the blacklist and whitelist:

      -  Whitelist: Traffic will be directly allowed without being checked by other functions.
      -  Blacklist: Traffic will be directly blocked.

-  For details about how to block network attacks, see :ref:`Blocking Network Attacks <cfw_01_0032>`.

.. |image1| image:: /_static/images/en-us_image_0000001259322747.png
