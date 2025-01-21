:original_name: cfw_01_0168.html

.. _cfw_01_0168:

Modifying the Protection Action of an Intrusion Prevention Rule
===============================================================

For rules in the basic defense rule library and the virtual patch rule library, you can manually modify their protection actions. After the modification, their actions do not change with the IPS protection mode.

If the rules in the rule library cannot meet your requirements, you can customize IPS signature rules. For details, see :ref:`Customizing IPS Signatures <cfw_01_0188>`.

Constraints
-----------

The restrictions on modifying an IPS rule are as follows:

-  The action of a manually modified rule remains unchanged even if **Protection Mode** is changed.
-  The constraints on manually modified actions are as follows:

   -  The actions of up to 3000 rules can be manually changed to observation.
   -  The actions of up to 3000 rules can be manually changed to interception.
   -  The actions of up to 128 rules can be manually changed to disabling.

.. _cfw_01_0168__section875111419156:

Default Actions of Rule Groups in Different Protection Modes
------------------------------------------------------------

+------------------------+---------+-----------------------------+-----------------------------+----------------------------+
| ``-``                  | Mode    | **Intercept mode - strict** | **Intercept mode - medium** | **Intercept mode - loose** |
+------------------------+---------+-----------------------------+-----------------------------+----------------------------+
| **Observe** rule group | Observe | Disable                     | Disable                     | Disable                    |
+------------------------+---------+-----------------------------+-----------------------------+----------------------------+
| **Strict** rule group  | Observe | Intercept                   | Disable                     | Disable                    |
+------------------------+---------+-----------------------------+-----------------------------+----------------------------+
| **Medium** rule group  | Observe | Intercept                   | Intercept                   | Disable                    |
+------------------------+---------+-----------------------------+-----------------------------+----------------------------+
| **Loose** rule group   | Observe | Intercept                   | Intercept                   | Intercept                  |
+------------------------+---------+-----------------------------+-----------------------------+----------------------------+

.. note::

   -  **Observe**: The firewall records the traffic that matches the current rule in :ref:`Attack Event Logs <cfw_01_0139__section1131659192010>` and does not block the traffic.
   -  **Intercept**: The firewall records the traffic that matches the current rule in :ref:`Attack Event Logs <cfw_01_0139__section1131659192010>` and blocks it.
   -  **Disable**: The firewall does not log or block the traffic that matches the current rule.

.. _cfw_01_0168__section204771329204015:

Modifying the Action of a Basic Protection Rule
-----------------------------------------------

#. Log in to the management console.
#. In the navigation pane on the left, click |image1| and choose **Security** > **Cloud Firewall**. The **Dashboard** page will be displayed.
#. (Optional) Switch to another firewall instance: Select a firewall from the drop-down list in the upper left corner of the page.
#. In the navigation pane, choose **Attack Defense** > **Intrusion Prevention**.
#. Click **View Effective Rules** under **Basic Protection**. The **Basic Protection** tab is displayed.
#. (Optional) To view the parameter details of a type of rules, set filter criteria in the input box above the list.
#. Click an action in the **Operation** column.

   -  **Observe**: The firewall logs the traffic that matches the current rule and does not block the traffic.
   -  **Intercept**: The firewall logs and blocks the traffic that matches the current rule.
   -  **Disable**: The firewall does not log or block the traffic that matches the current rule.

   .. note::

      -  The action of a manually modified rule remains unchanged even if **Protection Mode** is changed. To restore the default action, select a rule and click **Restore Default**.
      -  The constraints on manually modified actions are as follows:

         -  The actions of up to 3000 rules can be manually changed to observation.
         -  The actions of up to 3000 rules can be manually changed to interception.
         -  The actions of up to 128 rules can be manually changed to disabling.

Related Operations
------------------

-  Restoring the default actions of some rules: On the **Basic Protection** tab, select rules and click **Restore Default**.
-  Restoring the default actions of all rules: On the **Basic Protection** tab, select rules and click **Restore All Defaults**.

.. |image1| image:: /_static/images/en-us_image_0000001259322747.png
