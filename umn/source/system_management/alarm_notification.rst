:original_name: cfw_01_0166.html

.. _cfw_01_0166:

Alarm Notification
==================

After alarm notification is enabled, CFW will send notifications to you through the method you specified (such as email or SMS) so that you can monitor the firewall status and quickly detect exceptions.

CFW supports the following alarms:

-  Attack alarm: An alarm is triggered when the IPS detects an attack.
-  High traffic warning: An alarm is triggered if the traffic reaches the specified percentage of the traffic processing capability you purchased.
-  EIP not protected: An alarm is triggered when the current account has EIPs that are not protected.

Attack Alarm
------------

#. Log in to the management console.

#. In the navigation pane on the left, click |image1| and choose **Security** > **Cloud Firewall**. The **Dashboard** page will be displayed.

#. (Optional) Switch to another firewall instance: Select a firewall from the drop-down list in the upper left corner of the page.

#. In the navigation pane, choose **System Management** > **Notifications**.

#. In the **Operation** column of **Attack alarm**, click **Edit**, and configure notification item parameters. For details, see :ref:`Table 1 <cfw_01_0166__table1854192020589>`.

   .. _cfw_01_0166__table1854192020589:

   .. table:: **Table 1** Attack alarm parameters

      +-----------------------------------+-------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
      | Parameter                         | Description                                                                                                                                                             |
      +===================================+=========================================================================================================================================================================+
      | Description                       | IPS attack alarm                                                                                                                                                        |
      +-----------------------------------+-------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
      | Level                             | Select the risk levels that trigger notifications.                                                                                                                      |
      |                                   |                                                                                                                                                                         |
      |                                   | The options are **Serious**, **High**, **Medium**, and **Low**. Multiple options can be selected.                                                                       |
      |                                   |                                                                                                                                                                         |
      |                                   | For example, if you select **High** and **Medium**, the firewall will notify you by SMS message or email when detecting an intrusion with a high- or medium-level risk. |
      +-----------------------------------+-------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
      | Notification Time                 | Select a time range for sending notifications.                                                                                                                          |
      +-----------------------------------+-------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
      | Trigger Condition                 | Configure the trigger condition.                                                                                                                                        |
      |                                   |                                                                                                                                                                         |
      |                                   | .. note::                                                                                                                                                               |
      |                                   |                                                                                                                                                                         |
      |                                   |    Alarm notifications are sent if the number of attacks is at least equal to the threshold configured for a certain period.                                            |
      +-----------------------------------+-------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
      | Recipient Group                   | Select a topic from the drop-down list to configure the endpoints for receiving alarm notifications.                                                                    |
      +-----------------------------------+-------------------------------------------------------------------------------------------------------------------------------------------------------------------------+

#. Click **OK**.

#. In the **Status** column of **Attack alarm**, click |image2| to enable it.

High Traffic Warning
--------------------

#. Log in to the management console.

#. In the navigation pane on the left, click |image3| and choose **Security** > **Cloud Firewall**. The **Dashboard** page will be displayed.

#. (Optional) Switch to another firewall instance: Select a firewall from the drop-down list in the upper left corner of the page.

#. In the navigation pane, choose **System Management** > **Notifications**.

#. In the **Operation** column of **High Traffic Warning**, click **Edit**, and configure notification item parameters. For details, see :ref:`Table 2 <cfw_01_0166__table20810102320332>`.

   .. _cfw_01_0166__table20810102320332:

   .. table:: **Table 2** High traffic warning parameters

      +-----------------------------------+---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
      | Parameter                         | Description                                                                                                                                                                           |
      +===================================+=======================================================================================================================================================================================+
      | Description                       | An alarm is generated if the traffic reaches the specified percentage of the traffic processing capability you purchased.                                                             |
      +-----------------------------------+---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
      | Level                             | Select a percentage. When the maximum peak inbound or outbound traffic reaches the percentage of the traffic processing capability you purchased, an alarm notification is triggered. |
      |                                   |                                                                                                                                                                                       |
      |                                   | For example, you can select **70%**, **80%**, or **90%**.                                                                                                                             |
      |                                   |                                                                                                                                                                                       |
      |                                   | If this parameter is set to **80%**, an alarm notification is sent when the used traffic reaches 80% of the purchased traffic.                                                        |
      +-----------------------------------+---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
      | Notification Time                 | Select a time range for sending notifications.                                                                                                                                        |
      +-----------------------------------+---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
      | Trigger Condition                 | Once a day                                                                                                                                                                            |
      +-----------------------------------+---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
      | Recipient Group                   | Select a topic from the drop-down list to configure the endpoints for receiving alarm notifications.                                                                                  |
      +-----------------------------------+---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+

#. Click **OK**.

#. In the **Status** column of **High Traffic Warning**, click |image4| to enable it.

EIP Not Protected
-----------------

#. Log in to the management console.

#. In the navigation pane on the left, click |image5| and choose **Security** > **Cloud Firewall**. The **Dashboard** page will be displayed.

#. (Optional) Switch to another firewall instance: Select a firewall from the drop-down list in the upper left corner of the page.

#. In the navigation pane, choose **System Management** > **Notifications**.

#. In the **Operation** column of the **EIP Not Protected** alarm, click **Edit**, and configure notification item parameters. For details, see :ref:`Table 3 <cfw_01_0166__table19573228199>`.

   .. _cfw_01_0166__table19573228199:

   .. table:: **Table 3** Parameters of the alarm **EIP Not Protected**

      +-------------------+------------------------------------------------------------------------------------------------------+
      | Parameter         | Description                                                                                          |
      +===================+======================================================================================================+
      | Description       | This alarm indicates there are unprotected EIPs.                                                     |
      +-------------------+------------------------------------------------------------------------------------------------------+
      | Notification Time | Select a time range for sending notifications.                                                       |
      +-------------------+------------------------------------------------------------------------------------------------------+
      | Trigger Condition | Once a day                                                                                           |
      +-------------------+------------------------------------------------------------------------------------------------------+
      | Recipient Group   | Select a topic from the drop-down list to configure the endpoints for receiving alarm notifications. |
      +-------------------+------------------------------------------------------------------------------------------------------+

#. Click **OK**.

#. In the **Status** column of **EIP Not Protected**, click |image6| to enable it.

Related Operations
------------------

To add assets to the **EIP Not Protected** alarm whitelist, click **Add to Alarm Whitelist** in the **Operation** column of the alarm. Select EIPs, add them to the whitelist on the right, and click **OK**. The whitelisted EIPs will no longer trigger this alarm.

.. |image1| image:: /_static/images/en-us_image_0000001259322747.png
.. |image2| image:: /_static/images/en-us_image_0000001443711605.png
.. |image3| image:: /_static/images/en-us_image_0000001259322747.png
.. |image4| image:: /_static/images/en-us_image_0000001443792005.png
.. |image5| image:: /_static/images/en-us_image_0000001259322747.png
.. |image6| image:: /_static/images/en-us_image_0000001673130380.png
