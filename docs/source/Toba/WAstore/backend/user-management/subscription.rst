Subscription
++++++++++++

Untuk memperoleh data *subscription* berdasarkan *management user*. Endpoint yang digunakan sebagai berikut.

List
====

.. http:get:: /user-management/subscriptions/

    Mengembalikan data *Subscription* dari *user management*.

    .. list-table:: 
      :widths: 15 80
      :header-rows: 1

      * - Parameter
        - Deskripsi
      * - search
        - Istilah pencarian
      * - ordering
        - Nilai yang memesan hasil.
      * - page
        - Nomor halaman dalam kumpulan hasil paginasi.
      * - page_size
        - Jumlah hasil halaman yang dikembalikan per halaman.

    **Contoh Response**:

    .. sourcecode:: json

        {
            "count": 0,
            "next": "string",
            "previous": "string",
            "results": [
                {
                    "id": "3fa85f64-5717-4562-b3fc-2c963f66afa6",
                    "email": "user@example.com",
                    "first_name": "string",
                    "last_name": "string",
                    "last_login": "2022-12-28T09:03:58.134Z",
                    "date_joined": "2022-12-28T09:03:58.134Z",
                    "profile": {
                        "phone": "2138036043",
                        "photo": "string",
                        "photo_url": "string",
                        "category": {
                            "id": 0,
                            "name": "string"
                        },
                        "category_id": 0
                    },
                    "user": 0,
                    "group": 0,
                    "product": 0,
                    "plan": 0,
                    "period_start": "2022-12-28T09:03:58.134Z",
                    "period_end": "2022-12-28T09:03:58.134Z",
                    "price": 0,
                    "tax_aggregate": 0
                }
            ]
        }

Detail
======

.. http:get:: /user-management/subscriptions/(int:id)/

    Mengembalikan detail *Subscription* yang tersedia berdasarkan ``id``.

    **Penjelasan Parameter URL**

    .. list-table:: 
      :widths: 15 80
      :header-rows: 1

      * - Parameter
        - Deskripsi
      * - id
        - ID yang memiliki nilai *unique integer* untuk mengidentifikasi *Subscription Plan*

    **Contoh Response**:

    .. sourcecode:: json

        {
            "id": "3fa85f64-5717-4562-b3fc-2c963f66afa6",
            "email": "user@example.com",
            "first_name": "string",
            "last_name": "string",
            "last_login": "2022-12-28T09:13:47.801Z",
            "date_joined": "2022-12-28T09:13:47.801Z",
            "profile": {
                "phone": "23256219304442",
                "photo": "string",
                "photo_url": "string",
                "category": {
                    "id": 0,
                    "name": "string"
                },
                "category_id": 0
            },
            "user": 0,
            "group": 0,
            "product": 0,
            "plan": 0,
            "period_start": "2022-12-28T09:13:47.801Z",
            "period_end": "2022-12-28T09:13:47.801Z",
            "price": 0,
            "tax_aggregate": 0
        }

Add
===

.. http:post:: /user-management/subscriptions/

    Menambahkan data *subscription* pada *management user*.

    **Contoh Response**:

    .. sourcecode:: json

        {
            "id": "3fa85f64-5717-4562-b3fc-2c963f66afa6",
            "email": "user@example.com",
            "first_name": "string",
            "last_name": "string",
            "last_login": "2022-12-28T09:16:25.583Z",
            "date_joined": "2022-12-28T09:16:25.583Z",
            "profile": {
                "phone": "18648137314",
                "photo": "string",
                "photo_url": "string",
                "category": {
                    "id": 0,
                    "name": "string"
                },
                "category_id": 0
            },
            "user": 0,
            "group": 0,
            "product": 0,
            "plan": 0,
            "period_start": "2022-12-28T09:16:25.583Z",
            "period_end": "2022-12-28T09:16:25.583Z",
            "price": 0,
            "tax_aggregate": 0
        }