:original_name: DeleteBlackWhiteList.html

.. _DeleteBlackWhiteList:

Deleting a Blacklist or Whitelist Rule
======================================

Function
--------

This API is used to delete a blacklist or whitelist rule.

URI
---

DELETE /v1/{project_id}/black-white-list/{list_id}

.. table:: **Table 1** Path Parameters

   +------------+-----------+--------+-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
   | Parameter  | Mandatory | Type   | Description                                                                                                                                                                                                                                         |
   +============+===========+========+=====================================================================================================================================================================================================================================================+
   | project_id | Yes       | String | Project ID, which can be obtained by calling an API or from the console. For details, see :ref:`Obtaining a Project ID <cfw_02_0015>`.                                                                                                              |
   +------------+-----------+--------+-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
   | list_id    | Yes       | String | Blacklist or whitelist ID, which can be obtained through the :ref:`API for querying the blacklist or whitelist <listblackwhitelists>`. Find the value in **data.records.list_id** (The period [.] is used to separate different levels of objects). |
   +------------+-----------+--------+-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+

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

   +-----------+----------------------------------------------------------------------------------+------------------------------------------------------------------+
   | Parameter | Type                                                                             | Description                                                      |
   +===========+==================================================================================+==================================================================+
   | data      | :ref:`BlackWhiteListId <deleteblackwhitelist__response_blackwhitelistid>` object | Response to the request for deleting a blacklist/whitelist item. |
   +-----------+----------------------------------------------------------------------------------+------------------------------------------------------------------+

.. _deleteblackwhitelist__response_blackwhitelistid:

.. table:: **Table 5** BlackWhiteListId

   ========= ====== =========================
   Parameter Type   Description
   ========= ====== =========================
   id        String Blacklist/Whitelist ID.
   name      String Blacklist/Whitelist name.
   ========= ====== =========================

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

Delete the blacklist or whitelist whose ID is 2eee3fe8-0b9b-49ac-8e7f-eaafa321e99a from the project 9d80d070b6d44942af73c9c3d38e0429.

.. code-block::

   https://{Endpoint}/v1/9d80d070b6d44942af73c9c3d38e0429/black-white-list/2eee3fe8-0b9b-49ac-8e7f-eaafa321e99a

Example Responses
-----------------

**Status code: 200**

Blacklist/Whitelist deletion response.

.. code-block::

   {
     "data" : {
       "id" : "2eee3fe8-0b9b-49ac-8e7f-eaafa321e99a"
     }
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

=========== ======================================
Status Code Description
=========== ======================================
200         Blacklist/Whitelist deletion response.
400         Bad Request
401         Unauthorized
403         Forbidden
404         Not Found
500         Internal Server Error
=========== ======================================

Error Codes
-----------

See :ref:`Error Codes <errorcode>`.
