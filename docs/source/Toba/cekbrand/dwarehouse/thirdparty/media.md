# IG Media

Mewakili album, foto, atau video Instagram (video yang diunggah, video live, video yang dibuat dengan aplikasi Instagram TV, reel, atau story Instagram).

Cekbrand menggunakan 3rd-party dari pyfacebook yang memfasilitasi pemanggilan dari masing-masing endpoint API Graph facebook.

## Limitasi

- Kolom yang menampilkan nilai aggregat tidak menyertakan data yang digerakkan oleh iklan. Misalnya, comments_count menghitung komentar pada sebuah foto, tetapi tidak menghitung komentar pada iklan yang berisi foto tersebut.
- Caption tidak menyertakan simbol @ kecuali pengguna aplikasi juga dapat melakukan tugas yang setara dengan Admin di aplikasi.
- Beberapa kolom tidak dapat digunakan pada foto di dalam album (anak).
- Media Instagram TV harus dibagikan ke Instagram pada saat publikasi (Post a Preview atau Share Preview to Feed diaktifkan) agar dapat diakses melalui API.
- Live video IG Media hanya dapat dibaca saat sedang disiarkan.

## Persyaratan

| Tipe          | Deskripsi                                                                                                                                                                                           |
|---------------|-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Akses Token | User.                                                                                                                                                                                                 |
| Izin   | ``instagram_basic`` <br /> ``pages_read_engagement`` <br /> ``pages_show_list`` <br /><br /> Jika pengguna aplikasi diberi peran di Halaman melalui Business Manager, kita juga memerlukan salah satu dari yang berikut: <br /> ``ads_management`` <br /> ``business_management`` |

## Request Syntax

```http
GET https://graph.facebook.com/{api-version}/{ig-media-id}
    ?fields={fields}
    &access_token={access-token}
```

## Parameter Path

| Placeholder   | Value                  |
|---------------|------------------------|
| ``{api-version}`` | Versi API.           |
| ``{ig-media-id}`` | Perlu. IG Media ID. |

## Parameter String Kueri

|      Key     |   Placeholder  |                       Value                       |
|:------------:|:--------------:|:-------------------------------------------------:|
| ``access_token`` | ``{access-token}`` | Perlu. Token akses pengguna dari pengguna aplikasi.           |
| ``fields``       | ``{fields}``       | List yang dipisahkan dengan tanda koma dari field yang ingin dihasilkan. |

## Fields

Public fields dan dapat di-read via ekspansi field.

| Field                     | Deskripsi                                                                                                                                                                                                                                                                                                                                                                                      |
|---------------------------|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| ``caption`` <br />Public            | Caption. Tidak termasuk anak album. Simbol @ dikecualikan, kecuali jika pengguna aplikasi dapat melakukan tugas yang setara dengan admin di Halaman Facebook yang terhubung ke akun Instagram yang digunakan untuk membuat caption.                                                                                                                                                                                           |
| ``comments_count`` <br />Public     | Jumlah komentar di media. Tidak termasuk komentar pada media album anak dan keterangan media. Termasuk reply pada komentar.                                                                                                                                                                                                                                                                    |
| ``id`` <br />Public                 | Media ID.                                                                                                                                                                                                                                                                                                                                                                                        |
| ``ig_id`` <br />Public              | Instagram media ID. Sebelumnya menggunakan dengan Legacy Instagram API, sekarang tidak digunakan lagi. Sebagai gantinya menggunakan id.                                                                                                                                                                                                                                                                                                              |
| ``is_comment_enabled``        | Menunjukkan jika komentar diaktifkan atau dinonaktifkan. Tidak termasuk anak album.                                                                                                                                                                                                                                                                                                                          |
| ``is_shared_to_feed`` <br />Public  | Reels saja. Jika benar, berarti reel dapat muncul di tab feed dan reels. Jika salah, berarti gulungan hanya dapat muncul di tab reel. Perhatikan bahwa tidak ada nilai yang menunjukkan apakah reel benar-benar muncul di tab reels, karena reel mungkin tidak memenuhi persyaratan kelayakan atau telah dipilih oleh algoritme kami. Lihat spesifikasi reel untuk kriteria kelayakan.                   |
| ``like_count``                | Jumlah likes di media, termasuk reply di komentar. Tidak termasuk likes di media anak album dan likes di pos yang dipromosikan dibuat dari media. <br /><br /> Jika ditanyakan secara tidak langsung melalui titik akhir lain atau ekspansi fields: <br />-v10.0 dan calls yang lebih lama: Nilainya adalah 0 jika pemilik media menyembunyikan jumlah like. <br />-v11.0+ calls: Field like_count dihilangkan jika pemilik media memiliki jumlah like yang tersembunyi. |
| ``media_product_type`` <br />Public | Lokasi media dipublikasi. Dapat berupa iklan, feed, story, atau reels.                                                                                                                                                                                                                                                                                                                           |
| ``media_type`` <br />Public         | Tipe media. Dapat berupa album carousel, gambar, or video.                                                                                                                                                                                                                                                                                                                                              |
| ``media_url`` <br />Public          | URL untuk media. Field dari media_url field URL dihilangkan dari respons jika media berisi materi berhak cipta atau telah ditandai karena pelanggaran hak cipta. Contoh materi berhak cipta dapat mencakup audio pada reels.                                                                                                                                                                     |
| ``owner`` <br />Public              | ID pengguna Instagram yang membuat media. Hanya di-return jika pengguna aplikasi yang membuat kueri juga membuat media; jika tidak, field dari username yang di-return sebagai gantinya.                                                                                                                                                                                                                                   |
| ``permalink`` <br />Public          | URL permanen ke media.                                                                                                                                                                                                                                                                                                                                                                      |
| ``shortcode`` <br />Public          | Shortcode ke media.                                                                                                                                                                                                                                                                                                                                                                          |
| ``thumbnail_url`` <br />Public      | URL dari thumbnail media. Hanya tersedia di media video.                                                                                                                                                                                                                                                                                                                                              |
| ``timestamp`` <br />Public          | Tanggal pembuatan berformat ISO 8601 dalam UTC (standarnya adalah UTC ±00:00).                                                                                                                                                                                                                                                                                                                                 |
| ``username`` <br />Public           | Username pengguna yang membuat media.                                                                                                                                                                                                                                                                                                                                                          |
| ``video_title`` <br />Public        | Tidak digunakan lagi. Dihilangkan dari respons.                                                                                                                                                                                                                                                                                                                                                               |

## Edges

Public edges dapat dikembalikan melalui ekspansi field.

| Edge             | Description                                                       |
|------------------|-------------------------------------------------------------------|
| ``children`` <br />Public. | Merepresentasikan kumpulan objek IG Media di album IG Media. |
| ``comments``         | Merepresentasikan kumpulan Komentar IG pada objek Media IG.     |
| ``insights``         | Merepresentasikan metrik interaksi sosial pada objek IG Media.      |

## Request Syntax 3rd-party pyfacebook

```python
def get_user_medias(self,
  user_id, fields=None, since_time=None, until_time=None,  count=10, limit=10, return_json=False)
```

Mengambil data media pengguna ig berdasarkan user_id. Penjelasan parameter fungsi ``get_user_medias`` sebagai berikut.
|     Parameter      |     Tipe Data                                   |     Keterangan                                                                                                                      |
|--------------------|-------------------------------------------------|-------------------------------------------------------------------------------------------------------------------------------------|
|     ``user_id``        |     str                                         |     Id untuk   pengguna instagram business yang ingin kita dapatkan datanya.                                                        |
|     ``fields``         |     Optional[Union[str,   List, Tuple, Set]]    |     String id   yang dipisahkan koma untuk field data yang kita inginkan. Kita juga dapat pass   ini dengan list id, tuple, set.    |
|     ``since_time``     |     Optional[str]                               |     Batas bawah rentang waktu ke waktu publikasi media. Formatnya adalah %Y-%m-%d.                                                |
|     ``until_time``     |     Optional[str]                               |     Batas atas rentang waktu ke waktu publikasi media. Formatnya adalah %Y-%m-%d.                                                 |
|     ``count``          |     Optional[str]                               |     Jumlah kita ingin mendapatkan media. Jika perlu mendapatkan semuanya, set ini dengan None.                                    |
|     ``limit``          |     int                                         |     Setiap   permintaan mengambil jumlah media dari api. Untuk media sebaiknya tidak lebih   dari 500.                              |
|     ``return_json``    |     bool                                        |     Set ke False   akan mengembalikan instance dari IgProUser.                                                                      |
