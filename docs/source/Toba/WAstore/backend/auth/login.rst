Login
+++++

Pengguna dapat melakukan login pengguna. Endpoint berikut digunakan untuk mengelola akun yang dimiliki

POST
====

.. http:get:: /auth/login/

    Check the credentials and return the REST Token
    if the credentials are valid and authenticated.
    Calls Django Auth login method to register User ID
    in Django session framework

    Accept the following POST parameters: username, password
    Return the REST Framework Token Object's key.

    **Parameter**:

    .. sourcecode:: json

        {
            "email": "user@example.com",
            "password": "string"
        }


    **Contoh Response**:

    .. sourcecode:: json

        {
            "email": "user@example.com",
            "password": "string"
        }

Facebook Login
==============

.. http:put:: /auth/facebook/login/

    Login facebook account.

    **Parameter**:

    .. sourcecode:: json

        {
            "access_token": "string",
            "code": "string"
        }


    **Contoh Response**:

    .. sourcecode:: json

        {
            "access_token": "string",
            "code": "string"
        }