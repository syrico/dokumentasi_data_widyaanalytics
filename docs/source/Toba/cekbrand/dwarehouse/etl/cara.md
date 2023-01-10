#   Pengertian dan Langkah-Langkah

ETL adalah singkatan dari  **Extract, Transform, and Load**. ETL ini diperlukan untuk menyentralisasi data dari berbagai sumber ke satu database.

## Extract

Untuk dapat mengambil data, terlebih dahulu memasukkan endpoint untuk meng-update data, yang dilakukan di update_data.py. Selanjutnya, update.py akan memanggil fungsi API yang diperlukan dari file api_call.py. Fungsi tersebut memerlukan user id token argumen true/false. Kemudian, fungsi tersebut akan memanggil fungsi third party. Dengan fungsi tersebut, barulah diperoleh ekstraksi data dalam format JSON.

## Transform 

Selanjutnya, dilakukan transformasi data secara batch (paralel). Pertama-tama, format data JSON akan ditransformasikan ke dalam dictionary (key value), di mana key sesuai dengan kolom tabel tujuan. Proses ini dilakukan dengan memanggil fungsi transform dari file transform.py yang tersedia di folder utils. Dalam proses transformasi, dilakukan splitting data, pengaturan penulisan waktu dan rentang waktu, dll. Untuk media comment, akan digunakan untuk proses sentimen analisis lebih lanjut oleh data scientist baru agar diperoleh data sentimen.


## Load

Terakhir, dilakukan pemindahan data yang telah ditransformasi ke destinasi baru, yaitu Schema Instagram dan Schema Toba_Cek_Insta.


