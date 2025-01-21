:original_name: ListDomainParseDetail.html

.. _ListDomainParseDetail:

Querying an IP Address for Domain Name Resolution
=================================================

Function
--------

This API is used to check the validity of a domain name.

URI
---

GET /v1/{project_id}/domain/parse/{domain_name}

.. table:: **Table 1** Path Parameters

   +-------------+-----------+--------+----------------------------------------------------------------------------------------------------------------------------------------+
   | Parameter   | Mandatory | Type   | Description                                                                                                                            |
   +=============+===========+========+========================================================================================================================================+
   | project_id  | Yes       | String | Project ID, which can be obtained by calling an API or from the console. For details, see :ref:`Obtaining a Project ID <cfw_02_0015>`. |
   +-------------+-----------+--------+----------------------------------------------------------------------------------------------------------------------------------------+
   | domain_name | Yes       | String | Domain name, for example, **www.test.com**.                                                                                            |
   +-------------+-----------+--------+----------------------------------------------------------------------------------------------------------------------------------------+

.. table:: **Table 2** Query Parameters

   +-----------------------+-----------+---------+------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
   | Parameter             | Mandatory | Type    | Description                                                                                                                                                                                                                                                                  |
   +=======================+===========+=========+==============================================================================================================================================================================================================================================================================+
   | enterprise_project_id | No        | String  | Enterprise project ID, which is the ID of a project planned based on organizations. You can obtain the enterprise project ID by referring to :ref:`Obtaining an Enterprise Project ID <cfw_02_0027>`. If the enterprise project function is not enabled, the value is **0**. |
   +-----------------------+-----------+---------+------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
   | fw_instance_id        | No        | String  | Firewall ID, which can be obtained by referring to :ref:`Obtaining a Firewall ID <cfw_02_0028>`.                                                                                                                                                                             |
   +-----------------------+-----------+---------+------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
   | address_type          | No        | Integer | Address type: **0** (IPv4), **1** (IPv6).                                                                                                                                                                                                                                    |
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

   ========= ================ ===========================================
   Parameter Type             Description
   ========= ================ ===========================================
   data      Array of strings IP address list for domain name resolution.
   ========= ================ ===========================================

**Status code: 400**

.. table:: **Table 5** Response body parameters

   ========== ====== ==================
   Parameter  Type   Description
   ========== ====== ==================
   error_code String Error code.
   error_msg  String Error description.
   ========== ====== ==================

Example Requests
----------------

Check whether the domain name **ceshi.com** of project 5c69cf330cda42369cbd726ee1bc5e76 is valid.

.. code-block::

   https://{Endpoint}/v1/5c69cf330cda42369cbd726ee1bc5e76/domain/parse/ceshi.com

Example Responses
-----------------

**Status code: 200**

Return value for querying domain name validity.

.. code-block::

   {
     "data" : [ "192.168.88.85", "192.168.88.50", "192.168.88.22", "192.168.88.87", "192.168.88.86", "192.168.5.1", "192.168.88.88", "192.168.88.90", "192.168.88.83", "192.168.88.84" ]
   }

**Status code: 400**

Bad Request

.. code-block::

   {
     "error_code" : "CFW.00109004",
     "error_msg" : "HTTP request error."
   }

Status Codes
------------

=========== ===============================================
Status Code Description
=========== ===============================================
200         Return value for querying domain name validity.
400         Bad Request
401         Unauthorized
403         Forbidden
404         Not Found
500         Internal Server Error
=========== ===============================================

Error Codes
-----------

See :ref:`Error Codes <errorcode>`.
