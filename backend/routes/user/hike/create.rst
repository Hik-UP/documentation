.. _create:

Create
============

Create a new Hike.

Authentication
------------

Requires an access token.

URL
------------

:code:`POST https://pro-hikup.westeurope.cloudapp.azure.com/api/user/hike/create`

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
| trail             | Object    | Yes           | Object containing Trail data.                        |
+-------------------+-----------+---------------+------------------------------------------------------+
| id                | String    | Yes           | Trail unique identifier.                             |
+-------------------+-----------+---------------+------------------------------------------------------+
| hike              | Object    | Yes           | Object containing Hike data.                         |
+-------------------+-----------+---------------+------------------------------------------------------+
| name              | String    | Yes           | Hike name.                                           |
+-------------------+-----------+---------------+------------------------------------------------------+
| description       | String    | Yes           | Hike description.                                    |
+-------------------+-----------+---------------+------------------------------------------------------+
| guests            | Object[]  | No            | Object containing guests data.                       |
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
| message       | String    | A message confirming that the Hike was created.                      |
+---------------+-----------+----------------------------------------------------------------------+

Response Codes
------------

+---------------------------+----------------------------------------------------------------------+
| HTTP Code                 | Meaning                                                              |
+===========================+======================================================================+
| 201 Created               | Hike creation succeed.                                               |
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

    curl --location --request POST 'https://pro-hikup.westeurope.cloudapp.azure.com/api/user/hike/create'   \
    --header 'Authorization: Bearer xxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxx'                                  \
    --data-raw '{
        "user": {
            "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
            "roles": ["XXXX"]
        },
        "trail": {
            "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx"
        },
        "hike": {
            "name": "xxxxxxxxxxx",
            "description": "xxxx",
            "guests": [
                {
                    "email": "xxxx@xxxx.xxx"
                },
                {
                    "email": "xxxx@xxxx.xxx"
                }
            ],
            "schedule": 1677230731
        }
    }'

Example Response
------------

.. code-block:: console

    {
        "message": "Created"
    }
