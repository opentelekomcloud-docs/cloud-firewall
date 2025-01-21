:original_name: cfw_01_0230.html

.. _cfw_01_0230:

Viewing Inbound Traffic
=======================

The **Inbound Traffic** page displays the protected traffic from the Internet to EIPs on the cloud. CFW collects traffic statistics based on sessions. Traffic data is reported when the connection is terminated.

Prerequisites
-------------

EIP protection is enabled and there is already traffic passing through the EIP. For details, see :ref:`Enabling Internet Border Traffic Protection <cfw_01_0031>`.


Viewing Inbound Traffic
-----------------------

#. Log in to the management console.
#. In the navigation pane on the left, click |image1| and choose **Security** > **Cloud Firewall**. The **Dashboard** page will be displayed.
#. (Optional) Switch to another firewall instance: Select a firewall from the drop-down list in the upper left corner of the page.
#. In the navigation pane, choose **Traffic Analysis** > **Inbound Traffic**.
#. Check statistics on the traffic passing through the firewall within a time range, from 5 minutes to 7 days.

   -  **Traffic Dashboard**: Information about the highest traffic from the Internet to internal servers.

   -  **Inbound Traffic**: Inbound request traffic and response traffic. The traffic statistics of up to 30 EIPs can be queried at a time.

      .. table:: **Table 1** Value description

         ============= ====================================
         Time Range    Value
         ============= ====================================
         Last 1 hour   Average value within every minute
         Last 24 hours Average value within every 5 minutes
         Last 7 days   Average value within every hour
         ============= ====================================

   -  **Visualizations**: View the top 5 items ranked by specific parameters of inbound traffic within a specified period. For more information, see :ref:`Table 2 <cfw_01_0230__table12362103114169>`. You can click a data record to view the traffic details. A maximum of 50 data records can be viewed.

      .. _cfw_01_0230__table12362103114169:

      .. table:: **Table 2** Inbound traffic parameters

         +--------------------------------+-----------------------------------------------------------------------+
         | Parameter                      | Description                                                           |
         +================================+=======================================================================+
         | Top Access Source IP Addresses | Source IP addresses of inbound traffic.                               |
         +--------------------------------+-----------------------------------------------------------------------+
         | Top Access Source Regions      | Geographical locations of the source IP addresses of inbound traffic. |
         +--------------------------------+-----------------------------------------------------------------------+
         | Top Destination IP Addresses   | Destination IP addresses of inbound traffic.                          |
         +--------------------------------+-----------------------------------------------------------------------+
         | Top Open Ports                 | Destination ports of inbound traffic.                                 |
         +--------------------------------+-----------------------------------------------------------------------+
         | Application Distribution       | Application information about inbound traffic.                        |
         +--------------------------------+-----------------------------------------------------------------------+

   -  IP analysis: Top 50 traffic records in a specified period.

      -  **EIPs**: Traffic information about destination IP addresses.
      -  **Source IP Addresses**: Traffic information about source IP addresses.

.. |image1| image:: /_static/images/en-us_image_0000001259322747.png
