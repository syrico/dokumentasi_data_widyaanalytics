Vouchers Invitation
+++++++++++++++++++

Untuk memperoleh data *Vouchers Invitation*. Endpoint yang digunakan sebagai berikut.

List Invitation
===============

.. http:get:: /vouchers/invitation/

    Mengembalikan data list *Vouchers Invitation* yang tersedia.

    **Contoh Response**:

    .. sourcecode:: json

        [
            {
                "id": 0,
                "usage_count": "string",
                "created_at": "2022-12-29T15:22:37.617Z",
                "updated_at": "2022-12-29T15:22:37.617Z",
                "code": "string",
                "valid_from": "2022-12-29T15:22:37.617Z",
                "valid_to": "2022-12-29T15:22:37.617Z",
                "bound": true,
                "usage": 2147483647,
                "is_active": true,
                "name": "string",
                "user": 0
            }
        ]

Add Invitation
==============

.. http:post:: /vouchers/invitation/

    Menambahkan data *Invitation* baru.

    **Contoh Response**:

    .. sourcecode:: json

        {
            "code": "string",
            "valid_from": "2022-12-29T15:23:58.230Z",
            "valid_to": "2022-12-29T15:23:58.230Z",
            "bound": true,
            "usage": 2147483647,
            "is_active": true,
            "name": "string",
            "user": 0
        }

Detail Invitation
=================

.. http:get:: /vouchers/invitation/(int:id)/

    Mengembalikan data list *invitation* yang tersedia berdasarkan ``id``.

    **Penjelasan Parameter URL**

    .. list-table::
      :widths: 15 80
      :header-rows: 1

      * - Parameter
        - Deskripsi
      * - id
        - ID yang memiliki nilai untuk mengidentifikasi *invitation*

    **Contoh Response**:

    .. sourcecode:: json

        {
            "id": 0,
            "usage_count": "string",
            "created_at": "2022-12-29T15:24:43.777Z",
            "updated_at": "2022-12-29T15:24:43.778Z",
            "code": "string",
            "valid_from": "2022-12-29T15:24:43.778Z",
            "valid_to": "2022-12-29T15:24:43.778Z",
            "bound": true,
            "usage": 2147483647,
            "is_active": true,
            "name": "string",
            "user": 0
        }

Update Invitation
=================

.. http:put:: /vouchers/invitation/(int:id)/

    Memperbarui data list *invitation* yang tersedia berdasarkan ``id``.

    **Penjelasan Parameter URL**

    .. list-table::
      :widths: 15 80
      :header-rows: 1

      * - Parameter
        - Deskripsi
      * - id
        - ID yang memiliki nilai untuk mengidentifikasi *invitation*

    **Contoh Response**:

    .. sourcecode:: json

        {
            "id": 0,
            "usage_count": "string",
            "created_at": "2022-12-29T15:26:21.512Z",
            "updated_at": "2022-12-29T15:26:21.512Z",
            "code": "string",
            "valid_from": "2022-12-29T15:26:21.512Z",
            "valid_to": "2022-12-29T15:26:21.512Z",
            "bound": true,
            "usage": 2147483647,
            "is_active": true,
            "name": "string",
            "user": 0
        }

Delate Invitation
=================

.. http:delete:: /vouchers/invitation/(int:id)/

    Menghapus data list *invitation* yang tersedia berdasarkan ``id``.

    **Penjelasan Parameter URL**

    .. list-table::
      :widths: 15 80
      :header-rows: 1

      * - Parameter
        - Deskripsi
      * - id
        - ID yang memiliki nilai untuk mengidentifikasi *invitation*

Detail Redeemed Invitation
==========================

.. http:get:: /vouchers/invitation/(int:id)/redeemed

    Mengembalikan data list *invitation* yang tersedia berdasarkan ``id`` untuk diklaim.

    **Penjelasan Parameter URL**

    .. list-table::
      :widths: 15 80
      :header-rows: 1

      * - Parameter
        - Deskripsi
      * - id
        - ID yang memiliki nilai untuk mengidentifikasi *invitation*

    **Contoh Response**:

    .. sourcecode:: json

        {
            "id": 0,
            "usage_count": "string",
            "created_at": "2022-12-29T15:30:25.090Z",
            "updated_at": "2022-12-29T15:30:25.090Z",
            "code": "string",
            "valid_from": "2022-12-29T15:30:25.090Z",
            "valid_to": "2022-12-29T15:30:25.090Z",
            "bound": true,
            "usage": 2147483647,
            "is_active": true,
            "name": "string",
            "user": 0
        }

Update Reedem Invitation
========================

.. http:put:: /vouchers/invitation/(int:id)/redeem

    Memperbarui data list *invitation* yang tersedia berdasarkan ``id`` untuk diklaim.

    **Penjelasan Parameter URL**

    .. list-table::
      :widths: 15 80
      :header-rows: 1

      * - Parameter
        - Deskripsi
      * - id
        - ID yang memiliki nilai untuk mengidentifikasi *invitation*

    **Contoh Response**:

    .. sourcecode:: json

        {
            "id": 0,
            "usage_count": "string",
            "created_at": "2022-12-29T15:31:38.598Z",
            "updated_at": "2022-12-29T15:31:38.598Z",
            "code": "string",
            "valid_from": "2022-12-29T15:31:38.598Z",
            "valid_to": "2022-12-29T15:31:38.598Z",
            "bound": true,
            "usage": 2147483647,
            "is_active": true,
            "name": "string",
            "user": 0
        }