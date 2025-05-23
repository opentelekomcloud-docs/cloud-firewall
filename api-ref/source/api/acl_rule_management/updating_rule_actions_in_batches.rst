:original_name: BatchUpdateAclRuleActions.html

.. _BatchUpdateAclRuleActions:

Updating Rule Actions in Batches
================================

Function
--------

This API is used to update rule actions in batches.

URI
---

PUT /v1/{project_id}/acl-rule/action

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

   +-----------+-----------+------------------+---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
   | Parameter | Mandatory | Type             | Description                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                 |
   +===========+===========+==================+=============================================================================================================================================================================================================================================================================================================================================================================================================================================================================================================================================================================================================================================================================================================================================+
   | object_id | Yes       | String           | Protected object ID, which is used to distinguish between Internet border protection and VPC border protection after a cloud firewall is created. You can obtain the ID by calling the :ref:`API for querying firewall instances <listfirewalldetail>`. In the return value, find the ID in **data.records.protect_objects.object_id** (The period [.] is used to separate different levels of objects). If the value of **type** is **0**, the protected object ID belongs to the Internet border. If the value of **type** is **1**, the protected object ID belongs to the VPC border. You can obtain the value of **type** from **data.records.protect_objects.type** (The period [.] is used to separate different levels of objects). |
   +-----------+-----------+------------------+---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
   | action    | Yes       | String           | Rule action: **enable** (permit), **disable** (deny).                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                       |
   +-----------+-----------+------------------+---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
   | rule_ids  | Yes       | Array of strings | List of rule IDs. You can obtain the rule IDs by calling the :ref:`API for querying protection rules <listaclrules>`. Find the value in **data.records.rule_id** (The period [.] is used to separate different levels of objects).                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                          |
   +-----------+-----------+------------------+---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+

Response Parameters
-------------------

**Status code: 200**

.. table:: **Table 5** Response body parameters

   +-----------+------------------+---------------------------------------------------------------------------------------------------------+
   | Parameter | Type             | Description                                                                                             |
   +===========+==================+=========================================================================================================+
   | data      | Array of strings | IDs of ACL rules to be updated in batches. The value is the rule IDs transferred from the request body. |
   +-----------+------------------+---------------------------------------------------------------------------------------------------------+

Example Requests
----------------

Update the statuses of rules 4e12d889-c1d3-491b-8470-3d1b3dadc1fd and f798a6a8-c4c5-42b4-838c-c922c9908cb4 of firewall 546af3f8-88e9-47f2-a205-2346d7090925 in project 14181c1245cf4fd786824efe1e2b9388 to enabled.

.. code-block::

   https://{Endpoint}/v1/14181c1245cf4fd786824efe1e2b9388/acl-rule/action?fw_instance_id=546af3f8-88e9-47f2-a205-2346d7090925&enterprise_project_id=default

   {
     "action" : "enable",
     "rule_ids" : [ "4e12d889-c1d3-491b-8470-3d1b3dadc1fd", "f798a6a8-c4c5-42b4-838c-c922c9908cb4" ],
     "object_id" : "ae42418e-f077-41a0-9d3b-5b2f5ad9102b"
   }

Example Responses
-----------------

**Status code: 200**

Returned value for batch ACL rule update.

.. code-block::

   {
     "data" : [ "4e12d889-c1d3-491b-8470-3d1b3dadc1fd", "f798a6a8-c4c5-42b4-838c-c922c9908cb4" ]
   }

Status Codes
------------

=========== =========================================
Status Code Description
=========== =========================================
200         Returned value for batch ACL rule update.
=========== =========================================

Error Codes
-----------

See :ref:`Error Codes <errorcode>`.
