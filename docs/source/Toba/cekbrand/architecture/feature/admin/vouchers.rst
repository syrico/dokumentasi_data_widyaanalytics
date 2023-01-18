Kelola Kupon
++++++++++++

Halaman khusus admin Cekbrand Toba.ai untuk mengelola daftar kupon marketing yang berlaku untuk setiap pendaftaran pengguna baru.
Halaman terdiri dari kolom Grafik Penggunaan Kupon, Daftar Penggunaan Kupon, dan Daftar Kupon.
Selain itu terdafat fitur untuk menambah, mengubah, dan menghapus kupon oleh admin.
Berikut adalah diagram urutan yang mewakili proses-proses dalam halaman ini.

.. figure:: ./vouchers-sequence.png
    :scale: 50
    :align: left

1. Admin membuka halaman **Kelola Kupon**
2. Frontend melakukan request ke Backend Widya Analytic Store (WAS) untuk mendapatkan data kupon.
3. Frontend memuat dan menampilkan data kupon dalam bentuk grafik dan tabel.