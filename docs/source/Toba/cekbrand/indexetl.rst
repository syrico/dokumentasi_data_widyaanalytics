ETL
+++++++

ETL adalah singkatan dari  **Extract, Transform, and Load**. ETL ini diperlukan untuk menyentralisasi data dari berbagai sumber ke satu database.

Extract
============
Terlebih dahulu diambil data dari instagram yang masih dalam format JSON user, 
media user, dan competitor. Untuk dapat mengambil data tersebut, 
dimasukkan endpoint dari setiap datanya. Setelah itu, digunakan api call
untuk mengakses fungsi di instagram. Dengan demikian, baru dapat diperoleh 
data JSON dari instagram.

Transform 
===============

Selanjutnya, dilakukan transformasi data.
Secara batch (paralel) 
Pertama-tama, format data JSON akan ditransformasikan ke dalam dictionary (key value), di mana key sesuai dengan kolom tabel tujuan. Caranya adalah dengan melakukan import berikut ini.
```
from .utils import transform
```

 antara lain:
* Cleaning data
* Standardisasi data
* Duplikasi data
* Verifikasi data
* Kombinasi data
* Sorting data


Load
=========
Terakhir, dilakukan pemindahan data yang telah ditransformasi ke destinasi baru, yaitu

.. toctree::
   :maxdepth: 6
   
   
   etl/api
   etl/update


