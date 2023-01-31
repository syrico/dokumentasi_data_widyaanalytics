
# IG Comment Replies

Merupakan kumpulan Komentar IG pada IG Comment untuk mendapatkan semua balasan pada Komentar.

```http
GET /{ig-comment-id}/replies
```

Mengembalikan daftar komentar IG pada IG Comment.

## Limitasi

Kita tidak bisa mendapatkan balasan untuk komentar yang telah dihapus.

## Persyaratan

Token akses dari User yang membuat komentar, dengan izin berikut:

- ``instagram_basic``
- ``pages_show_list``
- ``page_read_engagement``

Jika token berasal dari User yang peran halamannya diberikan melalui Business Manager, salah satu izin berikut juga diperlukan:

- ``ads_management``
- ``pages_read_engagement``
- ``business_management``

## Request Syntax 3rd-party pyfacebook

```python
def get_replies_info(self, reply_ids, fields=None, return_json=False)
```

Mengambil info reply oleh reply id. Penjelasan parameter fungsi ``get_replies_info`` sebagai berikut, dengan tipe data dict.

| Parameter   | Tipe Data                    | Keterangan                                                      |
|-------------|------------------------------|-----------------------------------------------------------------|
| ``user_id``     | Union[str, List, Tuple, Set] | Id untuk instagram business user yang ingin kita dapatkan datanya.                    |
| ``fields``      | Optional[Union[str, List, Tuple, Set]] | String id yang dipisahkan koma untuk field data yang perlu diambil. Kita juga dapat meneruskan ini dengan list, tuple, atau set dari id. |
| ``return_json`` | bool                         | Set ke false akan mengembalikan list instance IgProComment. Atau mengembalikan data json. Default adalah false. |
