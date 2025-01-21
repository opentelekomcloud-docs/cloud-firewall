:original_name: DeleteServiceSet.html

.. _DeleteServiceSet:

Deleting a Service Group
========================

Function
--------

This API is used to delete a service group.

URI
---

DELETE /v1/{project_id}/service-sets/{set_id}

.. table:: **Table 1** Path Parameters

   +------------+-----------+--------+--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
   | Parameter  | Mandatory | Type   | Description                                                                                                                                                                                                                          |
   +============+===========+========+======================================================================================================================================================================================================================================+
   | project_id | Yes       | String | Project ID, which can be obtained by calling an API or from the console. For details, see :ref:`Obtaining a Project ID <cfw_02_0015>`.                                                                                               |
   +------------+-----------+--------+--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
   | set_id     | Yes       | String | Service group ID, which can be obtained by calling the :ref:`API for querying the service group list <listservicesets>`. Find the value in **data.records.set_id** (The period [.] is used to separate different levels of objects). |
   +------------+-----------+--------+--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+

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

   +-----------+----------------------------------------------------------------------+---------------------------------------------+
   | Parameter | Type                                                                 | Description                                 |
   +===========+======================================================================+=============================================+
   | data      | :ref:`ServiceSetId <deleteserviceset__response_servicesetid>` object | Data returned for deleting a service group. |
   +-----------+----------------------------------------------------------------------+---------------------------------------------+

.. _deleteserviceset__response_servicesetid:

.. table:: **Table 5** ServiceSetId

   ========= ====== ===================
   Parameter Type   Description
   ========= ====== ===================
   id        String Service group ID.
   name      String Service group name.
   ========= ====== ===================

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

Delete service group 221cfdca-3abf-4c30-ab0d-516a03c70866 in project 9d80d070b6d44942af73c9c3d38e0429.

.. code-block::

   https://{Endpoint}/v1/9d80d070b6d44942af73c9c3d38e0429/service-sets/221cfdca-3abf-4c30-ab0d-516a03c70866

Example Responses
-----------------

**Status code: 200**

Return value for deleting a service group.

.. code-block::

   {
     "data" : {
       "id" : "221cfdca-3abf-4c30-ab0d-516a03c70866",
       "name" : "test"
     }
   }

**Status code: 400**

Bad Request

.. code-block::

   {
     "error_code" : "CFW.00200004",
     "error_msg" : "Failed to delete the resource because it is being referenced."
   }

Status Codes
------------

=========== ==========================================
Status Code Description
=========== ==========================================
200         Return value for deleting a service group.
400         Bad Request
401         Unauthorized
403         Forbidden
404         Not Found
500         Internal Server Error
=========== ==========================================

Error Codes
-----------

See :ref:`Error Codes <errorcode>`.
