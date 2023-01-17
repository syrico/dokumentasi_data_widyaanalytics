Halaman Statistik
+++++++++++++++++

Halaman kedua pada aplikasi Toba.ai Cekbrand yang memiliki fungsi untuk menampilkan analisis data performa akun Instagram berbanding waktu.
Statistik yang ditampilkan dalam halaman ini adalah statistik wawasan akun, wawasan konten, keterikatan dengan pengikut Instagram, serta data sebaran pengikut Instagram.
Terdapat pula saran-saran singkat pada setiap data grafik yang ditampilkan.
Berikut adalah diagram alur yang mewakili halaman ini disertai penjelasannya.

.. figure:: ./statistic-sequence.png
    :scale: 80
    :align: center

1. Pengguna membuka tab **Halaman Statistik**.
2. Frontend melakukan request ke Backend untuk mendapatkan data statistik.
3. Backend mengambil data statistik yang dibutuhkan dari Database.
4. Database mengembalikan data statistik yang dibutuhkan.
5. Backend mengembalikan data statistik.
6. Frontend memuat kolom-kolom statistik pada halaman.
7. Frontend menampilkan kolom-kolom statistik pada halaman.

Halaman Statistik terdiri dari dua bagian **Performa Akun** dan **Followers**.
Berikut adalah diagram alur yang mewakili dua bagian tersebut dan disertai dengan penjelasannya.

.. toggle-header::
        :header: **Performa Akun**

        .. figure:: ./statistic-account-sequence.png
            :scale: 50
            :align: left

        1. Pengguna membuka tab **Halaman Statistik**.
        2. Frontend melakukan request ke endpoint :ref:`user-data-summary`.
        3. Backend mengambil data dari tabel ``instagram.user_data``.
        4. Backend melakukan kalkulasi *summary*.
        5. Backend mengembalikan user-data summary.
        6. Frontend memuat dan menampilkan grafik **Follower Growth Rate**.
        7. Frontend melakukan request ke endpoint :ref:`reach-average-summary`.
        8. Backend melakukan agregat rerata data reach pada tabel ``instagram.user_insight_reach``.
        9. Backend melakukan kalkulasi *summary* rerata data reach.
        10. Backend mengembalikan data summary rerata reach.
        11. Backend melakukan request ke endpoint :ref:`impressions-list`.
        12. Backend mengambil daftar reach dari tabel ``instagram.user_insight_reach``.
        13. Backend mengembalikan daftar reach.
        14. Frontend memuat dan menampilkan grafik **Reach**.
        15. Frontend melakukan request ke endpoint :ref:`impressions-average-summary`.
        16. Backend melakukan agregat rerata data impressions pada tabel ``instagram.user_insight_impressions``.
        17. Backend melakukan kalkulasi *summary* rerata data impressions.
        18. Backend mengembalikan data summary rerata impressions.
        19. Backend melakukan request ke endpoint :ref:`impressions-list`.
        20. Backend mengambil daftar impressions dari tabel ``instagram.user_insight_impressions``.
        21. Backend mengembalikan daftar impressions.
        22. Frontend memuat dan menampilkan grafik **Impressions**.
        23. Backend melakukan request ke endpoint :ref:`engagement-list`.
        24. Backend mengambil daftar like-comment dari tabel ``instagram.media_like_comment``.
        25. Backend mengembalikan daftar like-comment.
        26. Frontend memuat dan menampilkan grafik **Engagement**.
        27. Frontend melakukan request ke endpoint :ref:`engagement-summary`.
        28. Backend melakukan agregat data engagement rate pada tabel ``instagram.user_data`` dan ``instagram.media_like_comment``.
        29. Backend mengemb`alikan data summary engagement.
        30. Frontend memuat dan menampilkan grafik **Engagement Rate**.

.. toggle-header::
        :header: **Followers**

        .. figure:: ./statistic-followers-sequence.png
            :scale: 50
            :align: left

        1. Pengguna membuka tab **Halaman Statistik**.
        2. Frontend melakukan request ke Backend untuk mendapatkan data statistik.
        3. Backend mengambil data statistik yang dibutuhkan dari Database.
        4. Database mengembalikan data statistik yang dibutuhkan.
        5. Backend mengembalikan data statistik.
        6. Frontend memuat kolom-kolom statistik pada halaman.
        7. Frontend menampilkan kolom-kolom statistik pada halaman.

|