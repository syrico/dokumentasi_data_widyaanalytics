Register
++++++++

Pengguna dapat melakukan register pengguna. Endpoint berikut digunakan untuk mengelola akun yang dimiliki

POST
=====

.. http:post:: /auth/register/

    Untuk menambahkan pengguna baru dengan fitur register

    **Parameter**:

    .. sourcecode:: json

        {
            "first_name": "string",
            "last_name": "string",
            "email": "user@example.com",
            "password1": "string",
            "password2": "string",
            "phone": "+2356288276",
            "category": 0,
            "coupon_code": "string"
        }


    **Contoh Response**:

    .. sourcecode:: json

        {
            "first_name": "string",
            "last_name": "string",
            "email": "user@example.com",
            "password1": "string",
            "password2": "string",
            "phone": "+13874686276808",
            "category": 0,
            "coupon_code": "string"
        }