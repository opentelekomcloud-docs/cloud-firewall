:original_name: cfw_01_0239.html

.. _cfw_01_0239:

Viewing a Predefined Address Group
==================================

CFW provides you with predefined address groups, including **NAT64 Address Set** and **WAF_Back-to-Source_IP_Addresses**. You are advised to allow access from both the address groups.

-  **NAT64 Address Set**: If the IPv6 EIP function is enabled, CFW will convert a source IPv6 address to an IP address in this address group.

   .. note::

      If you have enabled the IPv6 EIP function, you are advised to allow traffic from **NAT64 Address Set**.

-  **WAF_Back-to-Source_IP_Addresses**: provides back-to-source IP addresses of WAF in cloud mode.

   .. caution::

      -  If these groups are specified in a protection rule and the back-to-source IP address changes, you do not need to manually update the rule. The firewall automatically updates the IP address in the address group every day.
      -  If these groups are added to the blacklist or whitelist, and the back-to-source IP address changes, you need to manually update the blacklist or whitelist.

You can only view predefined address groups, but cannot add IP addresses to it, or modify or delete it.


Viewing a Predefined Address Group
----------------------------------

#. Log in to the management console.
#. In the navigation pane on the left, click |image1| and choose **Security** > **Cloud Firewall**. The **Dashboard** page will be displayed.
#. (Optional) Switch to another firewall instance: Select a firewall from the drop-down list in the upper left corner of the page.
#. In the navigation pane, choose **Access Control** > **Object Groups**.
#. Click the **IP Address Groups** tab. Click the **Pre-defined Address Groups** tab and click the name of an address group. On the details page that is displayed, view the address group information.

.. |image1| image:: /_static/images/en-us_image_0000001259322747.png
