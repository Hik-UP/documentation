.. _update:

Update
============

Update an existing Hike.

Authentication
------------

Requires an access token.

URL
------------

:code:`PUT https://pro-hikup.westeurope.cloudapp.azure.com/api/hike/update`

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
| trail             | Object    | No            | Object containing Trail data.                        |
+-------------------+-----------+---------------+------------------------------------------------------+
| id                | String    | No            | Trail unique identifier.                             |
+-------------------+-----------+---------------+------------------------------------------------------+
| hike              | Object    | Yes           | Object containing Hike data.                         |
+-------------------+-----------+---------------+------------------------------------------------------+
| id                | String    | Yes           | Hike unique identifier.                              |
+-------------------+-----------+---------------+------------------------------------------------------+
| name              | String    | No            | Hike name.                                           |
+-------------------+-----------+---------------+------------------------------------------------------+
| description       | String    | No            | Hike description.                                    |
+-------------------+-----------+---------------+------------------------------------------------------+
| attendees         | Object    | No            | Object containing attendees data.                    |
+-------------------+-----------+---------------+------------------------------------------------------+
| remove            | Object[]  | No            | Object containing removed attendees data.            |
+-------------------+-----------+---------------+------------------------------------------------------+
| email             | String    | Yes           | Attendee email address.                              |
+-------------------+-----------+---------------+------------------------------------------------------+
| guests            | Object    | No            | Object containing guests data.                       |
+-------------------+-----------+---------------+------------------------------------------------------+
| add               | Object[]  | No            | Object containing added guests data.                 |
+-------------------+-----------+---------------+------------------------------------------------------+
| email             | String    | Yes           | Guest email address.                                 |
+-------------------+-----------+---------------+------------------------------------------------------+
| remove            | Object[]  | No            | Object containing removed guests data.               |
+-------------------+-----------+---------------+------------------------------------------------------+
| email             | String    | Yes           | Guest email address.                                 |
+-------------------+-----------+---------------+------------------------------------------------------+
| schedule          | Date      | No            | Hike schedule date (Epoch Unix Timestamp).           |
+-------------------+-----------+---------------+------------------------------------------------------+

Response Body
------------

+---------------+-----------+----------------------------------------------------------------------+
| Parameter     | Type      | Description                                                          |
+===============+===========+======================================================================+
| message       | String    | A message confirming that the Hike was updated.                      |
+---------------+-----------+----------------------------------------------------------------------+

Response Codes
------------

+---------------------------+----------------------------------------------------------------------+
| HTTP Code                 | Meaning                                                              |
+===========================+======================================================================+
| 200 OK                    | Hike was successfully updated.                                       |
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

    curl --location --request PUT 'https://pro-hikup.westeurope.cloudapp.azure.com/api/hike/update'     \
    --header 'Authorization: Bearer xxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxx'                              \
    --data-raw '{
        "user": {
            "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
            "roles": ["XXXX"]
        },
        "trail": {
            "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx"
        },
        "hike": {
            "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
            "name": "xxxxxxxxxxx",
            "description": "xxxx",
            "attendees": {
                "remove": [{ "email": "xxxx@xxxx.xxx" }]
            },
            "guests": {
                "add": [{ "email": "xxxx@xxxx.xxx" }],
                "remove": [{ "email": "xxxx@xxxx.xxx" }, { "email": "xxxx@xxxx.xxx" }]
            },
            "schedule": 1677230731
        }
    }'

Example Response
------------

.. code-block:: console

    {
        "message": "Updated"
    }
