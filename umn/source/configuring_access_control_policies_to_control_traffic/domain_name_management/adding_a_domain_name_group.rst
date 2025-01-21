:original_name: cfw_01_0183.html

.. _cfw_01_0183:

Adding a Domain Name Group
==========================

A domain name group is a collection of multiple domain names or wildcard domain names. You can configure domain name groups to protect domains in batches.

The options are as follows:

-  **Application Domain Name Group**: Supports the protection for domain names or wildcard domain names. Application-layer protocols such as HTTP/HTTPS are supported. Domain names are used for matching.
-  **Network Domain Name Group**: Supports protection for one or multiple domain names. Applies to network-layer protocols and supports all protocols. The resolved IP addresses are used for matching.

Matching Policy
---------------

-  **Application Domain Name Group**: CFW compares the HOST field in sessions with the application domain names. If they are consistent, the corresponding protection rule is hit.

-  **Network Domain Name Group**: CFW obtains the IP addresses resolved by DNS every 15 seconds, if the four-tuple of a session matches the network domain name rule and the resolved address has been saved (that is, the IP address has been obtained from the DNS server), the corresponding protection rule is hit.

   A single domain name can resolve up to 1,000 IP addresses. Each domain group can resolve up to 1,500 IP addresses. If the number of resolution results reaches the upper limit, no domain names can be added to the domain group.

.. note::

   You are advised to use the application domain name group for the domain names that have a large number of mapping addresses or rapidly changing mapping results.

Constraints
-----------

-  The domain names in a domain name group can be referenced by protection rules for up to 40,000 times, and wildcard domain names can be referenced for up to 2,000 times.

**Application domain name group (layer 7 protocol parsing)**

-  A firewall instance can have up to 500 domain name groups.
-  A firewall instance can have up to 2,500 domain names.
-  A domain name group can have up to 1,500 domain names.

**Network domain name group (layer 4 protocol parsing)**

-  A firewall instance can have up to 1,000 domain names.
-  A network domain name group can have up to 15 domain names.
-  Each domain name group can resolve up to 1,500 IP addresses.
-  Each domain name can resolve up to 1,000 IP addresses.


Adding a Domain Name Group
--------------------------

#. Log in to the management console.

#. In the navigation pane on the left, click |image1| and choose **Security** > **Cloud Firewall**. The **Dashboard** page will be displayed.

#. (Optional) Switch to another firewall instance: Select a firewall from the drop-down list in the upper left corner of the page.

#. In the navigation pane, choose **Access Control** > **Object Groups**.

#. (Optional) To add a network domain group, click the **Network Domain Name Group** tab.

#. Click the **Domain Name Groups** tab. Click **Add Domain Name Group** and configure :ref:`parameters <cfw_01_0183__table12362103114169>`.

   .. _cfw_01_0183__table12362103114169:

   .. table:: **Table 1** Domain name group parameters

      +-----------------------------------+----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
      | Parameter                         | Description                                                                                                                                                                                        |
      +===================================+====================================================================================================================================================================================================+
      | Domain Name Group Type            | Application/Network                                                                                                                                                                                |
      +-----------------------------------+----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
      | Group Name                        | Name of a user-defined domain name group.                                                                                                                                                          |
      +-----------------------------------+----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
      | Description                       | (Optional) Enter remarks for the domain name group.                                                                                                                                                |
      +-----------------------------------+----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
      | Domain Name                       | Enter one or multiple domain names.                                                                                                                                                                |
      |                                   |                                                                                                                                                                                                    |
      |                                   | -  You can enter a multi-level single domain name (for example, top-level domain name **example.com** and level-2 domain name **www.example.com**) or a wildcard domain name (**\*.example.com**). |
      |                                   | -  Multiple domain names are separated by commas (,), semicolons (;), line breaks, or spaces.                                                                                                      |
      |                                   |                                                                                                                                                                                                    |
      |                                   | .. note::                                                                                                                                                                                          |
      |                                   |                                                                                                                                                                                                    |
      |                                   |    Domain names must be unique.                                                                                                                                                                    |
      +-----------------------------------+----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+

Adding a Domain Name to a Domain Group
--------------------------------------

#. Log in to the management console.

#. In the navigation pane on the left, click |image2| and choose **Security** > **Cloud Firewall**. The **Dashboard** page will be displayed.

#. (Optional) Switch to another firewall instance: Select a firewall from the drop-down list in the upper left corner of the page.

#. In the navigation pane, choose **Access Control** > **Object Groups**.

#. Click the **Domain Name Groups** tab. Click the name of a domain name group. The **Domain Name Groups** dialog box is displayed.

#. Click **Add Domain** and enter domain name information.

   You can click **Add** to add multiple domain names.

#. Confirm the information and click **OK**.

Related Operation
-----------------

-  Exporting domain name groups: Click **Export** above the list and select a data range.
-  Batch deleting domain names: Select domain names in the domain name list and click **Delete** above the list.

-  Editing a domain name group: Click the name of a domain name group and modify parameters.
-  A domain name group takes effect only after it is set in a protection rule. For more information, see :ref:`Adding Protection Rules to Block or Allow Traffic <cfw_01_0030>`.
-  Viewing the IP addresses resolved by a domain name group of the network domain name group type: Click a domain name group name to go to the **Basic Information** page, and click **IP address** in the **Operation** column of the domain name list.

.. |image1| image:: /_static/images/en-us_image_0000001259322747.png
.. |image2| image:: /_static/images/en-us_image_0000001259322747.png
