:original_name: cfw_01_0071.html

.. _cfw_01_0071:

Deleting a User-defined Service Group
=====================================

A service group is a collection of ports. You can use service groups to easily protect high-risk ports and manage access rules, free from repeated editing of access rules.

This section describes how to delete a user-defined service group.

Constraints
-----------

The service group referenced by a protection rule cannot be deleted. Modify or delete the rule first.


Deleting a User-defined Service Group
-------------------------------------

#. Log in to the management console.
#. In the navigation pane on the left, click |image1| and choose **Security** > **Cloud Firewall**. The **Dashboard** page will be displayed.
#. (Optional) Switch to another firewall instance: Select a firewall from the drop-down list in the upper left corner of the page.
#. In the navigation pane, choose **Access Control** > **Object Groups**.
#. Click the **Service Groups** tab. In the **Operation** column of a service group, click **Delete**.
#. In the displayed dialog box, confirm the information, enter **DELETE**, and click **OK**.

   .. warning::

      Deleted service groups cannot be restored. Exercise caution when performing this operation.

.. |image1| image:: /_static/images/en-us_image_0000001259322747.png
