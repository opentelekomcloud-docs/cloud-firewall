:original_name: cfw_01_0268.html

.. _cfw_01_0268:

How Do I Verify the Validity of an Outbound HTTP/HTTPS Domain Protection Rule?
==============================================================================

To verify the validity, perform the following steps:

#. Send an HTTP or HTTPS request.

   -  Method 1: Use the **curl** command. For example:

      .. code-block::

         curl -k "https://www.example.com"

   -  Method 2: Use a browser to access the domain name.

   .. caution::

      Do not run the **telnet** command to test the domain name.

      If the **telnet** command is used to test the domain name and port (for example, **telnet www.example.com 80**), only TCP handshake traffic is generated, and no complete HTTP or HTTPS requests will be simulated. In this case, the application type will be identified as unknown and will not hit the HTTP or HTTPS application policy.

#. Log in to the CFW management console and view the number of hits and log records of the protection rule. If new hits and records are found, the rule takes effect. If not, modify the protection rule in a timely manner.

   a. Choose **Access Control** > **Access Policies**. On the **Protection Rules** tab, view the number of rule hits.
   b. Choose **Log Audit** > **Log Query**. On the **Access Control Logs** tab, view the protection records of the rule.
