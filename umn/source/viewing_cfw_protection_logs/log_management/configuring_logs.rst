:original_name: cfw_01_0141.html

.. _cfw_01_0141:

Configuring Logs
================

You can record attack event logs, access control logs, and traffic logs to Log Tank Service (LTS) and use these logs to quickly and efficiently perform real-time decision analysis, device O&M, and service trend analysis.

LTS analyzes and processes a large number of logs. It enables you to process logs in real-time, efficiently, and securely.

.. important::

   -  On the **Log Query** page, you can check and export log data of the last seven days. For details, see :ref:`Querying Logs <cfw_01_0139>`.
   -  LTS is billed by traffic and is billed separately from CFW.


Configuring Logs
----------------

#. Log in to the management console.
#. In the navigation pane on the left, click |image1| and choose **Security** > **Cloud Firewall**. The **Dashboard** page will be displayed.
#. (Optional) Switch to another firewall instance: Select a firewall from the drop-down list in the upper left corner of the page.
#. In the navigation pane on the left, choose **Log Audit** > **Log Management**. The Log Management page is displayed. Click **Configure LTS Synchronization**. Toggle on |image2| to enable the cloud log interconnection service.
#. Create log groups and log streams. For details, see **Log Tank Service > Getting Started > Creating Log Groups and Log Streams**.

   .. note::

      To make it easier for you to view, you are advised to:

      -  Add **-cfw** as the suffix when creating a log group.
      -  When creating log streams, add the suffixes **-attack**, **-access**, and **-flow** to attack event logs, access control logs, and traffic logs.

#. Select a created log group or log stream. Select a log group, enable and select log streams, and click **OK**.

   .. note::

      -  The formats of attack logs, access logs, and traffic logs are different. You need to configure different log streams for them.

      -  Attack logs: record attack alarm information, including the attack event type, protection rule, protection action, quintuple, and attack payload.

         Access logs: record information about the traffic that matches the ACL policy, including the matching time, quintuple, response action, and the matched access control rule.

         Traffic logs: record information about all traffic passing through the CFW, including the start time, end time, quintuple, number of bytes, and number of packets.

.. |image1| image:: /_static/images/en-us_image_0000001259322747.png
.. |image2| image:: /_static/images/en-us_image_0000001349643997.png
