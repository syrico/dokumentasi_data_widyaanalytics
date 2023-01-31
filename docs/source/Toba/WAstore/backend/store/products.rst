Products
++++++++

Untuk memperoleh data products dari *store*. Endpoint yang digunakan sebagai berikut.

List 
====

.. http:get:: /store/products

    Mengembalikan data list product yang tersedia di *store* .

    .. note::
        A viewset for viewing and editing store application (product) instances.

    **Contoh Response**:

    .. sourcecode:: json

        [
            {
                "id": 0,
                "name": "string",
                "nickname": "string",
                "description": "string",
                "app_link": "string",
                "landing_link": "string",
                "extra_data": {},
                "is_active": true
            }
        ]

Add Product
===========

.. http:post:: /store/payments/

    Menambahkan data product store baru.

    .. note::
        A viewset for viewing and editing store application (product) instances.

    **Contoh Response**:

    .. sourcecode:: json

        {
            "id": 0,
            "name": "string",
            "nickname": "string",
            "description": "string",
            "app_link": "string",
            "landing_link": "string",
            "extra_data": {},
            "is_active": true
        }

Detail Products
===============

.. http:get:: /store/products/(int:id)/

    Mengembalikan data list product yang tersedia di *store* berdasarkan ``id``.

    .. note::
        A viewset for viewing and editing store application (product) instances.

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
            "name": "string",
            "nickname": "string",
            "description": "string",
            "app_link": "string",
            "landing_link": "string",
            "extra_data": {},
            "is_active": true
        }

Update Products
===============

.. http:put:: /store/products/(int:id)/

    Memperbarui data list product yang tersedia di *store* berdasarkan ``id``.

    .. note::
        A viewset for viewing and editing store application (product) instances.

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
            "name": "string",
            "nickname": "string",
            "description": "string",
            "app_link": "string",
            "landing_link": "string",
            "extra_data": {},
            "is_active": true
        }

Delate Products
===============

.. http:delete:: /store/products/(int:id)/

    Menghapus data list product yang tersedia di *store* berdasarkan ``id``.

    .. note::
        A viewset for viewing and editing store application (product) instances.


    **Penjelasan Parameter URL**

    .. list-table::
      :widths: 15 80
      :header-rows: 1

      * - Parameter
        - Deskripsi
      * - id
        - ID yang memiliki nilai *unique integer* untuk mengidentifikasi *Products*

Add Claim Free Trial
====================

.. http:post:: /store/products/{int:id}/claim-free-trial/

    Menambah data list untu klaim *free trial* terhadap product yang tersedia di *store* berdasarkan ``id``.

    .. note::
        Convenience endpoint for claim free trial for a store product.


    **Penjelasan Parameter URL**

    .. list-table::
      :widths: 15 80
      :header-rows: 1

      * - Parameter
        - Deskripsi
      * - id
        - ID yang memiliki nilai *unique integer* untuk mengidentifikasi *Store Products*

    **Contoh Response**:

    .. sourcecode:: json

        {
            "id": 0,
            "name": "string",
            "nickname": "string",
            "description": "string",
            "app_link": "string",
            "landing_link": "string",
            "extra_data": {},
            "is_active": true
        }