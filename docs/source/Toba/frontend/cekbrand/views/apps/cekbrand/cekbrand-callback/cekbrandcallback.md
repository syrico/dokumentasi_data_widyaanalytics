# Cekbrand Callback Views

Cekbrand Callback views memiliki path seperti berikut:

```powershell
..\frontend\src\views\apps\cekbrand\cekbrand-callback\CekbrandCallback.vue
```

Terdapat function pada Cekbrand Callback views dengan tujuan, seperti berikut:

- fetchUserFacebookAccounts() function ini bertujuan untuk mengambil, menampilkan list account facebook dan data setiap account facebook user yang sudah terhubung dengan aplikasi toba.ai .
- fetchAccounts() funtion ini bertujuan untuk menampilkan list account instagram yang terikat oleh account facebook user dan account facebook user tersebut telah dikoneksikan dengan aplikasi toba.ai .
- disconnectFb() function ini bertujuan untuk melepaskan koneksi antara account facebook yang telah dikoneksikan dengan aplikasi toba.ai .
- disconnectIg() function ini bertujuan untuk mengkoneksikan antara account instagram user dengan aplikasi toba.ai .
- disconnect() function ini bertujuan untuk melepaskan koneksi account instagram user dengan aplikasi toba.ai atau account facebook dengan aplikasi toba.ai, pada function ini memiliki parameter yang digunakan untuk menjadikan opsi melepaskan koneksi account instagram user dengan aplikasi toba.ai atau account facebook dengan aplikasi toba.ai .
- finishConnectIg() function ini di eksekusi setelah proses koneksikan account ig user telah berhasil dan akan dilakukan refresh variable selectedAccounts dan pemanggilan function fetchAccounts().

Terdapat module yang dipakai pada Cekbrand root views ini :

- useCekbrand.js pada file ini merupakan kumpulan dari berbagai fungsi yang dapat dipakai secara berulang.
