:original_name: BatchDeleteServiceItems.html

.. _BatchDeleteServiceItems:

Deleting Service Group Members in Batches
=========================================

Function
--------

This API is used to delete service group members in batches.

URI
---

DELETE /v1/{project_id}/service-items

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

   +------------------+-----------+------------------+----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
   | Parameter        | Mandatory | Type             | Description                                                                                                                                                                                                                                                                      |
   +==================+===========+==================+==================================================================================================================================================================================================================================================================================+
   | set_id           | Yes       | String           | Service group ID, which can be obtained by calling the :ref:`API for querying the service group list <listservicesets>`. Find the value in **data.records.set_id** (The period [.] is used to separate different levels of objects).                                             |
   +------------------+-----------+------------------+----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
   | service_item_ids | Yes       | Array of strings | List of service group member IDs. Service group member IDs can be obtained by calling the :ref:`API for querying the service group member list <listserviceitems>`. Find the value in **data.records.item_id** (The period [.] is used to separate different levels of objects). |
   +------------------+-----------+------------------+----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+

Response Parameters
-------------------

**Status code: 200**

.. table:: **Table 5** Response body parameters

   +-----------+------------------+----------------------------------------------------------------+
   | Parameter | Type             | Description                                                    |
   +===========+==================+================================================================+
   | data      | Array of strings | ID list of the service group members to be deleted in batches. |
   +-----------+------------------+----------------------------------------------------------------+

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

Delete service group member f837f7ae-22c9-449d-a99c-4be24533e243 from service group 688faf62-20fc-4ca6-b9f9-6fbc518df5ae in project 9d80d070b6d44942af73c9c3d38e0429.

.. code-block::

   https://{Endpoint}/v1/9d80d070b6d44942af73c9c3d38e0429/service-items?fw_instance_id=7a004e79-0b8b-4679-ab20-267f3946e8ba&enterprise_project_id=default

   {
     "set_id" : "688faf62-20fc-4ca6-b9f9-6fbc518df5ae",
     "service_item_ids" : [ "f837f7ae-22c9-449d-a99c-4be24533e243" ]
   }

Example Responses
-----------------

**Status code: 200**

Return value for deleting service group members in batches.

.. code-block::

   {
     "data" : [ "f837f7ae-22c9-449d-a99c-4be24533e243" ]
   }

**Status code: 400**

Bad Request

.. code-block::

   {
     "error_code" : "CFW.00200005",
     "error_msg" : "Object not found."
   }

Status Codes
------------

=========== ===========================================================
Status Code Description
=========== ===========================================================
200         Return value for deleting service group members in batches.
400         Bad Request
=========== ===========================================================

Error Codes
-----------

See :ref:`Error Codes <errorcode>`.
