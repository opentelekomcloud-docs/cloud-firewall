:original_name: ListFlowLogs.html

.. _ListFlowLogs:

Querying Flow Logs
==================

Function
--------

This API is used to query flow logs.

URI
---

GET /v1/{project_id}/cfw/logs/flow

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
   | direction             | No        | String  | Direction. Its value can be **in2out** or **out2in**.                                                                                                                                                                                                                        |
   +-----------------------+-----------+---------+------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
   | log_type              | No        | String  | Log type. Its value can be **internet**, **vpc**, or **nat**.                                                                                                                                                                                                                |
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
   | next_date             | No        | Long    | Next date. For the first page, its value is null. For other pages, its value can be the **start_time** of the last record in the last query.                                                                                                                                 |
   +-----------------------+-----------+---------+------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
   | offset                | No        | Integer | Offset, which specifies the start position of the record to be returned. The value must be a number greater than 0. For the first page, its value is null. For other pages, its value is not null.                                                                           |
   +-----------------------+-----------+---------+------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
   | limit                 | Yes       | Integer | Number of records displayed on each page. The value ranges from 1 to 1024.                                                                                                                                                                                                   |
   +-----------------------+-----------+---------+------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
   | enterprise_project_id | No        | String  | Enterprise project ID, which is the ID of a project planned based on organizations. You can obtain the enterprise project ID by referring to :ref:`Obtaining an Enterprise Project ID <cfw_02_0027>`. If the enterprise project function is not enabled, the value is **0**. |
   +-----------------------+-----------+---------+------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
   | dst_host              | No        | String  | Destination host.                                                                                                                                                                                                                                                            |
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

   +-----------+--------------------------------------------------+--------------------------------------+
   | Parameter | Type                                             | Description                          |
   +===========+==================================================+======================================+
   | data      | :ref:`data <listflowlogs__response_data>` object | Return value for querying flow logs. |
   +-----------+--------------------------------------------------+--------------------------------------+

.. _listflowlogs__response_data:

.. table:: **Table 5** data

   +-----------+------------------------------------------------------------------+----------------------------------------------------------------------------+
   | Parameter | Type                                                             | Description                                                                |
   +===========+==================================================================+============================================================================+
   | total     | Integer                                                          | Total number of returned records for querying flow logs.                   |
   +-----------+------------------------------------------------------------------+----------------------------------------------------------------------------+
   | limit     | Integer                                                          | Number of records displayed on each page. The value ranges from 1 to 1024. |
   +-----------+------------------------------------------------------------------+----------------------------------------------------------------------------+
   | records   | Array of :ref:`records <listflowlogs__response_records>` objects | Record.                                                                    |
   +-----------+------------------------------------------------------------------+----------------------------------------------------------------------------+

.. _listflowlogs__response_records:

.. table:: **Table 6** records

   +-------------------+---------+----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
   | Parameter         | Type    | Description                                                                                                                                                                                                                |
   +===================+=========+============================================================================================================================================================================================================================+
   | bytes             | Double  | Byte.                                                                                                                                                                                                                      |
   +-------------------+---------+----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
   | direction         | String  | Direction: **in2out** (outbound) or **out2in** (inbound).                                                                                                                                                                  |
   +-------------------+---------+----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
   | packets           | Integer | Number of packets.                                                                                                                                                                                                         |
   +-------------------+---------+----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
   | start_time        | Long    | Start time, in milliseconds. The value is a timestamp, for example, 1718936272648.                                                                                                                                         |
   +-------------------+---------+----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
   | end_time          | Long    | End time, in milliseconds. The value is a timestamp, for example, 1718936272648.                                                                                                                                           |
   +-------------------+---------+----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
   | log_id            | String  | Document ID.                                                                                                                                                                                                               |
   +-------------------+---------+----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
   | src_ip            | String  | Source IP address.                                                                                                                                                                                                         |
   +-------------------+---------+----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
   | src_port          | Integer | Source port.                                                                                                                                                                                                               |
   +-------------------+---------+----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
   | dst_ip            | String  | Destination IP address.                                                                                                                                                                                                    |
   +-------------------+---------+----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
   | app               | String  | Rule application type. Its value can be **HTTP**, **HTTPS**, **TLS1**, **DNS**, **SSH**, **MYSQL**, **SMTP**, **RDP**, **RDPS**, **VNC**, **POP3**, **IMAP4**, **SMTPS**, **POP3S**, **FTPS**, **ANY**, or **BGP**.        |
   +-------------------+---------+----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
   | dst_port          | Integer | Destination port.                                                                                                                                                                                                          |
   +-------------------+---------+----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
   | protocol          | String  | Protocol type: **6** (TCP), **17** (UDP), **1** (ICMP), **58** (ICMPv6), or **-1** (any). It cannot be left blank when **type** is set to **0** (manual), and can be left blank when **type** is set to **1** (automatic). |
   +-------------------+---------+----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
   | dst_host          | String  | Destination host.                                                                                                                                                                                                          |
   +-------------------+---------+----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
   | dst_region_id     | String  | Destination region ID.                                                                                                                                                                                                     |
   +-------------------+---------+----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
   | dst_region_name   | String  | Destination region name.                                                                                                                                                                                                   |
   +-------------------+---------+----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
   | src_region_id     | String  | Source region ID.                                                                                                                                                                                                          |
   +-------------------+---------+----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
   | src_region_name   | String  | Source region name.                                                                                                                                                                                                        |
   +-------------------+---------+----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
   | dst_province_id   | String  | Destination province ID.                                                                                                                                                                                                   |
   +-------------------+---------+----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
   | dst_province_name | String  | Destination province name.                                                                                                                                                                                                 |
   +-------------------+---------+----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
   | dst_city_id       | String  | Destination city ID.                                                                                                                                                                                                       |
   +-------------------+---------+----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
   | dst_city_name     | String  | Destination city name.                                                                                                                                                                                                     |
   +-------------------+---------+----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
   | src_province_id   | String  | Source province ID.                                                                                                                                                                                                        |
   +-------------------+---------+----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
   | src_province_name | String  | Source province name.                                                                                                                                                                                                      |
   +-------------------+---------+----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
   | src_city_id       | String  | Source city ID.                                                                                                                                                                                                            |
   +-------------------+---------+----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
   | src_city_name     | String  | Source city name.                                                                                                                                                                                                          |
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

Query the flow logs on the first page of the firewall with the ID 2af58b7c-893c-4453-a984-bdd9b1bd6318 in the project 9d80d070b6d44942af73c9c3d38e0429. The query time range is 1663555012000 to 1664159798000.

.. code-block::

   https://{Endpoint}/v1/9d80d070b6d44942af73c9c3d38e0429/cfw/logs/flow?fw_instance_id=2af58b7c-893c-4453-a984-bdd9b1bd6318&start_time=1663555012000&end_time=1664159798000&limit=10

Example Responses
-----------------

**Status code: 200**

Value returned for flow log query.

.. code-block::

   {
     "data" : {
       "limit" : 10,
       "records" : [ {
         "app" : "SSH",
         "bytes" : 34.5,
         "direction" : "out2in",
         "dst_ip" : "100.95.148.49",
         "dst_port" : 22,
         "end_time" : 1664155493000,
         "log_id" : "76354",
         "packets" : 25,
         "protocol" : "TCP",
         "src_ip" : "100.93.27.17",
         "src_port" : 49634,
         "start_time" : 1664155428000,
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

=========== ==================================
Status Code Description
=========== ==================================
200         Value returned for flow log query.
400         Bad Request
401         Unauthorized
403         Forbidden
404         Not Found
500         Internal Server Error
=========== ==================================

Error Codes
-----------

See :ref:`Error Codes <errorcode>`.
