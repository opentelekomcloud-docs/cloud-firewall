:original_name: ListLogConfig.html

.. _ListLogConfig:

Obtaining Log Configurations
============================

Function
--------

This API is used to obtain log configurations.

URI
---

GET /v1/{project_id}/cfw/logs/configuration

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

Response Parameters
-------------------

**Status code: 200**

.. table:: **Table 4** Response body parameters

   +-----------+-------------------------------------------------------------------+---------------------+
   | Parameter | Type                                                              | Description         |
   +===========+===================================================================+=====================+
   | data      | :ref:`LogConfigDto <listlogconfig__response_logconfigdto>` object | Log configurations. |
   +-----------+-------------------------------------------------------------------+---------------------+

.. _listlogconfig__response_logconfigdto:

.. table:: **Table 5** LogConfigDto

   +------------------------------+---------+------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
   | Parameter                    | Type    | Description                                                                                                                                                                                                                                                |
   +==============================+=========+============================================================================================================================================================================================================================================================+
   | fw_instance_id               | String  | Firewall ID, which can be obtained by referring to :ref:`Obtaining a Firewall ID <cfw_02_0028>`.                                                                                                                                                           |
   +------------------------------+---------+------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
   | lts_enable                   | Integer | Whether to enable LTS: 1 (yes), 0 (no). If the parameter is set to 1 then parameters lts_attack_log_stream_enable, lts_access_log_stream_enable, lts_flow_log_stream_enable must be mandatory.                                                             |
   +------------------------------+---------+------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
   | lts_log_group_id             | String  | Log Tank Service (LTS) log group ID, which can be obtained by calling the API for querying all the log groups of an account in LTS. Find the value in **log_groups.log_group_id** (The period [.] is used to separate different levels of objects).        |
   +------------------------------+---------+------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
   | lts_attack_log_stream_id     | String  | Attack log stream ID, which can be obtained by calling the API for querying all the log streams in a specified log group in LTS. Find the value in **log_streams.log_stream_id** (The period [.] is used to separate different levels of objects).         |
   +------------------------------+---------+------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
   | lts_attack_log_stream_enable | Integer | Whether to enable the attack log stream: **1** (yes), **0** (no).                                                                                                                                                                                          |
   +------------------------------+---------+------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
   | lts_access_log_stream_id     | String  | Access control log stream ID, which can be obtained by calling the API for querying all the log streams in a specified log group in LTS. Find the value in **log_streams.log_stream_id** (The period [.] is used to separate different levels of objects). |
   +------------------------------+---------+------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
   | lts_access_log_stream_enable | Integer | Whether to enable the access control stream: **1** (yes), **0** (no).                                                                                                                                                                                      |
   +------------------------------+---------+------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
   | lts_flow_log_stream_id       | String  | Traffic log ID, which can be obtained by calling the API for querying all the log streams in a specified log group in LTS. Find the value in **log_streams.log_stream_id** (The period [.] is used to separate different levels of objects).               |
   +------------------------------+---------+------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
   | lts_flow_log_stream_enable   | Integer | Whether to enable the traffic log function: **1** (yes), **0** (no).                                                                                                                                                                                       |
   +------------------------------+---------+------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+

Example Requests
----------------

Query the log configuration of the firewall 4e113415-7811-4bb3-bf5e-eb835953f7d4 in project 408972e72dcd4c1a9b033e955802a36b.

.. code-block::

   https://{Endpoint}/v1/408972e72dcd4c1a9b033e955802a36b/cfw/logs/configuration?fw_instance_id=4e113415-7811-4bb3-bf5e-eb835953f7d4&enterprise_project_id=default

Example Responses
-----------------

**Status code: 200**

Return value for querying log configurations.

.. code-block::

   {
     "data" : {
       "fw_instance_id" : "4df2bcd1-6299-4fba-8e71-8d50ea807090",
       "lts_access_log_stream_enable" : 0,
       "lts_attack_log_stream_enable" : 0,
       "lts_enable" : 0,
       "lts_flow_log_stream_enable" : 0,
       "lts_log_group_id" : "d783ce42-7f56-4c2d-9a96-b1043d016f5a"
     }
   }

Status Codes
------------

=========== =============================================
Status Code Description
=========== =============================================
200         Return value for querying log configurations.
=========== =============================================

Error Codes
-----------

See :ref:`Error Codes <errorcode>`.
