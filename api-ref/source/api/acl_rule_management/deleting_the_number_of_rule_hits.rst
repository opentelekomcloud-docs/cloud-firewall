:original_name: DeleteAclRuleHitCount.html

.. _DeleteAclRuleHitCount:

Deleting the Number of Rule Hits
================================

Function
--------

This API is used to delete the number of rule hits.

URI
---

DELETE /v1/{project_id}/acl-rule/count

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
   | enterprise_project_id | No        | String | Enterprise project ID, which is the ID of a project planned based on organizations. You can obtain the enterprise project ID by referring to :ref:`Obtaining an Enterprise Project ID <cfw_02_0027>`. If the enterprise project function is not enabled, the value is **0**. |
   +-----------------------+-----------+--------+------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
   | fw_instance_id        | No        | String | Firewall ID, which can be obtained by referring to :ref:`Obtaining a Firewall ID <cfw_02_0028>`.                                                                                                                                                                             |
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

   +-----------+-----------+------------------+---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
   | Parameter | Mandatory | Type             | Description                                                                                                                                                                                                                                                   |
   +===========+===========+==================+===============================================================================================================================================================================================================================================================+
   | rule_ids  | Yes       | Array of strings | List of rules deleted during rule hit deletion. Rule IDs can be obtained by calling the :ref:`API for querying protection rules <listaclrules>`. Find the value in **data.records.rule_id** (The period [.] is used to separate different levels of objects). |
   +-----------+-----------+------------------+---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+

Response Parameters
-------------------

**Status code: 200**

.. table:: **Table 5** Response body parameters

   ========= ====== ===========
   Parameter Type   Description
   ========= ====== ===========
   ``-``     String   
   ========= ====== ===========

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

Clear the hits of ACL rule 59ff6bd9-0a76-41ec-9650-380086069965 whose project ID is 0b2179bbe180d3762fb0c01a2d5725c7.

.. code-block::

   https://{Endpoint}/v1/0b2179bbe180d3762fb0c01a2d5725c7/acl-rule/count

   {
     "rule_ids" : [ "59ff6bd9-0a76-41ec-9650-380086069965" ]
   }

Example Responses
-----------------

**Status code: 200**

OK

.. code-block::

   { }

**Status code: 400**

Bad Request

.. code-block::

   {
     "error_code" : "CFW.00400006",
     "error_msg" : "Error occurred when deleting the rule hit count."
   }

Status Codes
------------

=========== =====================
Status Code Description
=========== =====================
200         OK
400         Bad Request
401         Unauthorized
403         Forbidden
404         Not Found
500         Internal Server Error
=========== =====================

Error Codes
-----------

See :ref:`Error Codes <errorcode>`.
