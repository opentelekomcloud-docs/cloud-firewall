:original_name: cfw_01_0035.html

.. _cfw_01_0035:

Managing the Blacklist and the Whitelist
========================================

This section describes how to edit and remove items in a blacklist or whitelist.

.. _cfw_01_0035__section510452611127:

Editing the Blacklist or Whitelist
----------------------------------

#. Log in to the management console.

#. In the navigation pane on the left, click |image1| and choose **Security** > **Cloud Firewall**. The **Dashboard** page will be displayed.

#. (Optional) Switch to another firewall instance: Select a firewall from the drop-down list in the upper left corner of the page.

#. In the navigation pane, choose **Access Control** > **Access Policies**. Click the tab of a protected object, and then click the **Blacklist** or **Whitelist** tab.

#. In the row containing the desired rule, click **Edit** in the **Operation** column.

   Modify parameters. For details, see :ref:`Table 1 <cfw_01_0035__table12707131818297>`.

   .. _cfw_01_0035__table12707131818297:

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

Removing a Blacklisted or Whitelisted Item
------------------------------------------

#. Log in to the management console.
#. In the navigation pane on the left, click |image2| and choose **Security** > **Cloud Firewall**. The **Dashboard** page will be displayed.
#. (Optional) Switch to another firewall instance: Select a firewall from the drop-down list in the upper left corner of the page.
#. In the navigation pane, choose **Access Control** > **Access Policies**. Click the tab of a protected object, and then click the **Blacklist** or **Whitelist** tab.
#. In the row of an IP address, click **Delete** in the **Operation** column.
#. In the displayed **Remove from Blacklist** or **Remove from Whitelist** dialog box, confirm the information, enter **DELETE**, and click **OK**.

   .. warning::

      Removed items cannot be restored. Exercise caution when performing this operation.

.. |image1| image:: /_static/images/en-us_image_0000001259322747.png
.. |image2| image:: /_static/images/en-us_image_0000001259322747.png
