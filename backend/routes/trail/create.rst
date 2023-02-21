.. _create:

Create
============

Create a new Trail.

Authentication
------------

Requires an access token.
User need to be a member of the ADMIN group.

URL
------------

:code:`POST https://pro-hikup.westeurope.cloudapp.azure.com/api/trail/create`

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
| name              | String    | Yes           | Trail name.                                          |
+-------------------+-----------+---------------+------------------------------------------------------+
| description       | String    | Yes           | Trail description.                                   |
+-------------------+-----------+---------------+------------------------------------------------------+
| pictures          | String[]  | Yes           | Array of strings containing Trail pictures (URL).    |
+-------------------+-----------+---------------+------------------------------------------------------+
| latitude          | Double    | Yes           | Trail latitude coordinate.                           |
+-------------------+-----------+---------------+------------------------------------------------------+
| longitude         | Double    | Yes           | Trail longitude coordinate.                          |
+-------------------+-----------+---------------+------------------------------------------------------+
| difficulty        | Int       | Yes           | Trail difficulty.                                    |
+-------------------+-----------+---------------+------------------------------------------------------+
| duration          | Int       | Yes           | Trail duration (minutes).                            |
+-------------------+-----------+---------------+------------------------------------------------------+
| distance          | Int       | Yes           | Trail distance (meters).                             |
+-------------------+-----------+---------------+------------------------------------------------------+
| uphill            | Int       | Yes           | Trail uphill (meters).                               |
+-------------------+-----------+---------------+------------------------------------------------------+
| downhill          | Int       | Yes           | Trail downhill (meters).                             |
+-------------------+-----------+---------------+------------------------------------------------------+
| tools             | String[]  | Yes           | List of tools needed for this Trail.                 |
+-------------------+-----------+---------------+------------------------------------------------------+
| relatedArticles   | String[]  | Yes           | List of articles (URL) related to this Trail.        |
+-------------------+-----------+---------------+------------------------------------------------------+
| labels            | String[]  | Yes           | Trail labels.                                        |
+-------------------+-----------+---------------+------------------------------------------------------+
| geoJSON           | String    | Yes           | Trail geoJSON.                                       |
+-------------------+-----------+---------------+------------------------------------------------------+

Response Body
------------

+---------------+-----------+----------------------------------------------------------------------+
| Parameter     | Type      | Description                                                          |
+===============+===========+======================================================================+
| message       | String    | A message confirming that the Trail was created.                     |
+---------------+-----------+----------------------------------------------------------------------+

Response Codes
------------

+---------------------------+----------------------------------------------------------------------+
| HTTP Code                 | Meaning                                                              |
+===========================+======================================================================+
| 201 Created               | Trail creation succeed.                                              |
+---------------------------+----------------------------------------------------------------------+
| 400 Bad Request           |                                                                      |
+---------------------------+----------------------------------------------------------------------+
| 401 Unauthorized          | The Authorization header must specify a user access token.           |
|                           | The OAuth token is not valid.                                        |
|                           | User id specified does not match the userId specified in token.      |
|                           | User roles specified does not match roles specified in token.        |
+---------------------------+----------------------------------------------------------------------+
| 500 Internal Server Error | Latitude & longitude must be Double.                                 |
+---------------------------+----------------------------------------------------------------------+

Example Request
------------

.. code-block:: console

    curl --location --request POST 'https://pro-hikup.westeurope.cloudapp.azure.com/api/trail/create'   \
    --header 'Authorization: Bearer xxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxx'                              \
    --data-raw '{
        "user": {
            "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
            "roles": ["XXXX"]
        },
        "trail": {
            "name": "xxxxxxxxxxx",
            "description": "xxxx",
            "pictures": ["xxxxx"],
            "latitude": 48.862725,
            "longitude": 2.287592,
            "difficulty": 0,
            "duration": 0,
            "distance": 0,
            "uphill": 0,
            "downhill": 0,
            "tools": ["xxxxxxxx"],
            "relatedArticles": ["xxxxxxxxxx"],
            "labels": ["xxxxxxx"],
            "geoJSON": "xxxxxxxx"
        }
    }'

Example Response
------------

.. code-block:: console

    {
        "message": "Created"
    }
