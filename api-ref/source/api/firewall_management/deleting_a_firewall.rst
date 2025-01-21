:original_name: DeleteFirewall.html

.. _DeleteFirewall:

Deleting a Firewall
===================

Function
--------

This API is used to delete a firewall. It takes effect only for pay-per-use firewalls.

URI
---

DELETE /v2/{project_id}/firewall/{resource_id}

.. table:: **Table 1** Path Parameters

   +-------------+-----------+--------+----------------------------------------------------------------------------------------------------------------------------------------+
   | Parameter   | Mandatory | Type   | Description                                                                                                                            |
   +=============+===========+========+========================================================================================================================================+
   | project_id  | Yes       | String | Project ID, which can be obtained by calling an API or from the console. For details, see :ref:`Obtaining a Project ID <cfw_02_0015>`. |
   +-------------+-----------+--------+----------------------------------------------------------------------------------------------------------------------------------------+
   | resource_id | Yes       | String | Firewall ID, which can be obtained by referring to :ref:`Obtaining a Firewall ID <cfw_02_0028>`.                                       |
   +-------------+-----------+--------+----------------------------------------------------------------------------------------------------------------------------------------+

Request Parameters
------------------

.. table:: **Table 2** Request header parameters

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

.. table:: **Table 3** Response body parameters

   ========= ====== ===============================
   Parameter Type   Description
   ========= ====== ===============================
   data      String ID of a firewall deletion task.
   ========= ====== ===============================

Example Requests
----------------

Delete the pay-per-use firewall 08065281-860a-4c98-aeb5-82cf65c44c46 from project 06217ebc876e427a80a2c05d51264ab1.

.. code-block::

   https://{Endpoint}/v2/06217ebc876e427a80a2c05d51264ab1/firewall/08065281-860a-4c98-aeb5-82cf65c44c46

Example Responses
-----------------

**Status code: 200**

Return value for deleting a firewall.

.. code-block::

   {
     "data" : "56884cd0-cf3c-4cb7-bbeb-59d8722a2671"
   }

Status Codes
------------

=========== =====================================
Status Code Description
=========== =====================================
200         Return value for deleting a firewall.
=========== =====================================

Error Codes
-----------

See :ref:`Error Codes <errorcode>`.
