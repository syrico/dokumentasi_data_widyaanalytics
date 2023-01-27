Vouchers Reedem
+++++++++++++++

Untuk memperoleh data *Vouchers Reedem*. Endpoint yang digunakan sebagai berikut.

List Reedem
===========

.. http:get:: /vouchers/redeemed/invitation/

    Mengembalikan data list *Vouchers Reedem* yang tersedia.

    **Contoh Response**:

    .. sourcecode:: json

        {
            "count": 0,
            "next": "string",
            "previous": "string",
            "results": [
                {
                    "user": "string",
                    "code": "string",
                    "name": "string",
                    "redeemed": "2022-12-29T15:33:58.137Z"
                }
            ]
        }

Add Reedem
==========

.. http:post:: /vouchers/redeemed/invitation/

    Menambahkan data *Reedem* baru.

    **Contoh Response**:

    .. sourcecode:: json

        {
            "user": "string",
            "code": "string",
            "name": "string",
            "redeemed": "2022-12-29T15:35:24.148Z"
        }

Detail Reedem
=============

.. http:get:: /vouchers/redeemed/invitation/(int:id)/

    Mengembalikan data list *Reedem* yang tersedia berdasarkan ``id``.

    **Penjelasan Parameter URL**

    .. list-table::
      :widths: 15 80
      :header-rows: 1

      * - Parameter
        - Deskripsi
      * - id
        - ID yang memiliki nilai untuk mengidentifikasi *reedem*

    **Contoh Response**:

    .. sourcecode:: json

        {
            "user": "string",
            "code": "string",
            "name": "string",
            "redeemed": "2022-12-29T15:36:46.720Z"
        }

Update Reedem
=============

.. http:put:: /vouchers/redeemed/invitation/(int:id)/

    Memperbarui data list *reedem* yang tersedia berdasarkan ``id``.

    **Penjelasan Parameter URL**

    .. list-table::
      :widths: 15 80
      :header-rows: 1

      * - Parameter
        - Deskripsi
      * - id
        - ID yang memiliki nilai untuk mengidentifikasi *reedem*

    **Contoh Response**:

    .. sourcecode:: json

        {
            "user": "string",
            "code": "string",
            "name": "string",
            "redeemed": "2022-12-29T15:37:41.468Z"
        }

Delate Invitation
=================

.. http:delete:: /vouchers/redeemed/invitation/(int:id)/

    Menghapus data list *reedem* yang tersedia berdasarkan ``id``.

    **Penjelasan Parameter URL**

    .. list-table::
      :widths: 15 80
      :header-rows: 1

      * - Parameter
        - Deskripsi
      * - id
        - ID yang memiliki nilai untuk mengidentifikasi *reedem*