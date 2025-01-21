:original_name: cfw_01_0079.html

.. _cfw_01_0079:

Why Does a Protection Rule Not Take Effect?
===========================================

All Traffic Is Allowed Even If a Rule Is Configured to Allow Only Several EIPs
------------------------------------------------------------------------------

After EIP protection is enabled on CFW, the access control policy allows all traffic by default. If you want to allow traffic of only several EIPs, you need to configure a protection rule to block all traffic and set the lowest priority.

#. Log in to the management console.
#. In the navigation pane on the left, click |image1| and choose **Security** > **Cloud Firewall**. The **Dashboard** page will be displayed.
#. (Optional) Switch to another firewall instance: Select a firewall from the drop-down list in the upper left corner of the page.
#. In the navigation pane, choose **Access Control** > **Access Policies**. The **Access Policies** page is displayed. Click the **Internet Borders** or **Inter-VPC Borders** tab.

5. .. _cfw_01_0079__li15634535579:

   Configure a global blocking rule. Click **Add Rule**. Use the parameter settings shown in :ref:`Figure 1 <cfw_01_0079__fig15421538161515>` and configure other parameters as needed.

   .. _cfw_01_0079__fig15421538161515:

   .. figure:: /_static/images/en-us_image_0000001936832142.png
      :alt: **Figure 1** Blocking all traffic

      **Figure 1** Blocking all traffic

   .. note::

      You are advised to enable the rules after adding all required ones.

6. Configure an allow rule. For details about how to add a protection rule, see :ref:`Adding Protection Rules to Block or Allow Traffic <cfw_01_0030>`.

7. Set the priority of the global blocking rule in the :ref:`Step 5 <cfw_01_0079__li15634535579>` to the lowest. For details, see :ref:`Adjusting the Priority of a Protection Rule <cfw_01_0063>`.

8. Enable all rules. You are advised to enable the allow rules prior to the blocking rules.

Blocked IP Addresses Are Still Allowed Through Even If a Global Blocking Rule Is Configured
-------------------------------------------------------------------------------------------

The EIP protection rules configured on CFW are applied based on the EIP management list. If you have enabled global blocking (0.0.0.0/0) but the traffic of EIPs not in an allow rule is allowed through, check whether the EIPs are protected. For more information, see :ref:`Enabling Internet Border Traffic Protection <cfw_01_0031>`.

.. |image1| image:: /_static/images/en-us_image_0000001259322747.png
