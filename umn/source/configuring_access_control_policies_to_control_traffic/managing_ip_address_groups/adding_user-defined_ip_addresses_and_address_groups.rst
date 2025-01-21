:original_name: cfw_01_0068.html

.. _cfw_01_0068:

Adding User-defined IP Addresses and Address Groups
===================================================

An IP address group contains multiple IP addresses. An IP address group frees you from repeatedly modifying access rules and allows you to manage access rules in batch.

Constraints
-----------

-  A firewall instance can have up to 3800 IP address groups.
-  An IP address group can contain up to 640 IP addresses.
-  A firewall instance can contain up to 30,000 IP addresses.

Adding Custom Address Groups
----------------------------

#. Log in to the management console.

#. In the navigation pane on the left, click |image1| and choose **Security** > **Cloud Firewall**. The **Dashboard** page will be displayed.

#. (Optional) Switch to another firewall instance: Select a firewall from the drop-down list in the upper left corner of the page.

#. In the navigation pane, choose **Access Control** > **Object Groups**.

#. Click the **IP Address Groups** tab. Click **Add IP Address Group** and configure parameters on the **Add IP Address Group** slide-out panel. For more information, see :ref:`IP address group parameters <cfw_01_0068__table12707131818297>`.

   .. _cfw_01_0068__table12707131818297:

   .. table:: **Table 1** IP address group parameters

      +-----------------------------------+---------------------------------------------------------------------------------------------------------------------------------------------------------+
      | Parameter                         | Description                                                                                                                                             |
      +===================================+=========================================================================================================================================================+
      | IP Address Group Name             | Name of an IP address group.                                                                                                                            |
      +-----------------------------------+---------------------------------------------------------------------------------------------------------------------------------------------------------+
      | Description                       | Usage and application scenario of a rule                                                                                                                |
      +-----------------------------------+---------------------------------------------------------------------------------------------------------------------------------------------------------+
      | IP Addresses                      | Enter IP addresses and click **Parse** to add them to the IP address list.                                                                              |
      |                                   |                                                                                                                                                         |
      |                                   | The input can be:                                                                                                                                       |
      |                                   |                                                                                                                                                         |
      |                                   | -  A single IP address. Example: **192.168.10.5**                                                                                                       |
      |                                   | -  Address segment. Example: **192.168.2.0/24**                                                                                                         |
      |                                   | -  Consecutive IP addresses. Example: **192.168.0.2-192.168.0.10**                                                                                      |
      |                                   |                                                                                                                                                         |
      |                                   | -  Multiple IP addresses. Use commas (,), semicolons (;), line breaks, tab characters, or spaces to separate them. Example: 192.168.1.0,192.168.1.0/24. |
      +-----------------------------------+---------------------------------------------------------------------------------------------------------------------------------------------------------+

#. Confirm the information and click **OK**. The IP address group is added.

Adding an IP address to a user-defined address group
----------------------------------------------------

#. Log in to the management console.
#. In the navigation pane on the left, click |image2| and choose **Security** > **Cloud Firewall**. The **Dashboard** page will be displayed.
#. (Optional) Switch to another firewall instance: Select a firewall from the drop-down list in the upper left corner of the page.
#. In the navigation pane, choose **Access Control** > **Object Groups**.
#. Click the name of an IP address group on the **IP Address Groups** tab. The **IP Address Group Details** dialog box is displayed..
#. Click **Add IP Address**. The **Add IP Address** slide-out panel is displayed.

   -  To add IP addresses in batches, enter the IP addresses in the text box and click **Parse**.
   -  To add a single IP address, click **Add**, and enter the IP address and description.

#. Confirm the information and click **OK**.

Related Operations
------------------

-  Exporting IP address groups: Click **Export** above the list and select a data range.
-  Batch deleting IP addresses: In the **IP Address Group Details** slide-out panel, select IP addresses and click **Delete** above the list.

Follow-up Operations
--------------------

An IP address group takes effect only after it is set in a protection rule. For more information, see :ref:`Adding Protection Rules to Block or Allow Traffic <cfw_01_0030>`.

.. |image1| image:: /_static/images/en-us_image_0000001259322747.png
.. |image2| image:: /_static/images/en-us_image_0000001259322747.png
