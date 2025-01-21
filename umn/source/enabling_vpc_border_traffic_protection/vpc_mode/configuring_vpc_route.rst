:original_name: cfw_01_0204.html

.. _cfw_01_0204:

Configuring VPC Route
=====================

Configure routes on the VPC side.

Procedure
---------

#. Log in to the management console.

#. In the navigation tree on the left, click |image1| in the upper left corner. Click **Virtual Private Cloud** under **Networking** and choose **Virtual Private Cloud** > **Route Tables**.

#. In the **Name/ID** column, click the route table name of a VPC. The **Summary** page is displayed.

#. Click **Add Route**. For more information, see :ref:`Table 1 <cfw_01_0204__table231322472818>`.

   .. _cfw_01_0204__table231322472818:

   .. table:: **Table 1** Route parameters

      +-----------------------------------+------------------------------------------------------------------------------+
      | Parameter                         | Description                                                                  |
      +===================================+==============================================================================+
      | Destination                       | Destination CIDR block.                                                      |
      +-----------------------------------+------------------------------------------------------------------------------+
      | Next Hop Type                     | Select **VPC peering connection** from the drop-down list.                   |
      +-----------------------------------+------------------------------------------------------------------------------+
      | Next Hop                          | Select the VPC peering connection associated with the traffic diversion VPC. |
      +-----------------------------------+------------------------------------------------------------------------------+
      | Description                       | (Optional) Supplementary information about the route.                        |
      |                                   |                                                                              |
      |                                   | .. note::                                                                    |
      |                                   |                                                                              |
      |                                   |    Enter up to 255 characters. Angle brackets (< or >) are not allowed.      |
      +-----------------------------------+------------------------------------------------------------------------------+

.. |image1| image:: /_static/images/en-us_image_0000001625319329.png
