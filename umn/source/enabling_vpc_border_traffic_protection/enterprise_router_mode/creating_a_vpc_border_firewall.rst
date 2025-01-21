:original_name: cfw_01_0235.html

.. _cfw_01_0235:

Creating a VPC Border Firewall
==============================

A VPC border firewall can collect statistics on communication traffic between VPCs, helping you detect abnormal traffic. This section describes how to create a VPC border firewall.

Prerequisites
-------------

-  You have an enterprise router.
-  To create a VPC border firewall, you need to configure an inspection VPC that consumes a VPC protection quota for traffic diversion. The current account must have a VPC that does not transmit traffic and has no subnets associated, and the VPCs under the account can create at least 2 route tables.

Procedure
---------

#. Log in to the management console.

#. In the navigation pane on the left, click |image1| and choose **Security** > **Cloud Firewall**. The **Dashboard** page will be displayed.

#. (Optional) Switch to another firewall instance: Select a firewall from the drop-down list in the upper left corner of the page.

#. In the navigation pane, choose **Assets** > **Inter-VPC Border Firewalls**.

#. Configure the subnets associated with the enterprise router and the cloud firewall, respectively. Click **Create Firewall**. Configure the enterprise router and associated subnets.

   .. table:: **Table 1** Parameters for a VPC border firewall

      +---------------------------------------------------------------+-----------------------------------------------------------------------------------------------------------------------------------------+-----------------------+
      | Parameter                                                     | Description                                                                                                                             | Example Value         |
      +===============================================================+=========================================================================================================================================+=======================+
      | Enterprise Router                                             | Select an enterprise router.                                                                                                            | cfw-er                |
      +---------------------------------------------------------------+-----------------------------------------------------------------------------------------------------------------------------------------+-----------------------+
      | Inspection VPC                                                | Select a VPC. The inspection VPC cannot use the network segments already specified in other VPCs associated with the enterprise router. | vpc-cfw-er            |
      +---------------------------------------------------------------+-----------------------------------------------------------------------------------------------------------------------------------------+-----------------------+
      | IPv4 Segment                                                  | After you select a VPC, the IPv4 address is automatically displayed.                                                                    | xx.xx.0.0/16          |
      +---------------------------------------------------------------+-----------------------------------------------------------------------------------------------------------------------------------------+-----------------------+
      | AZ                                                            | Select an AZ.                                                                                                                           | AZ1                   |
      +---------------------------------------------------------------+-----------------------------------------------------------------------------------------------------------------------------------------+-----------------------+
      | Subnet                                                        | Subnet name.                                                                                                                            | cfw-er-1              |
      |                                                               |                                                                                                                                         |                       |
      | (Subnet Associated with Enterprise Router)                    |                                                                                                                                         |                       |
      +---------------------------------------------------------------+-----------------------------------------------------------------------------------------------------------------------------------------+-----------------------+
      | Subnet                                                        |                                                                                                                                         | cfw-er-2              |
      |                                                               |                                                                                                                                         |                       |
      | (Subnet Associated to Cloud Firewall-1)                       |                                                                                                                                         |                       |
      +---------------------------------------------------------------+-----------------------------------------------------------------------------------------------------------------------------------------+-----------------------+
      | Subnet                                                        |                                                                                                                                         | cfw-er-3              |
      |                                                               |                                                                                                                                         |                       |
      | (Subnet Associated to Cloud Firewall-2)                       |                                                                                                                                         |                       |
      +---------------------------------------------------------------+-----------------------------------------------------------------------------------------------------------------------------------------+-----------------------+
      | IPv4 CIDR Block                                               | IPv4 CIDR Block                                                                                                                         | xx.xx.1.0/24          |
      |                                                               |                                                                                                                                         |                       |
      | (Subnet Associated with Enterprise Router)                    | .. note::                                                                                                                               |                       |
      |                                                               |                                                                                                                                         |                       |
      |                                                               |    -  Ensure the value must not conflict with existing subnets.                                                                         |                       |
      |                                                               |    -  Ensure the three subnet segments do not conflict with each other.                                                                 |                       |
      +---------------------------------------------------------------+-----------------------------------------------------------------------------------------------------------------------------------------+-----------------------+
      | IPv4 CIDR Block (Subnet 1 Associated with a Cloud Firewall-1) |                                                                                                                                         | xx.xx.2.0/24          |
      +---------------------------------------------------------------+-----------------------------------------------------------------------------------------------------------------------------------------+-----------------------+
      | IPv4 CIDR Block                                               |                                                                                                                                         | xx.xx.3.0/24          |
      |                                                               |                                                                                                                                         |                       |
      | (Subnet Associated to Cloud Firewall-2)                       |                                                                                                                                         |                       |
      +---------------------------------------------------------------+-----------------------------------------------------------------------------------------------------------------------------------------+-----------------------+

#. Click **OK**. The firewall will be created in 3 to 5 minutes.

   During the creation, you can only check the **Dashboard** page. The firewall status will change to **Upgrading**.

.. |image1| image:: /_static/images/en-us_image_0000001259322747.png
