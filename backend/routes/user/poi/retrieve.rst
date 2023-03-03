.. _retrieve:

Retrieve
============

Retrieve all PointOfInterest created or shared with user.

Authentication
------------

Requires an access token.

URL
------------

:code:`POST https://pro-hikup.westeurope.cloudapp.azure.com/api/user/poi/retrieve`

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
| poi           | Object    | Yes           | Object containing poi data.                          |
+---------------+-----------+---------------+------------------------------------------------------+
| target        | String[]  | Yes           | Values: created || shared                            |
+---------------+-----------+---------------+------------------------------------------------------+

Response Body
------------

+---------------+-----------+----------------------------------------------------------------------+
| Parameter     | Type      | Description                                                          |
+===============+===========+======================================================================+
| poi           | Object[]  | Array of objects containing PointOfInterest data.                    |
+---------------+-----------+----------------------------------------------------------------------+
| id            | String    | PointOfInterest unique identifier.                                   |
+---------------+-----------+----------------------------------------------------------------------+
| name          | String    | PointOfInterest name.                                                |
+---------------+-----------+----------------------------------------------------------------------+
| description   | String    | PointOfInterest description.                                         |
+---------------+-----------+----------------------------------------------------------------------+
| pictures      | String[]  | Array of strings containing POI pictures (URL).                      |
+---------------+-----------+----------------------------------------------------------------------+
| sharedWith    | Object[]  | Array of objects containing shared user data.                        |
+---------------+-----------+----------------------------------------------------------------------+
| username      | String    | Username.                                                            |
+---------------+-----------+----------------------------------------------------------------------+
| picture       | String    | User profile picture (URL).                                          |
+---------------+-----------+----------------------------------------------------------------------+
| latitude      | Double    | PointOfInterest latitude coordinate.                                 |
+---------------+-----------+----------------------------------------------------------------------+
| longitude     | Double    | PointOfInterest longitude coordinate.                                |
+---------------+-----------+----------------------------------------------------------------------+
| createdAt     | Date      | PointOfInterest creation date (Epoch Unix Timestamp).                |
+---------------+-----------+----------------------------------------------------------------------+

Response Codes
------------

+---------------------------+----------------------------------------------------------------------+
| HTTP Code                 | Meaning                                                              |
+===========================+======================================================================+
| 200 OK                    | PointOfInterest was successfully retrieved.                          |
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

    curl --location --request POST 'https://pro-hikup.westeurope.cloudapp.azure.com/api/user/poi/retrieve'  \
    --header 'Authorization: Bearer xxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxx'                                  \
    --data-raw '{
        "user": {
            "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
            "roles": ["XXXX"]
        },
        "hike": {
            "target": ["created", "shared"]
        }
    }'

Example Response
------------

.. code-block:: console

    {
        "poi": {
            "created": [
                {
                    "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
                    "name": "xxxxxxxxxxxxxxxxx",
                    "description": "xxxxxxxxxx",
                    "pictures": [
                        "https://xxxxxxx.xxx"
                    ],
                    "creator": {
                        "username": "xxxxxxxxxxx",
                        "picture": "https://xxxxxxx.xxx"
                    },
                    "sharedWith": [
                        {
                            "username": "xxxxxxx",
                            "picture": "https://xxxxxx.xxx"
                        }
                    ],
                    "trail": {
                        "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
                        "name": "xxxxxxxxxxxx",
                        "address": "xxxxxxxxxxxxxxx",
                        "description": "xxxxxxxxxxxxxxxxx",
                        "pictures": [
                            "https://xxxxxxxx.xxxxx"
                        ],
                        "latitude": 0.000000000000,
                        "longitude": 0.000000000000,
                        "difficulty": 0,
                        "duration": 0,
                        "distance": 0,
                        "uphill": 0,
                        "downhill": 0,
                        "tools": [
                            "https://xxxxxxxxx.xxxxxx"
                        ],
                        "relatedArticles": [
                            "https://xxxxxx.xxx"
                        ],
                        "labels": [
                            "xxxxxxx"
                        ],
                        "geoJSON": "xxxxxxxxxxxx",
                        "comments": []
                    },
                    "latitude": 0.000000000000,
                    "longitude": 0.000000000000,
                    "createdAt": "2020-01-20T09:35:52.359Z"
                }
            ],
            "shared": []
        }
    }
