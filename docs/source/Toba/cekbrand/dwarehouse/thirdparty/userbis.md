
# IG User Business Discovery

Memungkinkan kita mendapatkan data tentang Pengguna Instagram Business atau Creator IG lainnya.

```http
GET /{ig-user-id}?fields=business_discovery.username({username})
```

Mengembalikan data tentang Pengguna Instagram Business atau Creator IG lainnya. Lakukan permintaan ini pada Pengguna Instagram Business atau Creator IG yang membuat kueri, dan identifikasi bisnis yang ditargetkan dengan parameter ``username``.

## Limitasi

Data tentang Instagram Business IG User yang dikenai pembatasan usia tidak akan dikembalikan.

## Parameter String Kueri

``{username}`` (required) — Nama pengguna Instagram Business atau Creator IG User yang ingin kita dapatkan datanya.

## Izin

Token akses Facebook User dengan izin berikut:

- ``instagram_basic``
- ``instagram_manage_insights``
- ``pages_read_engagement`` atau ``pages_show_list``
<br />
Jika token berasal dari User yang peran Page diberikan melalui Business Manager, salah satu izin berikut juga diperlukan:
- ads_management
- pages_read_engagement
- business_management

## Ekspansi Field

Kita dapat menggunakan ekspansi field untuk mendapatkan field publik pada IG Useryang ditargetkan. Lihat referensi IG User untuk daftar kolom publik.

## Request Syntax 3rd-party pyfacebook

```python
def discovery_user(self, username, fields=None, return_json=False)
```

Mengambil info dasar pengguna bisnis lain berdasarkan username. Penjelasan parameter fungsi ``discovery_user`` sebagai berikut, dengan tipe data Union[IgProUser, dict].
| Parameter   | Tipe Data                    | Keterangan                                                      |
|-------------|------------------------------|-----------------------------------------------------------------|
| ``username``     | str                          | Username untuk kita ingin mengambil data.                    |
| ``fields``      | Union[str, List, Tuple, Set] | String id yang dipisahkan koma untuk fields data yang perlu diambil. Kita juga dapat meneruskan ini dengan list, tuple, atau set dari id. |
| ``return_json`` | bool                         | Set ke false akan mengembalikan list instance IgProUser. Atau mengembalikan data json. Default adalah false. |
