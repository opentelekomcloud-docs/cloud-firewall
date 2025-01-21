:original_name: cfw_01_0085.html

.. _cfw_01_0085:

Configuring a DNS Server
========================

Select a default DNS server or add a DNS server IP address. The domain name protection policy will be delivered to the specified servers.

If the current account has multiple firewalls, the DNS resolution operation only applies to specified firewalls.

Constraints
-----------

A maximum of two DNS servers can be customized.


Configuring a DNS Server
------------------------

#. Log in to the management console.
#. In the navigation pane on the left, click |image1| and choose **Security** > **Cloud Firewall**. The **Dashboard** page will be displayed.
#. (Optional) Switch to another firewall instance: Select a firewall from the drop-down list in the upper left corner of the page.
#. In the navigation tree on the left, choose **System Management** > **DNS Resolution**.
#. Select the default DNS server or add a custom DNS server.

   .. note::

      Currently, only two specified DNS servers can be added.

#. Click **Apply**.

   .. note::

      If the current account has multiple firewalls, the DNS resolution operation only applies to specified firewalls.

.. |image1| image:: /_static/images/en-us_image_0000001259322747.png
