:original_name: cfw_01_0061.html

.. _cfw_01_0061:

Managing Protection Rules
=========================

This section describes the protection rule parameters page and how to edit, copy, and delete a protection rule.

The default priority of the copy of a protection rule is **1** (highest priority).

Viewing Protection Rules
------------------------

#. Log in to the management console.
#. In the navigation pane on the left, click |image1| and choose **Security** > **Cloud Firewall**. The **Dashboard** page will be displayed.
#. (Optional) Switch to another firewall instance: Select a firewall from the drop-down list in the upper left corner of the page.
#. In the navigation pane, choose **Access Control** > **Access Policies**. The **Access Policies** page is displayed. Click the **Internet Borders** or **Inter-VPC Borders** tab.

   .. table:: **Table 1** Protection rule parameters

      +-----------------------------------+-----------------------------------------------------------------------------------------------------------------------------------------------------------------------+
      | Parameter                         | Description                                                                                                                                                           |
      +===================================+=======================================================================================================================================================================+
      | Priority                          | Priority of the rule.                                                                                                                                                 |
      |                                   |                                                                                                                                                                       |
      |                                   | .. note::                                                                                                                                                             |
      |                                   |                                                                                                                                                                       |
      |                                   |    A smaller value indicates a higher priority.                                                                                                                       |
      +-----------------------------------+-----------------------------------------------------------------------------------------------------------------------------------------------------------------------+
      | Name/Rule ID                      | Custom rule name and ID                                                                                                                                               |
      +-----------------------------------+-----------------------------------------------------------------------------------------------------------------------------------------------------------------------+
      | Rule Type                         | Protection type of the rule. It can be an EIP or NAT rule.                                                                                                            |
      +-----------------------------------+-----------------------------------------------------------------------------------------------------------------------------------------------------------------------+
      | Direction                         | Traffic direction of the protection rule.                                                                                                                             |
      +-----------------------------------+-----------------------------------------------------------------------------------------------------------------------------------------------------------------------+
      | Source                            | Source of data packets in the access traffic.                                                                                                                         |
      +-----------------------------------+-----------------------------------------------------------------------------------------------------------------------------------------------------------------------+
      | Destination                       | Destination of data packets in the access traffic.                                                                                                                    |
      +-----------------------------------+-----------------------------------------------------------------------------------------------------------------------------------------------------------------------+
      | Service                           | -  Its value can be **TCP**, **UDP**, **ICMP**, or **Any**.                                                                                                           |
      |                                   |                                                                                                                                                                       |
      |                                   | -  Source Port: Source ports to be allowed or blocked. You can configure a single port or consecutive port groups (example: **80-443**).                              |
      |                                   |                                                                                                                                                                       |
      |                                   | -  Destination Port: Destination ports to be allowed or blocked.                                                                                                      |
      |                                   |                                                                                                                                                                       |
      |                                   |    You can configure a single port or consecutive port groups (example: **80-443**).                                                                                  |
      +-----------------------------------+-----------------------------------------------------------------------------------------------------------------------------------------------------------------------+
      | Action                            | -  **Allow**: Allow the traffic to pass through the firewall.                                                                                                         |
      |                                   | -  **Block**: Block the traffic from passing through the firewall.                                                                                                    |
      +-----------------------------------+-----------------------------------------------------------------------------------------------------------------------------------------------------------------------+
      | Hits                              | Total number of actions that have been triggered by the rule (since the last reset). For details, see :ref:`Access Control Logs <cfw_01_0139__section8485135919336>`. |
      +-----------------------------------+-----------------------------------------------------------------------------------------------------------------------------------------------------------------------+
      | Status                            | Status of the rule. It can be enabled or disabled.                                                                                                                    |
      +-----------------------------------+-----------------------------------------------------------------------------------------------------------------------------------------------------------------------+
      | Tags                              | Tag of a rule.                                                                                                                                                        |
      +-----------------------------------+-----------------------------------------------------------------------------------------------------------------------------------------------------------------------+

#. (Optional) Select a direction and a protocol type from the drop-down list boxes.

Editing a Protection Rule
-------------------------

#. Log in to the management console.
#. In the navigation pane on the left, click |image2| and choose **Security** > **Cloud Firewall**. The **Dashboard** page will be displayed.
#. (Optional) Switch to another firewall instance: Select a firewall from the drop-down list in the upper left corner of the page.
#. In the navigation pane, choose **Access Control** > **Access Policies**.
#. In the row of a rule, click **Edit** in the **Operation** column.
#. In the displayed **Edit Rule** dialog box, modify the rule parameters.
#. Click **OK**.

Copying a Protection Rule
-------------------------

#. Log in to the management console.
#. In the navigation pane on the left, click |image3| and choose **Security** > **Cloud Firewall**. The **Dashboard** page will be displayed.
#. (Optional) Switch to another firewall instance: Select a firewall from the drop-down list in the upper left corner of the page.
#. In the navigation pane, choose **Access Control** > **Access Policies**.
#. In the row of a rule, choose **More** > **Copy** in the **Operation** column.
#. Modify parameters and click **OK**. The default priority of the new protection rule is **1** (highest priority).

Deleting a Rule
---------------

#. Log in to the management console.
#. In the navigation pane on the left, click |image4| and choose **Security** > **Cloud Firewall**. The **Dashboard** page will be displayed.
#. (Optional) Switch to another firewall instance: Select a firewall from the drop-down list in the upper left corner of the page.
#. In the navigation pane, choose **Access Control** > **Access Policies**.
#. In the row of a rule, choose **More** > **Delete** in the **Operation** column.
#. In the **Delete Rule** dialog box, click **OK**.

   .. warning::

      Deleted rules cannot be restored. Exercise caution when performing this operation.

.. |image1| image:: /_static/images/en-us_image_0000001259322747.png
.. |image2| image:: /_static/images/en-us_image_0000001259322747.png
.. |image3| image:: /_static/images/en-us_image_0000001259322747.png
.. |image4| image:: /_static/images/en-us_image_0000001259322747.png
