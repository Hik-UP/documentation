.. _retrieve:

Retrieve
============

Retrieve all Trail created.

Authentication
------------

Requires an access token.

URL
------------

:code:`POST https://pro-hikup.westeurope.cloudapp.azure.com/api/trail/retrieve`

Request Body
------------

+---------------+-----------+---------------+------------------------------------------------------+
| Parameter     | Type      | Required?     | Description                                          |
+===============+===========+===============+======================================================+
| user          | Object    | Yes           | Object containing user data.                         |
+---------------+-----------+---------------+------------------------------------------------------+
| id            | String    | Yes           | User unique identifier.                              |
+---------------+-----------+---------------+------------------------------------------------------+
| roles         | String[]  | Yes           | Roles assigned to the user.                          |
+---------------+-----------+---------------+------------------------------------------------------+

Response Body
------------

+---------------+-----------+----------------------------------------------------------------------+
| Parameter     | Type      | Description                                                          |
+===============+===========+======================================================================+
| trails        | Object[]  | Array of objects containing Trail data.                              |
+---------------+-----------+----------------------------------------------------------------------+
| id            | String    | Trail unique identifier.                                             |
+---------------+-----------+----------------------------------------------------------------------+
| name          | String    | Trail name.                                                          |
+---------------+-----------+----------------------------------------------------------------------+
| description   | String    | Trail description.                                                   |
+---------------+-----------+----------------------------------------------------------------------+
| pictures      | String[]  | Array of strings containing Trail pictures (base64).                 |
+---------------+-----------+----------------------------------------------------------------------+
| latitude      | Double    | Trail latitude coordinate.                                           |
+---------------+-----------+----------------------------------------------------------------------+
| longitude     | Double    | Trail longitude coordinate.                                          |
+---------------+-----------+----------------------------------------------------------------------+
| difficulty    | Int       | Trail difficulty.                                                    |
+---------------+-----------+----------------------------------------------------------------------+
| duration      | Int       | Trail duration (minutes).                                            |
+---------------+-----------+----------------------------------------------------------------------+
| distance      | Int       | Trail distance (meters).                                             |
+---------------+-----------+----------------------------------------------------------------------+
| uphill        | Int       | Trail uphill (meters).                                               |
+---------------+-----------+----------------------------------------------------------------------+
| downhill      | Int       | Trail downhill (meters).                                             |
+---------------+-----------+----------------------------------------------------------------------+
| labels        | String    | Trail labels.                                                        |
+---------------+-----------+----------------------------------------------------------------------+
| geoJSON       | String    | Trail geoJSON.                                                       |
+---------------+-----------+----------------------------------------------------------------------+
| comments      | Object[]  | Array of objects containing Comment data.                            |
+---------------+-----------+----------------------------------------------------------------------+
| id            | String    | Comment unique identifier.                                           |
+---------------+-----------+----------------------------------------------------------------------+
| author        | Object    | Object containing User data.                                         |
+---------------+-----------+----------------------------------------------------------------------+
| username      | String    | Author username.                                                     |
+---------------+-----------+----------------------------------------------------------------------+
| picture       | String    | Author profile picture (base64).                                     |
+---------------+-----------+----------------------------------------------------------------------+
| body          | String    | Comment body.                                                        |
+---------------+-----------+----------------------------------------------------------------------+
| pictures      | String[]  | Array of pictures attached to Comment (base64).                      |
+---------------+-----------+----------------------------------------------------------------------+
| date          | Date      | Date on which the Comment has been created.                          |
+---------------+-----------+----------------------------------------------------------------------+

Response Codes
------------

+---------------------------+----------------------------------------------------------------------+
| HTTP Code                 | Meaning                                                              |
+===========================+======================================================================+
| 200 OK                    | Trail was successfully retrieved.                                    |
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

    curl --location --request POST 'https://pro-hikup.westeurope.cloudapp.azure.com/api/trail/retrieve' \
    --header 'Authorization: Bearer xxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxx'                              \
    --data-raw '{
        "user": {
            "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
            "roles": ["XXXX"]
        }
    }'

Example Response
------------

.. code-block:: console

    {
        "trails": [
            {
                "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
                "name": "xxxxxxxxxxx",
                "description": "xxxx",
                "pictures": [
                    "xxxxxxxxxxxxxxx"
                ],
                "latitude": 48.862725,
                "longitude": 2.287592,
                "difficulty": 0,
                "duration": 0,
                "distance": 0,
                "uphill": 0,
                "downhill": 0,
                "labels": [
                    "xxxx"
                ],
                "geoJSON": "xxxxxxxx",
                "comments": [
                    {
                        "username": "xxxxxxxx",
                        "picture": "xxxxxxxxx"
                    },
                    {
                        "username": "xxxxxxxx",
                        "picture": "xxxxxxxxx"
                    }
                ]
            },
            {
                "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
                "name": "xxxxxxxxxxx",
                "description": "xxxx",
                "pictures": [
                    "xxxxxxxxxxxxxxx",
                    "xxxxxxxxxxxxxxx"
                ],
                "latitude": 48.869725,
                "longitude": 9.287592,
                "difficulty": 0,
                "duration": 0,
                "distance": 0,
                "uphill": 0,
                "downhill": 0,
                "labels": [
                    "xxxx"
                ],
                "geoJSON": "xxxxxxxx",
                "comments": [
                    {
                        "username": "xxxxxxxx",
                        "picture": "xxxxxxxxx"
                    }
                ]
            }
        ]
    }
