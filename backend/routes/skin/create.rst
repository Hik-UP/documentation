.. _create:

Create
============

Create a new Skin.

Authentication
------------

Requires an access token.
User need to be a member of the ADMIN group.

URL
------------

:code:`POST https://pro-hikup.westeurope.cloudapp.azure.com/api/skin/create`

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
| skin          | Object    | Yes           | Object containing Skin data.                         |
+---------------+-----------+---------------+------------------------------------------------------+
| name          | String    | Yes           | Skin name.                                           |
+---------------+-----------+---------------+------------------------------------------------------+
| description   | String    | Yes           | Skin description.                                    |
+---------------+-----------+---------------+------------------------------------------------------+
| pictures      | String[]  | Yes           | Array of strings containing Skin pictures (URL).     |
+---------------+-----------+---------------+------------------------------------------------------+
| model         | String    | Yes           | String containing Skin model (URL).                  |
+---------------+-----------+---------------+------------------------------------------------------+

Response Body
------------

+---------------+-----------+----------------------------------------------------------------------+
| Parameter     | Type      | Description                                                          |
+===============+===========+======================================================================+
| message       | String    | A message confirming that the Skin was created.                      |
+---------------+-----------+----------------------------------------------------------------------+

Response Codes
------------

+---------------------------+----------------------------------------------------------------------+
| HTTP Code                 | Meaning                                                              |
+===========================+======================================================================+
| 201 Created               | Skin creation succeed.                                               |
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

    curl --location --request POST 'https://pro-hikup.westeurope.cloudapp.azure.com/api/skin/create'    \
    --header 'Authorization: Bearer xxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxx'                              \
    --data-raw '{
        "user": {
            "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
            "roles": ["XXXX"]
        },
        "skin": {
            "name": "xxxxxxxxxxx",
            "description": "xxxx",
            "pictures": ["https://xxxxxx.xxx"],
            "model": "xxxxxxxxxx"
        }
    }'

Example Response
------------

.. code-block:: console

    {
        "message": "Created"
    }
