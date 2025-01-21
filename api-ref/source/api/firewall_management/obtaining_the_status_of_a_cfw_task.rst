:original_name: ListJob.html

.. _ListJob:

Obtaining the Status of a CFW Task
==================================

Function
--------

This API is used to obtain the status of a CFW task.

URI
---

GET /v3/{project_id}/jobs/{job_id}

.. table:: **Table 1** Path Parameters

   +------------+-----------+--------+--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
   | Parameter  | Mandatory | Type   | Description                                                                                                                                                                                                        |
   +============+===========+========+====================================================================================================================================================================================================================+
   | project_id | Yes       | String | Project ID, which can be obtained by calling an API or from the console. For details, see :ref:`Obtaining a Project ID <cfw_02_0015>`.                                                                             |
   +------------+-----------+--------+--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
   | job_id     | Yes       | String | Task ID returned when a pay-per-use firewall is created. You can obtain the task ID by calling the :ref:`API for creating a firewall <createfirewall>`. Its value is obtained from **job_id** in the return value. |
   +------------+-----------+--------+--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+

Request Parameters
------------------

.. table:: **Table 2** Request header parameters

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

.. table:: **Table 3** Response body parameters

   +-----------+-----------------------------------------------------------------------------------------------------+----------------------------------------------------+
   | Parameter | Type                                                                                                | Description                                        |
   +===========+=====================================================================================================+====================================================+
   | data      | :ref:`GetCreateFirewallJobResponseData <listjob__response_getcreatefirewalljobresponsedata>` object | Data returned for creating a pay-per-use firewall. |
   +-----------+-----------------------------------------------------------------------------------------------------+----------------------------------------------------+

.. _listjob__response_getcreatefirewalljobresponsedata:

.. table:: **Table 4** GetCreateFirewallJobResponseData

   +-----------------------+-----------------------+-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
   | Parameter             | Type                  | Description                                                                                                                                                                                           |
   +=======================+=======================+=======================================================================================================================================================================================================+
   | id                    | String                | ID of the task for creating a pay-per-use firewall.                                                                                                                                                   |
   +-----------------------+-----------------------+-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
   | status                | String                | Task execution status, which indicates whether a firewall is successfully created.                                                                                                                    |
   |                       |                       |                                                                                                                                                                                                       |
   |                       |                       | Enumeration values:                                                                                                                                                                                   |
   |                       |                       |                                                                                                                                                                                                       |
   |                       |                       | -  **Running**                                                                                                                                                                                        |
   |                       |                       | -  **Success**                                                                                                                                                                                        |
   |                       |                       | -  **Failed**                                                                                                                                                                                         |
   +-----------------------+-----------------------+-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
   | begin_time            | String                | Creation time in the "yyyy-mm-ddThh:mm:ssZ" format.                                                                                                                                                   |
   |                       |                       |                                                                                                                                                                                                       |
   |                       |                       | **T** is the separator between the calendar and the hourly notation of time. **Z** indicates the time zone offset. For example, in the Beijing time zone, the time zone offset is shown as **+0800**. |
   +-----------------------+-----------------------+-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
   | end_time              | String                | End time in the "yyyy-mm-ddThh:mm:ssZ" format.                                                                                                                                                        |
   |                       |                       |                                                                                                                                                                                                       |
   |                       |                       | **T** is the separator between the calendar and the hourly notation of time. **Z** indicates the time zone offset. For example, in the Beijing time zone, the time zone offset is shown as **+0800**. |
   +-----------------------+-----------------------+-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+

Example Requests
----------------

Obtain information about the f588ce71-e26c-400d-8981-f854355f6849 task for creating a pay-per-use firewall in project 09bb24e6fe80d23d2fa2c010b53b418c.

.. code-block::

   https://{Endpoint}/v3/09bb24e6fe80d23d2fa2c010b53b418c/jobs/f588ce71-e26c-400d-8981-f854355f6849

Example Responses
-----------------

**Status code: 200**

Return value of the API for obtaining the information about a pay-per-use firewall creation task.

.. code-block::

   {
     "data" : {
       "begin_time" : 1641370501000,
       "end_time" : 1641370515000,
       "id" : "f588ce71-e26c-400d-8981-f854355f6849",
       "status" : "Success"
     }
   }

Status Codes
------------

+-------------+---------------------------------------------------------------------------------------------------+
| Status Code | Description                                                                                       |
+=============+===================================================================================================+
| 200         | Return value of the API for obtaining the information about a pay-per-use firewall creation task. |
+-------------+---------------------------------------------------------------------------------------------------+

Error Codes
-----------

See :ref:`Error Codes <errorcode>`.
