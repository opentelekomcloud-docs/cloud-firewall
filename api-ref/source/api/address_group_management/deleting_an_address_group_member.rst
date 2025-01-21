:original_name: DeleteAddressItem.html

.. _DeleteAddressItem:

Deleting an Address Group Member
================================

Function
--------

This API is used to delete a member from an address group.

URI
---

DELETE /v1/{project_id}/address-items/{item_id}

.. table:: **Table 1** Path Parameters

   +------------+-----------+--------+----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
   | Parameter  | Mandatory | Type   | Description                                                                                                                                                                                                                                  |
   +============+===========+========+==============================================================================================================================================================================================================================================+
   | item_id    | Yes       | String | Address group member ID, which can be obtained by calling the :ref:`API for querying address group members <listaddressitems>`. Find the value in **data.records.item_id** (The period [.] is used to separate different levels of objects). |
   +------------+-----------+--------+----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
   | project_id | Yes       | String | Project ID, which can be obtained by calling an API or from the console. For details, see :ref:`Obtaining a Project ID <cfw_02_0015>`.                                                                                                       |
   +------------+-----------+--------+----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+

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

   +-----------+-----------------------------------------------------------------------------------+------------------------------------+
   | Parameter | Type                                                                              | Description                        |
   +===========+===================================================================================+====================================+
   | data      | Array of :ref:`AddressItemId <deleteaddressitem__response_addressitemid>` objects | Delete an address group member ID. |
   +-----------+-----------------------------------------------------------------------------------+------------------------------------+

.. _deleteaddressitem__response_addressitemid:

.. table:: **Table 5** AddressItemId

   ========= ====== ================================
   Parameter Type   Description
   ========= ====== ================================
   id        String ID of an address group member.
   name      String Name of an address group member.
   ========= ====== ================================

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

Delete address group member 65cb47fc-e666-4af4-8c2c-1fbd2f4b1eae from project 9d80d070b6d44942af73c9c3d38e0429.

.. code-block::

   https://{Endpoint}/v1/9d80d070b6d44942af73c9c3d38e0429/address-items/65cb47fc-e666-4af4-8c2c-1fbd2f4b1eae

Example Responses
-----------------

**Status code: 200**

Return value for deleting an address group member.

.. code-block::

   {
     "data" : {
       "id" : "65cb47fc-e666-4af4-8c2c-1fbd2f4b1eae",
       "name" : "test"
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

=========== ==================================================
Status Code Description
=========== ==================================================
200         Return value for deleting an address group member.
400         Bad Request
401         Unauthorized
403         Forbidden
404         Not Found
500         Internal Server Error
=========== ==================================================

Error Codes
-----------

See :ref:`Error Codes <errorcode>`.
