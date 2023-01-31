Register
++++++++

Pengguna dapat melakukan register pengguna. Endpoint berikut digunakan untuk mengelola akun yang dimiliki

Add
===

.. http:post:: /auth/register/

    Untuk menambahkan pengguna baru dengan fitur register

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