:original_name: cfw_01_0136.html

.. _cfw_01_0136:

CFW Monitored Metrics
=====================

Description
-----------

This topic describes metrics reported by CFW to Cloud Eye as well as their namespaces. You can use Cloud Eye to query the metrics of the monitored object and alarms generated for CFW.

Namespace
---------

SYS.CFW

.. note::

   A namespace is an abstract collection of resources and objects. Multiple namespaces can be created in a single cluster with the data isolated from each other. This enables namespaces to share the same cluster services without affecting each other.

Metrics
-------

.. table:: **Table 1** CFW metrics

   +------------------------------------------+-----------------------------------------------------+-------------------------------------------------------------------------------------+-------------------+------------------+------------------------------+
   | Metric ID                                | Metric Name                                         | Description                                                                         | Value Range       | Monitored Object | Monitoring Interval (Minute) |
   +==========================================+=====================================================+=====================================================================================+===================+==================+==============================+
   | used_protection_bandwidth                | Boundary Protection Bandwidth Usage (Mbps)          | Used Internet bandwidth detected by CFW in the last 5 minutes                       | >= 0              | CFW              | 5                            |
   |                                          |                                                     |                                                                                     |                   |                  |                              |
   |                                          |                                                     | Unit: KB/s                                                                          | Value type: Float |                  |                              |
   +------------------------------------------+-----------------------------------------------------+-------------------------------------------------------------------------------------+-------------------+------------------+------------------------------+
   | protection_bandwidth_usage               | Boundary Protection Bandwidth Usage (%)             | Internet bandwidth usage rate detected by CFW within 5 minutes.                     | >= 0              | CFW              | 5                            |
   |                                          |                                                     |                                                                                     |                   |                  |                              |
   |                                          |                                                     | Unit: %                                                                             | Value type: Float |                  |                              |
   |                                          |                                                     |                                                                                     |                   |                  |                              |
   |                                          |                                                     | Usage rate = Use bandwidth/Percentage of the used bandwidth to the bandwidth quota. |                   |                  |                              |
   +------------------------------------------+-----------------------------------------------------+-------------------------------------------------------------------------------------+-------------------+------------------+------------------------------+
   | internet_protection_bandwidth_usage      | Internet Boundary Protection Bandwidth Usage (Mbps) | Bandwidth usage (Mbps) for protection at the Internet boundary.                     | >= 0              | CFW              | Every minute                 |
   |                                          |                                                     |                                                                                     |                   |                  |                              |
   |                                          |                                                     | Unit: bit/s                                                                         | Value type: Float |                  |                              |
   +------------------------------------------+-----------------------------------------------------+-------------------------------------------------------------------------------------+-------------------+------------------+------------------------------+
   | vpc_protection_bandwidth_usage           | Inter-VPC Protection Bandwidth Usage (Mbps)         | Bandwidth usage (Mbps) for inter-VPC protection.                                    | >= 0              | CFW              | Every minute                 |
   |                                          |                                                     |                                                                                     |                   |                  |                              |
   |                                          |                                                     | Unit: bit/s                                                                         | Value type: Float |                  |                              |
   +------------------------------------------+-----------------------------------------------------+-------------------------------------------------------------------------------------+-------------------+------------------+------------------------------+
   | internet_protection_bandwidth_usage_rate | Internet Boundary Protection Bandwidth Usage (%)    | Bandwidth usage (%) for protection at the Internet boundary.                        | >= 0              | CFW              | Every minute                 |
   |                                          |                                                     |                                                                                     |                   |                  |                              |
   |                                          |                                                     | Unit: %                                                                             | Value type: Float |                  |                              |
   +------------------------------------------+-----------------------------------------------------+-------------------------------------------------------------------------------------+-------------------+------------------+------------------------------+
   | vpc_protection_bandwidth_usage_rate      | Inter-VPC Protection Bandwidth Usage (%)            | Bandwidth usage (%) for inter-VPC protection.                                       | >= 0              | CFW              | Every minute                 |
   |                                          |                                                     |                                                                                     |                   |                  |                              |
   |                                          |                                                     | Unit: %                                                                             | Value type: Float |                  |                              |
   +------------------------------------------+-----------------------------------------------------+-------------------------------------------------------------------------------------+-------------------+------------------+------------------------------+
   | internet_protection_pps                  | Internet Boundary Firewall PPS                      | PPS of protected objects at the Internet boundary.                                  | >= 0              | CFW              | Every minute                 |
   |                                          |                                                     |                                                                                     |                   |                  |                              |
   |                                          |                                                     | Unit: N/A                                                                           | Value type: Float |                  |                              |
   +------------------------------------------+-----------------------------------------------------+-------------------------------------------------------------------------------------+-------------------+------------------+------------------------------+
   | vpc_protection_pps                       | Inter-VPC Firewall PPS                              | PPS of inter-VPC protected objects.                                                 | >= 0              | CFW              | Every minute                 |
   |                                          |                                                     |                                                                                     |                   |                  |                              |
   |                                          |                                                     | Unit: N/A                                                                           | Value type: Float |                  |                              |
   +------------------------------------------+-----------------------------------------------------+-------------------------------------------------------------------------------------+-------------------+------------------+------------------------------+
   | ips_hit_count                            | IPS Rule Hits                                       | Number of times that traffic matches IPS rules.                                     | >= 0              | CFW              | Every minute                 |
   |                                          |                                                     |                                                                                     |                   |                  |                              |
   |                                          |                                                     |                                                                                     | Value type: Int   |                  |                              |
   +------------------------------------------+-----------------------------------------------------+-------------------------------------------------------------------------------------+-------------------+------------------+------------------------------+
   | ips_deny_count                           | IPS Rule Block Count                                | Number of times that traffic is blocked based on IPS rules.                         | >= 0              | CFW              | Every minute                 |
   |                                          |                                                     |                                                                                     |                   |                  |                              |
   |                                          |                                                     | Unit: N/A                                                                           | Value type: Int   |                  |                              |
   +------------------------------------------+-----------------------------------------------------+-------------------------------------------------------------------------------------+-------------------+------------------+------------------------------+
   | acl_hit_count                            | ACL Rule Hits                                       | Number of times that traffic matches ACL rules.                                     | >= 0              | CFW              | Every minute                 |
   |                                          |                                                     |                                                                                     |                   |                  |                              |
   |                                          |                                                     | Unit: N/A                                                                           | Value type: Int   |                  |                              |
   +------------------------------------------+-----------------------------------------------------+-------------------------------------------------------------------------------------+-------------------+------------------+------------------------------+
   | acl_deny_count                           | ACL Rule Block Count                                | Number of times that traffic is blocked based on ACL rules.                         | >= 0              | CFW              | Every minute                 |
   |                                          |                                                     |                                                                                     |                   |                  |                              |
   |                                          |                                                     | Unit: N/A                                                                           | Value type: Int   |                  |                              |
   +------------------------------------------+-----------------------------------------------------+-------------------------------------------------------------------------------------+-------------------+------------------+------------------------------+

Dimension
---------

============== ===========
Key            Value
============== ===========
fw_instance_id Firewall ID
============== ===========
