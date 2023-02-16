.. _details:

Details
============

Get detail of Trail.

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
| weight        | Double    | Yes           | Weight of the user  (kg)                             |
+---------------+-----------+---------------+------------------------------------------------------+
| tall          | Int       | Yes           | Tall of the user (cm)                                |
+---------------+-----------+---------------+------------------------------------------------------+
| sex           | String    | Yes           | Sex of the user (Only pass M|F)                      |
+---------------+-----------+---------------+------------------------------------------------------+
| age           | Int       | Yes           | Age of the user                                      |
+---------------+-----------+---------------+------------------------------------------------------+
| trail         | Object    | Yes           | Object containing trail data                         |
+---------------+-----------+---------------+------------------------------------------------------+
| id            | String    | Yes           | Trail unique identifier                              |
+---------------+-----------+---------------+------------------------------------------------------+
| latitude      | Double    | Yes           | Latitude of the trail                                |
+---------------+-----------+---------------+------------------------------------------------------+
| longitude     | Double    | Yes           | Longitude of the trail                               |
+---------------+-----------+---------------+------------------------------------------------------+
| duration      | Int       | Yes           | Duration of the trail                                |
+---------------+-----------+---------------+------------------------------------------------------+


Response Body
------------

+-------------------+-----------+----------------------------------------------------------------------+
| Parameter         | Type      | Description                                                          |
+===================+===========+======================================================================+
| weather           | Int       | Current temperature in the hiking area                               |
+-------------------+-----------+----------------------------------------------------------------------+
| tools             | String[]  | Tools to have for the hiking                                         |
+-------------------+-----------+----------------------------------------------------------------------+
| calories          | Int       | Approximative number of calories to burn on the hiking               |
+-------------------+-----------+----------------------------------------------------------------------+

Response Codes
------------

+---------------------------+----------------------------------------------------------------------+
| HTTP Code                 | Meaning                                                              |
+===========================+======================================================================+
| 200 OK                    | Trail was successfully retrieved.                                    |
+---------------------------+----------------------------------------------------------------------+
| 400 Bad Request           |                                                                      |
+---------------------------|----------------------------------------------------------------------|
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

    curl --location --request POST 'https://pro-hikup.westeurope.cloudapp.azure.com/api/trail/details' \
    --header 'Authorization: Bearer xxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxx'                              \
    --data-raw '{
        "user": {
            "id": "xxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxx",
            "roles": [
                "USER"
            ],
            "weight": 90,
            "tall": 68,
            "sex": "F",
            "age": 20
        },
        "trail": {
            "id": "xxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxx",
            "latitude": 50.303814,
            "longitude": 11.942139,
            "duration": 4
        }
    }'

Example Response
------------

.. code-block:: console

    {
        "weather": {
            "temp": 4,
            "url_icon": "http://openweathermap.org/img/wn/01n@2x.png"
        },
        "tools": [],
        "recommendArticleUrls": [],
        "calories": 21280
    }
