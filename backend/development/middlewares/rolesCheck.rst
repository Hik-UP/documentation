.. _rolesCheck:

rolesCheck
============

Allow only specific roles to access a route.

Arguments
------------

+---------------+-----------+---------------+------------------------------------------------------+
| Parameter     | Type      | Required?     | Description                                          |
+===============+===========+===============+======================================================+
| allowRoles    | String[]  | Yes           | Roles allowed to access the route.                   |
+---------------+-----------+---------------+------------------------------------------------------+

Response Codes
------------

+---------------------------+----------------------------------------------------------------------+
| HTTP Code                 | Meaning                                                              |
+===========================+======================================================================+
| 401 Unauthorized          | User is not part of roles allowed to access the route.               |
+---------------------------+----------------------------------------------------------------------+
| 500 Internal Server Error |                                                                      |
+---------------------------+----------------------------------------------------------------------+

Example Usage
------------

Allow **only** ADMIN to access the route to create a new trail:

.. code-block:: console

    trailRoutes.post('/create', roleCheck(['ADMIN']), trailCtrl.create);

Allow ADMIN **and** USER to access the route to create a new trail:

.. code-block:: console

    trailRoutes.post('/create', roleCheck(['USER', 'ADMIN']), trailCtrl.create);
