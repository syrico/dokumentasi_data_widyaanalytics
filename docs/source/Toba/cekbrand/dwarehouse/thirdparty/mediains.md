# IG Media Insights

Mewakili metrik interaksi sosial pada objek IG Media.

## Limitasi

- Insight data tidak tersedia untuk media apa pun dalam album IG Media.
- Metrik story media hanya tersedia selama 24 jam, meskipun story tersebut diarsipkan atau di-highlight. Untuk mendapatkan insight terbaru tentang sebuah story sebelum kedaluwarsa, siapkan Webhook untuk field ``Instagram`` dan subscribe ke field ``story_insights``.
- Metrik story media dengan nilai kurang dari 5 menampilkan kode kesalahan ``10`` dengan pesan ``(#10) Not enough viewers for the media to show insights.``
- Untuk story yang dibuat oleh user di Eropa dan Jepang, metrik ``replies`` kini return nilai ``0``.
- Untuk story, balasan yang dibuat oleh pengguna di Eropa dan Jepang tidak termasuk dalam penghitungan ``replies``.
- Jika insight data yang kita minta tidak ada atau saat ini tidak tersedia, API akan return kumpulan data kosong, bukan 0 untuk masing-masing metrik.
- Data yang digunakan untuk menghitung metrik dapat ditunda hingga 48 jam.

## Persyaratan

| Tipe          | Deskripsi                                                                                                                                                                                           |
|---------------|-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Akses Token | User.                                                                                                                                                                                                 |
| Izin   | ``instagram_basic`` <br />``instagram_manage_insights`` <br />``pages_read_engagement`` <br />``pages_show_list`` <br /><br /> Jika pengguna aplikasi diberi peran di Halaman melalui Business Manager, kita juga memerlukan salah satu dari yang berikut: <br /> ``ads_management`` <br />``business_management`` |

## Request Syntax

```http
GET https://graph.facebook.com/{api-version}/{ig-media-id}/insights
    ?metric={metric}
    &access_token={access-token}
```

## Parameter Path

 Placeholder   | Value                  |
|---------------|------------------------|
| ``{api-version}`` | Versi API.           |
| ``{ig-media-id}`` | Perlu. IG Media ID. |

## Parameter String Kueri

| Parameter                           | Value                                                        |
|-------------------------------------|--------------------------------------------------------------|
| ``{access-token}`` <br />Type: string         | Perlu. Akses toker dari User pengguna aplikasi.                      |
| ``{metric}`` <br />Type: Comma-separated list | Perlu. List yang diseparasi oleh metrik yang mau di-return. |

## Metrik

### Metrik Album

| Metrik                     | Deskripsi                                                                                 |
|----------------------------|---------------------------------------------------------------------------------------------|
| ``carousel_album_engagement``  | Total jumlah like dan Komentar IG pada album objek IG Media.                         |
| ``carousel_album_impressions`` | Total berapa kali objek IG Media album telah dilihat.                              |
| ``carousel_album_reach``       | Total jumlah akun Instagram unik yang telah melihat album objek IG Media.         |
| ``carousel_album_saved``       | Total jumlah akun Instagram unik yang telah menyimpan album objek IG Media.        |
| ``carousel_album_video_views`` | Total jumlah akun Instagram unik yang telah melihat video IG Media dalam album. |

### Metrik Foto dan Video

Metrik pada media dalam album tidak didukung. Sebagai gantinya, diambil metrik di album.
| Metrik      | Deskripsi                                                                                                                                 |
|-------------|---------------------------------------------------------------------------------------------------------------------------------------------|
| ``engagement``  | Jumlahan dari ``likes_count``, ``comment_count``, dan ``saved counts`` pada IG Media.                                                                        |
| ``impressions`` | Total banyaknya objek IG Media telah dilihat.                                                                                    |
| ``reach``       | Total akun  Instagram unik yang telah melihat objek IG Media.                                                               |
| ``saved``       | Total jumlah akun Instagram unik yang telah melihat objek IG Media.                                                              |
| ``video_views`` | Total berapa kali video IG Media telah dilihat. Untuk album IG Media, berapa kali semua video dalam album telah dilihat. |

### Metrik Reels

| Metrik             | Deskripsi                                                                                                                                                                                                   |
|--------------------|---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| ``comments``           | Jumlah komentar pada reel. Metrik dalam pengembangan.                                                                                                                                                        |
| ``likes``              | Jumlah likes di reel. Metrik dalam pengembangan.                                                                                                                                                           |
| ``plays``              | Jumlah berapa kali reels mulai diputar setelah tayangan dihitung. Ini didefinisikan sebagai sesi video dengan pemutaran 1 ms atau lebih dan tidak termasuk pemutaran ulang. Metrik dalam pengembangan. |
| ``reach``              | Jumlah akun unik yang telah melihat reel setidaknya sekali. Reach berbeda dengan impresi, yang dapat mencakup beberapa penayangan reel oleh akun yang sama. Metrik diperkirakan dan dalam pengembangan. |
| ``saved``              | Jumlah penyimpanan reel. Metrik dalam pengembangan.                                                                                                                                                           |
| ``shares``             | Jumlah share dari reel. Metrik dalam pengembangan.                                                                                                                                                         |
| ``total_interactions`` | Jumlah likes, simpan, komentar, dan share pada reel, dikurangi jumlah unlikes, tidak simpan, dan komentar yang dihapus. Metrik dalam pengembangan.                                                                  |

### Metrik story

| Metrik       | Deskripsi                                                                                                                                                                                                                                                                                                    |
|--------------|----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| ``exits``        | Total berapa kali seseorang keluar dari story objek IG Media.                                                                                                                                                                                                                                                |
| ``impressions``  | Total berapa kali story objek IG Media telah dilihat.                                                                                                                                                                                                                                                 |
| ``reach``        | Total jumlah akun Instagram unik yang telah melihat story objek IG Media.                                                                                                                                                                                                                            |
| ``replies``      | Total jumlah reply (Komentar IG) pada story objek IG Media. Nilai tidak termasuk reply yang dibuat oleh pengguna di beberapa wilayah. Wilayah ini meliputi: Eropa mulai 1 Desember 2020 dan Jepang mulai 14 April 2021. Jika story dibuat oleh pengguna di salah satu wilayah ini, akan mengembalikan nilai 0. |
| ``taps_forward`` | Total jumlah tap untuk melihat foto atau video selanjutnya dari objek IG Media ini.                                                                                                                                                                                                                                  |
| ``taps_back``    | Total jumlah tap untuk melihat foto atau video sebelumnya dari objek IG Media ini.                                                                                                                                                                                                                            |

## Request Syntax 3rd-party pyfacebook

```python
def get_media_insights(self, media_id, metrics, access_token=None, return_json=False)
```

Mengambil data media insights. Penjelasan parameter fungsi ``get_media_insights``    sebagai berikut, dengan tipe data List[Union[IgProInsight, dict]].
| Parameter    | Tipe Data                    | Keterangan                                                      |
|--------------|------------------------------|-----------------------------------------------------------------|
| ``media_id``     | str                          | ID media yang ingin kita dapatkan datanya.                    |
| ``metrics``      | Union[str, List, Tuple, Set] | String id yang dipisahkan koma untuk metrik yang perlu diambil. Kita juga dapat meneruskan ini dengan list, tuple, atau set dari id. <br />Catatan: Jenis media yang berbeda memiliki metrik yang berbeda. <br />Lihat selengkapnya: <https://developers.facebook.com/docs/instagram-api/reference/media/insights#insights-2> |
| ``access_token`` | str                          | Token akses pengguna target. Jika tidak akan menggunakan token akses default. |
| ``return_json``  | bool                         | Set ke false akan mengembalikan list instance IgProInsight. Atau kembalikan data json. Default adalah false.   |
