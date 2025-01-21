:original_name: cfw_01_0202.html

.. _cfw_01_0202:

Creating a Firewall (VPC Mode)
==============================

A VPC border firewall can collect statistics on the traffic between VPCs, helping you detect abnormal traffic. This section describes how to create a VPC border firewall.

Constraints
-----------

Only the professional edition supports VPC border firewalls.

Procedure
---------

#. Log in to the management console.
#. In the navigation pane on the left, click |image1| and choose **Security** > **Cloud Firewall**. The **Dashboard** page will be displayed.
#. (Optional) Switch to another firewall instance: Select a firewall from the drop-down list in the upper left corner of the page.
#. In the navigation pane, choose **Assets** > **Inter-VPC Border Firewalls**.
#. Click **Create Firewall**.
#. Configure a CIDR block. An inspection VPC will be automatically created by default.

   .. note::

      Pay attention to the following restrictions during network planning:

      -  After a firewall is created, its CIDR block cannot be modified.
      -  The CIDR block must meet the following requirements:

         -  Only private network address segments (10.0.0.0/8, 172.16.0.0/12, and 192.168.0.0/16) are supported. Otherwise, route conflicts may occur in public network access scenarios, such as SNAT.
         -  The CIDR block 10.6.0.0/16-10.7.0.0/16 is reserved for CFW and cannot be used.
         -  This CIDR block cannot overlap with the private CIDR block to be protected, or routing conflicts and protection failures may occur.

#. Click **OK**.

.. |image1| image:: /_static/images/en-us_image_0000001259322747.png
