# Update

Update data dijalankan di main.py, dengan parameter yang digunakan adalah sebagai berikut.

| Parameter   | Tipe Data | Keterangan |
|-------------|-----------|------------|
| db_state    | str       | Penggunaan alamat IP address ketika staging (dev, test, prod). |
| airflow     | boolean   | Penggunaan alamat IP crawler internal (true) atau eksternal (false). |
| retry_count | int       | Batas berapa kali mengulang ketika request ke facebook timeout atau gagal. |
| range_data  | int       |            |

Untuk menjalankan main.py, terlebih dahulu dilakukan import berikut ini.

```
from cekbrand import update_data as ud
```

Update data akan dilakukan secara paralel, dengan cara update dan endpoint yang digunakan dijelaskan sebagai berikut.

## User
```
user = ud.UpdateDataUser(db_state='dev', airflow=False, retry_count=2, range_data=7)
user.update(end_point = '...')
```
| end_point           | Keterangan                                                                        |
|---------------------|-----------------------------------------------------------------------------------|
| info_static         |  Berisi tentang informasi yang statis atau jarang berubah, seperti id, usename, name, dll. |
| info_dynamic        | Berisi tentang informasi yang dinamis, seperti followers_count, media_count_dll. |
| audience_country    | Berisi   tentang data insight sebaran negara follower suatu user.                 |
| audience_city       | Berisi tentang data insight kota & provinsi dari follower suatu user.             |
| audience_gender_age | Berisi tentang data insight sebaran ISO Language Code follower   dari suatu user. |
| audience_locale     | Berisi tentang data insight sebaran ISO Language Code follower   dari suatu user. |
| online_followers    | Berisi   tentang data insight sebaran jam online follower dari suatu user.        |
| reach               | Berisi tentang data insight nilai reach dari suatu user.                          |
| impressions         | Berisi tentang data insight impression follower dari suatu user.                  |
| media               | Berisi tentang data media (foto/video) setiap user.                               |

## Competitor
```
comp = ud.UpdateDataCompetitor(db_state='dev', airflow=False, retry_count=2)
comp.update(end_point = '...')
```
| end_point    | Keterangan                                          |
|--------------|-----------------------------------------------------|
| info_static  | Berisi tentang informasi yang statis atau jarang berubah, seperti id, usename, name, dll. |
| info_dynamic | Berisi tentang informasi yang dinamis, seperti followers_count, media_count_dll. |
| media        | Berisi tentang data media (foto/video) setiap user. |

## Media
```
media = ud.UpdateDataMedia(db_state='dev', airflow=False, retry_count=2)
media.update(end_point = '...')
```

| end_point      | Keterangan                                                                                                        |
|----------------|-------------------------------------------------------------------------------------------------------------------|
| media_insights | Berisi   tentang data insight seperti engagement, impressions, reach, dan jumlah saved   pada media (foto/video). |
| media_comments | Berisi   tentang data komentar pada media (foto/video) setiap user.                                               |

## First Fetch
```
firstfetch = ud.single_fetch_update(db_state='dev', airflow=False, retry_count=2)
firstfetch.update(end_point = '...', user_id=str('17841408671998486'))
```
Parameter ``user_id`` merupakan nama id dari user yang akan dilakukan firstfetch, contoh seperti di atas, yaitu 17841408671998486. 

| end_point          | Keterangan                                                             |
|--------------------|------------------------------------------------------------------------|
| media_like_comment | Berisi   tentang data history jumlah like dan komen media setiap user. |
| media_comments     | Berisi   tentang data komentar pada media (foto/video) setiap user.    |
