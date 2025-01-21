:original_name: cfw_01_0063.html

.. _cfw_01_0063:

Adjusting the Priority of a Protection Rule
===========================================

When traffic hits a rule, the action of the rule will be performed, and CFW will not match the traffic against other protection rules. You are advised to set the priorities of the allowing rules to be higher than those of the blocking rules, and set the priorities of specific rules to be higher than those of general rules.

This section describes how to adjust the priorities of protection rules.

Priority
--------

A larger value indicates a lower priority. The value 1 indicates the highest priority.


Adjusting the Priority of a Protection Rule
-------------------------------------------

#. Log in to the management console.
#. In the navigation pane on the left, click |image1| and choose **Security** > **Cloud Firewall**. The **Dashboard** page will be displayed.
#. (Optional) Switch to another firewall instance: Select a firewall from the drop-down list in the upper left corner of the page.
#. In the navigation pane, choose **Access Control** > **Access Policies**.
#. In the **Operation** column of a rule, click **Configure Priority**.
#. Select **Pin on top** or **Lower than the selected rule**.

   -  If you select **Pin on top**, the policy is set to the highest priority.
   -  If you select **Lower than the selected rule**, you need to select a rule. The policy priority will be lower than the selected rule.

#. Click **OK**.

.. |image1| image:: /_static/images/en-us_image_0000001259322747.png
