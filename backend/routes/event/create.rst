.. _create:

Create
============

Create a new event.

Authentication
------------

Requires an access token.

URL
------------

:code:`POST https://pro-hikup.westeurope.cloudapp.azure.com/api/event/create`

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
| event         | Object    | Yes           | Object containing Event data.                        |
+---------------+-----------+---------------+------------------------------------------------------+
| title         | String    | Yes           | Event title.                                         |
+---------------+-----------+---------------+------------------------------------------------------+
| description   | String    | Yes           | Event description.                                   |
+---------------+-----------+---------------+------------------------------------------------------+
| coverUrl      | String    | Yes           | Cover pictures of the event                          |
+---------------+-----------+---------------+------------------------------------------------------+
| localisation  | String    | Yes           | localisation of the event (URL).                     |
+---------------+-----------+---------------+------------------------------------------------------+
| Tags          | String[]  | Yes           | Theme relative to the event                          |
+---------------+-----------+---------------+------------------------------------------------------+
|visibilityEvent| String    | No            | Type of visibility of the event                      |
+---------------+-----------+---------------+------------------------------------------------------+

Response Body
------------

+---------------+-----------+----------------------------------------------------------------------+
| Parameter     | Type      | Description                                                          |
+===============+===========+======================================================================+
| message       | String    | A message confirming that the Event was created.                     |
+---------------+-----------+----------------------------------------------------------------------+

Response Codes
------------

+---------------------------+----------------------------------------------------------------------+
| HTTP Code                 | Meaning                                                              |
+===========================+======================================================================+
| 201 Created               | Event creation succeed.                                              |
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

    curl --location --request POST 'https://pro-hikup.westeurope.cloudapp.azure.com/api/event/create'    \
    --header 'Authorization: Bearer xxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxx'                              \
    --data-raw '{
    "user": {
        "id": "4bf9e008-6511-4164-a8fd-df90325d3ec2",
        "roles": [
            "USER"
        ]
    },
    "event": {
        "title": "Protection du paysage",
        "description": "Séance de nettoyage",
        "coverUrl": "https://i.weltbild.de/p/boruto-naruto-the-next-generation-bd-9-325933125.jpg?v=1&wp=_max",
        "localisation": "Paris, France",
        "tags": ["nature", "rue-propre"],
        "visibilityEvent": "PRIVATE"
    }
}'

Example Response
------------

.. code-block:: console

    {
        "message": "Created"
    }
