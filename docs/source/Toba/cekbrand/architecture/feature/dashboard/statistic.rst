Halaman Statistik
+++++++++++++++++

Halaman kedua pada aplikasi Toba.ai Cekbrand yang memiliki fungsi untuk menampilkan analisis data performa akun Instagram berbanding waktu.
Statistik yang ditampilkan dalam halaman ini adalah statistik wawasan akun, wawasan konten, keterikatan dengan pengikut Instagram, serta data sebaran pengikut Instagram.
Terdapat pula saran-saran singkat pada setiap data grafik yang ditampilkan.
Berikut adalah diagram alur yang mewakili halaman ini disertai penjelasannya.

.. toggle-header::
        :header: **Performa Akun**

        .. figure:: ./statistic-account-sequence.png
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