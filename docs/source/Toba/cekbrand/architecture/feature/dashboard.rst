Dashboard
+++++++++

Halaman dashboard terdiri dari Kompetitor, Statistik dan Top Post.

.. toctree:: 

    dashboard/statistic
    dashboard/competitor
    dashboard/post

Selain itu fitur yang melengkapi setiap halaman dashboard antara lain pindah akun, filter tanggal dan export/download data. 
Berikut adalah diagram alur yang mewakili halaman ini disertai penjelasannya.

.. figure:: ./dashboard-sequence-v2.png
    :scale: 50
    :align: left

1. Pengguna memilih akun Instagram pada halaman **Pilih Akun** atau mengganti akun pada menu di dashboard.
2. Frontend menetapkan akun yang dipilih menjadi *active account* pada dashboard.
3. Untuk kasus pertama kali mengunjungi halaman dashboard, Frontend terlebih dahulu melakukan request endpoint :ref:`account-list`.
4. Backend mengambil data daftar akun Instagram dari database ``instagram.user``, ``instagram.user_data`` dan ``public.socialaccount_socialaccount``.
5. Database mengembalikan data daftar akun Instagram yang dibutuhkan.
6. Backend mengembalikan daftar akun Instagram ke Frontend
7. Frontend melakukan request ke endpoint :ref:`account-detail`.
8. Backend mengambil data detail akun Instagram dari database ``instagram.user``, ``instagram.user_data`` dan ``public.socialaccount_socialaccount``.
9. Database mengembalikan data detail akun Instagram yang dibutuhkan.
10. Backend melakukan validasi *access token* akun Instagram terkait.
11. Backend mengambil Instagram token dari database ``instagram.instagram_tokens`` atau ``public.socialaccount_socialtoken``.
12. Dashboard mengembalikan Instagram token terkait.
13. Jika token tidak valid Backend akan mengembalikan error.
14. Frontend akan mengalihkan tampilan ke halaman **Re-Authotization Facebook**.
15. Frontend menampilkan halaman tersebut pada Pengguna.
16. Jika token valid,
17. Backend mengembalikan data detail akun.
18. Frontend berhasil menetapkan *active account* pada dashboard.
19. Frontend memuat header dan tab-tab dashboard yang terdiri dari Kompetitor, Statistik dan Top Post.
20. Frontend menampilkan halaman dashboard pada Pengguna.

