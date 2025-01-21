:original_name: cfw_01_0065.html

.. _cfw_01_0065:

Adding Blacklist or Whitelist Items to Block or Allow Traffic
=============================================================

After protection is enabled, CFW allows all traffic by default. You can configure the blacklist to block access requests from IP addresses or configure the whitelist to allow them.

This topic describes how to add a single blacklist or whitelist item. For details about how to add items in batches, see :ref:`Importing and Exporting Protection Policies <cfw_01_0129>`.

.. caution::

   If your IP address is a back-to-source WAF IP address, you are advised to configure a protection rule or the whitelist to allow its access. Exercise caution when configuring the blacklist, which may affect your services.

   -  For details about how to configure protection rules, see :ref:`Adding Protection Rules to Block or Allow Traffic <cfw_01_0030>`.

Specification Limitations
-------------------------

-  CFW supports up to 2,000 blacklist items and 2,000 whitelist items. If there are too many IP addresses to be specified, you can put them in an IP address group and select the IP address group when configuring protection rules.

   -  For details about how to add an IP address group, see :ref:`Adding User-defined IP Addresses and Address Groups <cfw_01_0068>`.
   -  For details about how to add a protection rule, see :ref:`Adding Protection Rules to Block or Allow Traffic <cfw_01_0030>`.

-  To protect private IP addresses, use the professional edition firewall and enable :ref:`VPC border firewall <cfw_01_0078>` protection.

Impact on the System
--------------------

-  CFW directly allows whitelisted IP addresses and segments and blocks blacklisted ones without checking. To check the access and traffic statistics of these IP addresses, search for them by following the instructions in :ref:`Querying Logs <cfw_01_0139>`.
-  When configuring a blacklist, if address translation or proxy is involved, evaluate the impact of blocking IP addresses with caution.


Adding Blacklist or Whitelist Items to Block or Allow Traffic
-------------------------------------------------------------

#. Log in to the management console.

#. In the navigation pane on the left, click |image1| and choose **Security** > **Cloud Firewall**. The **Dashboard** page will be displayed.

#. (Optional) Switch to another firewall instance: Select a firewall from the drop-down list in the upper left corner of the page.

#. In the navigation pane, choose **Access Control** > **Access Policies**. Click the tab of a protected object, and then click the **Blacklist** or **Whitelist** tab.

#. Click **Add**. Set the address direction, IP address, protocol type, and port number. For details, see :ref:`Table 1 <cfw_01_0065__table12707131818297>`.

   .. _cfw_01_0065__table12707131818297:

   .. table:: **Table 1** Blacklist and whitelist parameters

      +-----------------------------------+----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
      | Parameter                         | Description                                                                                                                                                                                                                |
      +===================================+============================================================================================================================================================================================================================+
      | Direction                         | You can select **Source** or **Destination**.                                                                                                                                                                              |
      |                                   |                                                                                                                                                                                                                            |
      |                                   | -  **Source**: The IP address or IP address group that sends data packets.                                                                                                                                                 |
      |                                   | -  **Destination**: The destination IP address or IP address group that receives data packets.                                                                                                                             |
      +-----------------------------------+----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
      | Protocol Type                     | Its value can be **TCP**, **UDP**, **ICMP**, or **Any**.                                                                                                                                                                   |
      +-----------------------------------+----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
      | Port                              | If **Protocol Type** is set to **TCP** or **UDP**, set the ports to be allowed or blocked.                                                                                                                                 |
      |                                   |                                                                                                                                                                                                                            |
      |                                   | .. note::                                                                                                                                                                                                                  |
      |                                   |                                                                                                                                                                                                                            |
      |                                   |    -  To specify all the ports of an IP address, set **Port** to **1-65535**.                                                                                                                                              |
      |                                   |    -  You can specify a single port. For example, to allow or block the access from port 22 of an IP address, set **Port** to **22**.                                                                                      |
      |                                   |    -  To set a port range, use a hyphen (-) between the starting and ending ports. For example, to allow or block the access from ports 80-443 of an IP address, set **Port** to **80-443**.                               |
      +-----------------------------------+----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
      | Description                       | Description of the blacklist or whitelist                                                                                                                                                                                  |
      +-----------------------------------+----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
      | IP Addresses                      | -  User-defined IP address: Enter one or more IP addresses in the text box and click **Parse** to add the IP addresses to the list.                                                                                        |
      |                                   | -  Pre-defined address group: Click **Add Pre-defined IP Address Group**. In the dialog box that is displayed, select an address group. For more information, see :ref:`Viewing a Predefined Address Group <cfw_01_0239>`. |
      |                                   |                                                                                                                                                                                                                            |
      |                                   |    .. caution::                                                                                                                                                                                                            |
      |                                   |                                                                                                                                                                                                                            |
      |                                   |       CAUTION:                                                                                                                                                                                                             |
      |                                   |       After **WAF_Back-to-Source_IP_Addresses** is added to the blacklist or whitelist, if a back-to-source IP address changes, you need to manually update it in the blacklist or whitelist.                              |
      +-----------------------------------+----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+

#. Click **OK**.

Related Operations
------------------

-  For details about how to edit and remove blacklist or whitelist items, see :ref:`Managing the Blacklist and the Whitelist <cfw_01_0035>`.
-  For details about how to add blacklist or whitelist items in batches, see :ref:`Importing and Exporting Protection Policies <cfw_01_0129>`.

.. |image1| image:: /_static/images/en-us_image_0000001259322747.png
