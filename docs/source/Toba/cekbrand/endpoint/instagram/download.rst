Download Account Data
+++++++++++++++++++++

Data akun Instagram pengguna dapat diunduh (*download*) menggunakan endpoint berikut.

.. list-table:: 
      :widths: 15 80
      :header-rows: 1

      * - Parameter
        - Deskripsi
      * - account_id
        - ID akun Instagram pengguna
      * - data_type
        - Tipe data yang akan diunduh, mencakup: media, profile, city, country, gender, age, dan hashtag

CSV
===

.. http:get:: /cekbrand/accounts/(int:account_id)/download/csv/(string:data_type)

    Mengunduh data akun Instagram pengguna dengan format `csv`.

    :query string start: tanggal awal filter data in UTC-0 (ISO 8601 format)
    :query string end: tanggal akhir filter data in UTC-0 (ISO 8601 format)
    :query string date_frame: *frame* tanggal filter data, mencakup 7, 28, 60 dan 90

    **Contoh Hasil**:

    .. image:: ../images/download-csv.png

Excel
=====

.. http:get:: /cekbrand/accounts/(int:account_id)/download/xlsx

    Mengunduh data akun Instagram pengguna dengan format `xlsx`.

    :query string start: tanggal awal filter data in UTC-0 (ISO 8601 format)
    :query string end: tanggal akhir filter data in UTC-0 (ISO 8601 format)
    :query string date_frame: *frame* tanggal filter data, mencakup 7, 28, 60 dan 90

    **Contoh Hasil**:

    .. image:: ../images/download-xlsx.png
