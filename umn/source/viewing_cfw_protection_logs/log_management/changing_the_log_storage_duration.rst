:original_name: cfw_01_0142.html

.. _cfw_01_0142:

Changing the Log Storage Duration
=================================

Logs are stored for seven days by default. The storage duration can be set to 1 to 365 days. Logs that exceed the storage duration will be automatically deleted. For log data that needs to be stored for a long time (log persistence), LTS can dump the logs to OBS for medium- and long-term storage.


Changing the Log Storage Duration
---------------------------------

#. Dump logs to LTS. For details, see :ref:`Configuring Logs <cfw_01_0141>`.
#. Log in to the management console.
#. In the navigation pane on the left, click |image1| and choose **Security** > **Cloud Firewall**. The **Dashboard** page will be displayed.
#. (Optional) Switch to another firewall instance: Select a firewall from the drop-down list in the upper left corner of the page.
#. In the navigation pane on the left, choose **Log Audit** > **Log Management**. On the displayed page, click **Modify Log Storage Duration**.

   .. note::

      -  Logs can be stored for 1 to 365 days. Logs that exceed the specified storage duration are automatically deleted.
      -  The longer the storage duration, the larger the occupied storage. For details about how to dump logs to other cloud services for long-term storage, see **Log Tank Service User Guide> Log Transfer**.

.. |image1| image:: /_static/images/en-us_image_0000001259322747.png
