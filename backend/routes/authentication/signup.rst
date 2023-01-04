.. _signup:

Signup
============

Create an user.

Authentication
------------

None

URL
------------

:code:`POST https://pro-hikup.westeurope.cloudapp.azure.com/api/auth/signup`

Request Body
------------

+---------------+-----------+---------------+---------------------------------------------------------------+
| Parameter     | Type      | Required?     | Description                                                   |
+===============+===========+===============+===============================================================+
| user          | Object    | Yes           | Object containing user data.                                  |
+---------------+-----------+---------------+---------------------------------------------------------------+
| email         | String    | Yes           | User email address.                                           |
+---------------+-----------+---------------+---------------------------------------------------------------+
| password      | String    | Yes           | User password (must be a hash).                               |
+---------------+-----------+---------------+---------------------------------------------------------------+

Response Body
------------

+---------------+-----------+---------------------------------------------------------------+
| Parameter     | Type      | Description                                                   |
+===============+===========+===============================================================+
| message       | String    | A message confirming that the user was created.               |
+---------------+-----------+---------------------------------------------------------------+

Response Codes
------------

+---------------------------+---------------------------------------------------------------+
| HTTP Code                 | Meaning                                                       |
+===========================+===============================================================+
| 200 OK                    | User creation succeed.                                        |
+---------------------------+---------------------------------------------------------------+
| 500 Internal Server Error | An user with this email address already exist in our database.|
+---------------------------+---------------------------------------------------------------+

Example Request
------------

.. code-block:: console

    curl --location --request POST 'https://pro-hikup.westeurope.cloudapp.azure.com/api/auth/signup'    \
    --header 'Content-Type: application/json'                                                           \
    --data-raw '{
        "user": {
            "email": "xxxx@xxxx.xxx",
            "password": "XXXXXXXXXX"
        }
    }'

Example Response
------------

.. code-block:: console

    {
        "message": "Created"
    }
