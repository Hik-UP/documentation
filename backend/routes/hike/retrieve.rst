.. _retrieve:

Retrieve
============

Retrieve all Hike created.

Authentication
------------

Requires an access token.

URL
------------

:code:`POST https://pro-hikup.westeurope.cloudapp.azure.com/api/hike/retrieve`

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
| hikes             | Object    | Objects containing Hike data.                                        |
+-------------------+-----------+----------------------------------------------------------------------+
| organized         | Object[]  | Array of objects containing organized Hike data.                     |
+-------------------+-----------+----------------------------------------------------------------------+
| id                | String    | Hike unique identifier.                                              |
+-------------------+-----------+----------------------------------------------------------------------+
| name              | String    | Hike name.                                                           |
+-------------------+-----------+----------------------------------------------------------------------+
| description       | String    | Trail description.                                                   |
+-------------------+-----------+----------------------------------------------------------------------+
| trail             | Object    | Objects containing Trail data.                                       |
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
| organizers        | Object[]  | Array of objects containing organizers data.                         |
+-------------------+-----------+----------------------------------------------------------------------+
| username          | String    | Username.                                                            |
+-------------------+-----------+----------------------------------------------------------------------+
| picture           | String    | User profile picture (URL).                                          |
+-------------------+-----------+----------------------------------------------------------------------+
| attendees         | Object[]  | Array of objects containing attendees data.                          |
+-------------------+-----------+----------------------------------------------------------------------+
| username          | String    | Username.                                                            |
+-------------------+-----------+----------------------------------------------------------------------+
| picture           | String    | User profile picture (URL).                                          |
+-------------------+-----------+----------------------------------------------------------------------+
| guests            | Object[]  | Array of objects containing guests data.                             |
+-------------------+-----------+----------------------------------------------------------------------+
| username          | String    | Username.                                                            |
+-------------------+-----------+----------------------------------------------------------------------+
| picture           | String    | User profile picture (URL).                                          |
+-------------------+-----------+----------------------------------------------------------------------+
| schedule          | Date      | Hike schedule date (Epoch Unix Timestamp).                           |
+-------------------+-----------+----------------------------------------------------------------------+
| createdAt         | Date      | Hike creation date (Epoch Unix Timestamp).                           |
+-------------------+-----------+----------------------------------------------------------------------+
| attendee          | Object[]  | Array of objects containing attendee Hike data.                      |
+-------------------+-----------+----------------------------------------------------------------------+
| id                | String    | Hike unique identifier.                                              |
+-------------------+-----------+----------------------------------------------------------------------+
| name              | String    | Hike name.                                                           |
+-------------------+-----------+----------------------------------------------------------------------+
| description       | String    | Trail description.                                                   |
+-------------------+-----------+----------------------------------------------------------------------+
| trail             | Object    | Objects containing Trail data.                                       |
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
| organizers        | Object[]  | Array of objects containing organizers data.                         |
+-------------------+-----------+----------------------------------------------------------------------+
| username          | String    | Username.                                                            |
+-------------------+-----------+----------------------------------------------------------------------+
| picture           | String    | User profile picture (URL).                                          |
+-------------------+-----------+----------------------------------------------------------------------+
| attendees         | Object[]  | Array of objects containing attendees data.                          |
+-------------------+-----------+----------------------------------------------------------------------+
| username          | String    | Username.                                                            |
+-------------------+-----------+----------------------------------------------------------------------+
| picture           | String    | User profile picture (URL).                                          |
+-------------------+-----------+----------------------------------------------------------------------+
| guests            | Object[]  | Array of objects containing guests data.                             |
+-------------------+-----------+----------------------------------------------------------------------+
| username          | String    | Username.                                                            |
+-------------------+-----------+----------------------------------------------------------------------+
| picture           | String    | User profile picture (URL).                                          |
+-------------------+-----------+----------------------------------------------------------------------+
| schedule          | Date      | Hike schedule date (Epoch Unix Timestamp).                           |
+-------------------+-----------+----------------------------------------------------------------------+
| createdAt         | Date      | Hike creation date (Epoch Unix Timestamp).                           |
+-------------------+-----------+----------------------------------------------------------------------+
| guest             | Object[]  | Array of objects containing guest Hike data.                         |
+-------------------+-----------+----------------------------------------------------------------------+
| id                | String    | Hike unique identifier.                                              |
+-------------------+-----------+----------------------------------------------------------------------+
| name              | String    | Hike name.                                                           |
+-------------------+-----------+----------------------------------------------------------------------+
| description       | String    | Trail description.                                                   |
+-------------------+-----------+----------------------------------------------------------------------+
| trail             | Object    | Objects containing Trail data.                                       |
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
| organizers        | Object[]  | Array of objects containing organizers data.                         |
+-------------------+-----------+----------------------------------------------------------------------+
| username          | String    | Username.                                                            |
+-------------------+-----------+----------------------------------------------------------------------+
| picture           | String    | User profile picture (URL).                                          |
+-------------------+-----------+----------------------------------------------------------------------+
| attendees         | Object[]  | Array of objects containing attendees data.                          |
+-------------------+-----------+----------------------------------------------------------------------+
| username          | String    | Username.                                                            |
+-------------------+-----------+----------------------------------------------------------------------+
| picture           | String    | User profile picture (URL).                                          |
+-------------------+-----------+----------------------------------------------------------------------+
| guests            | Object[]  | Array of objects containing guests data.                             |
+-------------------+-----------+----------------------------------------------------------------------+
| username          | String    | Username.                                                            |
+-------------------+-----------+----------------------------------------------------------------------+
| picture           | String    | User profile picture (URL).                                          |
+-------------------+-----------+----------------------------------------------------------------------+
| schedule          | Date      | Hike schedule date (Epoch Unix Timestamp).                           |
+-------------------+-----------+----------------------------------------------------------------------+
| createdAt         | Date      | Hike creation date (Epoch Unix Timestamp).                           |
+-------------------+-----------+----------------------------------------------------------------------+

Response Codes
------------

+---------------------------+----------------------------------------------------------------------+
| HTTP Code                 | Meaning                                                              |
+===========================+======================================================================+
| 200 OK                    | Hike was successfully retrieved.                                     |
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

    curl --location --request POST 'https://pro-hikup.westeurope.cloudapp.azure.com/api/hike/retrieve'  \
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
        "hikes": {
            "organized": [
                {
                    "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
                    "name": "xxxxxxx",
                    "description": "xxxxxxxxx",
                    "trail": {
                        "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
                        "name": "xxxxxxxxx",
                        "address": "xxxxxxx",
                        "description": "xxxxxxxxxx",
                        "pictures": [
                            "https://xxxxxx.xxx"
                        ],
                        "latitude": 48.862725,
                        "longitude": 2.287592,
                        "difficulty": 0,
                        "duration": 0,
                        "distance": 0,
                        "uphill": 0,
                        "downhill": 0,
                        "tools": [
                            "https://xxxxxxx.xxx"
                        ],
                        "relatedArticles": [
                            "https://xxxxxxx.xxx"
                        ],
                        "labels": [
                            "xxxxxxxxx"
                        ],
                        "geoJSON": "xxxxxx",
                        "comments": []
                    },
                    "organizers": [
                        {
                            "username": "xxxxxxx",
                            "picture": "https://xxxxxx.xxx"
                        }
                    ],
                    "attendees": [
                        {
                            "username": "xxxxxxx",
                            "picture": "https://xxxxxx.xxx"
                        }
                    ],
                    "guests": [
                        {
                            "username": "xxxxxxxxx",
                            "picture": "https://xxxxxx.xxx"
                        }
                    ],
                    "schedule": "2020-01-20T09:37:20.000Z",
                    "createdAt": "2020-01-20T09:35:52.359Z"
                }
            ],
            "attendee": [
                {
                    "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
                    "name": "xxxxxxx",
                    "description": "xxxxxxxxx",
                    "trail": {
                        "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
                        "name": "xxxxxxxxx",
                        "address": "xxxxxxx",
                        "description": "xxxxxxxxxx",
                        "pictures": [
                            "https://xxxxxx.xxx"
                        ],
                        "latitude": 48.862725,
                        "longitude": 2.287592,
                        "difficulty": 0,
                        "duration": 0,
                        "distance": 0,
                        "uphill": 0,
                        "downhill": 0,
                        "tools": [
                            "https://xxxxxxx.xxx"
                        ],
                        "relatedArticles": [
                            "https://xxxxxxx.xxx"
                        ],
                        "labels": [
                            "xxxxxxxxx"
                        ],
                        "geoJSON": "xxxxxx",
                        "comments": []
                    },
                    "organizers": [
                        {
                            "username": "xxxxxxx",
                            "picture": "https://xxxxxx.xxx"
                        }
                    ],
                    "attendees": [
                        {
                            "username": "xxxxxxx",
                            "picture": "https://xxxxxx.xxx"
                        }
                    ],
                    "guests": [
                        {
                            "username": "xxxxxxxxx",
                            "picture": "https://xxxxxx.xxx"
                        }
                    ],
                    "schedule": "2020-01-20T09:37:20.000Z",
                    "createdAt": "2020-01-20T09:35:52.359Z"
                }
            ],
            "guest": [
                {
                    "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
                    "name": "xxxxxxx",
                    "description": "xxxxxxxxx",
                    "trail": {
                        "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
                        "name": "xxxxxxxxx",
                        "address": "xxxxxxx",
                        "description": "xxxxxxxxxx",
                        "pictures": [
                            "https://xxxxxx.xxx"
                        ],
                        "latitude": 48.862725,
                        "longitude": 2.287592,
                        "difficulty": 0,
                        "duration": 0,
                        "distance": 0,
                        "uphill": 0,
                        "downhill": 0,
                        "tools": [
                            "https://xxxxxxx.xxx"
                        ],
                        "relatedArticles": [
                            "https://xxxxxxx.xxx"
                        ],
                        "labels": [
                            "xxxxxxxxx"
                        ],
                        "geoJSON": "xxxxxx",
                        "comments": []
                    },
                    "organizers": [
                        {
                            "username": "xxxxxxx",
                            "picture": "https://xxxxxx.xxx"
                        }
                    ],
                    "attendees": [
                        {
                            "username": "xxxxxxx",
                            "picture": "https://xxxxxx.xxx"
                        }
                    ],
                    "guests": [
                        {
                            "username": "xxxxxxxxx",
                            "picture": "https://xxxxxx.xxx"
                        }
                    ],
                    "schedule": "2020-01-20T09:37:20.000Z",
                    "createdAt": "2020-01-20T09:35:52.359Z"
                },
                {
                    "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
                    "name": "xxxxxxx",
                    "description": "xxxxxxxxx",
                    "trail": {
                        "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
                        "name": "xxxxxxxxx",
                        "address": "xxxxxxx",
                        "description": "xxxxxxxxxx",
                        "pictures": [
                            "https://xxxxxx.xxx"
                        ],
                        "latitude": 48.862725,
                        "longitude": 2.287592,
                        "difficulty": 0,
                        "duration": 0,
                        "distance": 0,
                        "uphill": 0,
                        "downhill": 0,
                        "tools": [
                            "https://xxxxxxx.xxx"
                        ],
                        "relatedArticles": [
                            "https://xxxxxxx.xxx"
                        ],
                        "labels": [
                            "xxxxxxxxx"
                        ],
                        "geoJSON": "xxxxxx",
                        "comments": []
                    },
                    "organizers": [
                        {
                            "username": "xxxxxxx",
                            "picture": "https://xxxxxx.xxx"
                        }
                    ],
                    "attendees": [
                        {
                            "username": "xxxxxxx",
                            "picture": "https://xxxxxx.xxx"
                        }
                    ],
                    "guests": [
                        {
                            "username": "xxxxxxxxx",
                            "picture": "https://xxxxxx.xxx"
                        }
                    ],
                    "schedule": "2020-01-20T09:37:20.000Z",
                    "createdAt": "2020-01-20T09:35:52.359Z"
                }
            ]
        }
    }
