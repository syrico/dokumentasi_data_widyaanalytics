Kelola akun Instagram-Facebook
++++++++++++++++++++++++++++++

Fitur yang berperan sebagai pengelola akun Instagram-Facebook yang memungkinkan pengguna mengubah akun mana saja yang dapat diakses oleh aplikasi Toba.ai untuk ditampilkan analisis datanya.

.. figure:: ./account-manage-sequence.png
    :scale: 60
    :align: left

1. Pengguna membuka halaman **Kelola Akun**.
2. Frontend melakukan request ke endpoint :ref:`social-account-list`.
3. Backend mengambil daftar akun Facebook pengguna dari tabel ``public.socialaccount_socialaccount`` dan ``public.socialaccount_socialtoken``.
4. Backend mengembalikan daftar akun Facebook pengguna ke Frontend.
5. Frontend memuat dan menampilkan kolom daftar akun Facebook and Instagram pengguna.
6. Frontend melakukan request ke endpoint :ref:`account-list`.
7. Backend mengambil daftar akun Instagram pengguna dari tabel ``instagram.user``, ``instagram.user_data`` dan ``public.socialaccount_socialaccount``.
8. Backend mengembalikan daftar akun Instagram pengguna ke Frontend.
9. Frontend melakukan request ke endpoint :ref:`subs-groups-list`.
10. Backend mengambil daftar group langganan dari tabel ``public.subscriptions_group``.
11. Backend mengembalikan daftar group langganan ke Frontend.
12. Frontend memuat dan menampilkan keterangan jumlah akun Instagram yang telah terkoneksi dengan CekBrand.