:original_name: cfw_01_0236.html

.. _cfw_01_0236:

Configuring an Enterprise Router
================================

This section describes how to associate a firewall with an enterprise router and configure traffic diversion.

How to Configure
----------------

The process of configuring an enterprise router is as follows.


.. figure:: /_static/images/en-us_image_0000001636363317.png
   :alt: **Figure 1** Process of configuring an enterprise router

   **Figure 1** Process of configuring an enterprise router

Prerequisites
-------------

A firewall has been created.

Constraints
-----------

-  **Default Route Table Association**, **Default Route Table Propagation**, and **Auto Accept Shared Attachments** must be disabled.
-  Only the professional edition supports inter-VPC firewall protection.

Procedure
---------

#. Log in to the management console.

#. In the navigation pane on the left, click |image1| and choose **Security** > **Cloud Firewall**. The **Dashboard** page will be displayed.

#. (Optional) Switch to another firewall instance: Select a firewall from the drop-down list in the upper left corner of the page.

#. In the navigation pane, choose **Assets** > **Inter-VPC Border Firewalls**.

#. Click **Configure Enterprise Router**. On the displayed page, add attachments to an enterprise router. For details about the attachment types that can be added, see *Attachment Overview* in *Enterprise Router User Guide*.

   Assume you want to protect two VPCs. (At least two VPC attachments are required to connect the two VPCs to the enterprise router.) For details, see section *Adding VPC Attachments to an Enterprise Router* in "ER User Guide".

   .. note::

      -  Add at least three connections, for example, the firewall connection **cfw-er-auto** (automatically generated after the firewall is created), the VPC1 connection **vpc-1**, and the VPC2 connection **vpc-2**.
      -  To use the enterprise router of account A to protect VPCs under account B, share the router with account B, and add an attachment in account B. For details, see *Creating a Sharing* in *Enterprise Router User Guide*. Subsequent configurations should still be performed on account A.

#. Create two route tables to connect to the firewall and the VPC to be protected, respectively.

   Click the **Route Tables** tab. Click **Create Route Table**.

   Create a route table. For more information, see :ref:`Route table parameters <cfw_01_0236__en-us_topic_0000001636523073_table43151737288>`.

   .. _cfw_01_0236__en-us_topic_0000001636523073_table43151737288:

   .. table:: **Table 1** Route table parameters

      +-------------+-------------------------------------------------------------------------------------------------------------------------------------------------------------+---------------+
      | Parameter   | Description                                                                                                                                                 | Example Value |
      +=============+=============================================================================================================================================================+===============+
      | Name        | Route table name.                                                                                                                                           | er-rlb-4cd1   |
      +-------------+-------------------------------------------------------------------------------------------------------------------------------------------------------------+---------------+
      | Description | Route table description                                                                                                                                     | ``-``         |
      +-------------+-------------------------------------------------------------------------------------------------------------------------------------------------------------+---------------+
      | Tag         | During the route table creation, you can tag the route table resources. Tags identify cloud resources for purposes of easy categorization and quick search. | ``-``         |
      +-------------+-------------------------------------------------------------------------------------------------------------------------------------------------------------+---------------+

#. .. _cfw_01_0236__en-us_topic_0000001636523073_li19994174475:

   Configure the association and routing.

   a. Select the route table to be connected to the VPC. Click the **Associations** tab and click **Create Association**.

      For more information, see :ref:`Association parameters <cfw_01_0236__en-us_topic_0000001636523073_table97791556114616>`.

      .. _cfw_01_0236__en-us_topic_0000001636523073_table97791556114616:

      .. table:: **Table 2** Association parameters

         +-----------------+--------------------------------------------------------+---------------+
         | Parameter       | Description                                            | Example Value |
         +=================+========================================================+===============+
         | Attachment Type | Select **VPC**.                                        | VPC           |
         +-----------------+--------------------------------------------------------+---------------+
         | Attachment      | Select an item from the **Attachment** drop-down list. | er-attach-01  |
         +-----------------+--------------------------------------------------------+---------------+

   b. Create a route for the route table. Click the **Routes** tab and click **Create Route**. You can create one or more routes as needed.

      Create a route table. For more information, see :ref:`Route parameters <cfw_01_0236__en-us_topic_0000001636523073_table10603451195>`.

      .. _cfw_01_0236__en-us_topic_0000001636523073_table10603451195:

      .. table:: **Table 3** Route parameters

         +-----------------------+------------------------------------------------------------------------------------------------------------------------------------------------+-----------------------+
         | Parameter             | Description                                                                                                                                    | Example Value         |
         +=======================+================================================================================================================================================+=======================+
         | Destination           | Set the destination address.                                                                                                                   | 192.168.2.0/24        |
         |                       |                                                                                                                                                |                       |
         |                       | It can be a VPC CIDR block or subnet CIDR block.                                                                                               |                       |
         |                       |                                                                                                                                                |                       |
         |                       | .. note::                                                                                                                                      |                       |
         |                       |                                                                                                                                                |                       |
         |                       |    If your ECS is bound to an EIP, you need to specify the network segment when configuring the route. The value **0.0.0.0/0** is not allowed. |                       |
         +-----------------------+------------------------------------------------------------------------------------------------------------------------------------------------+-----------------------+
         | Attachment Type       | Select **VPC**.                                                                                                                                | VPC                   |
         +-----------------------+------------------------------------------------------------------------------------------------------------------------------------------------+-----------------------+
         | Next Hop              | Select the VPC attachment of the firewall.                                                                                                     | er-Inspection         |
         +-----------------------+------------------------------------------------------------------------------------------------------------------------------------------------+-----------------------+

#. .. _cfw_01_0236__en-us_topic_0000001636523073_li0478194414719:

   Configure the association and propagation.

   a. Select the route table to be connected to the firewall. Click the **Associations** tab and click **Create Association**.

      For more information, see :ref:`Association parameters <cfw_01_0236__en-us_topic_0000001636523073_table65591181764>`.

      .. _cfw_01_0236__en-us_topic_0000001636523073_table65591181764:

      .. table:: **Table 4** Association parameters

         +-----------------+--------------------------------------------------------+---------------+
         | Parameter       | Description                                            | Example Value |
         +=================+========================================================+===============+
         | Attachment Type | Select **VPC**.                                        | VPC           |
         +-----------------+--------------------------------------------------------+---------------+
         | Attachment      | Select an item from the **Attachment** drop-down list. | er-Inspection |
         +-----------------+--------------------------------------------------------+---------------+

   b. Create a propagation for the route table. Click the **Propagations** tab and click **Create Propagation**.

      For more information, see :ref:`Propagation parameters <cfw_01_0236__en-us_topic_0000001636523073_table13895331195018>`.

      .. _cfw_01_0236__en-us_topic_0000001636523073_table13895331195018:

      .. table:: **Table 5** Propagation parameters

         +-----------------+--------------------------------------------------------+---------------+
         | Parameter       | Description                                            | Example Value |
         +=================+========================================================+===============+
         | Attachment Type | Select **VPC**.                                        | VPC           |
         +-----------------+--------------------------------------------------------+---------------+
         | Attachment      | Select an item from the **Attachment** drop-down list. | er-attach-02  |
         +-----------------+--------------------------------------------------------+---------------+

      .. note::

         -  After a propagation is created, its route information will be extracted to the route table of the enterprise router, and a propagation route will be generated. In the same route table, the destinations of different propagation routes may be the same, and cannot be modified or deleted.
         -  You can add static routes for the attachments in a route table. The destinations of static routes in a table must be unique, and can be modified or deleted.
         -  If a static route and a propagation route in the same route table happen to use the same destination, the static route takes effect first.

Verifying Configurations
------------------------

**Prerequisites**

-  You have completed configuration.
-  Each of the two VPCs has an ECS.

**Method**

Ping ECSs in the VPC from each other to check whether they can properly communication if there is no traffic passing through the firewall.

**Troubleshooting**

#. Check whether the two route tables of the enterprise router are correctly configured. For details, see :ref:`Step 7 <cfw_01_0236__en-us_topic_0000001636523073_li19994174475>` and :ref:`Step 8 <cfw_01_0236__en-us_topic_0000001636523073_li0478194414719>`.

#. Check whether the default route table of the VPC directs routes to the enterprise router.

   Procedure

   1. In the service list, click **Virtual Private Cloud** under **Networking**. In the navigation pane, choose **Route Tables**. In the **Name/ID** column, click the route table name of the VPC to be protected.

   2. Check whether there is a route whose **Next Hop Type** is **Enterprise Router**. If there are no such routes, click **Add Route**. The following table describes the parameters.

   .. table:: **Table 6** Route parameters

      +-----------------------+-------------------------------------------------------------------------------------------+-----------------------+
      | Parameter             | Description                                                                               | Example Value         |
      +=======================+===========================================================================================+=======================+
      | Destination           | Destination CIDR block.                                                                   | 192.168.0.0/16        |
      |                       |                                                                                           |                       |
      |                       | A route destination must be unique, and cannot overlap with any subnets in the VPC.       |                       |
      |                       |                                                                                           |                       |
      |                       | .. note::                                                                                 |                       |
      |                       |                                                                                           |                       |
      |                       |    The value cannot conflict with existing routes or subnet CIDR blocks in the VPC.       |                       |
      +-----------------------+-------------------------------------------------------------------------------------------+-----------------------+
      | Next Hop Type         | Select **Enterprise Router** from the drop-down list.                                     | Enterprise Router     |
      +-----------------------+-------------------------------------------------------------------------------------------+-----------------------+
      | Next Hop              | Select a resource for the next hop.                                                       | er-01                 |
      |                       |                                                                                           |                       |
      |                       | Only the resources of the next hop type you selected are displayed in the drop-down list. |                       |
      +-----------------------+-------------------------------------------------------------------------------------------+-----------------------+
      | Description           | (Optional) Supplementary information about the route.                                     | ``-``                 |
      |                       |                                                                                           |                       |
      |                       | .. note::                                                                                 |                       |
      |                       |                                                                                           |                       |
      |                       |    Enter up to 255 characters. Angle brackets (< or >) are not allowed.                   |                       |
      +-----------------------+-------------------------------------------------------------------------------------------+-----------------------+

.. |image1| image:: /_static/images/en-us_image_0000001259322747.png
