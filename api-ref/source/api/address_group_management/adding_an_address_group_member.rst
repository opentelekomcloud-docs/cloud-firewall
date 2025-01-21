:original_name: AddAddressItem.html

.. _AddAddressItem:

Adding an Address Group Member
==============================

Function
--------

This API is used to add a member to an address group.

URI
---

POST /v1/{project_id}/address-items

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

   +---------------+-----------+-------------------------------------------------------------------------------+--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
   | Parameter     | Mandatory | Type                                                                          | Description                                                                                                                                                                                                                          |
   +===============+===========+===============================================================================+======================================================================================================================================================================================================================================+
   | set_id        | No        | String                                                                        | Address group ID, which can be obtained by calling the :ref:`API for querying the address group list <listaddresssets>`. Find the value in **data.records.set_id** (The period [.] is used to separate different levels of objects). |
   +---------------+-----------+-------------------------------------------------------------------------------+--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
   | address_items | No        | Array of :ref:`address_items <addaddressitem__request_address_items>` objects | Address group member list.                                                                                                                                                                                                           |
   +---------------+-----------+-------------------------------------------------------------------------------+--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+

.. _addaddressitem__request_address_items:

.. table:: **Table 5** address_items

   ============ ========= ======= =========================================
   Parameter    Mandatory Type    Description
   ============ ========= ======= =========================================
   address_type No        Integer Address type: **0** (IPv4), **1** (IPv6).
   address      Yes       String  ip
   description  No        String  Address group member description.
   ============ ========= ======= =========================================

Response Parameters
-------------------

**Status code: 200**

.. table:: **Table 6** Response body parameters

   +-----------+--------------------------------------------------------------------+-------------------------------------------------------+
   | Parameter | Type                                                               | Description                                           |
   +===========+====================================================================+=======================================================+
   | data      | :ref:`AddressItems <addaddressitem__response_addressitems>` object | Data returned after an address group member is added. |
   +-----------+--------------------------------------------------------------------+-------------------------------------------------------+

.. _addaddressitem__response_addressitems:

.. table:: **Table 7** AddressItems

   +------------+------------------------------------------------------------------------------------------------------+-----------------------------------+
   | Parameter  | Type                                                                                                 | Description                       |
   +============+======================================================================================================+===================================+
   | items      | Array of :ref:`AddressItemIdWithoutName <addaddressitem__response_addressitemidwithoutname>` objects | List of address group member IDs. |
   +------------+------------------------------------------------------------------------------------------------------+-----------------------------------+
   | covered_ip | Array of :ref:`CoveredIPVO <addaddressitem__response_coveredipvo>` objects                           | List of covered IP addresses.     |
   +------------+------------------------------------------------------------------------------------------------------+-----------------------------------+

.. _addaddressitem__response_addressitemidwithoutname:

.. table:: **Table 8** AddressItemIdWithoutName

   ========= ====== ==============================
   Parameter Type   Description
   ========= ====== ==============================
   id        String ID of an address group member.
   ========= ====== ==============================

.. _addaddressitem__response_coveredipvo:

.. table:: **Table 9** CoveredIPVO

   ========== ====== ====================
   Parameter  Type   Description
   ========== ====== ====================
   ip         String IP address
   covered_Ip String Cover an IP address.
   ========== ====== ====================

**Status code: 400**

.. table:: **Table 10** Response body parameters

   ========== ====== ==================
   Parameter  Type   Description
   ========== ====== ==================
   error_code String Error code.
   error_msg  String Error description.
   ========== ====== ==================

Example Requests
----------------

Add an address group member whose IP address is 2.2.2.2 and name is **ceshi** to the group whose **set_id** is 8773c082-2a6c-4529-939a-edc28ef1a67c in project 9d80d070b6d44942af73c9c3d38e0429.

.. code-block::

   https://{Endpoint}/v1/9d80d070b6d44942af73c9c3d38e0429/address-items

   {
     "set_id" : "8773c082-2a6c-4529-939a-edc28ef1a67c",
     "address_items" : [ {
       "description" : "",
       "address" : "2.2.2.2"
     } ]
   }

Example Responses
-----------------

**Status code: 200**

Return value for adding an address group member.

.. code-block::

   {
     "data" : {
       "covered_ip" : [ ],
       "items" : [ {
         "id" : "65cb47fc-e666-4af4-8c2c-1fbd2f4b1eae"
       } ]
     }
   }

**Status code: 400**

Bad Request

.. code-block::

   {
     "error_code" : "CFW.00200001",
     "error_msg" : "Empty parameter."
   }

Status Codes
------------

=========== ================================================
Status Code Description
=========== ================================================
200         Return value for adding an address group member.
400         Bad Request
401         Unauthorized
403         Forbidden
404         Not Found
500         Internal Server Error
=========== ================================================

Error Codes
-----------

See :ref:`Error Codes <errorcode>`.
