Kelola akun Instagram-Facebook
++++++++++++++++++++++++++++++

Fitur yang berperan sebagai pengelola akun Instagram-Facebook yang memungkinkan pengguna mengubah akun mana saja yang dapat diakses oleh aplikasi Toba.ai untuk ditampilkan analisis datanya.

.. figure:: ./account-manage-sequence.png
    :scale: 60
    :align: left

1. Pengguna membuka halaman **Kelola Akun**.
2. Frontend melakukan request ke endpoint :ref:`social-account-list`.
3. Frontend memuat dan menampilkan kolom daftar akun Facebook and Instagram pengguna.
4. Frontend melakukan request ke endpoint :ref:`account-list`.
5. Frontend melakukan request ke endpoint :ref:`subs-groups-list`.
6. Frontend memuat dan menampilkan keterangan jumlah akun Instagram yang telah terkoneksi dengan CekBrand.