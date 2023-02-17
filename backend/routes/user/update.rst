.. _update:

Update
============

Update user profile.

Authentication
------------

Requires an access token.

URL
------------

:code:`PUT https://pro-hikup.westeurope.cloudapp.azure.com/api/user/profile/update`

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
| username      | String    | No            | Username.                                            |
+---------------+-----------+---------------+------------------------------------------------------+
| email         | String    | No            | User email address.                                  |
+---------------+-----------+---------------+------------------------------------------------------+
| picture       | String    | No            | User profile picture (URL).                          |
+---------------+-----------+---------------+------------------------------------------------------+

Response Body
------------

+-------------------+-----------+----------------------------------------------------------------------+
| Parameter         | Type      | Description                                                          |
+===================+===========+======================================================================+
| message           | String    | A message confirming that the user was updated.                      |
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

    curl --location --request POST 'https://pro-hikup.westeurope.cloudapp.azure.com/api/user/profile/update'    \
    --header 'Authorization: Bearer xxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxx'                                      \
    --data-raw '{
        "user": {
            "id": "xxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxx",
            "roles": ["XXXXXX"],
            "picture": "https://xxxxxxxxxx.xxx"
        }
        
    }'

.. code-block:: console

    curl --location --request POST 'https://pro-hikup.westeurope.cloudapp.azure.com/api/user/profile/update'    \
    --header 'Authorization: Bearer xxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxx'                                      \
    --data-raw '{
        "user": {
            "id": "xxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxx",
            "roles": ["XXXXXX"],
            "username": "xxxxxxxxxx",
            "email": "xxxxx@xxxxx.xxx"
        }
        
    }'

.. code-block:: console

    curl --location --request POST 'https://pro-hikup.westeurope.cloudapp.azure.com/api/user/profile/update'    \
    --header 'Authorization: Bearer xxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxx'                                      \
    --data-raw '{
        "user": {
            "id": "xxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxx",
            "roles": ["XXXXXX"],
            "username": "xxxxxxxxxx"
        }
        
    }'

Example Response
------------

.. code-block:: console

    {
        "message": "Updated"
    }
