.. _retrieve:

Retrieve
============

Retrieve all Notification.

Authentication
------------

Requires an access token.

URL
------------

:code:`POST https://pro-hikup.westeurope.cloudapp.azure.com/api/user/notification/retrieve`

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
| notifications | Object[]  | Array of objects containing Notification data.                       |
+---------------+-----------+----------------------------------------------------------------------+
| id            | String    | Notification unique identifier.                                      |
+---------------+-----------+----------------------------------------------------------------------+
| title         | String    | Notification title.                                                  |
+---------------+-----------+----------------------------------------------------------------------+
| body          | String    | Notification body.                                                   |
+---------------+-----------+----------------------------------------------------------------------+
| read          | Boolean   | True if the user has read the Notification.                          |
+---------------+-----------+----------------------------------------------------------------------+
| date          | DateTime  | Notification creation date (Epoch Unix Timestamp).                   |
+---------------+-----------+----------------------------------------------------------------------+

Response Codes
------------

+---------------------------+----------------------------------------------------------------------+
| HTTP Code                 | Meaning                                                              |
+===========================+======================================================================+
| 200 OK                    | Notification was successfully retrieved.                             |
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

    curl --location --request POST 'https://pro-hikup.westeurope.cloudapp.azure.com/api/user/notification/retrieve' \
    --header 'Authorization: Bearer xxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxx'                                          \
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
        "notifications": [
            {
                "id": "xxxxxxxxxxxxxxxxxxxxxxxxxxxxx",
                "title": "xxxxxxxxxxxxx",
                "body": "xxxxxxxxxxxxxxxxxxxxxxxxxxx",
                "read": false,
                "date": "2020-01-20T09:35:52.359Z"
            },
            {
                "id": "xxxxxxxxxxxxxxxxxxxxxxxxxxxxx",
                "title": "xxxxxxxxxxxxx",
                "body": "xxxxxxxxxxxxxxxxxxxxxxxxxxx",
                "read": true,
                "date": "2020-01-20T09:35:52.359Z"
            }
        ]
    }
