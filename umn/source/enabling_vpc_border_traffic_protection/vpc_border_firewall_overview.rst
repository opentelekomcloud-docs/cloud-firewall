:original_name: cfw_01_0185.html

.. _cfw_01_0185:

VPC Border Firewall Overview
============================

The VPC border firewall supports access control for communication traffic between VPCs, visualizing and protecting internal service access.

Association Modes
-----------------

CFW can provide VPC border protection in VPC or enterprise router association modes. The following table describes the differences between these modes.

.. table:: **Table 1** Differences between VPC and enterprise router modes

   +------------------------------+----------------------------------------------------------------------------------------------+---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
   | Category                     | VPC                                                                                          | Enterprise Router                                                                                                                                                                                                                                                   |
   +==============================+==============================================================================================+=====================================================================================================================================================================================================================================================================+
   | Inter-VPC communication mode | Create a VPC peering connection.                                                             | Configure traffic diversion in an enterprise router.                                                                                                                                                                                                                |
   +------------------------------+----------------------------------------------------------------------------------------------+---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
   | Billing Mode                 | Free                                                                                         | Enterprise routers are billed per use. .                                                                                                                                                                                                                            |
   +------------------------------+----------------------------------------------------------------------------------------------+---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
   | Cross-account protection     | Not supported                                                                                | Supported. When you add VPC attachments in :ref:`Configuring an Enterprise Router <cfw_01_0236>`, share the enterprise router of account A with account B, and then add attachments in account B. Subsequent configurations should still be performed on account A. |
   +------------------------------+----------------------------------------------------------------------------------------------+---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
   | Scenario                     | -  Simple network structure                                                                  | -  Complex network structure                                                                                                                                                                                                                                        |
   |                              | -  Only a few VPCs need to be protected, and the peak traffic bandwidth between VPCs is low. | -  High bandwidth performance required                                                                                                                                                                                                                              |
   |                              |                                                                                              | -  Scalability required                                                                                                                                                                                                                                             |
   +------------------------------+----------------------------------------------------------------------------------------------+---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+

Example scenarios:

-  User A:

   After workloads are migrated to the cloud, a large number of VPCs need to be connected and the peak traffic between VPCs is high.

   The user needs flexible networking and wants its O&M to be easy and efficient. In this case, the VPC border firewall in enterprise router mode is recommended.

-  User B:

   The user has five or fewer VPCs, which communicate with each other through VPC peering connections. Their networking is fixed and peak traffic is low.

   The user wants to quickly provision a firewall and maintain it at low costs. In this case, the VPC border firewall in VPC mode is recommended.

Constraints
-----------

-  Only the professional edition supports VPC border firewalls.
-  Traffic diversion depends on the enterprise router in enterprise router mode.
-  Only VPCs in the enterprise project to which the current account belongs can be protected.

Configuration Process
---------------------

The following figure shows the configuration process in VPC mode.


.. figure:: /_static/images/en-us_image_0000001690646797.png
   :alt: **Figure 1** Configuration process in VPC mode

   **Figure 1** Configuration process in VPC mode

The following figure shows the configuration process in enterprise router association mode.


.. figure:: /_static/images/en-us_image_0000001525350932.png
   :alt: **Figure 2** Configuration process of the enterprise router

   **Figure 2** Configuration process of the enterprise router
