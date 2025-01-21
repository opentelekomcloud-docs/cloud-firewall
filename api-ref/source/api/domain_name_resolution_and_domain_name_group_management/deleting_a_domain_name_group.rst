:original_name: DeleteDomainSet.html

.. _DeleteDomainSet:

Deleting a Domain Name Group
============================

Function
--------

This API is used to delete a domain name group.

URI
---

DELETE /v1/{project_id}/domain-set/{set_id}

.. table:: **Table 1** Path Parameters

   +------------+-----------+--------+---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
   | Parameter  | Mandatory | Type   | Description                                                                                                                                                                                                                                 |
   +============+===========+========+=============================================================================================================================================================================================================================================+
   | project_id | Yes       | String | Project ID, which can be obtained by calling an API or from the console. For details, see :ref:`Obtaining a Project ID <cfw_02_0015>`.                                                                                                      |
   +------------+-----------+--------+---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
   | set_id     | Yes       | String | Domain name group ID, which can be obtained by calling the :ref:`API for querying the domain name group list <listdomainsets>`. Find the value in **data.records.set_id** (The period [.] is used to separate different levels of objects). |
   +------------+-----------+--------+---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+

.. table:: **Table 2** Query Parameters

   +-----------------------+-----------+--------+------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
   | Parameter             | Mandatory | Type   | Description                                                                                                                                                                                                                                                                  |
   +=======================+===========+========+==============================================================================================================================================================================================================================================================================+
   | enterprise_project_id | No        | String | Enterprise project ID, which is the ID of a project planned based on organizations. You can obtain the enterprise project ID by referring to :ref:`Obtaining an Enterprise Project ID <cfw_02_0027>`. If the enterprise project function is not enabled, the value is **0**. |
   +-----------------------+-----------+--------+------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
   | fw_instance_id        | Yes       | String | Firewall ID, which can be obtained by referring to :ref:`Obtaining a Firewall ID <cfw_02_0028>`.                                                                                                                                                                             |
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

   +-----------+---------------------------------------------------------------------------------------+-------------------------------------------------+
   | Parameter | Type                                                                                  | Description                                     |
   +===========+=======================================================================================+=================================================+
   | data      | :ref:`DomainSetResponseData <deletedomainset__response_domainsetresponsedata>` object | Returned data for deleting a domain name group. |
   +-----------+---------------------------------------------------------------------------------------+-------------------------------------------------+

.. _deletedomainset__response_domainsetresponsedata:

.. table:: **Table 5** DomainSetResponseData

   ========= ====== =======================
   Parameter Type   Description
   ========= ====== =======================
   id        String Domain name group ID.
   name      String Domain name group name.
   ========= ====== =======================

Example Requests
----------------

Delete domain name group 89bce6a4-9b59-4d7a-b5f9-cac5ac16d88a from firewall 7a004e79-0b8b-4679-ab20-267f3946e8ba in project 9d80d070b6d44942af73c9c3d38e0429.

.. code-block::

   https://{Endpoint}/v1/9d80d070b6d44942af73c9c3d38e0429/domain-set/89bce6a4-9b59-4d7a-b5f9-cac5ac16d88a?fw_instance_id=7a004e79-0b8b-4679-ab20-267f3946e8ba&enterprise_project_id=default

Example Responses
-----------------

**Status code: 200**

Return value for deleting a domain name group.

.. code-block::

   {
     "data" : {
       "id" : "89bce6a4-9b59-4d7a-b5f9-cac5ac16d88a",
       "name" : "test"
     }
   }

Status Codes
------------

=========== ==============================================
Status Code Description
=========== ==============================================
200         Return value for deleting a domain name group.
=========== ==============================================

Error Codes
-----------

See :ref:`Error Codes <errorcode>`.
