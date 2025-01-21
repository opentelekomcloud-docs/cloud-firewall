:original_name: UpdateDomainSet.html

.. _UpdateDomainSet:

Updating a Domain Name Group
============================

Function
--------

This API is used to update a domain name group.

URI
---

PUT /v1/{project_id}/domain-set/{set_id}

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
   | fw_instance_id        | Yes       | String | Firewall instance ID, which is automatically generated after a CFW instance is created. You can obtain the ID by calling the :ref:`API for querying a firewall instance <listfirewalldetail>`.                                                                               |
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

   =========== ========= ====== ==============================
   Parameter   Mandatory Type   Description
   =========== ========= ====== ==============================
   name        Yes       String Domain name group name.
   description No        String Domain name group description.
   =========== ========= ====== ==============================

Response Parameters
-------------------

**Status code: 200**

.. table:: **Table 5** Response body parameters

   +-----------+---------------------------------------------------------------------------------------+----------------------------------------------------+
   | Parameter | Type                                                                                  | Description                                        |
   +===========+=======================================================================================+====================================================+
   | data      | :ref:`DomainSetResponseData <updatedomainset__response_domainsetresponsedata>` object | Returned data of for updating a domain name group. |
   +-----------+---------------------------------------------------------------------------------------+----------------------------------------------------+

.. _updatedomainset__response_domainsetresponsedata:

.. table:: **Table 6** DomainSetResponseData

   ========= ====== =======================
   Parameter Type   Description
   ========= ====== =======================
   id        String Domain name group ID.
   name      String Domain name group name.
   ========= ====== =======================

Example Requests
----------------

Change the name of the domain name group 94da194d-24b2-4f60-919e-cf0bc76c75b3 of firewall 7a004e79-0b8b-4679-ab20-267f3946e8ba in project 9d80d070b6d44942af73c9c3d38e0429 to **test**.

.. code-block::

   https://{Endpoint}/v1/9d80d070b6d44942af73c9c3d38e0429/domain-set/94da194d-24b2-4f60-919e-cf0bc76c75b3?fw_instance_id=7a004e79-0b8b-4679-ab20-267f3946e8ba&enterprise_project_id=default

   {
     "name" : "test",
     "description" : ""
   }

Example Responses
-----------------

**Status code: 200**

Return value for updating a domain name group.

.. code-block::

   {
     "data" : {
       "id" : "94da194d-24b2-4f60-919e-cf0bc76c75b3",
       "name" : "test"
     }
   }

Status Codes
------------

=========== ==============================================
Status Code Description
=========== ==============================================
200         Return value for updating a domain name group.
=========== ==============================================

Error Codes
-----------

See :ref:`Error Codes <errorcode>`.
