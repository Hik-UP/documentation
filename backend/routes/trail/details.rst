.. _details:

Details
============

Get Trail details.

Authentication
------------

Requires an access token.

URL
------------

:code:`POST https://pro-hikup.westeurope.cloudapp.azure.com/api/trail/details`

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
| weight        | Double    | Yes           | Weight of the user  (KG).                            |
+---------------+-----------+---------------+------------------------------------------------------+
| tall          | Int       | Yes           | Tall of the user (CM).                               |
+---------------+-----------+---------------+------------------------------------------------------+
| sex           | String    | Yes           | Sex of the user (M|F).                               |
+---------------+-----------+---------------+------------------------------------------------------+
| age           | Int       | Yes           | Age of the user.                                     |
+---------------+-----------+---------------+------------------------------------------------------+
| trail         | Object    | Yes           | Object containing trail data.                        |
+---------------+-----------+---------------+------------------------------------------------------+
| id            | String    | Yes           | Trail unique identifier.                             |
+---------------+-----------+---------------+------------------------------------------------------+

Response Body
------------

+-------------------+-----------+----------------------------------------------------------------------+
| Parameter         | Type      | Description                                                          |
+===================+===========+======================================================================+
| weather           | Object    | Object containing weather data.                                      |
+-------------------+-----------+----------------------------------------------------------------------+
| temperature       | Int       | Temperature at the location of the Trail (°C).                       |
+-------------------+-----------+----------------------------------------------------------------------+
| icon              | String    | Icon related to the weather at the location of the Trail (URL).      |
+-------------------+-----------+----------------------------------------------------------------------+
| weather           | Object    | Object containing weather data.                                      |
+-------------------+-----------+----------------------------------------------------------------------+
| tools             | String[]  | Tools needed for the Trail.                                          |
+-------------------+-----------+----------------------------------------------------------------------+
| relatedArticles   | String[]  | Articles related to the Trail (URL).                                 |
+-------------------+-----------+----------------------------------------------------------------------+
| calories          | Int       | Approximative number of calories to burn on the Trail.               |
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

    curl --location --request POST 'https://pro-hikup.westeurope.cloudapp.azure.com/api/trail/details'  \
    --header 'Authorization: Bearer xxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxx'                              \
    --data-raw '{
        "user": {
            "id": "xxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxx",
            "roles": [
                "XXXXX"
            ],
            "weight": 90,
            "tall": 68,
            "sex": "F",
            "age": 20
        },
        "trail": {
            "id": "xxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxx"
        }
    }'

Example Response
------------

.. code-block:: console

    {
        "weather": {
            "temperature": 4,
            "icon": "http://xxxxxx.xxxxxx"
        },
        "tools": [],
        "relatedArticles": [],
        "calories": 21280
    }
