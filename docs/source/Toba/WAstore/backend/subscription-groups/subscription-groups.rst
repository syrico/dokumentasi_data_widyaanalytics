Subscription Groups
+++++++++++++++++++

Untuk memperoleh *Subscription Groups*. Endpoint yang digunakan sebagai berikut.

List
====

.. http:get:: /subscription-groups/

    Mengembalikan *Subscription Groups* yang dimiliki pengguna.

    **Contoh Response**:

    .. sourcecode:: json

        [
            {
                "id": 0,
                "name": "string",
                "permissions": [
                0
                ]
            }
        ]