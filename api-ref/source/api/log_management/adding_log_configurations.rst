:original_name: AddLogConfig.html

.. _AddLogConfig:

Adding Log Configurations
=========================

Function
--------

This API is used to add log configurations.

URI
---

POST /v1/{project_id}/cfw/logs/configuration

.. table:: **Table 1** Path Parameters

   +------------+-----------+--------+----------------------------------------------------------------------------------------------------------------------------------------+
   | Parameter  | Mandatory | Type   | Description                                                                                                                            |
   +============+===========+========+========================================================================================================================================+
   | project_id | Yes       | String | Project ID, which can be obtained by calling an API or from the console. For details, see :ref:`Obtaining a Project ID <cfw_02_0015>`. |
   +------------+-----------+--------+----------------------------------------------------------------------------------------------------------------------------------------+

.. table:: **Table 2** Query Parameters

   +-----------------------+-----------+--------+------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
   | Parameter             | Mandatory | Type   | Description                                                                                                                                                                                                                                                                  |
   +=======================+===========+========+==============================================================================================================================================================================================================================================================================+
   | fw_instance_id        | Yes       | String | Firewall ID, which can be obtained by referring to :ref:`Obtaining a Firewall ID <cfw_02_0028>`.                                                                                                                                                                             |
   +-----------------------+-----------+--------+------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
   | enterprise_project_id | No        | String | Enterprise project ID, which is the ID of a project planned based on organizations. You can obtain the enterprise project ID by referring to :ref:`Obtaining an Enterprise Project ID <cfw_02_0027>`. If the enterprise project function is not enabled, the value is **0**. |
   +-----------------------+-----------+--------+------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+

Request Parameters
------------------

.. table:: **Table 3** Request header parameters

   +--------------+-----------+--------+---------------------------------------------------------------------------------------------------+
   | Parameter    | Mandatory | Type   | Description                                                                                       |
   +==============+===========+========+===================================================================================================+
   | X-Auth-Token | Yes       | String | User token. You can obtain the token by referring to :ref:`Obtaining a User Token <cfw_02_0029>`. |
   +--------------+-----------+--------+---------------------------------------------------------------------------------------------------+
   | Content-Type | Yes       | String | Content type. It can only be set to application/json.                                             |
   +--------------+-----------+--------+---------------------------------------------------------------------------------------------------+

.. table:: **Table 4** Request body parameters

   +------------------------------+-----------+---------+------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
   | Parameter                    | Mandatory | Type    | Description                                                                                                                                                                                                                                                |
   +==============================+===========+=========+============================================================================================================================================================================================================================================================+
   | fw_instance_id               | Yes       | String  | Firewall ID, which can be obtained by referring to :ref:`Obtaining a Firewall ID <cfw_02_0028>`.                                                                                                                                                           |
   +------------------------------+-----------+---------+------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
   | lts_enable                   | Yes       | Integer | Whether to enable LTS: 1 (yes), 0 (no). If the parameter is set to 1 then parameters lts_attack_log_stream_enable, lts_access_log_stream_enable, lts_flow_log_stream_enable must be mandatory.                                                             |
   +------------------------------+-----------+---------+------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
   | lts_log_group_id             | Yes       | String  | Log Tank Service (LTS) log group ID, which can be obtained by calling the API for querying all the log groups of an account in LTS. Find the value in **log_groups.log_group_id** (The period [.] is used to separate different levels of objects).        |
   +------------------------------+-----------+---------+------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
   | lts_attack_log_stream_id     | No        | String  | Attack log stream ID, which can be obtained by calling the API for querying all the log streams in a specified log group in LTS. Find the value in **log_streams.log_stream_id** (The period [.] is used to separate different levels of objects).         |
   +------------------------------+-----------+---------+------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
   | lts_attack_log_stream_enable | No        | Integer | Whether to enable the attack log stream: **1** (yes), **0** (no).                                                                                                                                                                                          |
   +------------------------------+-----------+---------+------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
   | lts_access_log_stream_id     | No        | String  | Access control log stream ID, which can be obtained by calling the API for querying all the log streams in a specified log group in LTS. Find the value in **log_streams.log_stream_id** (The period [.] is used to separate different levels of objects). |
   +------------------------------+-----------+---------+------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
   | lts_access_log_stream_enable | No        | Integer | Whether to enable the access control stream: **1** (yes), **0** (no).                                                                                                                                                                                      |
   +------------------------------+-----------+---------+------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
   | lts_flow_log_stream_id       | No        | String  | Traffic log ID, which can be obtained by calling the API for querying all the log streams in a specified log group in LTS. Find the value in **log_streams.log_stream_id** (The period [.] is used to separate different levels of objects).               |
   +------------------------------+-----------+---------+------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
   | lts_flow_log_stream_enable   | No        | Integer | Whether to enable the traffic log function: **1** (yes), **0** (no).                                                                                                                                                                                       |
   +------------------------------+-----------+---------+------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+

Response Parameters
-------------------

**Status code: 200**

.. table:: **Table 5** Response body parameters

   +-----------+--------+---------------------------------------------------------------------------+
   | Parameter | Type   | Description                                                               |
   +===========+========+===========================================================================+
   | data      | String | Return value for adding log configurations. The value is the firewall ID. |
   +-----------+--------+---------------------------------------------------------------------------+

Example Requests
----------------

Add log stream configurations for firewall 4d6c860a-0338-49e8-ac64-fcaeb4182ba5 in project 408972e72dcd4c1a9b033e955802a36b. The LTS group ID is 20282428-a8f9-4e75-8246-165e64cf8ba8. The access control log stream, traffic log stream, attack log stream, and LTS are disabled.

.. code-block::

   https://{Endpoint}/v1/408972e72dcd4c1a9b033e955802a36b/cfw/logs/configuration?fw_instance_id=4d6c860a-0338-49e8-ac64-fcaeb4182ba5&enterprise_project_id=default

   {
     "fw_instance_id" : "4d6c860a-0338-49e8-ac64-fcaeb4182ba5",
     "lts_enable" : 0,
     "lts_log_group_id" : "20282428-a8f9-4e75-8246-165e64cf8ba8",
     "lts_attack_log_stream_enable" : 0,
     "lts_access_log_stream_enable" : 0,
     "lts_flow_log_stream_enable" : 0
   }

Example Responses
-----------------

**Status code: 200**

Return value for adding log configurations.

.. code-block::

   {
     "data" : "4d6c860a-0338-49e8-ac64-fcaeb4182ba5"
   }

Status Codes
------------

=========== ===========================================
Status Code Description
=========== ===========================================
200         Return value for adding log configurations.
=========== ===========================================

Error Codes
-----------

See :ref:`Error Codes <errorcode>`.
