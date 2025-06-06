:original_name: ListIpsProtectMode.html

.. _ListIpsProtectMode:

Querying a Protection Mode
==========================

Function
--------

This API is used to query a protection mode.

URI
---

GET /v1/{project_id}/ips/protect

.. table:: **Table 1** Path Parameters

   +------------+-----------+--------+----------------------------------------------------------------------------------------------------------------------------------------+
   | Parameter  | Mandatory | Type   | Description                                                                                                                            |
   +============+===========+========+========================================================================================================================================+
   | project_id | Yes       | String | Project ID, which can be obtained by calling an API or from the console. For details, see :ref:`Obtaining a Project ID <cfw_02_0015>`. |
   +------------+-----------+--------+----------------------------------------------------------------------------------------------------------------------------------------+

.. table:: **Table 2** Query Parameters

   +-----------------------+-----------+--------+----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
   | Parameter             | Mandatory | Type   | Description                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                              |
   +=======================+===========+========+==========================================================================================================================================================================================================================================================================================================================================================================================================================================================================================================================================================================================================================================================================================================================================================================================================+
   | object_id             | Yes       | String | Protected object ID, which is used to distinguish between Internet border protection and VPC border protection after a cloud firewall is created. You can obtain the ID by calling the :ref:`API for querying firewall instances <listfirewalldetail>`. In the return value, find the ID in **data.records.protect_objects.object_id** (The period [.] is used to separate different levels of objects). If the value of **type** is **0**, the protected object ID belongs to the Internet border. If the value of **type** is **1**, the protected object ID belongs to the VPC border. Here, a protected object ID whose **type** is **0** is used. You can obtain the value of **type** from **data.records.protect_objects.type** (The period [.] is used to separate different levels of objects). |
   +-----------------------+-----------+--------+----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
   | enterprise_project_id | No        | String | Enterprise project ID, which is the ID of a project planned based on organizations. You can obtain the enterprise project ID by referring to :ref:`Obtaining an Enterprise Project ID <cfw_02_0027>`. If the enterprise project function is not enabled, the value is **0**.                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                             |
   +-----------------------+-----------+--------+----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
   | fw_instance_id        | No        | String | Firewall ID, which can be obtained by referring to :ref:`Obtaining a Firewall ID <cfw_02_0028>`.                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                         |
   +-----------------------+-----------+--------+----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+

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

   +-----------+----------------------------------------------------------------------------------------+------------------------------------------------------+
   | Parameter | Type                                                                                   | Description                                          |
   +===========+========================================================================================+======================================================+
   | data      | :ref:`IpsProtectModeObject <listipsprotectmode__response_ipsprotectmodeobject>` object | Returned value for querying the IPS protection mode. |
   +-----------+----------------------------------------------------------------------------------------+------------------------------------------------------+

.. _listipsprotectmode__response_ipsprotectmodeobject:

.. table:: **Table 5** IpsProtectModeObject

   +-----------+---------+------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
   | Parameter | Type    | Description                                                                                                                                                                                                                                                                                                                  |
   +===========+=========+==============================================================================================================================================================================================================================================================================================================================+
   | id        | String  | IPS protection mode ID. The value is the ID of the protected object, which can be obtained by calling the :ref:`API for querying a firewall instance <listfirewalldetail>`. In the return value, find the ID in **data.records.protect_objects.object_id** (The period [.] is used to separate different levels of objects). |
   +-----------+---------+------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
   | mode      | Integer | IPS protection mode: **0** (observation mode), **1** (strict mode), 2 (medium mode), or 3 (loose mode). The observation mode is the default mode.                                                                                                                                                                            |
   +-----------+---------+------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+

**Status code: 400**

.. table:: **Table 6** Response body parameters

   ========== ====== ==================
   Parameter  Type   Description
   ========== ====== ==================
   error_code String Error code.
   error_msg  String Error description.
   ========== ====== ==================

Example Requests
----------------

Query the IPS protection mode of project 9d80d070b6d44942af73c9c3d38e0429.

.. code-block::

   https://{Endpoint}/v1/9d80d070b6d44942af73c9c3d38e0429/ips/protect?fw_instance_id=546af3f8-88e9-47f2-a205-2346d7090925&enterprise_project_id=default&object_id=cfebd347-b655-4b84-b938-3c54317599b2

Example Responses
-----------------

**Status code: 200**

Return value for a protection mode query

.. code-block::

   {
     "data" : {
       "id" : "d5b75aba-dfca-40e4-99dd-ed56578e8e48",
       "mode" : 0
     }
   }

**Status code: 400**

Bad Request

.. code-block::

   {
     "error_code" : "CFW.0020016",
     "error_msg" : "Incorrect instance status."
   }

Status Codes
------------

=========== ========================================
Status Code Description
=========== ========================================
200         Return value for a protection mode query
400         Bad Request
401         Unauthorized
403         Forbidden
404         Not Found
500         Internal Server Error
=========== ========================================

Error Codes
-----------

See :ref:`Error Codes <errorcode>`.
