Switch Instagram Competitor Account
+++++++++++++++++++++++++++++++++++

Switch instagram competitor account merupakan feature saat halaman dashboard aplikasi Toba.ai Cekbrand terbuka 
dan memiliki fungsi untuk mengganti account instagram competitor yang di pilih oleh user Toba.ai .

.. figure:: ./switch-instagram-competitor-account.png
    :scale: 50
    :align: left

1. Pengguna melakukan penggantian account instagram competitor pada aplikasi Toba.ai
2. Frontend akan melakukan request pada backend dengan endpoint :ref:`fetch-user-ig-competitor-data`, :ref:`fetch-media-average-ig-competitor-data`, :ref:`fetch-media-summary-ig-competitor-data`, :ref:`fetch-hashtag-ig-competitor-data` .
3. Backend akan mencari data sesuai request dari frontend.
4. Backend akan mendapatkan response berupa data yang direquest pada tahap ke-3.
5. Backend memberikan Backend akan mengembalikan response user instagram list account competitor detail pada frontend.