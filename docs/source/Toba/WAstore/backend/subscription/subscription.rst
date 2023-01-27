Subscription
++++++++++++

Untuk memperoleh data *Subscription*. Endpoint yang digunakan sebagai berikut.

List
====

.. http:get:: /subscription/

    Mengembalikan data *Subscription* yang tersedia.

    **Contoh Response**:

    .. sourcecode:: json

        [
            {
                "id": "3fa85f64-5717-4562-b3fc-2c963f66afa6",
                "user": 0,
                "status": "string",
                "plan": 0,
                "group": 0,
                "period_start": "2022-12-28T08:49:52.856Z",
                "period_end": "2022-12-28T08:49:52.856Z"
            }
        ]

Detail
======

.. http:get:: /subscription/(uuid:id)/

    Mengembalikan detail *Subscription* yang tersedia berdasarkan ``id``.

    *Penjelasan Parameter URL**

    .. list-table:: 
      :widths: 15 80
      :header-rows: 1

      * - Parameter
        - Deskripsi
      * - id
        - ID yang memiliki nilai *UUID* untuk mengidentifikasi *Subscription*

    **Contoh Response**:

    .. sourcecode:: json

        {
            "id": "3fa85f64-5717-4562-b3fc-2c963f66afa6",
            "user": 0,
            "status": "string",
            "plan": 0,
            "group": 0,
            "period_start": "2022-12-28T08:49:52.858Z",
            "period_end": "2022-12-28T08:49:52.858Z"
        }

Delate
======

.. http:delete:: /subscription/(uuid:id)/

    Menghapus detail *Subscription* yang tersedia berdasarkan ``id``.
    
    .. list-table:: 
      :widths: 15 80
      :header-rows: 1

      * - Parameter
        - Deskripsi
      * - id
        - ID yang memiliki nilai *UUID* untuk mengidentifikasi *Subscription*