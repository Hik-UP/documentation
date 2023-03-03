.. _update:

Update
============

Update an existing PointOfInterest.

Authentication
------------

Requires an access token.

URL
------------

:code:`PUT https://pro-hikup.westeurope.cloudapp.azure.com/api/user/poi/update`

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
| name              | String    | No            | PointOfInterest name.                                |
+-------------------+-----------+---------------+------------------------------------------------------+
| description       | String    | No            | PointOfInterest description.                         |
+-------------------+-----------+---------------+------------------------------------------------------+
| pictures          | String[]  | No            | Array of strings containing POI pictures (URL).      |
+-------------------+-----------+---------------+------------------------------------------------------+
| sharedWith        | Object    | No            | Object containing users data.                        |
+-------------------+-----------+---------------+------------------------------------------------------+
| add               | Object[]  | No            | Object containing added users data.                  |
+-------------------+-----------+---------------+------------------------------------------------------+
| email             | String    | Yes           | User email address.                                  |
+-------------------+-----------+---------------+------------------------------------------------------+
| remove            | Object[]  | No            | Object containing removed users data.                |
+-------------------+-----------+---------------+------------------------------------------------------+
| email             | String    | Yes           | User email address.                                  |
+-------------------+-----------+---------------+------------------------------------------------------+

Response Body
------------

+---------------+-----------+----------------------------------------------------------------------+
| Parameter     | Type      | Description                                                          |
+===============+===========+======================================================================+
| message       | String    | A message confirming that the PointOfInterest was updated.           |
+---------------+-----------+----------------------------------------------------------------------+

Response Codes
------------

+---------------------------+----------------------------------------------------------------------+
| HTTP Code                 | Meaning                                                              |
+===========================+======================================================================+
| 200 OK                    | PointOfInterest was successfully updated.                            |
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

    curl --location --request PUT 'https://pro-hikup.westeurope.cloudapp.azure.com/api/user/poi/update' \
    --header 'Authorization: Bearer xxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxx'                              \
    --data-raw '{
        "user": {
            "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
            "roles": ["XXXX"]
        },
        "poi": {
            "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
            "name": "xxxxxxxxxxx",
            "description": "xxxx",
            "pictures": ["https://xxxxxxx.xxx"],
            "sharedWith": {
                "add": [{ "email": "xxxx@xxxx.xxx" }],
                "remove": [{ "email": "xxxx@xxxx.xxx" }, { "email": "xxxx@xxxx.xxx" }]
            }
        }
    }'

Example Response
------------

.. code-block:: console

    {
        "message": "Updated"
    }
