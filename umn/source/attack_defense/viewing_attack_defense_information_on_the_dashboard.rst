:original_name: cfw_01_0228.html

.. _cfw_01_0228:

Viewing Attack Defense Information on the Dashboard
===================================================

On the security dashboard, you can quickly view protection information about attack defense functions (IPS, reverse shell defense, sensitive directory scan defense, and antivirus) and adjust IPS protection mode in a timely manner.

Viewing IPS Protection Information on the Dashboard
---------------------------------------------------

#. Log in to the management console.
#. In the navigation pane on the left, click |image1| and choose **Security** > **Cloud Firewall**. The **Dashboard** page will be displayed.
#. (Optional) Switch to another firewall instance: Select a firewall from the drop-down list in the upper left corner of the page.
#. In the navigation pane, choose **Attack Defense** > **Security Dashboard**.
#. In the upper part of the page, click the **Internet Borders** or **Inter-VPC Borders** tab.
#. View statistics about protection rules of a firewall instance. You can select a query duration from the drop-down list.

   -  **Security Dashboard**: Number of attacks detected by IPS, numbers of allowed and blocked accesses, and number of attacked ports.

   -  **Attacks**: Number of times that IPS blocks or allows traffic.

   -  **Visualizations**: Top 5 items ranked by certain parameters regarding the attacks detected or blocked by IPS. For more information, see :ref:`Table 1 <cfw_01_0228__table12362103114169>`. You can click a record to view attack details. For more information, see :ref:`Table 1 <cfw_01_0139__table1131654116506>`.

      .. _cfw_01_0228__table12362103114169:

      .. table:: **Table 1** Security dashboard statistics parameters

         +-----------------------------------------+------------------------------------------------------------------------------------------------+
         | Parameter                               | Description                                                                                    |
         +=========================================+================================================================================================+
         | Attack Types                            | Attack type.                                                                                   |
         +-----------------------------------------+------------------------------------------------------------------------------------------------+
         | Top Internal Attack Source IP Addresses | IP addresses of the assets that are on your cloud but launch attacks on external IP addresses. |
         +-----------------------------------------+------------------------------------------------------------------------------------------------+
         | Top External Attack Source IP Addresses | External IP addresses that launch attacks on your cloud assets.                                |
         +-----------------------------------------+------------------------------------------------------------------------------------------------+
         | Top External Attack Source Regions      | Regions of the external IP addresses that launch attacks on your cloud assets.                 |
         +-----------------------------------------+------------------------------------------------------------------------------------------------+
         | Top Attack Destination IP Addresses     | Destination IP addresses in attacks.                                                           |
         +-----------------------------------------+------------------------------------------------------------------------------------------------+
         | Top Attacked Ports                      | Attacked ports.                                                                                |
         +-----------------------------------------+------------------------------------------------------------------------------------------------+

   -  Top attack statistics: Top 50 attacks detected or blocked by IPS within a specified time range.

      -  **Top Attack Targets**: Destination IP addresses, ports, and applications.
      -  **Top Attack Sources**: Source IP addresses and types.

Related Operations
------------------

For details about logs, see :ref:`Attack Event Logs <cfw_01_0139__section1131659192010>`.

.. |image1| image:: /_static/images/en-us_image_0000001259322747.png
