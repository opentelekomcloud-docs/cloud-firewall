:original_name: cfw_01_0070.html

.. _cfw_01_0070:

Adding a User-defined Service Group
===================================

A service group is a collection of services (protocols, source ports, and destination ports). A service group frees you from repeatedly modifying access rules and simplifies security group rule management.

Constraints
-----------

-  A service group can have up to 64 services.
-  A firewall instance can have up to 512 service groups.
-  A firewall instance can have up to 900 services.


Adding a User-defined Service Group
-----------------------------------

#. Log in to the management console.
#. In the navigation pane on the left, click |image1| and choose **Security** > **Cloud Firewall**. The **Dashboard** page will be displayed.
#. (Optional) Switch to another firewall instance: Select a firewall from the drop-down list in the upper left corner of the page.
#. In the navigation pane, choose **Access Control** > **Object Groups**.
#. Click the **Service Groups** tab. Click **Add Service Group** and configure parameters in the **Add Service Group** area. Enter the service group name and description.

   .. table:: **Table 1** Service group parameters

      +-----------------------------------+---------------------------------------------------------------------------------------------------------------------------------------------------------------+
      | Parameter                         | Description                                                                                                                                                   |
      +===================================+===============================================================================================================================================================+
      | Service Group Name                | Name of a service group                                                                                                                                       |
      +-----------------------------------+---------------------------------------------------------------------------------------------------------------------------------------------------------------+
      | Description                       | Usage and application scenario                                                                                                                                |
      +-----------------------------------+---------------------------------------------------------------------------------------------------------------------------------------------------------------+
      | Services                          | -  **Protocol**: Select a protocol. Supported protocols include TCP, UDP, and ICMP.                                                                           |
      |                                   | -  **Source Port**: Set the source port to be allowed or blocked. You can configure a single port or consecutive port groups (example: **80-443**).           |
      |                                   | -  **Destination Port**: Set the destination port to be allowed or blocked. You can configure a single port or consecutive port groups (example: **80-443**). |
      |                                   | -  **Description**: Usage and application scenario of the service group                                                                                       |
      +-----------------------------------+---------------------------------------------------------------------------------------------------------------------------------------------------------------+

#. Confirm the information and click **OK**.

Adding a Service to a User-defined Service Group
------------------------------------------------

#. Log in to the management console.
#. In the navigation pane on the left, click |image2| and choose **Security** > **Cloud Firewall**. The **Dashboard** page will be displayed.
#. (Optional) Switch to another firewall instance: Select a firewall from the drop-down list in the upper left corner of the page.
#. In the navigation pane, choose **Access Control** > **Object Groups**.
#. Click the **Service Groups** tab. Click the name of a service group. The **Service Group Details** dialog box is displayed..
#. Click **Add Service**.

   .. table:: **Table 2** Adding a service

      +-----------------------+-------------------------------------------------------------------------------------------------------------------------------+-----------------------+
      | Parameter             | Description                                                                                                                   | Example Value         |
      +=======================+===============================================================================================================================+=======================+
      | Protocol              | Its value can be **TCP**, **UDP**, or **ICMP**.                                                                               | TCP                   |
      +-----------------------+-------------------------------------------------------------------------------------------------------------------------------+-----------------------+
      | Source Port           | Source ports to be allowed or blocked. You can configure a single port or consecutive port groups (example: **80-443**).      | 80                    |
      |                       |                                                                                                                               |                       |
      |                       | .. note::                                                                                                                     |                       |
      |                       |                                                                                                                               |                       |
      |                       |    If **Protocol** is set to **ICMP**, you do not need to specify any port number.                                            |                       |
      +-----------------------+-------------------------------------------------------------------------------------------------------------------------------+-----------------------+
      | Destination Port      | Destination ports to be allowed or blocked. You can configure a single port or consecutive port groups (example: **80-443**). | 80                    |
      |                       |                                                                                                                               |                       |
      |                       | .. note::                                                                                                                     |                       |
      |                       |                                                                                                                               |                       |
      |                       |    If **Protocol** is set to **ICMP**, you do not need to specify any port number.                                            |                       |
      +-----------------------+-------------------------------------------------------------------------------------------------------------------------------+-----------------------+
      | Description           | Usage and application scenario                                                                                                | ``-``                 |
      +-----------------------+-------------------------------------------------------------------------------------------------------------------------------+-----------------------+

#. You can click **Add** to add multiple services.
#. Confirm the information and click **OK**.

Related Operations
------------------

-  Exporting service groups: Click **Export** above the list and select a data range.
-  Deleting services in batches: On the **Service Groups** tab, select services and click **Delete** above the list.

Follow-up Operations
--------------------

A service group takes effect only after it is set in a protection rule. For more information, see :ref:`Adding Protection Rules to Block or Allow Traffic <cfw_01_0030>`.

.. |image1| image:: /_static/images/en-us_image_0000001259322747.png
.. |image2| image:: /_static/images/en-us_image_0000001259322747.png
