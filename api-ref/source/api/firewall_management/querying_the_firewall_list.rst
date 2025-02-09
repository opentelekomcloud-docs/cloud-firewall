:original_name: ListFirewallList.html

.. _ListFirewallList:

Querying the Firewall List
==========================

Function
--------

This API is used to query a firewall list.

URI
---

POST /v1/{project_id}/firewalls/list

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

   +-----------------------+-----------+---------------------------------------------------------------------+------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
   | Parameter             | Mandatory | Type                                                                | Description                                                                                                                                                                                                                                                                  |
   +=======================+===========+=====================================================================+==============================================================================================================================================================================================================================================================================+
   | enterprise_project_id | No        | String                                                              | Enterprise project ID, which is the ID of a project planned based on organizations. You can obtain the enterprise project ID by referring to :ref:`Obtaining an Enterprise Project ID <cfw_02_0027>`. If the enterprise project function is not enabled, the value is **0**. |
   +-----------------------+-----------+---------------------------------------------------------------------+------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
   | key_word              | No        | String                                                              | Query keyword, which can be a firewall ID or part of a firewall name. You can obtain the firewall ID by referring to :ref:`Obtaining a Firewall ID <cfw_02_0028>`.                                                                                                           |
   +-----------------------+-----------+---------------------------------------------------------------------+------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
   | tags                  | No        | Array of :ref:`TagInfo <listfirewalllist__request_taginfo>` objects | Tag list, which can be obtained by calling the API for querying tags. The return value is the tag list.                                                                                                                                                                      |
   +-----------------------+-----------+---------------------------------------------------------------------+------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
   | limit                 | Yes       | Integer                                                             | Number of records displayed on each page. The value ranges from 1 to 1024.                                                                                                                                                                                                   |
   +-----------------------+-----------+---------------------------------------------------------------------+------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
   | offset                | Yes       | Integer                                                             | Offset, which specifies the start position of the record to be returned. The value must be a number no less than 0. The default value is **0**.                                                                                                                              |
   +-----------------------+-----------+---------------------------------------------------------------------+------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+

.. _listfirewalllist__request_taginfo:

.. table:: **Table 5** TagInfo

   ========= ========= ================ ===============
   Parameter Mandatory Type             Description
   ========= ========= ================ ===============
   key       No        String           Tag key.
   values    No        Array of strings Tag value list.
   ========= ========= ================ ===============

Response Parameters
-------------------

**Status code: 200**

.. table:: **Table 6** Response body parameters

   +-----------------------------+----------------------------------------------------------------------------------------------------------------------+---------------------------------------------------------------------------------------------------------------------+
   | Parameter                   | Type                                                                                                                 | Description                                                                                                         |
   +=============================+======================================================================================================================+=====================================================================================================================+
   | user_support_eps            | Boolean                                                                                                              | Whether enterprise projects are supported: **true** (yes), **false** (no).                                          |
   +-----------------------------+----------------------------------------------------------------------------------------------------------------------+---------------------------------------------------------------------------------------------------------------------+
   | has_ndr                     | Boolean                                                                                                              | Whether NDR exists: **true** (yes), **false** (no). NDR is the original out-of-path firewall and is no longer sold. |
   +-----------------------------+----------------------------------------------------------------------------------------------------------------------+---------------------------------------------------------------------------------------------------------------------+
   | is_support_postpaid         | Boolean                                                                                                              | Whether pay-per-use purchase is supported: **true** (yes), **false** (no).                                          |
   +-----------------------------+----------------------------------------------------------------------------------------------------------------------+---------------------------------------------------------------------------------------------------------------------+
   | is_support_basic_version    | Boolean                                                                                                              | Whether the basic edition is supported: **true** (yes), **false** (no).                                             |
   +-----------------------------+----------------------------------------------------------------------------------------------------------------------+---------------------------------------------------------------------------------------------------------------------+
   | is_support_buy_professional | Boolean                                                                                                              | Whether the professional edition can be purchased: **true** (yes), **false** (no).                                  |
   +-----------------------------+----------------------------------------------------------------------------------------------------------------------+---------------------------------------------------------------------------------------------------------------------+
   | data                        | :ref:`HttpFirewallInstanceListResponseData <listfirewalllist__response_httpfirewallinstancelistresponsedata>` object | Data returned for querying the firewall list.                                                                       |
   +-----------------------------+----------------------------------------------------------------------------------------------------------------------+---------------------------------------------------------------------------------------------------------------------+

.. _listfirewalllist__response_httpfirewallinstancelistresponsedata:

.. table:: **Table 7** HttpFirewallInstanceListResponseData

   +------------+--------------------------------------------------------------------------------------------+-------------------------------------------------------------------------------------------------------------------------------------------------+
   | Parameter  | Type                                                                                       | Description                                                                                                                                     |
   +============+============================================================================================+=================================================================================================================================================+
   | limit      | Integer                                                                                    | Number of records displayed on each page. The value ranges from 1 to 1024.                                                                      |
   +------------+--------------------------------------------------------------------------------------------+-------------------------------------------------------------------------------------------------------------------------------------------------+
   | offset     | Integer                                                                                    | Offset, which specifies the start position of the record to be returned. The value must be a number no less than 0. The default value is **0**. |
   +------------+--------------------------------------------------------------------------------------------+-------------------------------------------------------------------------------------------------------------------------------------------------+
   | project_id | String                                                                                     | Tenant project ID                                                                                                                               |
   +------------+--------------------------------------------------------------------------------------------+-------------------------------------------------------------------------------------------------------------------------------------------------+
   | total      | Integer                                                                                    | Total number of firewalls.                                                                                                                      |
   +------------+--------------------------------------------------------------------------------------------+-------------------------------------------------------------------------------------------------------------------------------------------------+
   | records    | Array of :ref:`FirewallInstanceVO <listfirewalllist__response_firewallinstancevo>` objects | Query the firewall list.                                                                                                                        |
   +------------+--------------------------------------------------------------------------------------------+-------------------------------------------------------------------------------------------------------------------------------------------------+

.. _listfirewalllist__response_firewallinstancevo:

.. table:: **Table 8** FirewallInstanceVO

   +-----------------------+----------------------------------------------------------+------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
   | Parameter             | Type                                                     | Description                                                                                                                                                                                                                                                                                                      |
   +=======================+==========================================================+==================================================================================================================================================================================================================================================================================================================+
   | fw_instance_id        | String                                                   | Firewall instance ID, which is automatically generated by the system after a CFW instance is created.                                                                                                                                                                                                            |
   +-----------------------+----------------------------------------------------------+------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
   | resource_id           | String                                                   | Resource ID, which is the same as the firewall instance ID **fw_instance_id**.                                                                                                                                                                                                                                   |
   +-----------------------+----------------------------------------------------------+------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
   | name                  | String                                                   | Firewall creation timestamp.                                                                                                                                                                                                                                                                                     |
   +-----------------------+----------------------------------------------------------+------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
   | fw_instance_name      | String                                                   | Firewall name.                                                                                                                                                                                                                                                                                                   |
   +-----------------------+----------------------------------------------------------+------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
   | enterprise_project_id | String                                                   | Enterprise project ID, which is generated after the enterprise project is supported for a user.                                                                                                                                                                                                                  |
   +-----------------------+----------------------------------------------------------+------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
   | ha_type               | Integer                                                  | Cluster type: **0** (active/standby), **1** (cluster). In active/standby mode, there are four nodes. Two active nodes form a cluster, and the other two are the standby of the active nodes. In cluster mode, only two nodes are started to form a cluster.                                                      |
   +-----------------------+----------------------------------------------------------+------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
   | charge_mode           | Integer                                                  | Billing mode: **0** (yearly/monthly), **1** (pay-per-use).                                                                                                                                                                                                                                                       |
   +-----------------------+----------------------------------------------------------+------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
   | service_type          | Integer                                                  | Firewall protection type. Currently, its value can only be **0** (Internet protection).                                                                                                                                                                                                                          |
   +-----------------------+----------------------------------------------------------+------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
   | engine_type           | Integer                                                  | Engine type: **0** (self-developed engine), **1** (Hillstone engine), or **3** (TOPSEC engine).                                                                                                                                                                                                                  |
   +-----------------------+----------------------------------------------------------+------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
   | flavor                | :ref:`Flavor <listfirewalllist__response_flavor>` object | Firewall specifications.                                                                                                                                                                                                                                                                                         |
   +-----------------------+----------------------------------------------------------+------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
   | status                | Integer                                                  | Firewall status: **-1** (waiting for payment), **0** (creating), **1** (deleting), **2** (running), **3** (upgrading), **4** (deleted), **5** (frozen), **6** (creation failed), **7** (deletion failed), **8** (freezing failed), or **9** (being stored), **10** (storage failed), or **11** (upgrade failed). |
   +-----------------------+----------------------------------------------------------+------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
   | tags                  | String                                                   | Tag list, which is a JSON string converted from the tag key value map, for example, "{"key":"value"}".                                                                                                                                                                                                           |
   +-----------------------+----------------------------------------------------------+------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+

.. _listfirewalllist__response_flavor:

.. table:: **Table 9** Flavor

   +---------------------+---------+---------------------------------------------------------------------------------------------------------------------------------------------------------------------+
   | Parameter           | Type    | Description                                                                                                                                                         |
   +=====================+=========+=====================================================================================================================================================================+
   | version             | Integer | Firewall version. Its value can only be **1** (professional edition).                                                                                               |
   +---------------------+---------+---------------------------------------------------------------------------------------------------------------------------------------------------------------------+
   | eip_count           | Integer | Number of EIPs.                                                                                                                                                     |
   +---------------------+---------+---------------------------------------------------------------------------------------------------------------------------------------------------------------------+
   | vpc_count           | Integer | Number of VPCs.                                                                                                                                                     |
   +---------------------+---------+---------------------------------------------------------------------------------------------------------------------------------------------------------------------+
   | bandwidth           | Integer | Bandwidth, in Mbit/s.                                                                                                                                               |
   +---------------------+---------+---------------------------------------------------------------------------------------------------------------------------------------------------------------------+
   | log_storage         | Integer | Log storage, in bytes.                                                                                                                                              |
   +---------------------+---------+---------------------------------------------------------------------------------------------------------------------------------------------------------------------+
   | default_bandwidth   | Integer | Default firewall bandwidth, in Mbit/s. The value is 10 for the standard edition, 50 for the professional edition, and 200 for the pay-per-use professional edition. |
   +---------------------+---------+---------------------------------------------------------------------------------------------------------------------------------------------------------------------+
   | default_eip_count   | Integer | Default number of EIPs. The value is 20 for the standard edition, 50 for the professional edition, and 1,000 for the pay-per-use professional edition.              |
   +---------------------+---------+---------------------------------------------------------------------------------------------------------------------------------------------------------------------+
   | default_log_storage | Integer | Default log storage, in bytes. The default value is **0**.                                                                                                          |
   +---------------------+---------+---------------------------------------------------------------------------------------------------------------------------------------------------------------------+
   | default_vpc_count   | Integer | Default number of VPCs. The value is 0 for the standard edition, 2 for the professional edition, and 5 for the pay-per-use professional edition.                    |
   +---------------------+---------+---------------------------------------------------------------------------------------------------------------------------------------------------------------------+

Example Requests
----------------

Query the firewall list on the first page of the enterprise project whose ID is all_granted_eps and project ID is 14181c1245cf4fd786824efe1e2b9388.

.. code-block::

   https://{Endpoint}/v1/14181c1245cf4fd786824efe1e2b9388/firewalls/list?enterprise_project_id=all_granted_eps

   {
     "limit" : 10,
     "offset" : 0
   }

Example Responses
-----------------

**Status code: 200**

Return value for querying the firewall list.

.. code-block::

   {
     "data" : {
       "limit" : 1,
       "offset" : 0,
       "project_id" : "14181c1245cf4fd786824efe1e2b9388",
       "records" : [ {
         "fw_instance_id" : "ebf891cd-2163-48a0-9963-6309f99dd3c4",
         "resource_id" : "ebf891cd-2163-48a0-9963-6309f99dd3c4",
         "name" : "1709176078374",
         "fw_instance_name" : "test",
         "enterprise_project_id" : "default",
         "tags" : "{\"key_test3\":\"value_test3\"}",
         "ha_type" : 0,
         "charge_mode" : 0,
         "service_type" : 0,
         "engine_type" : 1,
         "flavor" : {
           "version" : 1,
           "eip_count" : 50,
           "vpc_count" : 6,
           "bandwidth" : 50,
           "log_storage" : 0,
           "default_eip_count" : 50,
           "default_vpc_count" : 2,
           "default_bandwidth" : 50,
           "default_log_storage" : 0
         },
         "status" : 2
       } ],
       "total" : 18
     },
     "has_ndr" : false,
     "is_support_basic_version" : true,
     "is_support_buy_professional" : false,
     "is_support_postpaid" : true,
     "user_support_eps" : false
   }

Status Codes
------------

=========== ============================================
Status Code Description
=========== ============================================
200         Return value for querying the firewall list.
=========== ============================================

Error Codes
-----------

See :ref:`Error Codes <errorcode>`.
