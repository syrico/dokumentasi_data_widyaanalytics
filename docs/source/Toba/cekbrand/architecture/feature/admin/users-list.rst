Daftar Pengguna
+++++++++++++++

Halaman khusus admin Cekbrand Toba.ai untuk mengelola daftar pengguna aplikasi dan masa aktif paket nya secara manual.
Dalam halaman ini admin dapat melakukan perubahan data subscription pengguna dan melihat detail data pengguna besera akun Facebook dan Instagram yang sudah terhubung dengan Toba.ai.
Berikut adalah diagram urutan yang mewakili proses-proses yang terjadi dalam halaman ini.

.. figure:: ./users-list-sequence.png
    :scale: 50
    :align: left

1. Admin membuka halaman **Daftar Pengguna**.
2. Frontend melakukan request ke Backend Widya Analytic Store (WAS) untuk daftar *group*, *category* dan *subscription* pengguna.
3. Frontend memuat dan menampilakn daftar pengguna dalam bentuk tabel.

