:original_name: cfw_01_0247.html

.. _cfw_01_0247:

Managing Security Reports
=========================

This section describes how to manage security reports, including enabling, disabling, modifying, and deleting security reports.

Enabling/Disabling the Security Report Function
-----------------------------------------------

#. Log in to the management console.
#. In the navigation pane on the left, click |image1| and choose **Security** > **Cloud Firewall**. The **Dashboard** page will be displayed.
#. (Optional) Switch to another firewall instance: Select a firewall from the drop-down list in the upper left corner of the page.
#. In the navigation tree on the left, choose **System Management** > **Security Report**. The **Security Report** page is displayed.
#. Toggle on or off the switch in the upper right corner of the target report to change the status.

   -  |image2|: enabled
   -  |image3|: disabled

Modifying a Security Report
---------------------------

#. Log in to the management console.
#. In the navigation pane on the left, click |image4| and choose **Security** > **Cloud Firewall**. The **Dashboard** page will be displayed.
#. (Optional) Switch to another firewall instance: Select a firewall from the drop-down list in the upper left corner of the page.
#. In the navigation tree on the left, choose **System Management** > **Security Report**. The **Security Report** page is displayed.
#. Click **Edit** in the lower right corner of the target report to modify the report information.

   .. table:: **Table 1** Parameters of the security report template

      +-----------------------------------+-------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
      | Parameter                         | Description                                                                                                                                                             |
      +===================================+=========================================================================================================================================================================+
      | Report Name                       | Name of a security report                                                                                                                                               |
      +-----------------------------------+-------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
      | Report Type                       | -  **Daily**                                                                                                                                                            |
      |                                   |                                                                                                                                                                         |
      |                                   |    Statistical period: 00:00:00 to 24:00:00 every day                                                                                                                   |
      |                                   |                                                                                                                                                                         |
      |                                   |    A report will be sent to the recipients the day after it is generated.                                                                                               |
      |                                   |                                                                                                                                                                         |
      |                                   | -  **Weekly**                                                                                                                                                           |
      |                                   |                                                                                                                                                                         |
      |                                   |    Statistical period: 00:00:00 on Monday to 24:00:00 on Sunday                                                                                                         |
      |                                   |                                                                                                                                                                         |
      |                                   |    A report will be sent to the recipients at the specified time after it is generated.                                                                                 |
      +-----------------------------------+-------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
      | Report Schedule                   | When **Report Type** is set to **Daily** or **Weekly**, you need to set the report sending time. By default, the log report of the previous statistical period is sent. |
      +-----------------------------------+-------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
      | Recipient Group                   | Select a topic from the drop-down list to configure the endpoints for receiving the log report.                                                                         |
      +-----------------------------------+-------------------------------------------------------------------------------------------------------------------------------------------------------------------------+

#. Click **OK**. A security report is created.

Deleting a Security Report
--------------------------

#. Log in to the management console.
#. In the navigation pane on the left, click |image5| and choose **Security** > **Cloud Firewall**. The **Dashboard** page will be displayed.
#. (Optional) Switch to another firewall instance: Select a firewall from the drop-down list in the upper left corner of the page.
#. In the navigation tree on the left, choose **System Management** > **Security Report**. The **Security Report** page is displayed.
#. Click **Delete** in the lower right corner of the target report to delete the report.

.. |image1| image:: /_static/images/en-us_image_0000001259322747.png
.. |image2| image:: /_static/images/en-us_image_0000001790475961.png
.. |image3| image:: /_static/images/en-us_image_0000001743556254.png
.. |image4| image:: /_static/images/en-us_image_0000001259322747.png
.. |image5| image:: /_static/images/en-us_image_0000001259322747.png
