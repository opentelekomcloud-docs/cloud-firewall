:original_name: cfw_01_0032.html

.. _cfw_01_0032:

Blocking Network Attacks
========================

CFW provides :ref:`attack defense <cfw_01_0200__section19642352202214>` to help you detect common network attacks.

Impacts on Services
-------------------

To change the protection mode, you are advised to enable the **Observe** mode and check false alarms for a period of time and then switch to the **Intercept** mode.

.. _cfw_01_0032__section385820543273:

Adjusting the IPS Protection Mode to Block Network Attacks
----------------------------------------------------------

#. Log in to the management console.
#. In the navigation pane on the left, click |image1| and choose **Security** > **Cloud Firewall**. The **Dashboard** page will be displayed.
#. (Optional) Switch to another firewall instance: Select a firewall from the drop-down list in the upper left corner of the page.
#. In the navigation pane, choose **Attack Defense** > **Intrusion Prevention**.
#. Select a proper protection mode.

   -  **Observe**: Attacks are detected and recorded in logs but are not intercepted.
   -  **Intercept**: Attacks and abnormal IP address access are automatically intercepted.

      -  **Intercept mode - loose**: The protection granularity is coarse. In this mode, only attacks with high threat and high certainty are blocked.
      -  **Intercept mode - moderate**: The protection granularity is medium. This mode meets protection requirements in most scenarios.
      -  **Intercept mode - strict**: The protection granularity is fine-grained, and all attack requests are intercepted.

   .. note::

      -  You are advised to use the **observe** mode for a period of time before using the **intercept** mode. For details about how to view attack event logs, see :ref:`Attack Event Logs <cfw_01_0139__section1131659192010>`.
      -  If packets are incorrectly blocked by a defense rule, you can modify the action of the rule in the basic defense rule library. For details, see :ref:`IPS Rule Management <cfw_01_0167>`.

.. _cfw_01_0032__section61321527141315:

Enabling Sensitive Directory Scan Defense
-----------------------------------------

#. Log in to the management console.
#. In the navigation pane on the left, click |image2| and choose **Security** > **Cloud Firewall**. The **Dashboard** page will be displayed.
#. (Optional) Switch to another firewall instance: Select a firewall from the drop-down list in the upper left corner of the page.
#. In the navigation pane, choose **Attack Defense** > **Intrusion Prevention**.
#. Click **Advanced**. In the **Sensitive Directory Scan Defense** area, click |image3| to enable protection.

   -  **Action**:

      -  **Observe**: If the firewall detects a sensitive directory scanning attack, it only records the attack in :ref:`Attack Event Logs <cfw_01_0139__section1131659192010>`.
      -  **Block session**: If the firewall detects a sensitive directory scan attack, it blocks the current session.
      -  **Block IP**: If CFW detects a sensitive directory scan attack, it blocks the attack IP address for a period of time.

         .. note::

            After **Block IP** is configured, CFW continuously blocks IP addresses. If address translation or proxy is involved, evaluate the impact of blocking IP addresses with caution.

   -  **Duration**: If **Action** is set to **Block IP**, you can set the blocking duration. The value range is 60s to 3,600s.
   -  **Threshold**: CFW performs the specified action if the scan frequency of a sensitive directory reaches this threshold.

.. _cfw_01_0032__section17909527114711:

Enabling Reverse Shell Defense
------------------------------

#. Log in to the management console.
#. In the navigation pane on the left, click |image4| and choose **Security** > **Cloud Firewall**. The **Dashboard** page will be displayed.
#. (Optional) Switch to another firewall instance: Select a firewall from the drop-down list in the upper left corner of the page.
#. In the navigation pane, choose **Attack Defense** > **Intrusion Prevention**.
#. Click **Advanced**. In the **Reverse Shell Defense** module, click |image5| to enable defense.

   -  **Action**:

      -  **Observe**: If the firewall detects a reverse shell attack, it only records the attack in :ref:`Attack Event Logs <cfw_01_0139__section1131659192010>`.
      -  **Block session**: If the firewall detects a reverse shell attack, it blocks the current session.
      -  **Block IP**: If CFW detects a reverse shell attack, it blocks the attack IP address for a period of time.

         .. note::

            After **Block IP** is configured, CFW continuously blocks IP addresses. If address translation or proxy is involved, evaluate the impact of blocking IP addresses with caution.

   -  **Duration**: If **Action** is set to **Block IP**, you can set the blocking duration. The value range is 60s to 3,600s.
   -  **Mode**:

      -  **Conservative**: coarse-grained protection. If a single session is attacked for four times, observation or interception is triggered. It ensures that no false positives are reported.
      -  **Sensitive**: fine-grained protection. If a single session is attacked for two times, observation or interception is triggered. It ensures that attacks can be detected and handled.

Follow-up Operations
--------------------

For details about the protection overview, see :ref:`Viewing Attack Defense Information on the Dashboard <cfw_01_0228>`. For details about logs, see :ref:`Attack Event Logs <cfw_01_0139__section1131659192010>`.

.. |image1| image:: /_static/images/en-us_image_0000001259322747.png
.. |image2| image:: /_static/images/en-us_image_0000001259322747.png
.. |image3| image:: /_static/images/en-us_image_0000001969790077.png
.. |image4| image:: /_static/images/en-us_image_0000001259322747.png
.. |image5| image:: /_static/images/en-us_image_0000001969671085.png
