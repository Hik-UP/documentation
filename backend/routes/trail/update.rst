.. _update:

Update
============

Update an existing Trail.

Authentication
------------

Requires an access token.
User need to be a member of the ADMIN group.

URL
------------

:code:`POST https://pro-hikup.westeurope.cloudapp.azure.com/api/trail/update`

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
| name              | String    | No            | Trail name.                                          |
+-------------------+-----------+---------------+------------------------------------------------------+
| address           | String    | No            | Trail address.                                       |
+-------------------+-----------+---------------+------------------------------------------------------+
| description       | String    | No            | Trail description.                                   |
+-------------------+-----------+---------------+------------------------------------------------------+
| pictures          | String[]  | No            | Array of strings containing Trail pictures (URL).    |
+-------------------+-----------+---------------+------------------------------------------------------+
| latitude          | Double    | No            | Trail latitude coordinate.                           |
+-------------------+-----------+---------------+------------------------------------------------------+
| longitude         | Double    | No            | Trail longitude coordinate.                          |
+-------------------+-----------+---------------+------------------------------------------------------+
| difficulty        | Int       | No            | Trail difficulty.                                    |
+-------------------+-----------+---------------+------------------------------------------------------+
| duration          | Int       | No            | Trail duration (minutes).                            |
+-------------------+-----------+---------------+------------------------------------------------------+
| distance          | Int       | No            | Trail distance (meters).                             |
+-------------------+-----------+---------------+------------------------------------------------------+
| uphill            | Int       | No            | Trail uphill (meters).                               |
+-------------------+-----------+---------------+------------------------------------------------------+
| downhill          | Int       | No            | Trail downhill (meters).                             |
+-------------------+-----------+---------------+------------------------------------------------------+
| tools             | String[]  | No            | List of tools needed for this Trail.                 |
+-------------------+-----------+---------------+------------------------------------------------------+
| relatedArticles   | String[]  | No            | List of articles (URL) related to this Trail.        |
+-------------------+-----------+---------------+------------------------------------------------------+
| labels            | String[]  | No            | Trail labels.                                        |
+-------------------+-----------+---------------+------------------------------------------------------+
| geoJSON           | String    | No            | Trail geoJSON.                                       |
+-------------------+-----------+---------------+------------------------------------------------------+

Response Body
------------

+---------------+-----------+----------------------------------------------------------------------+
| Parameter     | Type      | Description                                                          |
+===============+===========+======================================================================+
| message       | String    | A message confirming that the Trail was updated.                     |
+---------------+-----------+----------------------------------------------------------------------+

Response Codes
------------

+---------------------------+----------------------------------------------------------------------+
| HTTP Code                 | Meaning                                                              |
+===========================+======================================================================+
| 200 OK                    | Trail was successfully updated.                                      |
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

    curl --location --request POST 'https://pro-hikup.westeurope.cloudapp.azure.com/api/trail/update'   \
    --header 'Authorization: Bearer xxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxx'                              \
    --data-raw '{
        "user": {
            "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
            "roles": ["XXXX"]
        },
        "trail": {
            "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
            "name": "xxxxxxxxxxx",
            "address": "xxxxxxxx",
            "description": "xxxx",
            "pictures": ["https://xxxxxxx.xxx"],
            "latitude": 0.000000000000,
            "longitude": 0.000000000000,
            "difficulty": 0,
            "duration": 0,
            "distance": 0,
            "uphill": 0,
            "downhill": 0,
            "tools": ["xxxxxxxx"],
            "relatedArticles": ["https://xxxxxxx.xxx"],
            "labels": ["xxxxxxx"],
            "geoJSON": "xxxxxxxx"
        }
    }'

Example Response
------------

.. code-block:: console

    {
        "message": "Updated"
    }
