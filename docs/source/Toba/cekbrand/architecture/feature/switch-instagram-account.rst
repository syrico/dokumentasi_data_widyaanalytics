.. _switch-instagram-account:

Switch Instagram Account
========================

        Switch instagram account merupakan fitur saat halaman dashboard aplikasi Toba.ai Cekbrand terbuka 
        dan memiliki fungsi untuk mengganti account instagram milik user Toba.ai sesuai 
        account instagram yang telah dihubungkan dengan aplikasi Toba.ai.

        .. figure:: ./switch-instagram-account.png
            :scale: 50
            :align: left

        1. Pengguna melakukan penggantian account instagram pada aplikasi Toba.ai
        2. Dari aksi pengguna tersebut, maka frontend akan melakukan request dengan endpoint :ref:`account-detail`, :ref:`user-data-summary`, :ref:`fetch-user-data`, :ref:`fetch-hashtag-ig-user-data`.
        3. Backend akan mencari user instagram account detail di database.
        4. Backend akan mendapatkan response berupa data yang direquest pada tahap ke-4.
        5. Backend mengembalikan response user instagram account detail.
        6. Frontend melakukan request pada backend dengan endpoint :ref:`fetch-list-ig-competitor-data`.
        7. Backend akan mencari user instagram list account competitor data.
        8. Backend akan mendapatkan response berupa data yang direquest pada tahap ke-7.
        9. Backend akan mengembalikan response user instagram list account competitor pada frontend.
        10. Frontend akan melakukan request pada backend dengan endpoint :ref:`fetch-user-ig-competitor-data`, :ref:`fetch-media-average-ig-competitor-data`, :ref:`fetch-media-summary-ig-competitor-data`, :ref:`fetch-hashtag-ig-competitor-data` .
        11. Backend akan mencari data sesuai request dari frontend.
        12. Backend akan mendapatkan response berupa data yang direquest pada tahap ke-11.
        13. Backend memberikan Backend akan mengembalikan response user instagram list account competitor detail pada frontend.
