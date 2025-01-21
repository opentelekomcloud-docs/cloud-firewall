:original_name: cfw_01_0009.html

.. _cfw_01_0009:

Checking the Dashboard
======================

On the **Dashboard** page, you can view the basic information, overall protection capabilities, and statistics of firewall instances to learn about the security status and traffic of cloud assets at any time.

Constraints
-----------

VPC border protection details can be viewed only after a :ref:`VPC border firewall <cfw_01_0078>` is configured.


Checking the Dashboard
----------------------

#. Log in to the management console.

#. In the navigation pane on the left, click |image1| and choose **Security** > **Cloud Firewall**. The **Dashboard** page will be displayed.

#. (Optional) Switch or view firewall instances.

   -  Switch to another firewall instance: Select a firewall from the drop-down list in the upper left corner of the page.

   -  View firewall instance information: Click **Firewall List** in the upper right corner. For details about parameters, see :ref:`Firewall instance information <cfw_01_0009__table14973162216315>`.

      .. _cfw_01_0009__table14973162216315:

      .. table:: **Table 1** Firewall instance information

         +--------------------------------+---------------------------------------------------------------+
         | Parameter                      | Description                                                   |
         +================================+===============================================================+
         | Firewall Name/ID               | Name and ID of the firewall.                                  |
         +--------------------------------+---------------------------------------------------------------+
         | Status                         | Firewall status.                                              |
         +--------------------------------+---------------------------------------------------------------+
         | Edition                        | Edition of a firewall.                                        |
         +--------------------------------+---------------------------------------------------------------+
         | Available EIP Protection Quota | Maximum number of EIPs that can be protected by the firewall. |
         +--------------------------------+---------------------------------------------------------------+
         | Peak Traffic Protection        | Maximum peak traffic that can be protected by the firewall.   |
         +--------------------------------+---------------------------------------------------------------+
         | Billing Mode                   | Billing mode of the current firewall.                         |
         +--------------------------------+---------------------------------------------------------------+
         | Enterprise Project             | Enterprise project that the firewall belongs to.              |
         +--------------------------------+---------------------------------------------------------------+
         | Operation                      | Check instance details.                                       |
         +--------------------------------+---------------------------------------------------------------+

#. In the **Resource Protection Overview** area, view the protection status of all cloud resources (EIPs and VPCs) in the current region under the current account.

#. View firewall instance information.

   :ref:`Table 2 <cfw_01_0009__table16203648134114>` describes the parameters in the **Firewall Details** area on the right part of the page.

   .. _cfw_01_0009__table16203648134114:

   .. table:: **Table 2** Firewall instance details

      +-----------------------+--------------------------------------+--------------------------------------------------------------------------------------------------------------------------------+
      | Parameter             |                                      | Description                                                                                                                    |
      +=======================+======================================+================================================================================================================================+
      | Basic Information     | Version                              | Firewall edition. Standard and professional editions are supported.                                                            |
      +-----------------------+--------------------------------------+--------------------------------------------------------------------------------------------------------------------------------+
      |                       | Firewall Name                        | Firewall instance name. You can click |image2| to change the name.                                                             |
      +-----------------------+--------------------------------------+--------------------------------------------------------------------------------------------------------------------------------+
      |                       | Firewall ID                          | Firewall instance ID.                                                                                                          |
      +-----------------------+--------------------------------------+--------------------------------------------------------------------------------------------------------------------------------+
      |                       | Status                               | Firewall status. It takes about 5 minutes to update the firewall status after purchase or unsubscription.                      |
      +-----------------------+--------------------------------------+--------------------------------------------------------------------------------------------------------------------------------+
      |                       | Enterprise Project                   | Enterprise project that the firewall belongs to.                                                                               |
      +-----------------------+--------------------------------------+--------------------------------------------------------------------------------------------------------------------------------+
      | Flavor                | Used/Available EIP Protection Quota  | *Number of protected EIPs*\ **/**\ *Total number of EIPs* under the current CFW instance.                                      |
      +-----------------------+--------------------------------------+--------------------------------------------------------------------------------------------------------------------------------+
      |                       | Used/Available VPC Protection Quota  | *Number of protected VPCs*\ **/**\ *Total number of VPCs* under a firewall instance.                                           |
      +-----------------------+--------------------------------------+--------------------------------------------------------------------------------------------------------------------------------+
      |                       | Internet Border Protection Bandwidth | Maximum inbound or outbound traffic of all EIPs protected by CFW.                                                              |
      +-----------------------+--------------------------------------+--------------------------------------------------------------------------------------------------------------------------------+
      |                       | VPC Border Protection Bandwidth      | Peak east-west traffic that can be protected.                                                                                  |
      |                       |                                      |                                                                                                                                |
      |                       |                                      | Maximum total traffic of all VPCs protected by CFW.                                                                            |
      +-----------------------+--------------------------------------+--------------------------------------------------------------------------------------------------------------------------------+
      |                       | Used/Available Protection Rules      | *Number of created protection rules*\ **/**\ *Total number of protection rules that can be created* under a firewall instance. |
      +-----------------------+--------------------------------------+--------------------------------------------------------------------------------------------------------------------------------+
      | Other Information     | Billing Mode                         | Billing mode.                                                                                                                  |
      +-----------------------+--------------------------------------+--------------------------------------------------------------------------------------------------------------------------------+
      | Tags                  |                                      | Configure tags to identify firewalls so that you can classify and trace firewall instances.                                    |
      +-----------------------+--------------------------------------+--------------------------------------------------------------------------------------------------------------------------------+

#. On the **Operations Dashboard** page, view the overall protection data of cloud resources.

   Click the **Internet Boundaries** or **Inter-VPC Borders** tab to view the corresponding overall protection data.

   In the upper right corner, change the query range.

   -  View the blocking results of access control policies and the maximum inbound and outbound traffic.
   -  **Traffic Trend** displays the inbound, outbound, and overall traffic trends..

      .. table:: **Table 3** Values

         +---------------+-----------------------------------+-----------------------------------+
         | Time Range    | Average                           | Maximum                           |
         +===============+===================================+===================================+
         | Last 1 hour   | Average value within every minute | Maximum value within every minute |
         +---------------+-----------------------------------+-----------------------------------+
         | Last 24 hours | Average value within 5 minutes    | Maximum value within 5 minutes    |
         +---------------+-----------------------------------+-----------------------------------+
         | Last 7 days   | Average value within one hour     | Maximum value within one hour     |
         +---------------+-----------------------------------+-----------------------------------+

      .. note::

         Data is updated in real time based on traffic statistics.

   -  **Attacks**: View the traffic blocked or allowed by intrusion prevention.
   -  **Access Control**: View the traffic blocked or allowed by access control policies.

.. |image1| image:: /_static/images/en-us_image_0000001259322747.png
.. |image2| image:: /_static/images/en-us_image_0000001986387925.png
