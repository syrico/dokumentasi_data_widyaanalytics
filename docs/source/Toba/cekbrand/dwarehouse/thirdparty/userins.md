
# IG User Insights

Merepresentasi metrik interaksi sosial pada IG User.

```http
GET /{ig-user-id}/insights
```

Mengembalikan insights tentang IG User.

## Limitasi

- Metrik ``follower_count``, ``online_followers``, dan semua ``audience_\``* tidak tersedia di IG Users dengan followers kurang dari 100.
- Data insights untuk metrik ``online_followers`` hanya tersedia selama 30 hari terakhir.
- Jika data insights yang kita minta tidak ada atau saat ini tidak tersedia, API akan mengembalikan kumpulan data kosong, bukan 0 untuk masing-masing metrik.
- Metrik demografis hanya menampilkan 45 artis dengan performa teratas (misalnya untuk ``audience_city``, hingga 45 kota dengan jumlah pengikut tertinggi dapat ditampilkan).
- Hanya viewers yang data demografisnya kami miliki yang digunakan dalam penghitungan metrik demografis.
- Menjumlahkan nilai metrik demografi dapat menghasilkan nilai yang kurang dari jumlah pengikut (lihat poin-poin sebelumnya).
- Metrik ``audience_\``* tidak mendukung parameter range ``since`` dan ``until``.
- Data yang digunakan untuk menghitung metrik mungkin tertunda hingga 48 jam.

## Persyaratan

| Tipe          | Deskripsi                                                                                                                                                                                                            |
|---------------|------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Akses Token | User                                                                                                                                                                                                                   |
| Izin   | ``instagram_basic`` <br /> ``instagram_manage_insights`` <br /> ``pages_read_engagement`` <br /> ``pages_show_list`` <br /><br /> Jika pengguna aplikasi diberi peran di Halaman melalui Business Manager, kita juga memerlukan salah satu dari: ``ads_management`` <br /> ``business_management`` <br /> |

## Request Syntax

```http
GET https://graph.facebook.com/{api-version}/{ig-user-id}/insights
    ?metric={metric}
    &period={period}
    &since={since}
    &until={until}
    &access_token={access-token}
```

## Parameter Path

| Placeholder   | Value                  |
|---------------|------------------------|
| ``{api-version}`` | Versi API.           |
| ``{ig-user-id}`` | Perlu. IG User ID. |

## Parameter String Kueri

| Parameter                              | Value                                                                                                                                                                                                                                                                                              |
|----------------------------------------|----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| ``{access-token}``<br /> Required<br /> String         | Token Akses Pengguna dari pengguna aplikasi.                                                                                                                                                                                                                                                                  |
| ``{metric}``<br /> Required<br /> Comma-separated list | Daftar Metrik yang dipisahkan koma yang ingin kita kembalikan. Jika meminta beberapa metrik, semuanya harus memiliki Periode kompatibel yang sama.                                                                                                                                                   |
| ``{period}``<br /> Required<br /> String               | Periode yang kompatibel dengan metrik yang kita minta.                                                                                                                                                                                                                                   |
| ``{since}``<br /> Unix timestamp                 | Digunakan bersamaan dengan ``{until}`` untuk mendefinisikan Range. Jika kita menghilangkan ``since`` dan ``until``, API default ke range 2 hari: kemarin hingga hari ini. Catatan: Kursor paginasi (sebelum dan sesudahnya) mengambil window waktu berikutnya dari hasil, bukan kelompok hasil berikutnya dalam window waktu saat ini. |
| ``{until}``<br /> Unix timestamp                 | Digunakan bersamaan dengan ``{since}`` untuk menentukan Range. Jika kita menghilangkan ``since`` dan ``until``, API default ke range 2 hari: kemarin hingga hari ini. Catatan: Kursor paginasi (previous dan ``next``) mengambil window waktu berikutnya dari hasil, bukan kelompok hasil berikutnya dalam window waktu saat ini. |

## Metrik dan Periode

Metrik yang mendukung periode ``lifetime`` akan memiliki hasil yang dikembalikan dalam susunan periode 24 jam, dengan periode yang berakhir pada UTC−07:00. metrik ``audience_\``* tidak mendukung parameter range ``since`` dan ``until``.

| Metrik                | Periode Kompatibel  | Deskripsi                                                                                                                                                                                                                                                                                                                          |
|-----------------------|--------------------|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| audience_city         | lifetime           | Kota pengikut yang data demografisnya kita miliki. <br /><br /> - Tidak termasuk data hari ini. <br /> - Tidak tersedia di IG User dengan pengikut kurang dari 100. <br /> - Hanya 45 kota teratas dengan nilai tertinggi yang dikembalikan. <br /> - Tidak mendukung parameter ``since`` dan ``until``. <br /> - Respons tidak menyertakan properti JSON ``end_time``.                             |
| audience_country      | lifetime           | Negara pengikut yang data demografisnya kita miliki. <br /><br /> - Tidak termasuk data hari ini.<br /> - Tidak tersedia di IG User dengan pengikut kurang dari 100.<br /> - Hanya 45 negara teratas dengan nilai tertinggi yang dikembalikan.<br /> - Tidak mendukung parameter ``since`` dan ``until``.<br /> - Respons tidak menyertakan properti JSON ``end_time``.                       |
| audience_gender_age   | lifetime           | Distribusi gender dan usia pengikut yang data demografisnya kami miliki. Nilai yang mungkin: ``M`` (laki-laki), ``F`` (perempuan), ``U`` (tidak diketahui).<br /><br /> - Tidak termasuk data hari ini.<br /> - Tidak tersedia di IG User dengan pengikut kurang dari 100.<br /> - Tidak mendukung parameter ``since`` dan ``until``.<br /> - Respons tidak menyertakan properti JSON ``end_time``. |
| audience_locale       | lifetime           | Lokal menurut kode negara pengikut yang data demografisnya kita miliki.<br /><br /> - Tidak termasuk data hari ini.<br /> - Tidak tersedia di IG User dengan pengikut kurang dari 100. <br /> - Hanya 45 lokal teratas dengan nilai tertinggi yang dikembalikan. <br /> - Tidak mendukung parameter ``since`` dan ``until``. <br /> - Respons tidak menyertakan properti JSON ``end_time``.          |
| email_contacts        | day                | Total jumlah ketukan pada tautan email di profil IG User.                                                                                                                                                                                                                                                                     |
| follower_count        | day                | Total jumlah pengikut baru setiap hari dalam range yang ditentukan. Mengembalikan data maksimal 30 hari. Tidak tersedia di Pengguna IG dengan pengikut kurang dari 100.                                                                                                                                                              |
| get_directions_clicks | day                | Total jumlah ketukan pada tautan petunjuk arah di profil IG User.                                                                                                                                                                                                                                                                |
| impressions           | day, week, days_28 | Total berapa kali IG Media dari IG User telah dilihat. Mencakup aktivitas iklan yang dihasilkan melalui API, antarmuka iklan Facebook, dan fitur Promote. Tidak termasuk view dari profil.                                                                                                                                     |
| online_followers      | lifetime           |  Total jumlah pengikut IG User yang online selama range yang ditentukan. Tidak tersedia di IG User dengan pengikut kurang dari 100.                                                                                                                                                                                       |
| phone_call_clicks     | day                | Total jumlah ketukan pada tautan panggilan di profil IG User.                                                                                                                                                                                                                                                                      |
| profile_views         | day                |  Total jumlah pengguna yang telah melihat profil IG User dalam periode yang ditentukan.                                                                                                                                                                                                                                             |
| reach                 | day, week, days_28 | Total jumlah pengguna unik yang telah melihat setidaknya satu IG Media dari IG User. Tampilan berulang dan tampilan di berbagai IG Media yang dimiliki oleh IG User oleh pengguna yang sama hanya dihitung sebagai satu tampilan. Mencakup aktivitas iklan yang dihasilkan melalui API, antarmuka iklan Facebook, dan fitur Promote.                    |
| text_message_clicks   | day                |  Total jumlah ketukan pada tautan pesan teks di profil IG User.                                                                                                                                                                                                                                                              |
| website_clicks        | day                |  Total jumlah ketukan pada tautan situs web di profil IG User.                                                                                                                                                                                                                                                                   |

## Range

Edge ini mendukung paginasi berbasis waktu, sehingga kita dapat menyertakan parameter ``since`` dan ``until`` dengan Unix timestamps untuk menentukan range. Misalnya, untuk mendapatkan impression selama 28 hari — setiap hari selama 10 hari terakhir — kita dapat membuat Unix timestamps untuk 10 hari yang lalu dan hari ini, assign ke parameter ``since`` dan ``until``, dan menyertakannya dalam permintaan kita: <br />
``metric=impressions&period=days_28&since=1501545600&until=1502493720``
<br />Parameter ``since`` dan ``until`` bersifat inklusif, sehingga jika range kita menyertakan hari yang belum berakhir (misalnya hari ini), kueri berikutnya sepanjang hari dapat mengembalikan nilai yang meningkat. Jika kita tidak menyertakan parameter ``since`` dan ``until``, API akan default ke range 2 hari: kemarin sampai hari ini.

## Request Syntax 3rd-party pyfacebook

```python
def get_user_insights(self, user_id, period, metrics, since=None, until=None, access_token=None, return_json=False)
```

Mengambil user insights data dari akun instagram business. Penjelasan parameter fungsi ``get_user_insights`` sebagai berikut, dengan tipe data List[Union[IgProInsight, dict]].
| Parameter    | Tipe Data                    | Keterangan                                                         |
|--------------|------------------------------|--------------------------------------------------------------------|
| ``user_id``      | str    | Id untuk instagram business user yang ingin kita dapatkan datanya.     |
| ``period``       | str                          | Periode untuk data agregasi. Parameter yang diterima: lifetime, day, dan days_28.                                    |
| ``metrics``      | Union[str, List, Tuple, Set] | String id yang dipisahkan koma untuk metrik yang perlu diambil. Kita juga dapat meneruskan ini dengan list, tuple, atau set dari id. <br/>Catatan: Beberapa metrik tidak sesuai dengan periode.  <br/>Lihat selengkapnya: <https://developers.facebook.com/docs/instagram-api/reference/user/insights#metrics-periods|>
| ``since``        | Optional[int]                | Batas bawah rentang waktu untuk mengambil data. Perlu Unix timestamps. |
| ``until``        | Optional[int]                | Batas atas rentang waktu untuk mengambil data. Perlu Unix timestamps. Rentang waktu tidak lebih dari 30 hari (2592000 detik). |
| ``access_token`` | str                          | Token akses pengguna target. Jika tidak akan menggunakan token akses default.    |
| ``return_json``  | bool                         | Set ke false akan mengembalikan list instance IgProInsight.       |
