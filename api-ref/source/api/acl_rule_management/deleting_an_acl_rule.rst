:original_name: DeleteAclRule.html

.. _DeleteAclRule:

Deleting an ACL Rule
====================

Function
--------

This API is used to delete an ACL rule.

URI
---

DELETE /v1/{project_id}/acl-rule/{acl_rule_id}

.. table:: **Table 1** Path Parameters

   +-------------+-----------+--------+---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
   | Parameter   | Mandatory | Type   | Description                                                                                                                                                                                                         |
   +=============+===========+========+=====================================================================================================================================================================================================================+
   | project_id  | Yes       | String | Project ID, which can be obtained by calling an API or from the console. For details, see :ref:`Obtaining a Project ID <cfw_02_0015>`.                                                                              |
   +-------------+-----------+--------+---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
   | acl_rule_id | Yes       | String | Rule ID, which can be obtained by calling the :ref:`API for querying protection rules <listaclrules>`. Find the value in **data.records.rule_id** (The period [.] is used to separate different levels of objects). |
   +-------------+-----------+--------+---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+

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

Response Parameters
-------------------

**Status code: 200**

.. table:: **Table 4** Response body parameters

   +-----------+-------------------------------------------------------+-------------+
   | Parameter | Type                                                  | Description |
   +===========+=======================================================+=============+
   | data      | :ref:`RuleId <deleteaclrule__response_ruleid>` object | Rule ID.    |
   +-----------+-------------------------------------------------------+-------------+

.. _deleteaclrule__response_ruleid:

.. table:: **Table 5** RuleId

   ========= ====== ===========
   Parameter Type   Description
   ========= ====== ===========
   id        String Rule ID.
   name      String Rule name.
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

Delete the rule ceaa0407-b9c8-4dfd-9eca-b6ead2dfd031 from project 9d80d070b6d44942af73c9c3d38e0429.

.. code-block::

   https://{Endpoint}/v1/9d80d070b6d44942af73c9c3d38e0429/acl-rule/ceaa0407-b9c8-4dfd-9eca-b6ead2dfd031

Example Responses
-----------------

**Status code: 200**

Data returned for rule deletion.

.. code-block::

   {
     "data" : {
       "id" : "ceaa0407-b9c8-4dfd-9eca-b6ead2dfd031",
       "name" : "name"
     }
   }

**Status code: 400**

Bad Request

.. code-block::

   {
     "error_code" : "CFW.00900016",
     "error_msg" : "Import is in progress. Please wait until it is complete."
   }

Status Codes
------------

=========== ================================
Status Code Description
=========== ================================
200         Data returned for rule deletion.
400         Bad Request
401         Unauthorized
403         Forbidden
404         Not Found
500         Internal Server Error
=========== ================================

Error Codes
-----------

See :ref:`Error Codes <errorcode>`.
