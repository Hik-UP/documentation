.. _create:

Create
============

Create a new PointOfInterest.

Authentication
------------

Requires an access token.

URL
------------

:code:`POST https://pro-hikup.westeurope.cloudapp.azure.com/api/user/poi/create`

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
| trail         | Object    | Yes           | Object containing Trail data.                        |
+---------------+-----------+---------------+------------------------------------------------------+
| id            | String    | Yes           | Trail unique identifier.                             |
+---------------+-----------+---------------+------------------------------------------------------+
| poi           | Object    | Yes           | Object containing PointOfInterest data.              |
+---------------+-----------+---------------+------------------------------------------------------+
| name          | String    | Yes           | PointOfInterest name.                                |
+---------------+-----------+---------------+------------------------------------------------------+
| description   | String    | Yes           | PointOfInterest description.                         |
+---------------+-----------+---------------+------------------------------------------------------+
| pictures      | String[]  | No            | Array of strings containing POI pictures (URL).      |
+---------------+-----------+---------------+------------------------------------------------------+
| sharedWith    | Object[]  | No            | Object containing shared user data.                  |
+---------------+-----------+---------------+------------------------------------------------------+
| email         | String    | Yes           | User email address.                                  |
+---------------+-----------+---------------+------------------------------------------------------+
| latitude      | Double    | Yes           | PointOfInterest latitude coordinate.                 |
+---------------+-----------+---------------+------------------------------------------------------+
| longitude     | Double    | Yes           | PointOfInterest longitude coordinate.                |
+---------------+-----------+---------------+------------------------------------------------------+

Response Body
------------

+---------------+-----------+----------------------------------------------------------------------+
| Parameter     | Type      | Description                                                          |
+===============+===========+======================================================================+
| message       | String    | A message confirming that the PointOfInterest was created.           |
+---------------+-----------+----------------------------------------------------------------------+

Response Codes
------------

+---------------------------+----------------------------------------------------------------------+
| HTTP Code                 | Meaning                                                              |
+===========================+======================================================================+
| 201 Created               | PointOfInterest creation succeed.                                    |
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

    curl --location --request POST 'https://pro-hikup.westeurope.cloudapp.azure.com/api/user/poi/create'    \
    --header 'Authorization: Bearer xxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxx'                                  \
    --data-raw '{
        "user": {
            "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
            "roles": ["XXXX"]
        },
        "trail": {
            "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx"
        },
        "poi": {
            "name": "xxxxxxxxxxxxxxxxx",
            "description": "xxxxxxxxxx",
            "pictures": ["https://xxxxxxx.xxx"],
            "sharedWith": [
                {
                    "email": "xxxx@xxxx.xxx"
                },
                {
                    "email": "xxxx@xxxx.xxx"
                }
            ],
            "latitude": 0.000000000000,
            "longitude": 0.0000000000000
        }
    }'

Example Response
------------

.. code-block:: console

    {
        "message": "Created"
    }
