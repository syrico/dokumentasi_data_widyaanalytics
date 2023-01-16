Connect Facebook
++++++++++++++++

Untuk mengolah data akun Instagram pengguna.
CekBrand membutuhkan *privilege* untuk melakukan *crawling* data pengguna melewati Facebook Graph API.
Privilege didapatkan melalui rangkaian otorisasi akun Facebook pengguna dengan layanan CekBrand atau yang disebut dengan **connect Facebook**.
Berikut adalah diagram alur yang mewakili usecase ini disertai penjelasannya.

.. figure:: ./facebook-connect-sequence.png
    :scale: 50
    :align: left

1. Pengguna melakukan request connect Facebook pada halaman **Depan** atau **Kelola Akun**
2. Frontend melakukan request :ref:`fb-auth-login`.
3. Backend mengembalikan URL untuk menuju halaman otentikasi Facebook.
4. Frontend membuka halaman otentikasi Facebook dengan alamat tersebut.
5. Pengguna mengisi formulir otentikasi Facebook.
6. Facebook melakukan *callback* dengan menyertakan kode otentikasi ke alamat :ref:`fb-auth-callback`.
7. Backend mengalihkan rute ke halaman **Callback Login**
8. Frontend menggunakan endpoint :ref:`fb-auth-login-callback` untuk connect Facebook menggunakan kode otorisasi.
9. Backend meminta *access token* ke Facebook API menggunakan kode tersebut.
10. Facebook mengembalikan *access token* yang bersifat *long-term*.
11. Backend menggunakan access token yang didapatkan sebelumnya untuk melakukan request data akun Facebook pengguna.
12. Facebook mengembalikan data akun Facebook pengguna.
13. Backend menyimpan data akun Facebook pengguna tersebut ke dalam database.
14. Penyimpanan data akun Facebook pengguna di database berhasil.
15. Backend menginfokan ke Frontent bahwa proses connect facebook berhasil.
16. Frontend mengalihkan pengguna ke halaman **Kelola Akun**.
17. Pengguna memilih akun Instagram yang akan dihubungkan ke CekBrand Dashboard.
18. Frontend menggunakan endpoint :ref:`fetch-ig-data` untuk melakuakn request mengambilan data akun Instagram pengguna.
19. Backend melakuakn request data akun Instagram pengguna ke Facebook API.
20. Facebook mengembalikan data akun Instagram tersebut.
21. Backend menyimpan data akun Instagram tersebut ke database.
22. Penyimpanan data akun Instagram di database berhasil.
23. Backend menjalankan fungsi analitik untuk akun Instagram tersebut.
24. Backend menyimpan data hasil analitik ke database.
25. Penyimpanan data hasil analitik di database berhasil.
26. Backend menginformasikan bahwa proses akuisisi data akun Instagram berhasil.
27. Proses 17-23 dilakukan sebanyak akun Instagram yang dipilih.