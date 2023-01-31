Feedback
++++++++

Untuk memperoleh data *feedback*. Endpoint yang digunakan sebagai berikut.

List Feedback
=============

.. http:get:: /feedback/

    Mengembalikan data list *feedback* yang ada.

    **Contoh Response**:

    .. sourcecode:: json

        [
            {
                "id": 0,
                "user": "string",
                "satisfaction": "string",
                "type": "string",
                "page": "string",
                "message": "string",
                "attachment": "string",
                "attachment_url": "string",
                "created_at": "2022-12-29T06:06:20.933Z"
            }
        ]

Add Feedback
============

.. http:post:: /feedback/

    Menambahkan data feedback baru.

    **Penjelasan Parameter URL**

    .. list-table::
      :widths: 15 80
      :header-rows: 1

      * - Parameter
        - Deskripsi
      * - id
        - ID yang memiliki nilai *unique integer* untuk mengidentifikasi *Products*

    **Contoh Response**:

    .. sourcecode:: json

        {
            "id": 0,
            "user": "string",
            "satisfaction": "string",
            "type": "string",
            "page": "string",
            "message": "string",
            "attachment": "string",
            "attachment_url": "string",
            "created_at": "2022-12-29T06:07:57.543Z"
        }

Detail Feedback
===============

.. http:get:: /feedback/{int:id}/

    Mengembalikan data detail list feedback yang tersedia berdasarkan ``id``.

    **Penjelasan Parameter URL**

    .. list-table::
      :widths: 15 80
      :header-rows: 1

      * - Parameter
        - Deskripsi
      * - id
        - ID yang memiliki nilai *unique integer* untuk mengidentifikasi *Feedback*

    **Contoh Response**:

    .. sourcecode:: json

        {
            "id": 0,
            "user": "string",
            "satisfaction": "string",
            "type": "string",
            "page": "string",
            "message": "string",
            "attachment": "string",
            "attachment_url": "string",
            "created_at": "2022-12-29T06:10:02.651Z"
        }

Update Feedback
===============

.. http:put:: /feedback/{int:id}/

    Memperbarui data list feedback yang tersedia berdasarkan ``id``.

    **Penjelasan Parameter URL**

    .. list-table::
      :widths: 15 80
      :header-rows: 1

      * - Parameter
        - Deskripsi
      * - id
        - ID yang memiliki nilai *unique integer* untuk mengidentifikasi *Feedback*

    **Contoh Response**:

    .. sourcecode:: json

        {
            "id": 0,
            "user": "string",
            "satisfaction": "string",
            "type": "string",
            "page": "string",
            "message": "string",
            "attachment": "string",
            "attachment_url": "string",
            "created_at": "2022-12-29T06:10:02.665Z"
        }

Delate Feedback
===============

.. http:delete:: /feedback/{int:id}/

    Menghapus data list feedback yang tersedia berdasarkan ``id``.

    **Penjelasan Parameter URL**

    .. list-table::
      :widths: 15 80
      :header-rows: 1

      * - Parameter
        - Deskripsi
      * - id
        - ID yang memiliki nilai *unique integer* untuk mengidentifikasi *Feedback*
