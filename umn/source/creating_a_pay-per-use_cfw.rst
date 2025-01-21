:original_name: cfw_01_0004.html

.. _cfw_01_0004:

Creating a Pay-per-Use CFW
==========================

You can purchase multiple firewalls in a region and assign them different resources and policies.

Prerequisites
-------------

The current account has the BSS Administrator and CFW FullAccess permissions.

Constraints
-----------

-  CFW can be used only in the region where it was created. To use CFW in another region, switch to that region and create it.

Creating a Pay-per-Use Professional CFW
---------------------------------------

#. Log in to the management console.

#. In the navigation pane on the left, click |image1| and choose **Security** > **Cloud Firewall**. The **Dashboard** page will be displayed.

#. Click **Create CFW** and configure parameters. For details, see :ref:`Table 1 <cfw_01_0004__cfw_01_0265_table1546793616132>`.

   .. _cfw_01_0004__cfw_01_0265_table1546793616132:

   .. table:: **Table 1** Parameters for creating CFW

      +-----------------------------------+---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
      | Parameter                         | Description                                                                                                                                                                                                                           |
      +===================================+=======================================================================================================================================================================================================================================+
      | Billing Mode                      | **Pay-per-use** indicates that you will be charged for the protection on your workloads.                                                                                                                                              |
      +-----------------------------------+---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
      | Region                            | Region where the CFW is to be purchased.                                                                                                                                                                                              |
      +-----------------------------------+---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
      | Edition                           | Currently, only the professional edition is supported.                                                                                                                                                                                |
      +-----------------------------------+---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
      | Firewall Name                     | Firewall name.                                                                                                                                                                                                                        |
      |                                   |                                                                                                                                                                                                                                       |
      |                                   | It must meet the following requirements:                                                                                                                                                                                              |
      |                                   |                                                                                                                                                                                                                                       |
      |                                   | -  Only letters (A to Z and a to z), numbers (0 to 9), spaces, and the following characters are allowed: -\_                                                                                                                          |
      |                                   | -  The value can contain 1 to 48 characters.                                                                                                                                                                                          |
      +-----------------------------------+---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
      | Enterprise Project                | In the drop-down list, select the enterprise project that you belong to. The purchased CFW then belongs to that enterprise project and protects all resources in that project.                                                        |
      |                                   |                                                                                                                                                                                                                                       |
      |                                   | This option is only available if you have enabled enterprise projects, or if you are logged in using an enterprise master account. You can use an enterprise project to centrally manage your cloud resources and members by project. |
      |                                   |                                                                                                                                                                                                                                       |
      |                                   | .. note::                                                                                                                                                                                                                             |
      |                                   |                                                                                                                                                                                                                                       |
      |                                   |    Value **default** indicates the default enterprise project. Resources that are not allocated to any enterprise projects under your account are displayed in the default enterprise project.                                        |
      +-----------------------------------+---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
      | Tags                              | It is recommended that you use the TMS predefined tag function to add the same tag to different cloud resources.                                                                                                                      |
      +-----------------------------------+---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+

#. Confirm the information and click **Create Firewall**.

.. |image1| image:: /_static/images/en-us_image_0000001259322747.png
