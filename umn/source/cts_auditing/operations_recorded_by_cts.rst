:original_name: cfw_01_0149.html

.. _cfw_01_0149:

Operations Recorded by CTS
==========================

CTS provides records of operations on CFW. With CTS, you can query, audit, and backtrack these operations. For details, see the *Cloud Trace Service User Guide*.

:ref:`CFW operations recorded by CTS <cfw_01_0149__table191031950132519>` lists details about the CFW operations on CTS.

.. _cfw_01_0149__table191031950132519:

.. table:: **Table 1** CFW operations recorded by CTS

   +-----------------------------------------------+------------------+---------------------------------+
   | Operation                                     | Resource Type    | Trace Name                      |
   +===============================================+==================+=================================+
   | EIP protection                                | cfw              | eipOperateProtectService        |
   +-----------------------------------------------+------------------+---------------------------------+
   | Enable EIP protection                         | cfw              | eipOperateProtectServiceEnable  |
   +-----------------------------------------------+------------------+---------------------------------+
   | Disable EIP protection                        | cfw              | eipOperateProtectServiceDisable |
   +-----------------------------------------------+------------------+---------------------------------+
   | Creating an ACL rule                          | acl              | addRuleAclService               |
   +-----------------------------------------------+------------------+---------------------------------+
   | Modify an ACL rule                            | acl              | updateRuleAclService            |
   +-----------------------------------------------+------------------+---------------------------------+
   | Delete an ACL rule                            | acl              | deleteRuleAclService            |
   +-----------------------------------------------+------------------+---------------------------------+
   | Configure ACL rule priority                   | acl              | setACLRulePriority              |
   +-----------------------------------------------+------------------+---------------------------------+
   | Create a blacklist                            | black_white_list | addBlackListService             |
   +-----------------------------------------------+------------------+---------------------------------+
   | Modify a blacklist                            | black_white_list | updateBlackListService          |
   +-----------------------------------------------+------------------+---------------------------------+
   | Delete a blacklist                            | black_white_list | deleteBlackListService          |
   +-----------------------------------------------+------------------+---------------------------------+
   | Create a whitelist                            | black_white_list | addWhiteListService             |
   +-----------------------------------------------+------------------+---------------------------------+
   | Modify a whitelist                            | black_white_list | updateWhiteListService          |
   +-----------------------------------------------+------------------+---------------------------------+
   | Delete a whitelist                            | black_white_list | deleteWhiteListService          |
   +-----------------------------------------------+------------------+---------------------------------+
   | Create an IP address group                    | address_group    | addAddressSetInfoService        |
   +-----------------------------------------------+------------------+---------------------------------+
   | Update an IP address group                    | address_group    | updateAddressSetInfoService     |
   +-----------------------------------------------+------------------+---------------------------------+
   | Delete an IP address group                    | address_group    | deleteAddressSetInfoService     |
   +-----------------------------------------------+------------------+---------------------------------+
   | Add a member to an IP address group           | address_group    | addAddressItemsService          |
   +-----------------------------------------------+------------------+---------------------------------+
   | Update a member in an IP address group.       | address_group    | updateAddressItemService        |
   +-----------------------------------------------+------------------+---------------------------------+
   | Delete a member from an IP address group      | address_group    | deleteAddressItemService        |
   +-----------------------------------------------+------------------+---------------------------------+
   | Create a service group                        | service_group    | addServiceSetService            |
   +-----------------------------------------------+------------------+---------------------------------+
   | Update a service group                        | service_group    | updateServiceSetService         |
   +-----------------------------------------------+------------------+---------------------------------+
   | Delete a service group                        | service_group    | deleteServiceSetService         |
   +-----------------------------------------------+------------------+---------------------------------+
   | Add a member to a service group               | service_group    | addServiceItemsService          |
   +-----------------------------------------------+------------------+---------------------------------+
   | Update a member in a service group            | service_group    | updateServiceItemService        |
   +-----------------------------------------------+------------------+---------------------------------+
   | Delete a member from a service group          | service_group    | deleteServiceItemService        |
   +-----------------------------------------------+------------------+---------------------------------+
   | Create an east-west CFW instance              | cfw_instance     | createEWFirewallInstance        |
   +-----------------------------------------------+------------------+---------------------------------+
   | Create a south-north CFW instance             | cfw_instance     | createSNFirewallInstance        |
   +-----------------------------------------------+------------------+---------------------------------+
   | Update a firewall                             | cfw_instance     | updateFirewallInstance          |
   +-----------------------------------------------+------------------+---------------------------------+
   | Delete a firewall                             | cfw_instance     | deleteFirewallInstance          |
   +-----------------------------------------------+------------------+---------------------------------+
   | Upgrade a firewall                            | cfw_instance     | upgradeFirewallInstance         |
   +-----------------------------------------------+------------------+---------------------------------+
   | Add a tag                                     | cfw_instance     | createTags                      |
   +-----------------------------------------------+------------------+---------------------------------+
   | Delete a tag                                  | cfw_instance     | deleteTags                      |
   +-----------------------------------------------+------------------+---------------------------------+
   | Freeze a firewall                             | cfw_instance     | freezeFirewallInstance          |
   +-----------------------------------------------+------------------+---------------------------------+
   | Update attack logs and deliver configurations | alarm_config     | updateAlarmConfig               |
   +-----------------------------------------------+------------------+---------------------------------+
   | Update a user's DNS server configurations     | dns_server       | updateDnsServer                 |
   +-----------------------------------------------+------------------+---------------------------------+
   | Create an east-west firewall                  | cfw              | createEastWestFirewall          |
   +-----------------------------------------------+------------------+---------------------------------+
   | Enable an east-west firewall                  | cfw              | enableEwFirewallProtect         |
   +-----------------------------------------------+------------------+---------------------------------+
   | Disable an east-west firewall                 | cfw              | disableEwFirewallProtect        |
   +-----------------------------------------------+------------------+---------------------------------+
   | Purchase a firewall                           | cfw              | addFirewallOrder                |
   +-----------------------------------------------+------------------+---------------------------------+
   | Delete a firewall                             | cfw              | deleteFirewall                  |
   +-----------------------------------------------+------------------+---------------------------------+
   | Upgrade a firewall                            | cfw              | changeFirewall                  |
   +-----------------------------------------------+------------------+---------------------------------+
   | Modify or create an IPS protection mode       | ips              | createOrUpdateIpsMode           |
   +-----------------------------------------------+------------------+---------------------------------+
   | Enable a virtual patch                        | ips              | enableVirtualPatches            |
   +-----------------------------------------------+------------------+---------------------------------+
   | Disable a virtual patch                       | ips              | disableVirtualPatches           |
   +-----------------------------------------------+------------------+---------------------------------+
   | Create log management configurations          | log_config       | createLogConfig                 |
   +-----------------------------------------------+------------------+---------------------------------+
   | Modify log management configurations          | log_config       | updateLogConfig                 |
   +-----------------------------------------------+------------------+---------------------------------+
   | Import an ACL                                 | import           | importCFW                       |
   +-----------------------------------------------+------------------+---------------------------------+
