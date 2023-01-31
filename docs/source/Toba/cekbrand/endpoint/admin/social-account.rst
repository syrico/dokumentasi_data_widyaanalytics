Social Account
++++++++++++++

Berikut adalah beberapa endpoint yang digunakan pada halaman **Daftar Pengguna** yang hanya dapat digunakan oleh `admin`.

.. _facebook-list:

Facebook List
=============

.. http:get:: /user-management/(int:user_id)/socialaccount/facebook

    Mengambil semua daftar data akun Facebook pengguna.

    .. list-table:: 
      :widths: 15 80
      :header-rows: 1

      * - Parameter
        - Deskripsi
      * - user_id
        - ID pengguna

    **Contoh Response**:

    .. sourcecode:: http

        HTTP/1.1 200 OK
        Content-Type: application/json

        [
            {
                "id": 0,
                "provider": "facebook",
                "uid": "string",
                "last_login": "2022-12-19T17:49:51.867Z",
                "date_joined": "2022-12-19T17:49:51.867Z",
                "extra_data": "string",
                "socialtoken": [
                    {
                    "app": "string",
                    "token": "string",
                    "token_secret": "string",
                    "expires_at": "2022-12-19T17:49:51.867Z"
                    }
                ],
                "instagram_accounts": [
                    "string"
                ]
            }
        ]

.. _instagram-list:

Instagram List
==============

.. http:get:: /user-management/(int:user_id)/socialaccount/instagram

    Mengambil semua daftar data akun Instagram pengguna.

    .. list-table:: 
      :widths: 15 80
      :header-rows: 1

      * - Parameter
        - Deskripsi
      * - user_id
        - ID pengguna

    **Contoh Response**:

    .. sourcecode:: http

        HTTP/1.1 200 OK
        Content-Type: application/json

        [
            {
                "biography": "string",
                "id": "string",
                "name": "string",
                "profile_picture_url": "string",
                "username": "string",
                "social_account": {
                    "id": 0,
                    "uid": "string",
                    "name": "string",
                    "email": "string"
                },
                "updated_timestamp": "2022-12-19T18:20:50.522Z",
                "latest_user_data": {
                    "followers_count": 0,
                    "follows_count": 0,
                    "media_count": 0,
                    "followers_count_growth": 0,
                    "media_count_growth": 0,
                    "updated_timestamp": "2022-12-26T20:25:53+07:00",
                    "datestamp": "2022-12-26"
                }
            }
        ]