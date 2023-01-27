Categories
++++++++++

Untuk memperoleh data *categories* berdasarkan *management user*. Endpoint yang digunakan sebagai berikut.

List
====

.. http:get:: /user-management/categories/

    Mengembalikan data *categories* dari *user management*.

    **Contoh Response**:

    .. sourcecode:: json

        [
            {
                "id": 0,
                "name": "string"
            }
        ]