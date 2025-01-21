:original_name: cfw_01_0275.html

.. _cfw_01_0275:

Example 4: Configuring SNAT Protection Rules
============================================

This section describes how to configure SNAT-based defense. For more parameter settings, see :ref:`Adding Protection Rules to Block or Allow Traffic <cfw_01_0030>`.

SNAT Protection Configuration
-----------------------------

Assume your private IP address is **10.1.1.2** and the external domain name accessed through the NAT gateway is **www.example.com**. Configure NAT protection as follows and set other parameters based on your deployment:

-  **Rule Type**: Select **NAT**.
-  **Direction**: Select **SNAT**.
-  **Source**: Select **IP address** and enter **10.1.1.2**.
-  **Destination**: Select **Domain Name/Domain Group** and **Network**, and enter **www.example.com**.
-  **Service**: Select **Service** and select **TCP/1-65535/1-65535** from the drop-down list.
