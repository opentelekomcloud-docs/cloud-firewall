:original_name: cfw_01_0232.html

.. _cfw_01_0232:

Viewing Inter-VPC Traffic
=========================

The **Inter-VPC Access** page displays the traffic between the protected VPCs.

Prerequisites
-------------

VPC border traffic protection is enabled, and there is already traffic passing through the VPC. For details, see :ref:`Enabling VPC Border Traffic Protection <cfw_01_0078>`.


Viewing Inter-VPC Traffic
-------------------------

#. Log in to the management console.
#. In the navigation pane on the left, click |image1| and choose **Security** > **Cloud Firewall**. The **Dashboard** page will be displayed.
#. (Optional) Switch to another firewall instance: Select a firewall from the drop-down list in the upper left corner of the page.
#. In the navigation pane, choose **Traffic Analysis** > **Inter-VPC Access**.
#. Check statistics on the traffic passing through the cloud firewall within a time range, from 5 minutes to 7 days.

   -  **Traffic Dashboard**: Information about the maximum traffic between VPCs.

   -  **Inter-VPC Access**: Request and response traffic between VPCs.

      .. table:: **Table 1** Value description

         ============= ====================================
         Time Range    Value
         ============= ====================================
         Last 1 hour   Average value within every minute
         Last 24 hours Average value within every 5 minutes
         Last 7 days   Average value within every hour
         ============= ====================================

   -  **Visualizations**: View the top 5 items ranked by specific parameters of inter-VPC traffic within a specified period. For more information, see :ref:`Table 2 <cfw_01_0232__table12362103114169>`. You can click a data record to view the traffic details. A maximum of 50 data records can be viewed.

      .. _cfw_01_0232__table12362103114169:

      .. table:: **Table 2** Inter-VPC traffic parameters

         +--------------------------------+--------------------------------------------------+
         | Parameter                      | Description                                      |
         +================================+==================================================+
         | Top Access Source IP Addresses | Source IP address of inter-VPC traffic.          |
         +--------------------------------+--------------------------------------------------+
         | Top Destination IP Addresses   | Destination IP addresses of inter-VPC traffic.   |
         +--------------------------------+--------------------------------------------------+
         | Top Open Ports                 | Destination port of inter-VPC traffic.           |
         +--------------------------------+--------------------------------------------------+
         | Application Distribution       | Application information about inter-VPC traffic. |
         +--------------------------------+--------------------------------------------------+

   -  Private IP Address Accesses: Top 50 private IP addresses with the highest traffic within a specified period.

.. |image1| image:: /_static/images/en-us_image_0000001259322747.png
