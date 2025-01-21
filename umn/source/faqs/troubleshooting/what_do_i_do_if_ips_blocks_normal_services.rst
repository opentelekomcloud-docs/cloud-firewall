:original_name: cfw_01_0225.html

.. _cfw_01_0225:

What Do I Do If IPS Blocks Normal Services?
===========================================

If normal service traffic is intercepted, perform either of the following operations:

-  Query the ID of the rule that blocks traffic and modify the action of the rule in the IPS rule library. For details, see :ref:`Querying Hit Rules and Modifying Protection Actions <cfw_01_0225__section19761827175210>`.
-  Use a less strict IPS protection mode. For details, see :ref:`Blocking Network Attacks <cfw_01_0032>`.

.. _cfw_01_0225__section19761827175210:

Querying Hit Rules and Modifying Protection Actions
---------------------------------------------------

#. Log in to the management console.

#. In the navigation pane on the left, click |image1| and choose **Security** > **Cloud Firewall**. The **Dashboard** page will be displayed.

#. (Optional) Switch to another firewall instance: Select a firewall from the drop-down list in the upper left corner of the page.

#. In the navigation pane, choose **Log Audit** > **Log Query**. Click the **Attack Event Logs** query and record the **Rule ID** of the rule that blocks traffic.


   .. figure:: /_static/images/en-us_image_0000001707369821.png
      :alt: **Figure 1** Rule ID

      **Figure 1** Rule ID

#. Click **View Effective Rules** under **Basic Protection**. The **Basic Protection** tab is displayed.

#. Search for the rule by its ID. In the **Operation** column, change its action to **Observe** or **Disable**.

   -  **Observe**: The firewall logs the traffic that matches the current rule and does not block the traffic.
   -  **Disable**: The firewall does not log or block the traffic that matches the current rule.

.. |image1| image:: /_static/images/en-us_image_0000001259322747.png
