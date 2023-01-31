# Cekbrand Roots Views

Cekbrand root views memiliki path seperti berikut:

```powershell
..\frontend\src\views\apps\cekbrand\Cekbrand.vue
```

Didalam Cekbrand root views ini terdapat beberapa component penyusun, berikut component penyusun yang ada pada Cekbrand root views:

- CekbrandSplashScreen.vue
- CekbrandHeader.vue
- CekbrandFooter.vue

Pada Cekbrand root views  ini juga terdapat fungsi untuk melakukan pemanggilan API, seperti berikut:

- fetchUserAccounts() dipanggil pada component ini bertujuan untuk mendapatkan data account yang dimiliki oleh user dan ditampilkan dalam bentuk social media card.
- connectFacebook() dipanggil pada component ini bertujuan untuk mengaitkan/mengkonekan account facebook dengan aplikasi toba.

Terdapat module yang dipakai pada Cekbrand root views ini :

- useCekbrand.js pada file ini merupakan kumpulan dari berbagai fungsi yang dapat dipakai secara berulang.
