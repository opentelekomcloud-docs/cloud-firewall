:original_name: cfw_01_0226.html

.. _cfw_01_0226:

Viewing Protection Information Using the Policy Assistant
=========================================================

After a protection policy is configured, you can use the policy assistant to check policy hits and adjust policies.


Viewing Protection Information Using the Policy Assistant
---------------------------------------------------------

#. Log in to the management console.
#. In the navigation pane on the left, click |image1| and choose **Security** > **Cloud Firewall**. The **Dashboard** page will be displayed.
#. (Optional) Switch to another firewall instance: Select a firewall from the drop-down list in the upper left corner of the page.
#. In the navigation pane, choose **Access Control** > **Policy Assistant**.
#. View statistics about the protection rules of a firewall instance.

   -  **Policy Dashboard**: Number of accesses that hit policies (protection rules, blacklist, and whitelist), numbers of allowed and blocked accesses, and the allow and block policies that were frequently hit within a specified time range.

   -  **Policy Hits**: Hits of a rule within a specified time range.

   -  **Visualizations**: Top 5 items ranked by certain parameters regarding blocked attacks within a specified time range. For more information, see :ref:`Table 1 <cfw_01_0226__table12362103114169>`. You can click a record to view policy matching details. For more information, see :ref:`Table 2 <cfw_01_0139__table099515711343>`.

      .. _cfw_01_0226__table12362103114169:

      .. table:: **Table 1** Policy assistant statistics parameters

         +-----------------------------------+------------------------------------------------------------------------------------------------------------------------------------------+
         | Parameter                         | Description                                                                                                                              |
         +===================================+==========================================================================================================================================+
         | Top Policies By Hits              | Policies that match and block traffic.                                                                                                   |
         +-----------------------------------+------------------------------------------------------------------------------------------------------------------------------------------+
         | Top Blocked Outbound IP Addresses | Blocked outbound IP addresses. You can click **Source** or **Destination** to view the source or destination IP addresses.               |
         +-----------------------------------+------------------------------------------------------------------------------------------------------------------------------------------+
         | Top Blocked Inbound IP Addresses  | Blocked inbound IP addresses. You can click **Source** or **Destination** to view the source or destination IP addresses.                |
         +-----------------------------------+------------------------------------------------------------------------------------------------------------------------------------------+
         | Top Blocked Destination Ports     | Blocked destination ports. You can click **Outbound** or **Inbound** to view ports in the corresponding direction.                       |
         +-----------------------------------+------------------------------------------------------------------------------------------------------------------------------------------+
         | Top Blocked IP Address Regions    | Regions of blocked IP addresses. You can click **Destination of outbound access** or **Source of inbound access** to check IP addresses. |
         +-----------------------------------+------------------------------------------------------------------------------------------------------------------------------------------+

   -  **Inactive Policies**: Policies that have not been hit or enabled for more than a week, a month, three months, or six months. You are advised to modify or delete the policies in a timely manner.

.. |image1| image:: /_static/images/en-us_image_0000001259322747.png
