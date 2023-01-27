Payments
++++++++

Untuk memperoleh data transaksi dari API Midtrans. Endpoint yang digunakan sebagai berikut.

Detail List Payment with Midtrans
=================================

.. http:get:: /store/payments/{uuid:id}/

    Mengembalikan data transaksi dari Midtrans.

    .. note::
        Retrieve including updating (using Midtrans get status API) a product payment instance.


    **Penjelasan Parameter URL**

    .. list-table::
      :widths: 15 80
      :header-rows: 1

      * - Parameter
        - Deskripsi
      * - id
        - ID yang memiliki nilai *UUID* untuk mengidentifikasi *payment product*

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

Delate Payment with Midtrans
============================

.. http:delete:: /store/payments/{uuid:id}/

    Menghapus data transaksi dari Midtrans.

    .. note::
        Retrieve including updating (using Midtrans get status API) a product payment instance.


    **Penjelasan Parameter URL**

    .. list-table::
      :widths: 15 80
      :header-rows: 1

      * - Parameter
        - Deskripsi
      * - id
        - ID yang memiliki nilai *UUID* untuk mengidentifikasi *payment product*

Detail List Payment
===================

.. http:get:: /store/payments/{uuid:var}/

    Mengembalikan seluruh data transaksi.

    .. note::
        List all product payments transaction.

    **Penjelasan Parameter URL**

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
      * - var
        - var yang memiliki nilai *UUID* untuk mengidentifikasi *payment product*

    **Contoh Response**:

    .. sourcecode:: json

        {
            "count": 0,
            "next": "string",
            "previous": "string",
            "results": [
                    {
                        "id": "3fa85f64-5717-4562-b3fc-2c963f66afa6",
                        "user": 0,
                        "subscription_plan": 0,
                        "transaction_status": "settlement",
                        "transaction_details": {}
                    }
                ]
        }

Add Payment
===========

.. http:post:: /store/payments/{uuid:var}/

    Menambahkan data transaksi baru.

    .. note::
        create a new product payment transaction.


    **Penjelasan Parameter URL**

    .. list-table::
      :widths: 15 80
      :header-rows: 1

      * - Parameter
        - Deskripsi
      * - var
        - var yang memiliki nilai *UUID* untuk mengidentifikasi *payment product*

    **Contoh Response**:

    .. sourcecode:: json

        {
            "id": "3fa85f64-5717-4562-b3fc-2c963f66afa6",
            "user": 0,
            "subscription_plan": 0,
            "transaction_status": "settlement",
            "transaction_details": {}
        }