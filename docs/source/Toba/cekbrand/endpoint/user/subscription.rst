Subscription
++++++++++++

Meskipun data subscription pengguna disimpan dalam layanan Widya Analytic Store, pada setiap layanan atau produk terdapat kelompok subscription yang memiliki hak nya masing-masing.

.. _subs-groups-list:

Groups List
===========

.. http:get:: /user-management/subscription-groups

    Mengambil semua daftar data kelompok subscirption yang mencakup hak-hak masing-masing, contohnya batas jumlah akun Instagram, kompetitor, pilihan *data frame*, dsb.

    **Contoh Response**:

    .. sourcecode:: http

        HTTP/1.1 200 OK
        Content-Type: application/json

        [
            {
                "group": 0,
                "limit_ig_account": 2147483647,
                "limit_ig_competitor": 2147483647,
                "limit_social_account": 2147483647
            }
        ]
