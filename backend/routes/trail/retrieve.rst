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

+-------------------+-----------+----------------------------------------------------------------------+
| Parameter         | Type      | Description                                                          |
+===================+===========+======================================================================+
| trails            | Object[]  | Array of objects containing Trail data.                              |
+-------------------+-----------+----------------------------------------------------------------------+
| id                | String    | Trail unique identifier.                                             |
+-------------------+-----------+----------------------------------------------------------------------+
| name              | String    | Trail name.                                                          |
+-------------------+-----------+----------------------------------------------------------------------+
| address           | String    | Trail address.                                                       |
+-------------------+-----------+----------------------------------------------------------------------+
| description       | String    | Trail description.                                                   |
+-------------------+-----------+----------------------------------------------------------------------+
| pictures          | String[]  | Array of strings containing Trail pictures (URL).                    |
+-------------------+-----------+----------------------------------------------------------------------+
| latitude          | Double    | Trail latitude coordinate.                                           |
+-------------------+-----------+----------------------------------------------------------------------+
| longitude         | Double    | Trail longitude coordinate.                                          |
+-------------------+-----------+----------------------------------------------------------------------+
| difficulty        | Int       | Trail difficulty.                                                    |
+-------------------+-----------+----------------------------------------------------------------------+
| duration          | Int       | Trail duration (minutes).                                            |
+-------------------+-----------+----------------------------------------------------------------------+
| distance          | Int       | Trail distance (meters).                                             |
+-------------------+-----------+----------------------------------------------------------------------+
| uphill            | Int       | Trail uphill (meters).                                               |
+-------------------+-----------+----------------------------------------------------------------------+
| downhill          | Int       | Trail downhill (meters).                                             |
+-------------------+-----------+----------------------------------------------------------------------+
| tools             | String[]  | List of tools needed for this Trail.                                 |
+-------------------+-----------+----------------------------------------------------------------------+
| relatedArticles   | String[]  | List of articles (URL) related to this Trail.                        |
+-------------------+-----------+----------------------------------------------------------------------+
| labels            | String[]  | Trail labels.                                                        |
+-------------------+-----------+----------------------------------------------------------------------+
| geoJSON           | String    | Trail geoJSON.                                                       |
+-------------------+-----------+----------------------------------------------------------------------+
| comments          | Object[]  | Array of objects containing Comment data.                            |
+-------------------+-----------+----------------------------------------------------------------------+
| id                | String    | Comment unique identifier.                                           |
+-------------------+-----------+----------------------------------------------------------------------+
| author            | Object    | Object containing User data.                                         |
+-------------------+-----------+----------------------------------------------------------------------+
| username          | String    | Author username.                                                     |
+-------------------+-----------+----------------------------------------------------------------------+
| picture           | String    | Author profile picture (URL).                                        |
+-------------------+-----------+----------------------------------------------------------------------+
| body              | String    | Comment body.                                                        |
+-------------------+-----------+----------------------------------------------------------------------+
| pictures          | String[]  | Array of pictures attached to Comment (URL).                         |
+-------------------+-----------+----------------------------------------------------------------------+
| date              | Date      | Date on which the Comment has been created.                          |
+-------------------+-----------+----------------------------------------------------------------------+

Response Codes
------------

+---------------------------+----------------------------------------------------------------------+
| HTTP Code                 | Meaning                                                              |
+===========================+======================================================================+
| 200 OK                    | Trail was successfully retrieved.                                    |
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
                "address": "xxxxxxxx",
                "description": "xxxx",
                "pictures": [
                    "https://xxxxxx.xxx"
                ],
                "latitude": 0.000000000000,
                "longitude": 0.000000000000,
                "difficulty": 0,
                "duration": 0,
                "distance": 0,
                "uphill": 0,
                "downhill": 0,
                "tools": [
                    "xxxxxxxxxxxxxxxxxxxx"
                ],
                "relatedArticles": [
                    "https://xxxxxx.xxx"
                ],
                "labels": [
                    "xxxx"
                ],
                "geoJSON": "xxxxxxxx",
                "comments": [
                    {
                        "username": "xxxxxxxx",
                        "picture": "https://xxxxxx.xxx"
                    },
                    {
                        "username": "xxxxxxxx",
                        "picture": "https://xxxxxx.xxx"
                    }
                ]
            },
            {
                "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
                "name": "xxxxxxxxxxx",
                "address": "xxxxxxxx",
                "description": "xxxx",
                "pictures": [
                    "https://xxxxxx.xxx",
                    "https://xxxxxx.xxx"
                ],
                "latitude": 0.000000000000,
                "longitude": 0.000000000000,
                "difficulty": 0,
                "duration": 0,
                "distance": 0,
                "uphill": 0,
                "downhill": 0,
                "tools": [
                    "xxxxxxxxxxxxxxxxxxxx"
                ],
                "relatedArticles": [
                    "https://xxxxxx.xxx"
                ],
                "labels": [
                    "xxxx"
                ],
                "geoJSON": "xxxxxxxx",
                "comments": [
                    {
                        "username": "xxxxxxxx",
                        "picture": "https://xxxxxx.xxx"
                    }
                ]
            }
        ]
    }
