.. _unlocked:

Unlocked
============

Retrieve all unlocked Skin created.

Authentication
------------

Requires an access token.

URL
------------

:code:`POST https://pro-hikup.westeurope.cloudapp.azure.com/api/user/skin/unlocked`

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

+---------------+-----------+----------------------------------------------------------------------+
| Parameter     | Type      | Description                                                          |
+===============+===========+======================================================================+
| skins         | Object[]  | Array of objects containing unlocked Skin data.                      |
+---------------+-----------+----------------------------------------------------------------------+
| id            | String    | Unlocked Skin unique identifier.                                     |
+---------------+-----------+----------------------------------------------------------------------+
| name          | String    | Unlocked Skin name.                                                  |
+---------------+-----------+----------------------------------------------------------------------+
| description   | String    | Unlocked Skin description.                                           |
+---------------+-----------+----------------------------------------------------------------------+
| pictures      | String[]  | Array of strings containing unlocked Skin pictures (URL).            |
+---------------+-----------+----------------------------------------------------------------------+
| model         | Double    | String containing unlocked Skin model (URL).                         |
+---------------+-----------+----------------------------------------------------------------------+

Response Codes
------------

+---------------------------+----------------------------------------------------------------------+
| HTTP Code                 | Meaning                                                              |
+===========================+======================================================================+
| 200 OK                    | Unlocked Skin was successfully retrieved.                            |
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

    curl --location --request POST 'https://pro-hikup.westeurope.cloudapp.azure.com/api/user/skin/unlocked' \
    --header 'Authorization: Bearer xxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxx'                                  \
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
        "skins": [
            {
                "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
                "name": "xxxxxxxxxxx",
                "description": "xxxx",
                "pictures": [
                    "xxxxxxxxxxxxxxx"
                ],
                "model": "xxxxxxxxxx"
            },
            {
                "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
                "name": "xxxxxxxxxxx",
                "description": "xxxx",
                "pictures": [
                    "xxxxxxxxxxxxxxx"
                ],
                "model": "xxxxxxxxxx"
            }
        ]
    }
