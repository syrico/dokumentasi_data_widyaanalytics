.. _download-export:

Download/Export Data
++++++++++++++++++++++++++++

Download/Export account data merupakan fasilitas 
yang memungkinkan pengguna untuk dapat menyimpan seluruh data 
statistik dari akun Instagramnya. Bisa diunduh menjadi format csv, excel, bahkan pdf.
Berikut penjelasan dan diagram alur mengenail export data dengan format csv, format excel dan format pdf.

.. toggle-header::
        :header: **Export data format csv**

        Export account data format csv merupakan fitur export untuk mendapatkan account data dalam bentuk file csv.

        .. figure:: ./download-csv-account-data.png
            :scale: 50
            :align: left

        1. Pengguna menekan tombol export.
        2. Frontend akan menampilkan pop up dropdown file extension.
        3. Response pop up diterima oleh pengguna.
        4. Pengguna akan memilih file extension csv.
        5. Frontend akan menampilkan pop up radio button yang mengandung isi content dari file yang akan terdownload, 
           terdapat pilihan content seperti Media, Negara, Profil, Jenis Kelamin, Kota, Umur.
        6. Response pop up akan dikirim ke pengguna.
        7. Pengguna memilih isi content file.
        8. Frontend akan meminta request download file csv melalui endpoint :ref:`csv`.
        9. Backend mengambil data yang ada dalam database.
        10. Backend akan menerima response success/error dari database
        11. Backend mengembalikan response data ke frontend.
        12. Frontend akan mengenerate data kedalam bentuk file csv.
        13. Frontend akan memberikan file yang telah tergenerate ke pengguna.

.. toggle-header::
        :header: **Export data format excel**

        Export account data format excel merupakan fitur export untuk mendapatkan account data dalam bentuk file excel.

        .. figure:: ./download-xlsx-account-data.png
            :scale: 50
            :align: left

        1. Pengguna menekan tombol export.
        2. Frontend akan menampilkan pop up dropdown file extension.
        3. Response pop up diterima oleh pengguna.
        4. Pengguna akan memilih file extension xlsx.
        5. Frontend akan meminta request download file xlsx melalui endpoint :ref:`excel`.
        6. Backend akan mencari data berdasarkan request.
        7. Backend akan menerima response success/error dari database.
        8. Backend akan mengenerate xlsx file.
        9. Pengguna akan mendapatkan file xlsx yang digenerate oleh backend.

.. toggle-header::
        :header: **Export data format pdf**

        Export account data format pdf merupakan fitur export untuk mendapatkan account data dalam bentuk file pdf.

        .. figure:: ./download-pdf-account-data.png
            :scale: 50
            :align: left

        1. Pengguna menekan tombol export.
        2. Frontend akan menampilkan pop up dropdown file extension.
        3. Response pop up diterima oleh pengguna.
        4. Pengguna akan memilih file extension pdf.
        5. Frontend akan menampilkan pop up combobox yang mengandung halaman mana saja yang akan di export, 
           terdapat pilihan halaman seperti Kompetitor, Statistik, Top post.
        6. Response pop up akan dikirim ke pengguna.
        7. Pengguna memilih halaman yang akan di export.
        8. Dari aksi pengguna tersebut, maka frontend akan melakukan request :ref:`account-user`.
        9. Backend akan mencari data pengguna berdasarkan token data user active current login.
        10. Backend akan mendapatkan response berupa data yang direquest pada tahap ke-9.
        11. Backend akan mengembalikan response user account toba.ai tahap ke-10 ke frontend.
        12. Frontend akan melakukan request user list instagram account dengan endpoint :ref:`account-list`.
        13. Backend akan mencari user list instagram account data di database.
        14. Backend akan mendapatkan response berupa data yang direquest pada tahap ke-13.
        15. Backend mengembalikan response user list instagram account ke frontend.
        16. Frontend melakukan request ke backend dengan endpoint :ref:`account-detail`, :ref:`user-data-summary`, :ref:`fetch-user-data`, :ref:`fetch-hashtag-ig-user-data`.
        17. Backend akan mencari user instagram account detail di database.
        18. Backend akan mendapatkan response berupa data yang direquest pada tahap ke-17.
        19. Backend mengembalikan response user instagram account detail.
        20. Frontend melakukan request pada backend dengan endpoint :ref:`fetch-list-ig-competitor-data`.
        21. Backend akan mencari user instagram list account competitor data.
        22. Backend akan mendapatkan response berupa data yang direquest pada tahap ke-21.
        23. Backend akan mengembalikan response user instagram list account competitor pada frontend.
        24. Frontend akan melakukan request pada backend dengan endpoint :ref:`fetch-user-ig-competitor-data`, :ref:`fetch-media-average-ig-competitor-data`, :ref:`fetch-media-summary-ig-competitor-data`, :ref:`fetch-hashtag-ig-competitor-data` .
        25. Backend akan mencari data sesuai request dari frontend.
        26. Backend akan mendapatkan response berupa data yang direquest pada tahap ke-25.
        27. Backend memberikan Backend akan mengembalikan response user instagram list account competitor detail pada frontend.
        28. Frontend akan mengenerate data kedalam bentuk file pdf.
        29. Frontend juga akan menngcompress file menjadi file zip.
        30. Pengguna menerima file export.
