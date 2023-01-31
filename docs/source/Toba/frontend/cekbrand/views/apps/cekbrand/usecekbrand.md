# Cekbrand Modules

Cekbrand root views memiliki path seperti berikut:

```powershell
..\frontend\src\views\apps\cekbrand\useCekbrand.js
```

Pada Cekbrand modules  ini juga terdapat fungsi untuk melakukan pemanggilan API, seperti berikut:

- fetchUserAccounts() dipanggil pada component ini bertujuan untuk mendapatkan data account yang dimiliki oleh user dan ditampilkan dalam bentuk social media card.
- connectFacebook() fungsi ini bertujuan untuk mengaitkan/mengkonekan account facebook dengan aplikasi toba.ai .
- fetchUserFacebookAccounts() fungsi ini bertujuan untuk mendapatkan list id account instagram user yang terhubung dengan account facebook yang user miliki.
- fetchUserAccountUserData() fungsi ini bertujuan untuk mendapatkan list detail data account mengenai followers_count, followers_count_growth, follows_count, media_count, media_count_growth, berdasarkan range waktu(7, 28, 60, 90, dan pilih tanggal secara manual) yang dipilih oleh user.
- fetchUserAccountInstagram() fungsi ini bertujuan untuk mengkonekan account instagram yang dimiliki oleh user dengan aplikasi toba.ai .
- removeUserAccountInstagram() fungsi ini bertujuan untuk melepas koneksi antara account instagram user dengan aplikasi toba.ai .
- removeUserAccountFacebook() fungsi ini bertujuan untuk melepas koneksi antara account facebook user yang telah dikoneksikan dengan aplikasi toba.ai dengan aplikasi toba.ai itu sendiri.
- fetchUserAccountInsightsReach() fungsi ini bertujuan untuk mengetahui nilai reach dari setiap account instagram user yang di koneksikan dengan aplikasi toba.ai .
- fetchUserAccountInsightsImpressions() fungsi ini bertujuan untuk mengetahui nilai impressions dari setiap account instagram user yang dikoneksikan dengan aplikasi toba.ai .
- fetchUserAccountMediaEngagement() fungsi ini bertujuan untuk mengetahui nilai engagement dari setiap account instagram user yang dikoneksikan dengan aplikasi toba.ai .
- handleInvalidUserActiveAccountToken() fungsi ini untuk menghandle apabila user account active invalid_token dan akan diarahkan ke component cekbrandReAuthorization.vue
