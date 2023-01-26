Social Account
++++++++++++++

Pengguna dapat menambahkan koneksi terhadap akun media sosial terkait, misalkan Facebook, Instagram, Twitter, dsb.
Endpoint berikut digunakan untuk mengelola akun-akun tersebut.

List
====

.. http:get:: /user/socialaccount

    Mengembalikan semua daftar data akun media sosial pengguna.

    **Contoh Response**:

    .. sourcecode:: json

        [
            {
                "id": 0,
                "provider": "facebook",
                "uid": "string",
                "last_login": "2022-12-19T19:33:23.323Z",
                "date_joined": "2022-12-19T19:33:23.323Z",
                "extra_data": "string",
                "socialtoken": [
                    {
                        "app": "string",
                        "token": "string",
                        "token_secret": "string",
                        "expires_at": "2022-12-19T19:33:23.323Z"
                    }
                ],
                    "instagram_accounts": [
                    "string"
                ]
            }
        ]

    :query string provider: adalah vendor media sosial, contoh nya; `facebook`, `twitter`, dsb.

Detail
======

.. http:get:: /user/socialaccount/(int:id)

    Mengembalikan detail data akun media sosial pengguna.

    .. list-table:: 
      :widths: 15 80
      :header-rows: 1

      * - Parameter
        - Deskripsi
      * - id
        - ID social account


    **Contoh Response**:

    .. sourcecode:: json

        {
            "id": 0,
            "provider": "facebook",
            "uid": "string",
            "last_login": "2022-12-19T19:39:59.473Z",
            "date_joined": "2022-12-19T19:39:59.473Z",
            "extra_data": "string",
            "socialtoken": [
                {
                    "app": "string",
                    "token": "string",
                    "token_secret": "string",
                    "expires_at": "2022-12-19T19:39:59.473Z"
                }
            ],
            "instagram_accounts": [
                "string"
            ]
        }


Update
======

.. http:put:: /user/socialaccount/(int:id)

    Mengubah detail data akun media sosial pengguna.

    .. list-table:: 
      :widths: 15 80
      :header-rows: 1

      * - Parameter
        - Deskripsi
      * - id
        - ID social account

    **Contoh Request**:abbr:

    .. sourcecode:: json

        {
            "provider": "facebook",
            "uid": "string",
            "extra_data": "string"
        }

    **Contoh Response**:

    .. sourcecode:: json

        {
            "id": 0,
            "provider": "facebook",
            "uid": "string",
            "last_login": "2022-12-19T19:39:59.476Z",
            "date_joined": "2022-12-19T19:39:59.476Z",
            "extra_data": "string",
            "socialtoken": [
                {
                    "app": "string",
                    "token": "string",
                    "token_secret": "string",
                    "expires_at": "2022-12-19T19:39:59.477Z"
                }
            ],
            "instagram_accounts": [
                "string"
            ]
        }

Delete
======

.. http:delete:: /user/socialaccount/(int:id)

    Menghapus data akun media sosial pengguna.

    .. list-table:: 
      :widths: 15 80
      :header-rows: 1

      * - Parameter
        - Deskripsi
      * - id
        - ID social account

