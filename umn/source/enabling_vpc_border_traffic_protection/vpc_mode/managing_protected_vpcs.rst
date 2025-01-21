:original_name: cfw_01_0203.html

.. _cfw_01_0203:

Managing Protected VPCs
=======================

After creating a VPC border firewall, you need to associate VPCs with the firewall. For details, see :ref:`Associating a Protected VPC with the Firewall <cfw_01_0203__section8154163010584>`.

If a VPC does not need to be protected, you can disassociate the VPC from the firewall. For details, see :ref:`Disassociating a Protected VPC from a Firewall <cfw_01_0203__section3412449112919>`.

Constraints
-----------

Before disassociating a protected VPC from a firewall, delete the route pointing to the firewall in :ref:`Configuring VPC Route <cfw_01_0204>`.

.. _cfw_01_0203__section8154163010584:

Associating a Protected VPC with the Firewall
---------------------------------------------

#. Log in to the management console.

#. In the navigation pane on the left, click |image1| and choose **Security** > **Cloud Firewall**. The **Dashboard** page will be displayed.

#. (Optional) Switch to another firewall instance: Select a firewall from the drop-down list in the upper left corner of the page.

#. In the navigation pane, choose **Assets** > **Inter-VPC Border Firewalls**.

#. In the **Operation** column of a VPC, click **Associate Firewall**.

#. On the **Associate Firewall** page, configure :ref:`parameters for the protected VPC <cfw_01_0203__table157052295912>`.

   .. _cfw_01_0203__table157052295912:

   .. table:: **Table 1** Parameters for adding a protected VPC

      +-----------------------+--------------------------+----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
      | Parameter             |                          | Description                                                                                                                                                                                        |
      +=======================+==========================+====================================================================================================================================================================================================+
      | Protection Type       |                          | The value cannot be changed. The default value **VPC** is used.                                                                                                                                    |
      +-----------------------+--------------------------+----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
      | VPC                   |                          | Name and CIDR block of the protected VPC.                                                                                                                                                          |
      +-----------------------+--------------------------+----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
      | Firewall Route        | Protected VPC CIDR Block | By default, the CIDR block of the selected VPC is used. You can modify the CIDR block or click |image2| to add a CIDR block.                                                                       |
      +-----------------------+--------------------------+----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
      |                       | Next Hop Type            | The value cannot be changed. The default value is **VPC peering**.                                                                                                                                 |
      +-----------------------+--------------------------+----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
      |                       | Next Hop                 | The value cannot be changed. The VPC uses this VPC peering connection to forward traffic to the firewall.                                                                                          |
      +-----------------------+--------------------------+----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
      |                       | Description              | (Optional) Enter the description of the VPC.                                                                                                                                                       |
      +-----------------------+--------------------------+----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
      | Route                 | Configure VPC route      | If it is selected, the routes pointing to 10.0.0.0/8, 172.16.0.0/12, and 192.168.0.0/16 and whose next hop type is a firewall peering connection will be added to all the route tables of the VPC. |
      |                       |                          |                                                                                                                                                                                                    |
      |                       |                          | .. caution::                                                                                                                                                                                       |
      |                       |                          |                                                                                                                                                                                                    |
      |                       |                          |    CAUTION:                                                                                                                                                                                        |
      |                       |                          |    Before selecting it, confirm that it will not affect your network.                                                                                                                              |
      +-----------------------+--------------------------+----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+

#. Click **OK** to associate the protected VPC with the firewall.

.. _cfw_01_0203__section3412449112919:

Disassociating a Protected VPC from a Firewall
----------------------------------------------

#. Log in to the management console.
#. In the navigation pane on the left, click |image3| and choose **Security** > **Cloud Firewall**. The **Dashboard** page will be displayed.
#. (Optional) Switch to another firewall instance: Select a firewall from the drop-down list in the upper left corner of the page.
#. In the navigation pane, choose **Assets** > **Inter-VPC Border Firewalls**.
#. In the **Operation** column of a VPC, click **Disassociate**.
#. In the confirmation dialog box, click **OK**.

   .. note::

      If a VPC has a route whose next hop is the peering connection created by the firewall, the VPC cannot be deleted. To delete this VPC, delete the route first.

Follow-up Operations
--------------------

After VPCs are associated, perform the operations in :ref:`Configuring VPC Route <cfw_01_0204>` to add routes.

.. |image1| image:: /_static/images/en-us_image_0000001259322747.png
.. |image2| image:: /_static/images/en-us_image_0000001625198857.png
.. |image3| image:: /_static/images/en-us_image_0000001259322747.png
