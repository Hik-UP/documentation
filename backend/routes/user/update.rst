.. _update:

Details
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
| picture       | String    | Yes           | Url image picture of user                            |
+---------------+-----------+---------------+------------------------------------------------------+

Response Body
------------

+-------------------+-----------+----------------------------------------------------------------------+
| Parameter         | Type      | Description                                                          |
+===================+===========+======================================================================+
| message           | String    | A message that represent the state of the request                    |
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

    curl --location --request POST 'https://pro-hikup.westeurope.cloudapp.azure.com/api/user/profile/update' \
    --header 'Authorization: Bearer xxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxx'                              \
    --data-raw '{
        "user": {
            "id": "xxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxx",
            "roles": ["USER"],
            "picture": "https://static.wikia.nocookie.net/denaruto3/images/f/f0/BorutoInMovie.png/revision/latest?cb=20150513165125&path-prefix=de"
        }
        
    }'

Example Response
------------

.. code-block:: console

    {
        "message": "Updated"
    }