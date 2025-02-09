:original_name: ListAccessControlLogs.html

.. _ListAccessControlLogs:

Querying Access Control Logs
============================

Function
--------

This API is used to query access control logs.

URI
---

GET /v1/{project_id}/cfw/logs/access-control

.. table:: **Table 1** Path Parameters

   +------------+-----------+--------+----------------------------------------------------------------------------------------------------------------------------------------+
   | Parameter  | Mandatory | Type   | Description                                                                                                                            |
   +============+===========+========+========================================================================================================================================+
   | project_id | Yes       | String | Project ID, which can be obtained by calling an API or from the console. For details, see :ref:`Obtaining a Project ID <cfw_02_0015>`. |
   +------------+-----------+--------+----------------------------------------------------------------------------------------------------------------------------------------+

.. table:: **Table 2** Query Parameters

   +-----------------------+-----------+---------+------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
   | Parameter             | Mandatory | Type    | Description                                                                                                                                                                                                                                                                  |
   +=======================+===========+=========+==============================================================================================================================================================================================================================================================================+
   | fw_instance_id        | Yes       | String  | Firewall ID, which can be obtained by referring to :ref:`Obtaining a Firewall ID <cfw_02_0028>`.                                                                                                                                                                             |
   +-----------------------+-----------+---------+------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
   | rule_id               | No        | String  | Rule ID, which can be obtained by calling the :ref:`API for querying protection rules <listaclrules>`. Find the value in **data.records.rule_id** (The period [.] is used to separate different levels of objects).                                                          |
   +-----------------------+-----------+---------+------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
   | start_time            | Yes       | Long    | Start time, in milliseconds. The value is a timestamp, for example, 1718936272648.                                                                                                                                                                                           |
   +-----------------------+-----------+---------+------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
   | end_time              | Yes       | Long    | End time, in milliseconds. The value is a timestamp, for example, 1718936272648.                                                                                                                                                                                             |
   +-----------------------+-----------+---------+------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
   | src_ip                | No        | String  | Source IP address.                                                                                                                                                                                                                                                           |
   +-----------------------+-----------+---------+------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
   | src_port              | No        | Integer | Source port.                                                                                                                                                                                                                                                                 |
   +-----------------------+-----------+---------+------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
   | dst_ip                | No        | String  | Destination IP address.                                                                                                                                                                                                                                                      |
   +-----------------------+-----------+---------+------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
   | dst_port              | No        | Integer | Destination port.                                                                                                                                                                                                                                                            |
   +-----------------------+-----------+---------+------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
   | protocol              | No        | String  | Protocol type. Its value can be **TCP**, **UDP**, **ICMP**, or **ICMPv6**.                                                                                                                                                                                                   |
   +-----------------------+-----------+---------+------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
   | app                   | No        | String  | Rule application type. Its value can be **HTTP**, **HTTPS**, **TLS1**, **DNS**, **SSH**, **MYSQL**, **SMTP**, **RDP**, **RDPS**, **VNC**, **POP3**, **IMAP4**, **SMTPS**, **POP3S**, **FTPS**, **ANY**, or **BGP**.                                                          |
   +-----------------------+-----------+---------+------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
   | log_id                | No        | String  | Document ID. For the first page, its value is null. For other pages, its value can be the **log_id** of the last record in the last query.                                                                                                                                   |
   +-----------------------+-----------+---------+------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
   | next_date             | No        | Integer | Next date. For the first page, its value is null. For other pages, its value can be the **start_time** of the last record in the last query.                                                                                                                                 |
   +-----------------------+-----------+---------+------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
   | offset                | No        | Integer | Offset, which specifies the start position of the record to be returned. The value must be a number greater than 0. For the first page, its value is null. For other pages, its value is not null.                                                                           |
   +-----------------------+-----------+---------+------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
   | limit                 | Yes       | Integer | Number of records displayed on each page. The value ranges from 1 to 1024.                                                                                                                                                                                                   |
   +-----------------------+-----------+---------+------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
   | log_type              | No        | String  | Log type. Its value can be **internet**, **vpc**, or **nat**.                                                                                                                                                                                                                |
   +-----------------------+-----------+---------+------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
   | enterprise_project_id | No        | String  | Enterprise project ID, which is the ID of a project planned based on organizations. You can obtain the enterprise project ID by referring to :ref:`Obtaining an Enterprise Project ID <cfw_02_0027>`. If the enterprise project function is not enabled, the value is **0**. |
   +-----------------------+-----------+---------+------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
   | dst_host              | No        | String  | Destination host.                                                                                                                                                                                                                                                            |
   +-----------------------+-----------+---------+------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
   | rule_name             | No        | String  | Rule name.                                                                                                                                                                                                                                                                   |
   +-----------------------+-----------+---------+------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
   | action                | No        | String  | Action. Its value can be **permit** or **deny**.                                                                                                                                                                                                                             |
   +-----------------------+-----------+---------+------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
   | src_region_name       | No        | String  | Source region name.                                                                                                                                                                                                                                                          |
   +-----------------------+-----------+---------+------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
   | dst_region_name       | No        | String  | Destination region name.                                                                                                                                                                                                                                                     |
   +-----------------------+-----------+---------+------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
   | src_province_name     | No        | String  | Source province name.                                                                                                                                                                                                                                                        |
   +-----------------------+-----------+---------+------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
   | dst_province_name     | No        | String  | Destination province name.                                                                                                                                                                                                                                                   |
   +-----------------------+-----------+---------+------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
   | src_city_name         | No        | String  | Source city name.                                                                                                                                                                                                                                                            |
   +-----------------------+-----------+---------+------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
   | dst_city_name         | No        | String  | Destination city name.                                                                                                                                                                                                                                                       |
   +-----------------------+-----------+---------+------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+

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

   +-----------+-----------------------------------------------------------+-------------------------------------------------+
   | Parameter | Type                                                      | Description                                     |
   +===========+===========================================================+=================================================+
   | data      | :ref:`data <listaccesscontrollogs__response_data>` object | Returned data for querying access control logs. |
   +-----------+-----------------------------------------------------------+-------------------------------------------------+

.. _listaccesscontrollogs__response_data:

.. table:: **Table 5** data

   +-----------+---------------------------------------------------------------------------+----------------------------------------------------------------------------+
   | Parameter | Type                                                                      | Description                                                                |
   +===========+===========================================================================+============================================================================+
   | total     | Integer                                                                   | Query the total number of access control logs.                             |
   +-----------+---------------------------------------------------------------------------+----------------------------------------------------------------------------+
   | limit     | Integer                                                                   | Number of records displayed on each page. The value ranges from 1 to 1024. |
   +-----------+---------------------------------------------------------------------------+----------------------------------------------------------------------------+
   | records   | Array of :ref:`records <listaccesscontrollogs__response_records>` objects | Query access control logs.                                                 |
   +-----------+---------------------------------------------------------------------------+----------------------------------------------------------------------------+

.. _listaccesscontrollogs__response_records:

.. table:: **Table 6** records

   +-------------------+---------+----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
   | Parameter         | Type    | Description                                                                                                                                                                                                                |
   +===================+=========+============================================================================================================================================================================================================================+
   | action            | String  | Action: **0** (allow), **1** (deny).                                                                                                                                                                                       |
   +-------------------+---------+----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
   | rule_name         | String  | Rule name.                                                                                                                                                                                                                 |
   +-------------------+---------+----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
   | rule_id           | String  | Rule ID.                                                                                                                                                                                                                   |
   +-------------------+---------+----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
   | hit_time          | Long    | Hit time, in milliseconds. The value is a timestamp, for example, 1718936272648.                                                                                                                                           |
   +-------------------+---------+----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
   | src_region_id     | String  | Source region ID.                                                                                                                                                                                                          |
   +-------------------+---------+----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
   | src_region_name   | String  | Source region name.                                                                                                                                                                                                        |
   +-------------------+---------+----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
   | dst_region_id     | String  | Destination region ID.                                                                                                                                                                                                     |
   +-------------------+---------+----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
   | dst_region_name   | String  | Destination region name.                                                                                                                                                                                                   |
   +-------------------+---------+----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
   | log_id            | String  | Document ID.                                                                                                                                                                                                               |
   +-------------------+---------+----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
   | src_ip            | String  | Source IP address.                                                                                                                                                                                                         |
   +-------------------+---------+----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
   | src_port          | Integer | Source port.                                                                                                                                                                                                               |
   +-------------------+---------+----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
   | dst_ip            | String  | Destination IP address.                                                                                                                                                                                                    |
   +-------------------+---------+----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
   | dst_port          | Integer | Destination port.                                                                                                                                                                                                          |
   +-------------------+---------+----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
   | protocol          | String  | Protocol type: **6** (TCP), **17** (UDP), **1** (ICMP), **58** (ICMPv6), or **-1** (any). It cannot be left blank when **type** is set to **0** (manual), and can be left blank when **type** is set to **1** (automatic). |
   +-------------------+---------+----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
   | app               | String  | Rule application type. Its value can be **HTTP**, **HTTPS**, **TLS1**, **DNS**, **SSH**, **MYSQL**, **SMTP**, **RDP**, **RDPS**, **VNC**, **POP3**, **IMAP4**, **SMTPS**, **POP3S**, **FTPS**, **ANY**, or **BGP**.        |
   +-------------------+---------+----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
   | dst_host          | String  | Destination host.                                                                                                                                                                                                          |
   +-------------------+---------+----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
   | src_province_id   | String  | Source province ID.                                                                                                                                                                                                        |
   +-------------------+---------+----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
   | src_province_name | String  | Source province name.                                                                                                                                                                                                      |
   +-------------------+---------+----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
   | src_city_id       | String  | Source city ID.                                                                                                                                                                                                            |
   +-------------------+---------+----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
   | src_city_name     | String  | Source city name.                                                                                                                                                                                                          |
   +-------------------+---------+----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
   | dst_province_id   | String  | Destination province ID.                                                                                                                                                                                                   |
   +-------------------+---------+----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
   | dst_province_name | String  | Destination province name.                                                                                                                                                                                                 |
   +-------------------+---------+----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
   | dst_city_id       | String  | Destination city ID.                                                                                                                                                                                                       |
   +-------------------+---------+----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
   | dst_city_name     | String  | Destination city name.                                                                                                                                                                                                     |
   +-------------------+---------+----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+

**Status code: 400**

.. table:: **Table 7** Response body parameters

   ========== ====== ==================
   Parameter  Type   Description
   ========== ====== ==================
   error_code String Error code.
   error_msg  String Error description.
   ========== ====== ==================

Example Requests
----------------

Query the records whose initial position is 0 on the first page of the firewall with the ID 2af58b7c-893c-4453-a984-bdd9b1bd6318 in the project 9d80d070b6d44942af73c9c3d38e0429. The query time range is 1664159069544 to 1664162669544.

.. code-block::

   https://{Endpoint}/v1/9d80d070b6d44942af73c9c3d38e0429/cfw/logs/access-control?fw_instance_id=2af58b7c-893c-4453-a984-bdd9b1bd6318&start_time=1664159069544&end_time=1664162669544&limit=10

Example Responses
-----------------

**Status code: 200**

Return value for querying access control logs.

.. code-block::

   {
     "data" : {
       "limit" : 10,
       "records" : [ {
         "action" : "deny",
         "app" : "PING",
         "dst_ip" : "100.85.216.211",
         "dst_port" : 59,
         "hit_time" : 1664164255000,
         "log_id" : "46032",
         "protocol" : "ICMP: ECHO_REQUEST",
         "rule_id" : "c755be1c-4b92-4ae7-a15e-c2d02b152538",
         "rule_name" : "eip_ipv4_w_n_default_deny",
         "src_ip" : "100.95.148.49",
         "src_port" : 24954,
         "src_province_id" : "source province id",
         "src_province_name" : "source province name",
         "src_city_id" : "source city id",
         "src_city_name" : "source city name",
         "dst_province_id" : "dst province id",
         "dst_province_name" : "dst province name",
         "dst_city_id" : "dst city id",
         "dst_city_name" : "dst city name"
       } ],
       "total" : 1
     }
   }

**Status code: 400**

Bad Request

.. code-block::

   {
     "error_code" : "CFW.00500002",
     "error_msg" : "Invalid interval."
   }

Status Codes
------------

=========== ==============================================
Status Code Description
=========== ==============================================
200         Return value for querying access control logs.
400         Bad Request
401         Unauthorized
403         Forbidden
404         Not Found
500         Internal Server Error
=========== ==============================================

Error Codes
-----------

See :ref:`Error Codes <errorcode>`.
