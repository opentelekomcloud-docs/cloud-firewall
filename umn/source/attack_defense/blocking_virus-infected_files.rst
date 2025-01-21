:original_name: cfw_01_0195.html

.. _cfw_01_0195:

Blocking Virus-infected Files
=============================

The anti-virus function identifies and processes virus files through virus feature detection to prevent data damage, permission change, and system breakdown caused by virus files.

The antivirus function can check access via HTTP, SMTP, POP3, FTP, IMAP4, and SMB.

Specification Limitations
-------------------------

Antivirus is available only in the professional edition.

Enabling Antivirus to Block Virus-infected Files
------------------------------------------------

#. Log in to the management console.
#. In the navigation pane on the left, click |image1| and choose **Security** > **Cloud Firewall**. The **Dashboard** page will be displayed.
#. (Optional) Switch to another firewall instance: Select a firewall from the drop-down list in the upper left corner of the page.
#. In the navigation pane, choose **Attack Defense** > **Antivirus**.
#. Click |image2| to enable antivirus.

   .. note::

      After antivirus is enabled, **Current Action** is **Disable** by default. For details about how to change the defense action, see :ref:`Modifying the Virus Defense Action for Better Protection Effect <cfw_01_0195__section115051117231>`.

.. _cfw_01_0195__section115051117231:

Modifying the Virus Defense Action for Better Protection Effect
---------------------------------------------------------------

#. Log in to the management console.
#. In the navigation pane on the left, click |image3| and choose **Security** > **Cloud Firewall**. The **Dashboard** page will be displayed.
#. (Optional) Switch to another firewall instance: Select a firewall from the drop-down list in the upper left corner of the page.
#. In the navigation pane, choose **Attack Defense** > **Antivirus**.
#. Click an action in the **Operation** column of a rule.

   -  **Observe**: The firewall checks the traffic of a protocol. If attack traffic is detected, the firewall records it in :ref:`attack event logs <cfw_01_0139__section1131659192010>` but does not block it.
   -  **Block**: The firewall checks the traffic of a protocol. If attack traffic is detected, the firewall records it in :ref:`attack event logs <cfw_01_0139__section1131659192010>` and blocks it.
   -  **Disable**: The firewall does not perform virus checks on the traffic of a protocol.

Follow-up Operations
--------------------

For details about the protection overview, see :ref:`Viewing Attack Defense Information on the Dashboard <cfw_01_0228>`. For details about logs, see :ref:`Attack Event Logs <cfw_01_0139__section1131659192010>`.

.. |image1| image:: /_static/images/en-us_image_0000001259322747.png
.. |image2| image:: /_static/images/en-us_image_0000001617930157.png
.. |image3| image:: /_static/images/en-us_image_0000001259322747.png
