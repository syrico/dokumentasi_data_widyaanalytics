
# IG Comment
Merupakan komentar di IG Media.

```
GET /{ig-comment-id}?fields={fields}
```
Dapatkan field dan edges pada IG Comment.

## Limitasi
- Permintaan tidak dapat dilakukan pada komentar yang ditemukan melalui Mentions API kecuali jika permintaan dibuat oleh pemilik comment. Sebagai gantinya, gunakan simpul Mentioned Comment.
- Komentar pada media yang dibatasi usia tidak dikembalikan.
- Komentar yang dibuat oleh IG User yang telah dibatasi oleh pengguna aplikasi tidak akan dikembalikan kecuali IG User tersebut tidak dibatasi dan Comment tersebut disetujui.
- Komentar pada video langsung Media IG hanya dapat dibaca saat IG Media tempat komentar dibuat sedang disiarkan.

## Persyaratan

| Tipe          | Deskripsi                                                                                                                                                                                                            |
|---------------|------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Akses Token | User                                                                                                                                                                                                                   |
| Izin   | ``instagram_basic``<br />``pages_read_engagement`` <br />``pages_show_list``<br /><br /> Jika pengguna aplikasi diberi peran di Halaman melalui Business Manager, kita juga memerlukan salah satu dari: ``ads_management`` <br />``business_management`` <br /> | 

## Request Syntax
```
GET https://graph.facebook.com/{api-version}/{ig-comment-id}
    ?fields={fields}
    &access_token={access-token}
```

## Parameter Path

| Placeholder   | Value                  |
|---------------|------------------------|
| ``{api-version}`` | Versi API.           |
| ``{ig-comment-id}`` | Perlu. IG Comment ID. |

## Parameter String Kueri
| Key          | Placeholder    | Value                                                                                              |
|--------------|----------------|----------------------------------------------------------------------------------------------------|
| ``access_token`` | ``{access-token}`` | Required. Token akses pengguna dari pengguna aplikasi.                                                            |
| ``fields``       | ``{fields}``       | Daftar fields dari IG Comment yang dipisahkan koma yang ingin kita kembalikan untuk setiap IG Comment di himpunan hasil. |                

## Fields

| Nama Field | Deskripsi                                                                                                                                                                                                    |   |
|------------|----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|---|
| ``from``       | Objek yang berisi: <br />``id`` — IGSID pengguna Instagram yang membuat IG Comment. <br />``username`` — Nama pengguna dari pengguna Instagram yang membuat IG Comment.                                                       |   |
| ``hidden``     | Mengindikasi apakah komentar telah disembunyikan (``true``) atau tidak (``false``).                                                                                                                                                    |   |
| ``id``         | IG Comment ID.                                                                                                                                                                                                 |   |
| ``like_count`` | Jumlah suka di IG Comment.                                                                                                                                                                             |   |
| ``media``      | Objek yang berisi: <br /> ``id`` — ID dari IG Media tempat IG Comment dibuat. <br /> ``media_product_type`` — Permukaan IG Media yang dipublikasikan (yaitu tempat IG Media muncul) tempat IG Comment dibuat. |   |
| ``parent_id``  | ID dari parent IG Comment jika komentar ini dibuat di IG Comment lain (yaitu balasan untuk komentar lain).                                                                                                |   |
| ``replies``    | Daftar balasan (IG Comment) dibuat di IG Comment.                                                                                                                                                        |   |
| ``text``       | teks di IG Comment.                                                                                                                                                                                               |   |
| ``timestamp``  | Timestamp berformat ISO 8601 yang menunjukkan kapan IG Comment dibuat. Contoh: 2017-05-19T23:27:28+0000.                                                                                                        |   |
| ``user``       | ID dari IG User yang membuat IG Comment. Hanya dikembalikan jika pengguna aplikasi membuat IG Comment, jika tidak, nama pengguna akan dikembalikan.                                                                   |   |
| ``username``   | Username pengguna Instagram yang membuat IG Comment.                                                                                                                                                         |   |

## Edges

| Edge    | Deskripsi                                                                         |
|---------|-------------------------------------------------------------------------------------|
| ``replies`` | Dapatkan daftar komentar IG di IG Comment; Buat Komentar IG di IG Comment. |

## Request Syntax 3rd-party pyfacebook

```
def get_comments_by_media(self, media_id, fields=None, count=10, limit=10, include_reply=True, return_json=False)
```

Ambil data komentar untuk id media yang diberikan. Penjelasan parameter fungsi get_comments_by_media sebagai berikut, dengan tipe data List[Union[IgProComment, dict]].
| Parameter     | Tipe Data                              | Keterangan |
|---------------|----------------------------------------|------------|
| ``media_id``      | str                                    | Id media yang ingin kita dapatkan data komentarnya. |
| ``fields``        | Optional[Union[str, List, Tuple, Set]] | String id yang dipisahkan koma untuk fields data yang perlu diambil. Kita juga dapat meneruskan ini dengan list, tuple, atau set dari id. |
| ``count``         | Optional[int]                          | Jumlah komentar yang kita inginkan. Default adalah 10. Jika perlu mendapatkan semua, set ini dengan None. |
| ``limit``         | int                                    | Setiap permintaan mengambil hitungan komentar dari api. Untuk komentar sebaiknya tidak lebih dari 50. |
| ``include_reply`` | bool                                   | Set ke True akan menyertakan balasan ke komentar. Default adalah benar. |
| ``return_json``   | bool                                   | Set ke false akan mengembalikan list instance IgProComment. Atau mengembalikan data json. Default adalah false. |
