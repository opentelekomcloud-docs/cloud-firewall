:original_name: cfw_01_0272.html

.. _cfw_01_0272:

Example 1: Allowing the Inbound Traffic from a Specified IP Address
===================================================================

This section describes how to allow access traffic from a specified IP address in the inbound direction. For more parameter settings, see :ref:`Adding Protection Rules to Block or Allow Traffic <cfw_01_0030>`.

Allowing the Inbound Traffic from a Specified IP Address
--------------------------------------------------------

Configure two protection rules. One of them blocks all traffic, as shown in :ref:`Figure 1 <cfw_01_0272__cfw_01_0030_fig15421538161515>`. Its priority is the lowest. The other allows the traffic of a specified IP address, as shown in :ref:`Figure 2 <cfw_01_0272__cfw_01_0030_fig1718831219247>`. Its priority is the highest.

.. _cfw_01_0272__cfw_01_0030_fig15421538161515:

.. figure:: /_static/images/en-us_image_0000001936832142.png
   :alt: **Figure 1** Blocking all traffic

   **Figure 1** Blocking all traffic

.. _cfw_01_0272__cfw_01_0030_fig1718831219247:

.. figure:: /_static/images/en-us_image_0000001936832146.png
   :alt: **Figure 2** Allowing a specified IP address

   **Figure 2** Allowing a specified IP address
