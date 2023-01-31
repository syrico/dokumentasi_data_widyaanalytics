# IG User

Mewakili Akun Bisnis Instagram atau Akun Kreator Instagram.

```http
GET /{ig-user-id}
```

Mendapatkan fields dan edges pada Instagram Business atau Akun Kreator.

## Persyaratan

| Tipe           | Deskripsi                                                                                                                                                                                                                                                                                                                                                        |
|----------------|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Aksen Token  | User.                                                                                                                                                                                                                                                                                                                                                              |
| Peran Bisnis | Jika kita meminta field ``shopping_product_tag_eligibility`` untuk tagging produk, pengguna aplikasi harus memiliki peran admin di Business Manager yang memiliki Instagram Shop dari Pengguna IG.                                                                                                                                                                        |
| Instagram Shop | Jika kita meminta field ``shopping_product_tag_eligibility`` untuk tagging produk, Pengguna IG harus memiliki Instagram Shop yang disetujui dengan katalog produk berisi produk.                                                                                                                                                                                 |
| Izin    | ``instagram_basic`` \ ``pages_read_engagement`` <br /> ``pages_show_list`` <br /> Jika pengguna aplikasi diberi peran di Halaman melalui Business Manager, kita juga memerlukan salah satu dari yang berikut: <br />``ads_management`` <br /> ``business_management`` <br /> Jika kita meminta field ``shopping_product_tag_eligibility`` untuk pemberian tag produk, kita juga memerlukan: <br /> ``catalog_management`` <br /> ``instagram_shopping_tag_products`` <br /> |

## Request Syntax

```http
GET https://graph.facebook.com/{api-version}/{ig-user-id}
    ?fields={fields}
    &access_token={access-token}
```

## Parameter Path

| Placeholder   | Value                  |
|---------------|------------------------|
| ``{api-version}`` | Versi API.           |
| ``{ig-used-id}`` | Perlu. IG User ID. |

## Parameter String Kueri

|      Key     |   Placeholder  |                       Value                       |
|:------------:|:--------------:|:-------------------------------------------------:|
| ``access_token`` | ``{access-token}`` | Perlu. Token akses pengguna dari pengguna aplikasi.           |
| ``fields``       | ``{fields}``       | List yang dipisahkan dengan tanda koma dari field IG User yang ingin dihasilkan oleh setiap IG User pada himpunan hasil.|

## Fields

Field publik dapat dikembalikan oleh edge menggunakan ekspansi field.

| Field Nama                       | Deskripsi                                                                                                                      |
|----------------------------------|-----------------------------------------------------------------------------------------------------------------------------------|
| ``biography`` <br />Public                 | Teks dari profil bio.                                                                                                                 |
| ``id`` <br /> Public                        |User ID dalam cakupan aplikasi.                                                                                                               |
| ``ig_id``                            | User ID Instagram. Digunakan dengan Legacy Instagram API, sekarang sudah tidak digunakan lagi. Menggunakan id sebagai gantinya.                                                |
| ``followers_count`` <br /> Public           | Total jumlah Instagram user yang mengikuti user.                                                                  |
| ``follows_count``                    | Total jumlah pengguna Instagram yang diikuti user.                                                                            |
| ``media_count`` <br /> Public               | Total jumlah Media IG yang dipublikasikan oleh user.                                                                                  |
| ``name``                             | Nama profil.                                                                                                                   |
| ``profile_picture_url``              | URL gambar profil.                                                                                                              |
| ``shopping_product_tag_eligibility`` | Mengembalikan nilai true jika pengguna aplikasi telah menyiapkan Instagram Shop dan karenanya memenuhi syarat untuk pemberian tag produk, jika tidak, mengembalikan nilai false. |
| ``username`` <br /> Public                  | Username dari profil.                                                                                                                 |
| ``website`` <br /> Public                   | URL dari laman profil.                                                                                                              |

## Edges

| Edge                       | Deskripsi                                                                                                                   |
|----------------------------|-------------------------------------------------------------------------------------------------------------------------------|
| ``business_discovery``         | Mendapatkan data tentang User IG Instagram Business atau Instagram Creator IG.                                                        |
| ``content_publishing_limit``   | Merepresentasikan penggunaan penerbitan konten User IG saat ini.                                                                     |
| ``insights``                   | Mewakili metrik interaksi sosial pada User IG.                                                                          |
| ``live_media``                 | Merepresentasi kumpulan live video IG Media pada IG User.                                                                 |
| ``media``                      | Merepresentasi kumpulan IG Media pada IG User.                                                                           |
| ``media_publish``              | Mempublikasi IG Container di User ID Instagram Business.                                                                     |
| ``mentions``                   | Create an IG Comment on an IG Comment or captioned IG Media that an IG User has been @mentioned in by another Instagram user. |
| ``mentioned_comment``          | Get data on an IG Comment in which an IG User has been @mentioned by another Instagram user.                                  |
| ``mentioned_media``            | Get data on an IG Media in which an IG User has been @mentioned in a caption by another Instagram user.                       |
| ``recently_searched_hashtags`` | Get IG Hashtags that an IG User has searched for within the last 7 days.                                                      |
| ``stories``                    | Represents a collection of story IG Media objects on an IG User.                                                              |
| ``tags``                       | Represents a collection of IG Media in which an IG User has been tagged by another Instagram user.                            |

## Request Syntax 3rd-party pyfacebook

```python
def get_user_info(self, user_id, fields=None, return_json=False)
```

Mengambil data pengguna ig dari user id. Penjelasan parameter fungsi ``get_user_info`` sebagai berikut, dengan tipe data Optional[IgProUser, dict].
| Parameter   | Tipe Data                    | Keterangan                                                      |
|-------------|------------------------------|-----------------------------------------------------------------|
| ``user_id``     | str                          | Id untuk instagram business user yang ingin kita dapatkan datanya.                    |
| ``fields``      | Optional[Union[str, List, Tuple, Set]] | String id yang dipisahkan koma untuk metrik yang perlu diambil. Kita juga dapat meneruskan ini dengan list, tuple, atau set dari id. |
| ``return_json`` | bool                         | Set ke false akan mengembalikan list instance IgProUser.    |
