:original_name: cfw_01_0242.html

.. _cfw_01_0242:

Can WAF and CFW Be Deployed Together?
=====================================

Yes. WAF has two modes: exclusive mode and cloud mode. The traffic trend varies depending on the mode. The details are as follows:

-  Exclusive mode: Internet -> CFW -> WAF (dedicated mode) -> Origin server
-  Cloud mode: Internet -> WAF (cloud mode) -> CFW -> Origin server

.. note::

   -  If you have purchased WAF in cloud mode, exercise caution when configuring traffic blocking rules. You are advised to configure traffic permitting rules or whitelists.
   -  If you have purchased WAF in dedicated mode, configure it based on service requirements.
