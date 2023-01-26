
.. _choose-date-frame:

Choose Date Frame
==================

        Choose Date Frame merupakan fitur saat halaman dashboard aplikasi Toba.ai Cekbrand terbuka 
        dan memiliki fungsi untuk memilih date frame account instagram data load sesuai user inginkan.

        .. figure:: ./choose-date-frame.png
            :scale: 50
            :align: left

        1. Pengguna memilih dateframe sesuai user inginkan
        2. Dari aksi pengguna tersebut, maka frontend melakukan request ke backend dengan endpoint :ref:`account-detail`, :ref:`user-data-summary`, :ref:`fetch-user-data`, :ref:`fetch-hashtag-ig-user-data` dengan mengirimkan params berupa *start-date dan end-date* atau *date_frame*.
        3. Backend akan mencari data sesuai request dari frontend di dalam database
        4. Backend akan mendapatkan response sesuai request yang
        5. Backend mengembalikan response user instagram account detail ke frontend
        6. Frontend melakukan request pada backend dengan endpoint :ref:`fetch-list-ig-competitor-data`.
        7. Backend akan mencari user instagram list account competitor data.
        8. Backend akan mendapatkan response berupa data yang direquest pada tahap ke-7.
        9. Backend akan mengembalikan response user instagram list account competitor pada frontend.
        10. Frontend akan melakukan request pada backend dengan endpoint :ref:`fetch-user-ig-competitor-data`, :ref:`fetch-media-average-ig-competitor-data`, :ref:`fetch-media-summary-ig-competitor-data`, :ref:`fetch-hashtag-ig-competitor-data` dengan mengirimkan params berupa *start-date dan end-date* atau *date_frame*.
        11. Backend akan mencari data sesuai request dari frontend.
        12. Backend akan mendapatkan response berupa data yang direquest pada tahap ke-11.
        13. Backend akan mengembalikan response user instagram list account competitor detail pada frontend.
