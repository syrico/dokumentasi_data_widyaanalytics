Login
+++++

Pengguna dapat melakukan login pengguna. Endpoint berikut digunakan untuk mengelola akun yang dimiliki

Add
===

.. http:post:: /auth/login/

    Menambahkan login pengguna

    .. note::
        - Check the credentials and return the REST Token
        - if the credentials are valid and authenticated.
        - Calls Django Auth login method to register User ID in Django session framework

        - Accept the following POST parameters: username, password
        - Return the REST Framework Token Object's key.

    
    **Contoh Response**:

    .. sourcecode:: json

        {
            "email": "user@example.com",
            "password": "string"
        }
    

Facebook Login
==============

.. http:post:: /auth/facebook/login/

    Menambahkan login facebook account.

    **Contoh Response**:

    .. sourcecode:: json

        {
            "access_token": "string",
            "code": "string"
        }