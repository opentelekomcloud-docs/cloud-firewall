:original_name: cfw_01_0189.html

.. _cfw_01_0189:

Constraints and Limitations
===========================

This topic describes some limitations and constraints on using CFW.

CFW Usage Restrictions
----------------------

-  Only the services deployed on the cloud platform can be protected. Cross-cloud access is not supported.
-  Traffic protection supports EIPs, but does not support global EIPs or the EIPs bound to API Gateway.

Protection Policy Quota Limit
-----------------------------

-  Protection rules

   A maximum of 20,000 protection rules can be added to a firewall instance.

-  Blacklist/Whitelist

   -  A maximum of 2000 blacklist items can be added to a firewall instance.
   -  A maximum of 2000 whitelist items can be added to a firewall instance.

-  Groups

   -  IP address groups

      -  A firewall instance can have up to 3800 IP address groups.
      -  An IP address group can contain up to 640 IP addresses.
      -  A firewall instance can contain up to 30,000 IP addresses.

   -  Service groups

      -  A firewall instance can have up to 900 services.
      -  A firewall instance can have up to 512 service groups.
      -  A service group can have up to 64 services.

   -  Domain name groups

      -  The domain names in a domain name group can be referenced by protection rules for up to 40,000 times, and wildcard domain names can be referenced for up to 2,000 times.
      -  **Application domain name group (layer 7 protocol parsing)**

         -  A firewall instance can have up to 500 domain name groups.
         -  A firewall instance can have up to 2,500 domain names.
         -  A domain name group can have up to 1,500 domain names.

      -  **Network domain name group (layer 4 protocol parsing)**

         -  A firewall instance can have up to 1,000 domain names.
         -  A network domain name group can have up to 15 domain names.
         -  Each domain name group can resolve up to 1,500 IP addresses.
         -  Each domain name can resolve up to 1,000 IP addresses.

Restrictions on Basic IPS
-------------------------

-  Modifying the action of a basic protection rule

   -  The actions of up to 3000 rules can be manually changed to observation.
   -  The actions of up to 3000 rules can be manually changed to interception.
   -  The actions of up to 128 rules can be manually changed to disabling.

-  Custom IPS signature

   -  Only the professional edition supports custom IPS signatures.
   -  A maximum of 500 features can be added.

Restrictions on Logs
--------------------

-  CFW allows you to view log data of the last seven days. One or multiple types of logs can be recorded in LTS. You can view log data in the past 1 to 365 days.
-  Up to 100,000 records can be exported for a single log at a time.
