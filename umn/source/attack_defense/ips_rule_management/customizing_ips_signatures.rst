:original_name: cfw_01_0188.html

.. _cfw_01_0188:

Customizing IPS Signatures
==========================

You can configure network detection signature rules in CFW. CFW will detect threats in data traffic based on signatures.

HTTP, TCP, UDP, POP3, SMTP and FTP protocols can be configured in user-defined IPS signatures.

.. caution::

   User-defined signatures need to be specific. General signatures may match too much traffic and affect traffic forwarding performance.

Constraints
-----------

-  Only the professional edition supports custom IPS signatures.
-  A maximum of 500 features can be added.
-  Custom IPS signatures are not affected by the change of the basic protection mode.
-  **Content** can be set to **URI** only if **Direction** is set to **Client to server** and **Protocol Type** is set to **HTTP**.


Customizing IPS Signatures
--------------------------

#. Log in to the management console.

#. In the navigation pane on the left, click |image1| and choose **Security** > **Cloud Firewall**. The **Dashboard** page will be displayed.

#. (Optional) Switch to another firewall instance: Select a firewall from the drop-down list in the upper left corner of the page.

#. In the navigation pane, choose **Attack Defense** > **Intrusion Prevention**. Click **Check Rules** in the **Custom IPS Signature** area.

#. Click **Add Custom IPS Signature** in the upper right corner of the list. For more information, see :ref:`Table 1 <cfw_01_0188__table12964195445211>`.

   .. _cfw_01_0188__table12964195445211:

   .. table:: **Table 1** Custom IPS signature parameters

      +-----------------------------------+--------------------------------------------------------------------------------------------------------------------------------------------------------------------+
      | Parameter Name                    | Description                                                                                                                                                        |
      +===================================+====================================================================================================================================================================+
      | Name                              | Feature name.                                                                                                                                                      |
      +-----------------------------------+--------------------------------------------------------------------------------------------------------------------------------------------------------------------+
      | Risk Level                        | Risk level of the feature.                                                                                                                                         |
      +-----------------------------------+--------------------------------------------------------------------------------------------------------------------------------------------------------------------+
      | Rule Type                         | Rule type of the feature.                                                                                                                                          |
      +-----------------------------------+--------------------------------------------------------------------------------------------------------------------------------------------------------------------+
      | Affected Software                 | Affected software.                                                                                                                                                 |
      +-----------------------------------+--------------------------------------------------------------------------------------------------------------------------------------------------------------------+
      | OS                                | OS.                                                                                                                                                                |
      +-----------------------------------+--------------------------------------------------------------------------------------------------------------------------------------------------------------------+
      | Direction                         | Direction of the traffic matching the feature. Its value can be:                                                                                                   |
      |                                   |                                                                                                                                                                    |
      |                                   | -  **Any**: Any direction. Traffic in any direction that meets other specified conditions matches the current rule.                                                |
      |                                   | -  Server to client                                                                                                                                                |
      |                                   | -  Client to server                                                                                                                                                |
      +-----------------------------------+--------------------------------------------------------------------------------------------------------------------------------------------------------------------+
      | Protocol Type                     | Protocol type of the feature.                                                                                                                                      |
      +-----------------------------------+--------------------------------------------------------------------------------------------------------------------------------------------------------------------+
      | Source Type                       | Source port type. Its value can be:                                                                                                                                |
      |                                   |                                                                                                                                                                    |
      |                                   | -  **Any**: Any port type. All ports match this type.                                                                                                              |
      |                                   | -  **Include**                                                                                                                                                     |
      |                                   | -  **Exclude**                                                                                                                                                     |
      |                                   |                                                                                                                                                                    |
      |                                   | .. note::                                                                                                                                                          |
      |                                   |                                                                                                                                                                    |
      |                                   |    You are advised to select **Any**.                                                                                                                              |
      +-----------------------------------+--------------------------------------------------------------------------------------------------------------------------------------------------------------------+
      | Source Port                       | Set **Source Port** if **Source Type** is set to **Include** or **Exclude**.                                                                                       |
      |                                   |                                                                                                                                                                    |
      |                                   | -  You can set one or more ports. Use commas (,) to separate multiple ports. Example: **80,100**                                                                   |
      |                                   | -  You can also set a port range. Use hyphens (-) to separate ports, for example, 80-443.                                                                          |
      +-----------------------------------+--------------------------------------------------------------------------------------------------------------------------------------------------------------------+
      | Destination Type                  | Destination port type. Its value can be:                                                                                                                           |
      |                                   |                                                                                                                                                                    |
      |                                   | -  **Any**: Any port type. All ports match this type.                                                                                                              |
      |                                   | -  **Include**                                                                                                                                                     |
      |                                   | -  **Exclude**                                                                                                                                                     |
      |                                   |                                                                                                                                                                    |
      |                                   | .. note::                                                                                                                                                          |
      |                                   |                                                                                                                                                                    |
      |                                   |    You are advised to select **Any**.                                                                                                                              |
      +-----------------------------------+--------------------------------------------------------------------------------------------------------------------------------------------------------------------+
      | Destination Port                  | Set **Destination Port** if **Destination Type** is set to **Include** or **Exclude**.                                                                             |
      |                                   |                                                                                                                                                                    |
      |                                   | -  You can set one or more ports. Use commas (,) to separate multiple ports. Example: **80,100**                                                                   |
      |                                   |                                                                                                                                                                    |
      |                                   | -  You can also set a port range. Use hyphens (-) to separate ports, for example, 80-443.                                                                          |
      +-----------------------------------+--------------------------------------------------------------------------------------------------------------------------------------------------------------------+
      | Action                            | Action taken by the firewall when it detects traffic with the feature.                                                                                             |
      |                                   |                                                                                                                                                                    |
      |                                   | -  **Observe**: Attacks are detected and recorded in logs. For details about how to query logs, see :ref:`Querying Logs <cfw_01_0139>`.                            |
      |                                   | -  **Intercept**: Attacks are automatically blocked.                                                                                                               |
      |                                   |                                                                                                                                                                    |
      |                                   | .. note::                                                                                                                                                          |
      |                                   |                                                                                                                                                                    |
      |                                   |    Before you enable the **Intercept** mode, you are advised to select **Observe** first and check whether the attack logs are correct for a period of time.       |
      +-----------------------------------+--------------------------------------------------------------------------------------------------------------------------------------------------------------------+
      | Content                           | Content matching the feature rule.                                                                                                                                 |
      |                                   |                                                                                                                                                                    |
      |                                   | -  **Content**: content field that matches the feature, for example, **cfw**.                                                                                      |
      |                                   | -  **Content Option**: Select a rule for content matching.                                                                                                         |
      |                                   |                                                                                                                                                                    |
      |                                   |    -  **Hexadecimal**: The content must be in hexadecimal format. Example: 0x1F                                                                                    |
      |                                   |    -  **Case insensitive**: Match content without checking cases.                                                                                                  |
      |                                   |    -  **URL**: Match the fields that are consistent with the content in URLs.                                                                                      |
      |                                   |                                                                                                                                                                    |
      |                                   | -  **Relative Position** specifies the start position in a feature matching.                                                                                       |
      |                                   |                                                                                                                                                                    |
      |                                   |    -  **Head**: The start position depends on the **Offset** from the head. For example, if **Offset** is **10**, the content check starts from the eleventh bit.  |
      |                                   |                                                                                                                                                                    |
      |                                   |       .. note::                                                                                                                                                    |
      |                                   |                                                                                                                                                                    |
      |                                   |          If **Content Option** is set to **URL**, the matching position of the header starts from the end of the domain name (including the port number).          |
      |                                   |                                                                                                                                                                    |
      |                                   |          For example, if the URL is www.example.com/test and the **Offset** is **0**, the content check starts from the slash (/) following **com**.               |
      |                                   |                                                                                                                                                                    |
      |                                   |          If the URL is www.example.com:80/test and the **Offset** is **0**, the content check starts from the slash (/) after **80**.                              |
      |                                   |                                                                                                                                                                    |
      |                                   |    -  **After previous content**: Packet capture starts from the specified position.                                                                               |
      |                                   |                                                                                                                                                                    |
      |                                   |       Formula: Start position = Length of the previous **Content** field + Previous **Offset** + **Offset** + 1                                                    |
      |                                   |                                                                                                                                                                    |
      |                                   |       For example, if the previous content is **test**, the previous **offset** is 10, and the current offset is 5, the start position is the 20th (4+10+5+1) bit. |
      |                                   |                                                                                                                                                                    |
      |                                   | -  **Offset** specifies the start position of feature matching. For example, if the offset is 10, the start position is the eleventh bit.                          |
      |                                   | -  **Depth** specifies the end position of feature matching. For example, if the depth is 65,535, the end position is the 65,535th bit.                            |
      |                                   |                                                                                                                                                                    |
      |                                   | .. note::                                                                                                                                                          |
      |                                   |                                                                                                                                                                    |
      |                                   |    -  **Depth** must be greater than the length of the **Content** field.                                                                                          |
      |                                   |    -  Up to four items can be added to an IPS signature.                                                                                                           |
      +-----------------------------------+--------------------------------------------------------------------------------------------------------------------------------------------------------------------+

#. Click **OK**.

Related Operations
------------------

-  To copy an IPS feature, click **Copy** in the **Operation** column, modify parameters, and click **OK**.
-  To modify an IPS signature, click **Edit** in the **Operation** column.
-  To delete IPS signatures in batches, select signatures and click **Delete** above the list.
-  To modify actions in batches, select signatures and click **Observe** or **Intercept** above the list.

Follow-up Operations
--------------------

For details about the protection overview, see :ref:`Viewing Attack Defense Information on the Dashboard <cfw_01_0228>`. For details about logs, see :ref:`Attack Event Logs <cfw_01_0139__section1131659192010>`.

.. |image1| image:: /_static/images/en-us_image_0000001259322747.png
