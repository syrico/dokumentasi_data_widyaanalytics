Subscription Plans
++++++++++++++++++

Untuk memperoleh *Subscription Plans*. Endpoint yang digunakan sebagai berikut.

List
====

.. http:get:: /subscription-plans/

    Mengembalikan *Subscription Plans* yang tersedia.

    **Contoh Response**:

    .. sourcecode:: json

        [
            {
                "id": 0,
                "name": "string",
                "description": "string",
                "price": 2147483647,
                "period_days": 2147483647,
                "perks": [
                "string"
                ],
                "extra_data": {},
                "product": 0
            }
        ]


Detail
======

.. http:get:: /subscription-plans/(int:id)/

    Mengembalikan *Subscription Plans* yang tersedia berdasarkan ``id``.

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
            "id": 0,
            "name": "string",
            "description": "string",
            "price": 2147483647,
            "period_days": 2147483647,
            "perks": [
                "string"
            ],
            "extra_data": {},
            "product": 0
        }