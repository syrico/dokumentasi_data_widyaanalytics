Account
+++++++

Pengguna dapat melakukan pengaturan akun terhadap akun pengguna yang dimiliki. Endpoint berikut digunakan untuk mengelola akun yang dimiliki

.. _account-user:

GET
===

.. http:get:: /account

    Untuk mendapatkan data akun 
    
    Note:
    Default accepted fields: username, first_name, last_name 
    Default display fields: pk, username, email, first_name, last_name
    Read-only fields: pk, email
    Returns UserModel fields.

    **Contoh Response**:

    .. sourcecode:: json

        [
            {
                "id": 0,
                "email": "user@example.com",
                "first_name": "string",
                "last_name": "string",
                "is_staff": true,
                "is_superuser": true,
                "is_verified": "string",
                "profile": {
                    "phone": "74874011579",
                    "photo": "string",
                    "photo_url": "string",
                    "category": {
                        "id": 0,
                        "name": "string"
                    },
                    "category_id": 0
                },
                "subscriptions": [
                    {
                        "id": "3fa85f64-5717-4562-b3fc-2c963f66afa6",
                        "user": 0,
                        "status": "string",
                        "plan": 0,
                        "group": 0,
                        "period_start": "2022-12-23T05:07:49.637Z",
                        "period_end": "2022-12-23T05:07:49.637Z"
                    }
                ]
            }
        ]

UPDATE
======
.. http:put:: /account

    Mengupdate data akun.

    Note:
    Default accepted fields: username, first_name, last_name
    Default display fields: pk, username, email, first_name, last_name
    Read-only fields: pk, email

        **Parameter**:

    .. sourcecode:: json

        {
            "first_name": "string",
            "last_name": "string",
            "profile": {
                    "phone": "316373486",
                    "category": {
                    "name": "string"
                },
                "category_id": 0
            }
        }


   **Contoh Response**:

    .. sourcecode:: json

        {
            "id": 0,
            "email": "user@example.com",
            "first_name": "string",
            "last_name": "string",
            "is_staff": true,
            "is_superuser": true,
            "is_verified": "string",
            "profile": {
                "phone": "1512062301716",
                "photo": "string",
                "photo_url": "string",
                "category": {
                    "id": 0,
                    "name": "string"
                },
                "category_id": 0
            },
            "subscriptions": [
                {
                    "id": "3fa85f64-5717-4562-b3fc-2c963f66afa6",
                    "user": 0,
                    "status": "string",
                    "plan": 0,
                    "group": 0,
                    "period_start": "2022-12-23T05:21:19.868Z",
                    "period_end": "2022-12-23T05:21:19.869Z"
                }
            ]
        }


Patch
=====

.. http:patch:: /account

    Mengupdate data akun pengguna

    **Parameter**:
    
    .. sourcecode:: json

        {
            "first_name": "string",
            "last_name": "string",
            "profile": {
                "phone": "124697711486559",
                "category": {
                    "name": "string"
                },
                "category_id": 0
            }
        }

    **Contoh Response**:

    .. sourcecode:: json

        {
            "id": 0,
            "email": "user@example.com",
            "first_name": "string",
            "last_name": "string",
            "is_staff": true,
            "is_superuser": true,
            "is_verified": "string",
            "profile": {
                "phone": "+150348788356826",
                "photo": "string",
                "photo_url": "string",
                "category": {
                    "id": 0,
                    "name": "string"
                },
                "category_id": 0
            },
            "subscriptions": [
                {
                    "id": "3fa85f64-5717-4562-b3fc-2c963f66afa6",
                    "user": 0,
                    "status": "string",
                    "plan": 0,
                    "group": 0,
                    "period_start": "2022-12-23T05:21:19.876Z",
                    "period_end": "2022-12-23T05:21:19.876Z"
                }
            ]
        }