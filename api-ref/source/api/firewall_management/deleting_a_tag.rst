:original_name: DeleteTag.html

.. _DeleteTag:

Deleting a Tag
==============

Function
--------

This API is used to delete a tag.

URI
---

DELETE /v2/{project_id}/cfw-cfw/{fw_instance_id}/tags/delete

.. table:: **Table 1** Path Parameters

   +----------------+-----------+--------+----------------------------------------------------------------------------------------------------------------------------------------+
   | Parameter      | Mandatory | Type   | Description                                                                                                                            |
   +================+===========+========+========================================================================================================================================+
   | project_id     | Yes       | String | Project ID, which can be obtained by calling an API or from the console. For details, see :ref:`Obtaining a Project ID <cfw_02_0015>`. |
   +----------------+-----------+--------+----------------------------------------------------------------------------------------------------------------------------------------+
   | fw_instance_id | Yes       | String | Firewall ID, which can be obtained by referring to :ref:`Obtaining a Firewall ID <cfw_02_0028>`.                                       |
   +----------------+-----------+--------+----------------------------------------------------------------------------------------------------------------------------------------+

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

.. table:: **Table 3** Request body parameters

   +-----------+-----------+----------------------------------------------------------------------+--------------------+
   | Parameter | Mandatory | Type                                                                 | Description        |
   +===========+===========+======================================================================+====================+
   | tags      | No        | Array of :ref:`ResourceTag <deletetag__request_resourcetag>` objects | Firewall tag list. |
   +-----------+-----------+----------------------------------------------------------------------+--------------------+

.. _deletetag__request_resourcetag:

.. table:: **Table 4** ResourceTag

   =========== ========= ====== ================
   Parameter   Mandatory Type   Description
   =========== ========= ====== ================
   key         No        String Tag key.
   value       No        String Tag value.
   update_time No        String Tag update time.
   =========== ========= ====== ================

Response Parameters
-------------------

**Status code: 200**

.. table:: **Table 5** Response body parameters

   ========= ====== ===========
   Parameter Type   Description
   ========= ====== ===========
   ``-``     String   
   ========= ====== ===========

Example Requests
----------------

Delete a tag from firewall 5e7eba7f-5de4-4ce9-8f60-11330dfc6565 in project 0b2179bbe180d3762fb0c01a2d5725c7. The tag key is **keytest** and the tag value is **valuetest**.

.. code-block::

   https://{Endpoint}/v2/408972e72dcd4c1a9b033e955802a36b/cfw-cfw/5e7eba7f-5de4-4ce9-8f60-11330dfc6565/tags/delete

   {
     "tags" : [ {
       "key" : "keytest",
       "value" : "valuetest"
     } ]
   }

Example Responses
-----------------

None

Status Codes
------------

=========== ===========
Status Code Description
=========== ===========
200         OK
=========== ===========

Error Codes
-----------

See :ref:`Error Codes <errorcode>`.
