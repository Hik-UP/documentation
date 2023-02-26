.. _remove:

Remove
============

Remove an existing Hike.

Authentication
------------

Requires an access token.

URL
------------

:code:`DELETE https://pro-hikup.westeurope.cloudapp.azure.com/api/hike/remove`

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
| hike              | Object    | Yes           | Object containing Hike data.                         |
+-------------------+-----------+---------------+------------------------------------------------------+
| id                | String    | Yes           | Hike unique identifier.                              |
+-------------------+-----------+---------------+------------------------------------------------------+

Response Body
------------

+---------------+-----------+----------------------------------------------------------------------+
| Parameter     | Type      | Description                                                          |
+===============+===========+======================================================================+
| message       | String    | A message confirming that the Hike was removed.                      |
+---------------+-----------+----------------------------------------------------------------------+

Response Codes
------------

+---------------------------+----------------------------------------------------------------------+
| HTTP Code                 | Meaning                                                              |
+===========================+======================================================================+
| 200 OK                    | Hike was successfully removed.                                       |
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

    curl --location --request DELETE 'https://pro-hikup.westeurope.cloudapp.azure.com/api/hike/remove'  \
    --header 'Authorization: Bearer xxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxx'                              \
    --data-raw '{
        "user": {
            "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
            "roles": ["XXXX"]
        },
        "hike": {
            "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx"
        }
    }'

Example Response
------------

.. code-block:: console

    {
        "message": "Deleted"
    }
