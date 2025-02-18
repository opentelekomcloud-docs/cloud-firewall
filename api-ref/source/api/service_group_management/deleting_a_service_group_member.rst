:original_name: DeleteServiceItem.html

.. _DeleteServiceItem:

Deleting a Service Group Member
===============================

Function
--------

This API is used to delete a member from a service group.

URI
---

DELETE /v1/{project_id}/service-items/{item_id}

.. table:: **Table 1** Path Parameters

   +------------+-----------+--------+------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
   | Parameter  | Mandatory | Type   | Description                                                                                                                                                                                                                                          |
   +============+===========+========+======================================================================================================================================================================================================================================================+
   | project_id | Yes       | String | Project ID, which can be obtained by calling an API or from the console. For details, see :ref:`Obtaining a Project ID <cfw_02_0015>`.                                                                                                               |
   +------------+-----------+--------+------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
   | item_id    | Yes       | String | Service group member ID, which can be obtained by calling the :ref:`API for querying the service group member list <listserviceitems>`. Find the value in **data.records.item_id** (The period [.] is used to separate different levels of objects). |
   +------------+-----------+--------+------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+

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

   +-----------+-----------------------------------------------------------------------------------------------------------------+-----------------------------------+
   | Parameter | Type                                                                                                            | Description                       |
   +===========+=================================================================================================================+===================================+
   | data      | :ref:`DeleteServiceItemResponseBodyData <deleteserviceitem__response_deleteserviceitemresponsebodydata>` object | Delete service group member data. |
   +-----------+-----------------------------------------------------------------------------------------------------------------+-----------------------------------+

.. _deleteserviceitem__response_deleteserviceitemresponsebodydata:

.. table:: **Table 5** DeleteServiceItemResponseBodyData

   +-----------+--------+--------------------------------------------------------------------------+
   | Parameter | Type   | Description                                                              |
   +===========+========+==========================================================================+
   | id        | String | Service group member ID.                                                 |
   +-----------+--------+--------------------------------------------------------------------------+
   | name      | String | Service group member name,which is the source port and destination port. |
   +-----------+--------+--------------------------------------------------------------------------+

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

Delete the service group member whose ID is 6b37ed55-1e21-46a5-a7dc-a59ef418d359 from project 9d80d070b6d44942af73c9c3d38e0429.

.. code-block::

   https://{Endpoint}/v1/9d80d070b6d44942af73c9c3d38e0429/service-items/6b37ed55-1e21-46a5-a7dc-a59ef418d359

Example Responses
-----------------

**Status code: 200**

Information returned for service group member deletion.

.. code-block::

   {
     "data" : {
       "id" : "26f562c4-fe11-43d0-9654-f54298d5b12e",
       "name" : "0|1"
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

=========== =======================================================
Status Code Description
=========== =======================================================
200         Information returned for service group member deletion.
400         Bad Request
401         Unauthorized
403         Forbidden
404         Not Found
500         Internal Server Error
=========== =======================================================

Error Codes
-----------

See :ref:`Error Codes <errorcode>`.
