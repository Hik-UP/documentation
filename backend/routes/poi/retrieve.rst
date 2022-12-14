.. _login:

Retrieve
============

Retrieve all PointOfInterest created by user.

Authentication
------------

Requires an access token.

URL
------------

:code:`POST https://pro-hikup.westeurope.cloudapp.azure.com/api/poi/retrieve`

Request Body
------------

+---------------+-----------+---------------+---------------------------------------------------------------+
| Parameter     | Type      | Required?     | Description                                                   |
+===============+===========+===============+===============================================================+
| user          | Object    | Yes           | Object containing user data.                                  |
+---------------+-----------+---------------+---------------------------------------------------------------+
| id            | String    | Yes           | User unique identifier.                                       |
+---------------+-----------+---------------+---------------------------------------------------------------+

Response Body
------------

+---------------+-----------+---------------------------------------------------------------+
| Parameter     | Type      | Description                                                   |
+===============+===========+===============================================================+
| poi           | Object[]  | Array of objects containing PointOfInterest data.             |
+---------------+-----------+---------------------------------------------------------------+
| latitude      | Double    | PointOfInterest latitude coordinate.                          |
+---------------+-----------+---------------------------------------------------------------+
| longitude     | Double    | PointOfInterest longitude coordinate.                         |
+---------------+-----------+---------------------------------------------------------------+

Response Codes
------------

+---------------------------+-----------------------------------------------------------------------------------------------+
| HTTP Code                 | Meaning                                                                                       |
+===========================+===============================================================================================+
| 200 OK                    | PointOfInterest was successfully retrieved.                                                   |
+---------------------------+-----------------------------------------------------------------------------------------------+
| 401 Unauthorized          | The Authorization header must specify a user access token.                                    |
|                           | The OAuth token is not valid.                                                                 |
|                           | The ID specified in the userId data does not match the userId specified in the access token.  |
+---------------------------+-----------------------------------------------------------------------------------------------+
| 500 Internal Server Error |                                                                                               |
+---------------------------+-----------------------------------------------------------------------------------------------+

Example Request
------------

.. code-block:: console

    curl --location --request POST 'https://pro-hikup.westeurope.cloudapp.azure.com/api/poi/retrieve'   \
    --header 'Authorization: Bearer xxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxx'                              \
    --data-raw '{
        "user": {
            "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx"
        }
    }'

Example Response
------------

.. code-block:: console

    {
        "poi": [{
            "latitude": 00.000000000000,
            "longitude": 0.0000000000000
        },
        {
            "latitude": 00.000000000000,
            "longitude": 0.0000000000000
        },
        {
            "latitude": 00.000000000000,
            "longitude": 0.0000000000000
        }]
    }
