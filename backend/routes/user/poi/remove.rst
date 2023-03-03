.. _remove:

Remove
============

Remove an existing PointOfInterest from shared or created list.

Authentication
------------

Requires an access token.

URL
------------

:code:`DELETE https://pro-hikup.westeurope.cloudapp.azure.com/api/user/poi/remove`

Request Body
------------

+-------------------+-----------+---------------+------------------------------------------------------+
| Parameter         | Type      | Required?     | Description                                          |
+===================+===========+===============+======================================================+
| user              | Object    | Yes           | Object containing user data.                         |
+-------------------+-----------+---------------+------------------------------------------------------+
| id                | String    | Yes           | User unique identifier.                              |
+-------------------+-----------+---------------+------------------------------------------------------+
| roles             | String[]  | Yes           | Roles assigned to the user.                          |
+-------------------+-----------+---------------+------------------------------------------------------+
| poi               | Object    | Yes           | Object containing PointOfInterest data.              |
+-------------------+-----------+---------------+------------------------------------------------------+
| id                | String    | Yes           | PointOfInterest unique identifier.                   |
+-------------------+-----------+---------------+------------------------------------------------------+

Response Body
------------

+---------------+-----------+----------------------------------------------------------------------+
| Parameter     | Type      | Description                                                          |
+===============+===========+======================================================================+
| message       | String    | A message confirming that the PointOfInterest was removed.           |
+---------------+-----------+----------------------------------------------------------------------+

Response Codes
------------

+---------------------------+----------------------------------------------------------------------+
| HTTP Code                 | Meaning                                                              |
+===========================+======================================================================+
| 200 OK                    | PointOfInterest was successfully removed.                            |
+---------------------------+----------------------------------------------------------------------+
| 400 Bad Request           |                                                                      |
+---------------------------+----------------------------------------------------------------------+
| 401 Unauthorized          | The Authorization header must specify a user access token.           |
|                           | The OAuth token is not valid.                                        |
|                           | User id specified does not match the userId specified in token.      |
|                           | User roles specified does not match roles specified in token.        |
+---------------------------+----------------------------------------------------------------------+
| 500 Internal Server Error |                                                                      |
+---------------------------+----------------------------------------------------------------------+

Example Request
------------

.. code-block:: console

    curl --location --request DELETE 'https://pro-hikup.westeurope.cloudapp.azure.com/api/user/poi/remove'  \
    --header 'Authorization: Bearer xxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxx'                                  \
    --data-raw '{
        "user": {
            "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
            "roles": ["XXXX"]
        },
        "poi": {
            "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx"
        }
    }'

Example Response
------------

.. code-block:: console

    {
        "message": "Deleted"
    }
