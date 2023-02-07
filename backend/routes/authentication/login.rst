.. _login:

Login
============

Authenticate an user.

Authentication
------------

Requires an email address & a password.

URL
------------

:code:`POST https://pro-hikup.westeurope.cloudapp.azure.com/api/auth/login`

Request Body
------------

+---------------+-----------+---------------+------------------------------------------------------+
| Parameter     | Type      | Required?     | Description                                          |
+===============+===========+===============+======================================================+
| user          | Object    | Yes           | Object containing user data.                         |
+---------------+-----------+---------------+------------------------------------------------------+
| email         | String    | Yes           | User email address.                                  |
+---------------+-----------+---------------+------------------------------------------------------+
| password      | String    | Yes           | User password (must be a hash).                      |
+---------------+-----------+---------------+------------------------------------------------------+

Response Body
------------

+---------------+-----------+----------------------------------------------------------------------+
| Parameter     | Type      | Description                                                          |
+===============+===========+======================================================================+
| user          | Object    | Object containing user data.                                         |
+---------------+-----------+----------------------------------------------------------------------+
| id            | String    | The ID that uniquely identifies this user.                           |
+---------------+-----------+----------------------------------------------------------------------+
| roles         | String[]  | Roles assigned to the user.                                          |
+---------------+-----------+----------------------------------------------------------------------+
| token         | String    | The access token needed to authenticate your requests.               |
+---------------+-----------+----------------------------------------------------------------------+

Response Codes
------------

+---------------------------+----------------------------------------------------------------------+
| HTTP Code                 | Meaning                                                              |
+===========================+======================================================================+
| 200 OK                    | User login succeed.                                                  |
+---------------------------+----------------------------------------------------------------------+
| 401 Unauthorized\         | The Authorization header must specify a user access token.\          |
|                 \         | The OAuth token is not valid.\                                       |
|                 \         | Email address is incorrect.\                                         |
|                 \         | Password is incorrect.\                                              |
+---------------------------+----------------------------------------------------------------------+
| 500 Internal Server Error |                                                                      |
+---------------------------+----------------------------------------------------------------------+

Example Request
------------

.. code-block:: console

    curl --location --request POST 'https://pro-hikup.westeurope.cloudapp.azure.com/api/auth/login' \
    --header 'Content-Type: application/json'                                                       \
    --data-raw '{
        "user": {
            "email": "xxxx@xxxx.xxx",
            "password": "xxxxxxxxxx"
        }
    }'

Example Response
------------

.. code-block:: console

    {
        "userId": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
        "token": "xxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxx"
    }
