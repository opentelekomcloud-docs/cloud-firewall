:original_name: cfw_01_0245.html

.. _cfw_01_0245:

Creating a Security Report
==========================

You can obtain security reports to learn about the security status of your assets in a timely manner. CFW sends log reports to you based on the time period and receiving mode you configured.

This section describes how to create a security report.

Constraints
-----------

-  Up to 10 security reports can be created for a CFW instance.
-  A security report is retained for only three months. You are advised to periodically download security reports for audit.
-  A custom security report cannot be modified. If you need to modify a custom security report, delete it and create a new one.


Creating a Security Report
--------------------------

#. Log in to the management console.

#. In the navigation pane on the left, click |image1| and choose **Security** > **Cloud Firewall**. The **Dashboard** page will be displayed.

#. (Optional) Switch to another firewall instance: Select a firewall from the drop-down list in the upper left corner of the page.

#. In the navigation tree on the left, choose **System Management** > **Security Report**. The **Security Report** page is displayed.

#. Click **Create Template**. For details about the parameters, see :ref:`Parameters of the security report template <cfw_01_0245__table23531501379>`.

   .. _cfw_01_0245__table23531501379:

   .. table:: **Table 1** Parameters of the security report template

      +-----------------------------------+-------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
      | Parameter                         | Description                                                                                                                                                             |
      +===================================+=========================================================================================================================================================================+
      | Report Name                       | Name of the custom security report                                                                                                                                      |
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
      |                                   |                                                                                                                                                                         |
      |                                   | -  **Custom**: Customize a time range.                                                                                                                                  |
      |                                   |                                                                                                                                                                         |
      |                                   |    **Statistical Period**: Configure a statistical period for your report.                                                                                              |
      |                                   |                                                                                                                                                                         |
      |                                   |    A report will be sent to the specified recipients after it is generated.                                                                                             |
      +-----------------------------------+-------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
      | Statistical Period                | If **Report Type** is set to **Custom**, you need to set **Statistical Period**.                                                                                        |
      +-----------------------------------+-------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
      | Report Schedule                   | When **Report Type** is set to **Daily** or **Weekly**, you need to set the report sending time. By default, the log report of the previous statistical period is sent. |
      |                                   |                                                                                                                                                                         |
      |                                   | .. note::                                                                                                                                                               |
      |                                   |                                                                                                                                                                         |
      |                                   |    To ensure correctness, the report sending time may be delayed.                                                                                                       |
      +-----------------------------------+-------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
      | Recipient Group                   | Select a topic from the drop-down list to configure the endpoints for receiving the log report.                                                                         |
      +-----------------------------------+-------------------------------------------------------------------------------------------------------------------------------------------------------------------------+

#. Click **OK**. A security report is created.

.. |image1| image:: /_static/images/en-us_image_0000001259322747.png
