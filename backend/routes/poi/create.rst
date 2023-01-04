.. _login:

Create
============

Create a new PointOfInterest.

Authentication
------------

Requires an access token.

URL
------------

:code:`POST https://pro-hikup.westeurope.cloudapp.azure.com/api/poi/create`

Request Body
------------

+---------------+-----------+---------------+---------------------------------------------------------------+
| Parameter     | Type      | Required?     | Description                                                   |
+===============+===========+===============+===============================================================+
| user          | Object    | Yes           | Object containing user data.                                  |
+---------------+-----------+---------------+---------------------------------------------------------------+
| id            | String    | Yes           | User unique identifier.                                       |
+---------------+-----------+---------------+---------------------------------------------------------------+
| poi           | Object    | Yes           | Object containing PointOfInterest data.                       |
+---------------+-----------+---------------+---------------------------------------------------------------+
| latitude      | Double    | Yes           | PointOfInterest latitude coordinate.                          |
+---------------+-----------+---------------+---------------------------------------------------------------+
| longitude     | Double    | Yes           | PointOfInterest longitude coordinate.                         |
+---------------+-----------+---------------+---------------------------------------------------------------+

Response Body
------------

+---------------+-----------+---------------------------------------------------------------+
| Parameter     | Type      | Description                                                   |
+===============+===========+===============================================================+
| message       | String    | A message confirming that the PointOfInterest was created.    |
+---------------+-----------+---------------------------------------------------------------+

Response Codes
------------

+---------------------------+-----------------------------------------------------------------------------------------------+
| HTTP Code                 | Meaning                                                                                       |
+===========================+===============================================================================================+
| 201 Created               | PointOfInterest creation succeed.                                                             |
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

    curl --location --request POST 'https://pro-hikup.westeurope.cloudapp.azure.com/api/poi/create' \
    --header 'Authorization: Bearer xxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxx'                          \
    --data-raw '{
        "user": {
            "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx"
        },
        "poi": {
            "latitude": 00.000000000000,
            "longitude": 0.0000000000000
        }
    }'

Example Response
------------

.. code-block:: console

    {
        "message": "Created"
    }
