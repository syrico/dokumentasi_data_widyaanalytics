# Toba

## CekBrand 

### System Database

#### Schema Instagram
Berisi tentang data yang diambil dari instagram seperti data user, data media, dan  data-data insight dari API instagram.

![ER Diagram Instagram](image/instagram.png)

##### **user**
Berisi tentang data user yang diambil dari instagram.

| Nama Kolom          | Tipe        | Tipe Data | Isi                                                                                                 | Catatan |
|---------------------|-------------|-----------|-----------------------------------------------------------------------------------------------------|---------|
| id                  | Primary Key | varchar   | Nomor ID User                                                                                       |         |
| username            | -           | varchar   | Username instagram                                                                                  |         |
| name                | -           | varchar   | Display name user                                                                                   |         |
| biography           | -           | varchar   | Biography user                                                                                      |         |
| profile_picture_url | -           | varchar   | Alamat Url Profil Picture                                                                           |         |
| website             | -           | varchar   | Alamat website user                                                                                 |         |
| social_account_id   | Foreign Key | int       | Id Facebook fans page                                                                               |         |
| updated_timestamp   | -           | timestamp | Timestamp kapan data di update                                                                      |         |
| has_problems        | -           | bool      | Keterangan apakah user bermasalah                                                                   |         |
| is_userid_valid     | -           | bool      | Keterangan apakah user id tersebut valid, ditandai dengan bisa/tidaknya akun tersebut mereturn data |         |

##### **user_data**
Berisi tentang data user dengan atribut sosial media di instagram seperti jumlah follower, jumlah media (foto/video).

| Nama Kolom             | Tipe        | Tipe Data | Isi                                                                                                 | Catatan |
|------------------------|-------------|-----------|-----------------------------------------------------------------------------------------------------|---------|
| id                     | Primary Key | int       | Nomor Id                                                                                            |         |
| user_id                | Foreign Key | varchar   | Nomor ID pada tabel user                                                                            |         |
| followers_count        | -           | int       | Jumlah user follower                                                                                |         |
| follows_count          | -           | int       | Jumlah user following                                                                               |         |
| media_count            | -           | int       | Jumlah media yang diupload user                                                                     |         |
| updated_timestamp      | -           | timestamp | Timestamp kapan data di update                                                                      | Unique  |
| datestamp              | -           | date      | Datestamp kapan data di update                                                                      | Unique  |
| followers_count_growth | -           | int4      | Pertumbuhan jumlah followers                                                                        |         |
| media_count_growth     | -           | int4      | Pertumbuhan jumlah media/postingan                                                                  |         |


##### **user_competitor**
Berisi tentang data id user dengan id user competitor. 

| Nama Kolom    | Tipe        | Tipe Data | Isi                                                                             | Catatan |
|---------------|-------------|-----------|---------------------------------------------------------------------------------|---------|
| id            | Primary Key | serial    | Nomor Id                                                                        |         |
| user_id       | Foreign Key | varchar   | Nomor ID yang merujuk pada table user                                           |         |
| competitor_id | Foreign Key | varchar   | Nomor ID yang merujuk pada table user yang merupakan kompetitor dari suatu user |         |

##### **user_insight_audience_city**
Berisi tentang data insight kota & provinai dari follower suatu user.

| Nama Kolom | Tipe        | Tipe Data | Isi                                               | Catatan |
|------------|-------------|-----------|---------------------------------------------------|---------|
| id         | Primary Key | bigserial | Nomor ID                                          |         |
| user_id    | Foreign Key | varchar   | Nomor ID yang merujuk pada table user             |         |
| city       | -           | varchar   | Nama Kota                                         |         |
| province   | -           | varchar   | Nama Province                                     |         |
| value      | -           | int       | Jumlah follower dengan kota dan provinsi tertentu |         |

##### **user_insight_audience_country**
Berisi tentang data insight sebaran negara follower suatu user.

| Nama Kolom        | Tipe        | Tipe Data | Isi                                    | Catatan |
|-------------------|-------------|-----------|----------------------------------------|---------|
| id                | Primary Key | bigserial | Nomor ID                               |         |
| user_id           | Foreign Key | varchar   | Nomor ID yang merujuk pada table user  |         |
| country_code      | -           | varchar   | Kode Negara                            |         |
| value             | -           | int       | Jumlah follower dengan negara tertentu |         |
| end_time          | -           | timestamp | Datestamp data update dari facebook    |         |
| updated_timestamp | -           | timestamp | Timestamp kapan data di update         |         |

##### **user_insight_audience_gender_age**
Berisi tentang data insight sebaran jenis kelamin dan range usia follower dari suatu user.
| Nama Kolom        | Tipe        | Tipe Data | Isi                                                          | Catatan |
|-------------------|-------------|-----------|--------------------------------------------------------------|---------|
| id                | Primary Key | bigserial | Nomor ID                                                     |         |
| user_id           | Foreign Key | varchar   | Nomor ID yang merujuk pada table user                        |         |
| gender            | -           | varchar   | Jenis kelamin user                                           |         |
| age               | -           | varchar   | Range usia user                                              |         |
| value             | -           | int       | Jumlah follower dengan jenis kelamin dan range usia tertentu |         |
| end_time          | -           | timestamp | Datestamp data update dari facebook                          |         |
| updated_timestamp | -           | timestamp | Timestamp kapan data di update                               |         |


##### **user_insight_audience_locale**
Berisi tentang data insight sebaran *ISO Language Code* follower dari suatu user.

| Nama Kolom        | Tipe        | Tipe Data | Isi                                         | Catatan |
|-------------------|-------------|-----------|---------------------------------------------|---------|
| id                | Primary Key | bigserial | Nomor ID                                    |         |
| user_id           | Foreign Key | varchar   | Nomor ID yang merujuk pada table user       |         |
| locale_code       | -           | varchar   | Kode Bahasa                                 |         |
| value             | -           | int       | Jumlah follower dengan kode bahasa tertentu |         |
| end_time          | -           | timestamp | Datestamp data update dari facebook         |         |
| updated_timestamp | -           | timestamp | Timestamp kapan data di update              |         |

##### **user_insight_impressions**
Berisi tentang data insight impression follower dari suatu user.

| Nama Kolom        | Tipe        | Tipe Data | Isi                                   | Catatan             |
|-------------------|-------------|-----------|---------------------------------------|---------------------|
| id                | Primary Key | bigserial | Nomor ID                              |                     |
| user_id           | Foreign Key | varchar   | Nomor ID yang merujuk pada table user |                     |
| period            | -           | varchar   | Periode Perhitungan Impressions       | [Day, Week, Day28]  |
| value             | -           | int       | Nilai Impression user                 |                     |
| end_time          | -           | timestamp | Datestamp data update dari facebook   |                     |
| updated_timestamp | -           | timestamp | Timestamp kapan data di update        |                     | 

##### **user_insight_online_follower**
Berisi tentang data insight sebaran jam online follower dari suatu user.

| Nama Kolom        | Tipe        | Tipe Data | Isi                                            | Catatan |
|-------------------|-------------|-----------|------------------------------------------------|---------|
| id                | Primary Key | int       | Nomor ID                                       |         |
| user_id           | Foreign Key | varchar   | Nomor ID yang merujuk pada table user          |         |
| hour              | -           | int       | Rentang Jam dari 0-24                          |         |
| value             | -           | int       | Nilai jumlah online follower pada jam tertentu |         |
| end_time          | -           | timestamp | Datestamp data update dari facebook            |         |
| updated_timestamp | -           | timestamp | Timestamp kapan data di update                 |         |

##### **user_insight_reach**
Berisi tentang data insight nilai reach dari suatu user.

| Nama Kolom        | Tipe        | Tipe Data | Isi                                                         | Catatan             |
|-------------------|-------------|-----------|-------------------------------------------------------------|---------------------|
| id                | Primary Key | bigserial | Nomor ID                                                    |                     |
| user_id           | Foreign Key | varchar   | Nomor ID yang merujuk pada table user                       |                     |
| period            | -           | varchar   | Periode Perhitungan Reach                                   | [Day, Week, Day28]  |
| value             | -           | int       | Jumlah nilai Reach user                                     |                     |
| end_time          | -           | timestamp | Datestamp data dihitung dari tanggal berapa (dari facebook) |                     |
| updated_timestamp | -           | timestamp | Timestamp kapan data di update                              |                     |

##### **media**
Berisi tentang data media (foto/video) setiap user.

| Nama Kolom         | Tipe        | Tipe Data   | Isi                                          | Catatan                        |
|--------------------|-------------|-------------|----------------------------------------------|--------------------------------|
| id                 | Primary Key | varchar     | Nomor ID                                     | Unique                         |
| user_id            | Foreign Key | varchar     | Nomor ID yang merujuk pada table user        |                                |
| permalink          | -           | varchar     | Alamat url media                             |                                |
| media_type         | -           | varchar     | Tipe media yang diupload                     | [IMAGE, VIDEO, CAROUSEL ALBUM] |
| timestamp          | -           | timestamptz   | Timestamp kapan data di upload di instagram  |                                |
| username           | -           | varchar     | Username di instagram                        |                                |
| caption            |             | text        | Text caption pada suatu media (photo/video)  |                                |
| is_comment_enabled |             | bool        | Boolean apakah comment aktif / tidak         |                                |
| comments_count     |             | int         | Jumlah komentar pada suatu media             |                                |
| like_count         |             | int         | Jumlah Like pada suatu media                 |                                |
| media_url          |             | varchar     | Alamat url media                             |                                |
| thumbnail_url      |             | varchar     | Alamat url thumbnail image                   |                                |
| shortcode          |             | varchar     | Short code untuk url                         |                                |
| owner_id           |             | varchar     | Nomor ID yang sama dengan User ID            |                                |
| media_hastag       |             | varchar     | List Hastag yang dipakai pada suatu media    |                                |
| is_archieved       |             | bool        | Boolean apakah media di archieved atau tidak |                                |
| updated_timestamp  |             | timestamptz | Timestamp kapan data di update               |                                |
| datestamp          |             | date        | Tanggal kapan data di update                 |                                |

##### **media_comment**
Berisi tentang data komentar pada media (foto/video) setiap user.

| Nama Kolom        | Tipe        | Tipe Data  | Isi                                               | Catatan |
|-------------------|-------------|------------|---------------------------------------------------|---------|
| id                | Primary Key | varchar    | Nomor ID                                          | Unique  |
| username          |             | varchar    | Username  yang melakukan komen                    |         |
| media_id          | Foreign Key | varchar    | Nomor ID yang merujuk pada table media            |         |
| text              | -           | text       | Text komentar dari suatu media                    |         |
| timestamp         | -           | timestampz | Waktu komentar pada suatu media                   |         |
| like_count        | -           | int4       | Jumlah Like pada suatu komentar                   |         |
| hidden            | -           | bool       | Boolean apakah komentar di sembunyikan atau tidak |         |
| updated_timestamp |             | timestampz | Timestamp kapan data di update                    |         |

##### **media_like_comment**
Berisi tentang data history jumlah like dan komen media setiap user.

| Nama Kolom            | Tipe        | Tipe Data  | Isi                                    | Catatan |
|-----------------------|-------------|------------|----------------------------------------|---------|
| id                    | Primary Key | varchar    | Nomor ID                               |         |
| media_id              | Foreign Key | varchar    | Nomor ID yang merujuk pada table media | Unique  |
| like_count            | -           | int4       | Jumlah Like pada suatu komentar        |         |
| comments_count        | -           | int4       | Jumlah komen pada suatu media          |         |
| updated_timestamp     |             | timestampz | Timestamp kapan data di update         |         |
| datestamp             |             | timestampz | Tanggal kapan data di update           | Unique  |
| comments_count_growth |             | int4       | Pertumbuhan jumlah komen               |         |
| like_count_growth     |             | int4       | Pertumbuhan jumlah like                |         |

##### **media_insight**
Berisi tentang data insight seperti engagement, impressions, reach, dan jumlah saved pada media (foto/video).

| Nama Kolom        | Tipe        | Tipe Data  | Isi                                                            | Catatan                                                      |
|-------------------|-------------|------------|----------------------------------------------------------------|--------------------------------------------------------------|
| id                | Primary Key | varchar    | Nomor ID                                                       |                                                              |
| media_id          | Foreign Key | varchar    | Nomor ID yang merujuk pada table media                         | Unique                                                       |
| metric            | -           | varchar    | metric perhitungan suatu media seperti engagement, reach, dll. | [Engagement, Impressions, Reach, Saved, Video_Views], Unique |
| value             | -           | int        | Nilai pada setiap setiap metric                                |                                                              |
| updated_timestamp | -           | timestampz | Timestamp kapan data di update                                 |                                                              |
| datestamp         | -           | date       | Date kapan data di update                                      | Unique                                                       |

##### **instagram_tokens**
Berisi tentang data token instagram pada setiap user.

| Nama Kolom   | Tipe        | Tipe Data   | Isi                                      | Catatan |
|--------------|-------------|-------------|------------------------------------------|---------|
| user_id      | Primary Key | varchar     | Nomor ID                                 |         |
| token        | -           | text        | Token untuk autentikasi dengan instagram |         |
| token_secret | -           | text        | Secret Token                             |         |
| expired_at   | -           | timestamptz | Waktu kadaluarsa token                   |         |

##### **fetch_catalogue**
Berisi tentang data fetch.

| Nama Kolom | Tipe        | Tipe Data | Isi         | Catatan |
|------------|-------------|-----------|-------------|---------|
| fetch_id   | Primary Key | int       | Nomor ID    |         |
| fetch_name | -           | varchar   | Nama Fetch  |         |

##### **user_insight_visitor**
Berisi data nilai insight visitor dengan perhitungan nilai pada hari ini dibandingkan dengan nilai 7 hari atau 28 hari yang lalu untuk setiap user. 

| Nama Kolom        | Tipe        | Tipe Data   | Isi                                       | Catatan |
|-------------------|-------------|-------------|-------------------------------------------|---------|
| user_id           | Foreign Key | varchar     | Nomor ID yang merujuk pada table user     |         |
| value             | -           | int4        | Jumlah visitor                            |         |
| end_time          | -           | timestamptz | Periode waktu selesai perhitungan visitor |         |
| datestamp         | -           | varchar     | Tanggal kapan data di update              | Unique  |
| id                | Primary Key | bigserial   | Nomor ID                                  | Unique  |
| updated_timestamp | -           | timestamptz | Timestamp kapan data di update            |         |


#### Schema Toba_Cek_Insta

Berisi tentang data olahan analytics dari data awal instagram.

![ER Diagram Instagram](image/toba_cek_insta.png)

##### **user_insight_engagement**
Berisi data nilai engagement yang diperoleh dari penambahan jumlah like dan jumlah comment untuk setiap user dengan periode waktu 7 hari dan 28 hari.
| Nama Kolom        | Tipe        | Tipe Data | Isi                                               | Catatan         |
|-------------------|-------------|-----------|---------------------------------------------------|-----------------|
| id                | Primary Key | serial    | Nomor ID                                          |                 |
| user_id           | Foreign Key | varchar   | Nomor ID yang merujuk pada table user             | Unique          |
| engagement        | -           | int       | Nilai engagement untuk suatu user                 |                 |
| likes_count       | -           | int       | Jumlah like pada suatu user                       |                 |
| comments_count    | -           | int       | Jumlah komentar pada suatu user                   |                 |
| timeframe         | -           | int       | Periode waktu (dalam hari) perhitungan engagement | [7, 28], Unique |
| datestamp         | -           | date      | datestamp kapan data di update                    | Unique          |
| updated_timestamp | -           | timestamp | Timestamp kapan data di update                    |                 |

##### **user_insight_engagement_growth**
Berisi data nilai growth engagement dengan perhitungan nilai engagement pada hari ini dibandingkan dengan 7 hari atau 28 hari yang lalu untuk setiap user.

| Nama Kolom        | Tipe        | Tipe Data | Isi                                                      | Catatan |
|-------------------|-------------|-----------|----------------------------------------------------------|---------|
| id                | Primary Key | bigserial | Nomor ID                                                 |         |
| user_id           | Foreign Key | varchar   | Nomor ID yang merujuk pada table user                    |         |
| growth            | -           | float     | Nilai engagement growth untuk suatu user                 |         |
| timeframe         | -           | int       | Periode waktu (dalam hari) perhitungan engagement growth | [7, 28] |
| datestamp         | -           | date      | datestamp kapan data di update                           |         |
| updated_timestamp | -           | timestamp | Timestamp kapan data di update                           |         |

##### **user_insight_engagement_rate_growth**
Berisi data nilai rate growth engagement dengan perhitungan nilai engagement pada hari ini dibagi jumlah follower dibandingkan dengan nilai 7 hari atau 28 hari yang lalu untuk setiap user.

| Nama Kolom        | Tipe        | Tipe Data | Isi                                                           | Catatan |
|-------------------|-------------|-----------|---------------------------------------------------------------|---------|
| id                | Primary Key | bigserial | Nomor ID                                                      |         |
| user_id           | Foreign Key | varchar   | Nomor ID yang merujuk pada table user                         |         |
| growth            | -           | float     | Nilai engagement rate growth untuk suatu user                 |         |
| timeframe         | -           | int       | Periode waktu (dalam hari) perhitungan engagement rate growth | [7, 28] |
| datestamp         | -           | date      | datestamp kapan data di update                                |         |
| updated_timestamp | -           | timestamp | Timestamp kapan data di update                                |         |

##### **user_insight_follower_online**
Berisi tentang data insight sebaran jam online follower dari suatu user.

| Nama Kolom   | Tipe        | Tipe Data | Isi                                   | Catatan |
|--------------|-------------|-----------|---------------------------------------|---------|
| id           | Primary Key | varchar   | Nomor ID                              |         |
| user_id      | Foreign Key | varchar   | Nomor ID yang merujuk pada table user |         |
| hours        | -           | varchar   | Rentang Jam dari 0-24                 |         |
| val          | -           | varchar   | Nilai Impression user                 |         |
| date_range   | -           | varchar   | Range tanggal penghitungan            |         |
| updated_date | -           | timestamp | Timestamp kapan data di update        |         |

##### **user_insight_follower_growth**
Berisi data nilai growth jumlah follower dengan perhitungan nilai pada hari ini dibandingkan dengan nilai 7 hari atau 28 hari yang lalu untuk setiap user.

| Nama Kolom        | Tipe        | Tipe Data | Isi                                             | Catatan  |
|-------------------|-------------|-----------|-------------------------------------------------|----------|
| id                | Primary Key | serial    | Nomor ID                                        |          |
| user_id           | Foreign Key | varchar   | Nomor ID yang merujuk pada table user           |          |
| date_stamp        | -           | date      | tanggal kapan data di update                    |          |
| timeframe         | -           | int       | Periode waktu perhitungan perbandingan follower | [7 , 28] |
| growth            | -           | float     | Nilai growth follower setiap user               |          |
| updated_timestamp | -           | timestamp | Timestamp kapan data di update                  |          |

##### **user_insight_impressions_growth**
Berisi data nilai growth impression user dengan perhitungan nilai pada hari ini dibandingkan dengan nilai 7 hari atau 28 hari yang lalu untuk setiap user.

| Nama Kolom        | Tipe        | Tipe Data | Isi                                             | Catatan  |
|-------------------|-------------|-----------|-------------------------------------------------|----------|
| id                | Primary Key | serial    | Nomor ID                                        |          |
| user_id           | Foreign Key | varchar   | Nomor ID yang merujuk pada table user           |          |
| date_stamp        | -           | date      | tanggal kapan data di update                    |          |
| timeframe         | -           | int       | Periode waktu perhitungan perbandingan follower | [7 , 28] |
| growth            | -           | float     | Nilai growth impressions setiap user            |          |
| updated_timestamp | -           | timestamp | Timestamp kapan data di update                  |          |

##### **user_insight_reach_growth**
Berisi data nilai growth jumlah reach user dengan perhitungan nilai pada hari ini dibandingkan dengan nilai 7 hari atau 28 hari yang lalu untuk setiap user.

| Nama Kolom        | Tipe        | Tipe Data | Isi                                             | Catatan  |
|-------------------|-------------|-----------|-------------------------------------------------|----------|
| id                | Primary Key | serial    | Nomor ID                                        |          |
| user_id           | Foreign Key | varchar   | Nomor ID yang merujuk pada table user           |          |
| date_stamp        | -           | date      | tanggal kapan data di update                    |          |
| timeframe         | -           | int       | Periode waktu perhitungan perbandingan follower | [7 , 28] |
| growth            | -           | float     | Nilai growth impressions setiap user            |          |
| updated_timestamp | -           | timestamp | Timestamp kapan data di update                  |          |

##### **user_insight_sentiment**
Berisi data nilai sentiment user (positif, negatif, dan netral) dari komentar pada media suatu user.

| Nama Kolom        | Tipe        | Tipe Data | Isi                                   | Catatan |
|-------------------|-------------|-----------|---------------------------------------|---------|
| id                | Primary Key | serial    | Nomor ID                              |         |
| user_id           | Foreign Key | varchar   | Nomor ID yang merujuk pada table user |         |
| date_stamp        | -           | date      | tanggal kapan data di update          |         |
| neu               | -           | int       | Jumlah sentiment netral               |         |
| pos               | -           | int       | Jumlah sentiment positive             |         |
| neg               |             | int       | Jumlah sentiment negative             |         |
| updated_timestamp | -           | timestamp | Timestamp kapan data di update        |         |

##### **user_insight_sentiment_growth**
Berisi data nilai growth setiap sentiment dengan melakukan penguragan nilai pada hari ini dibandingkan dengan nilai 7 hari atau 28 hari yang lalu untuk setiap user.

| Nama Kolom        | Tipe        | Tipe Data | Isi                                              | Catatan  |
|-------------------|-------------|-----------|--------------------------------------------------|----------|
| id                | Primary Key | serial    | Nomor ID                                         |          |
| user_id           | Foreign Key | varchar   | Nomor ID yang merujuk pada table user            |          |
| date_stamp        | -           | date      | tanggal kapan data di update                     |          |
| neu               | -           | float     | Jumlah growth sentiment netral                   |          |
| pos               | -           | float     | Jumlah growth sentiment positive                 |          |
| neg               |             | float     | Jumlah growth sentiment negative                 |          |
| updated_timestamp | -           | timestamp | Timestamp kapan data di update                   |          |
| timeframe         | -           | int       | Periode waktu perhitungan perbandingan sentiment | [7 , 28] |

##### **user_media_largest_engagement**
Berisi data media yang memiliki nilai engagement terbanyak pada suatu user dengan periode waktu 7 atau 28 hari.

| Nama Kolom        | Tipe        | Tipe Data | Isi                                            | Catatan  |
|-------------------|-------------|-----------|------------------------------------------------|----------|
| id                | Primary Key | bigserial | Nomor ID                                       |          |
| user_id           | Foreign Key | varchar   | Nomor ID yang merujuk pada table user          |          |
| media_id          | Foreign Key | varchar   | Nomor ID yang merujuk pada table media         |          |
| timeframe         | -           | int       | Periode waktu perhitungan engagement terbanyak | [7 , 28] |
| engagement_count  | -           | int       | Jumlah engagement media                        |          |
| updated_timestamp | -           | timestamp | Timestamp kapan data di update                 |          |

##### **user_media_largest_reach**
Berisi data media yang memiliki nilai reach terbanyak pada suatu user dengan periode waktu 7 atau 28 hari.

| Nama Kolom        | Tipe        | Tipe Data | Isi                                            | Catatan  |
|-------------------|-------------|-----------|------------------------------------------------|----------|
| id                | Primary Key | bigserial | Nomor ID                                       |          |
| user_id           | Foreign Key | varchar   | Nomor ID yang merujuk pada table user          |          |
| media_id          | Foreign Key | varchar   | Nomor ID yang merujuk pada table media         |          |
| timeframe         | -           | int       | Periode waktu perhitungan engagement terbanyak | [7 , 28] |
| reach_count       | -           | int       | Jumlah reach suatu media                       |          |
| updated_timestamp | -           | timestamp | Timestamp kapan data di update                 |          |

##### **user_media_most_negative**
Berisi data media yang memiliki sentiment negatif terbanyak pada suatu user dengan periode waktu 7 atau 28 hari.

| Nama Kolom        | Tipe        | Tipe Data | Isi                                            | Catatan  |
|-------------------|-------------|-----------|------------------------------------------------|----------|
| id                | Primary Key | bigserial | Nomor ID                                       |          |
| user_id           | Foreign Key | varchar   | Nomor ID yang merujuk pada table user          |          |
| media_id          | Foreign Key | varchar   | Nomor ID yang merujuk pada table media         |          |
| timeframe         | -           | int       | Periode waktu perhitungan engagement terbanyak | [7 , 28] |
| negative_count    | -           | int       | Jumlah sentiment negatif suatu media           |          |
| updated_timestamp | -           | timestamp | Timestamp kapan data di update                 |          |

##### **user_media_most_positive**
Berisi data media yang memiliki sentiment positif terbanyak pada suatu user dengan periode waktu 7 atau 28 hari.

| Nama Kolom        | Tipe        | Tipe Data | Isi                                            | Catatan  |
|-------------------|-------------|-----------|------------------------------------------------|----------|
| id                | Primary Key | bigserial | Nomor ID                                       |          |
| user_id           | Foreign Key | varchar   | Nomor ID yang merujuk pada table user          |          |
| media_id          | Foreign Key | varchar   | Nomor ID yang merujuk pada table media         |          |
| timeframe         | -           | int       | Periode waktu perhitungan engagement terbanyak | [7 , 28] |
| positive_count    | -           | int       | Jumlah sentiment positive suatu media          |          |
| updated_timestamp | -           | timestamp | Timestamp kapan data di update                 |          |

##### **user_media_smallest_engagement**
Berisi data media yang memiliki nilai engagement paling sedikit pada suatu user dengan periode waktu 7 atau 28 hari.

| Nama Kolom        | Tipe        | Tipe Data | Isi                                            | Catatan  |
|-------------------|-------------|-----------|------------------------------------------------|----------|
| id                | Primary Key | bigserial | Nomor ID                                       |          |
| user_id           | Foreign Key | varchar   | Nomor ID yang merujuk pada table user          |          |
| media_id          | Foreign Key | varchar   | Nomor ID yang merujuk pada table media         |          |
| timeframe         | -           | int       | Periode waktu perhitungan engagement terbanyak | [7 , 28] |
| engagement_count  | -           | int       | Jumlah engagement media                        |          |
| updated_timestamp | -           | timestamp | Timestamp kapan data di update                 |          |

##### **user_media_comment_sentiment**
Berisi data sentiment setiap komentar pada suatu media.

| Nama Kolom        | Tipe        | Tipe Data | Isi                                      | Catatan          |
|-------------------|-------------|-----------|------------------------------------------|------------------|
| id                | Primary Key | bigserial | Nomor ID                                 |                  |
| comment_id        | Foreign Key | varchar   | Nomor ID yang merujuk pada table comment |                  |
| media_id          | Foreign Key | varchar   | Nomor ID yang merujuk pada table media   |                  |
| sentiment         | -           | varchar   | Sentiment komentar suatu media           | [neu , pos, neg] |
| updated_timestamp | -           | timestamp | Timestamp kapan data di update           |                  |

##### **user_hastags_metrics**
Berisi data metrics setiap hashtag pada suatu media user.

| Nama Kolom          | Tipe        | Tipe Data   | Isi                                                         | Catatan          |
|---------------------|-------------|-------------|-------------------------------------------------------------|------------------|
| id                  | Primary Key | serial      | Nomor ID                                                    |                  |
| user_id             | Foreign Key | varchar     | Nomor ID yang merujuk pada table user                       | Unique           |
| hastag              | -           | timestamptz | Hastag yang tertera pada caption (#Hastag)                  | Unique           |
| total_engagement    | -           | int         | Jumlah engagement                                           | [neu , pos, neg] |
| post_count          | -           | int         | Jumlah post yang menggunakan hastag tertentu                |                  |
| engagement_per_post |             | float       | Perhitungan engagement dibagi jumlah postingan              |                  |
| updated_timestamp   |             | timestamptz | Timestamp kapan data di update                              |                  |
| datestamp           |             | date        | Date kapan data di update                                   | Unique           |
| total_reach         |             | int         | Jumlah total reach                                          |                  |
| total_saved         |             | int         | Jumlah total post yang di simpan dengan menggunakan hastag  |                  |
| reach_per_post      |             | int         | Penghitungan reach per jumlah post                          |                  |
| saved_per_post      |             | int         | Penghitungan media disimpan per jumlah post                 |                  |

##### **user_hastags_metrics_distribution**
Berisi data distribusi metrics setiap hashtag pada suatu media user.

| Nama Kolom        | Tipe        | Tipe Data   | Isi                                            | Catatan |
|-------------------|-------------|-------------|------------------------------------------------|---------|
| id                | Primary Key | serial      | Nomor ID                                       |         |
| user_id           | Foreign Key | varchar     | Nomor ID yang merujuk pada table user          |         |
| media_id          | Foreign Key | varchar     | Nomor ID yang merujuk pada table media         | Unique  |
| hastag            | -           | timestamptz | Hastag yang tertera pada caption (#Hastag)     | Unique  |
| media_timestamp   |             | timestamptz | Timestamp kapan media di update                | Unique  |
| engagement        |             | int4        | Perhitungan engagement dibagi jumlah postingan |         |
| reach             | -           | int4        | Jumlah reach post                              |         |
| impressions       |             | int4        | Jumlah impressions                             |         |
| updated_timestamp |             | timestamptz | Timestamp kapan data di update                 |         |
| datestamp         |             | date        | Date kapan data di update                      | Unique  |
| comments_count    |             | int         | Jumlah komentar pada suatu media               |         |
| like_count        |             | int         | Jumlah Like pada suatu media                   |         |

##### **user_insight_follower_online_wording (not active)**
Berisi data insight.

| Nama Kolom        | Tipe        | Tipe Data | Isi                                   | Catatan |
|-------------------|-------------|-----------|---------------------------------------|---------|
| id                | Primary Key | serial    | Nomor ID                              |         |
| user_id           | Foreign Key | varchar   | Nomor ID yang merujuk pada table user |         |
| highlight_wording | -           | varchar   |                                       |         |
| highlight_type    | -           | varchar   |                                       |         |
| date_range        | -           | date      | datestamp kapan data di update        |         |
| lang              | -           | varchar   | bahasa yang digunakan                 |         |
| updated_date      | -           | timestamp | Timestamp kapan data di update        |         |

##### **user_media_comment_sentiment (not active)**
Berisi data waktu paling aktif suatu user.

| Nama Kolom         | Tipe        | Tipe Data   | Isi                                   | Catatan |
|--------------------|-------------|-------------|---------------------------------------|---------|
| id                 | Primary Key | serial      | Nomor ID                              |         |
| user_id            | Foreign Key | varchar     | Nomor ID yang merujuk pada table user |         |
| waktu_paling_aktif | -           | timestamptz |                                       |         |
| value_paling_aktif | -           | varchar     |                                       |         |
| updated_date       | -           | timestamp   | Timestamp kapan data di update        |         |

### Routine

#### IG Media
Mewakili album, foto, atau video Instagram (video yang diunggah, video live, video yang dibuat dengan aplikasi Instagram TV, reel, atau story Instagram).

#####  Reading
Menggunakan third party (?)

###### Limitasi
- Kolom yang menampilkan nilai aggregat tidak menyertakan data yang digerakkan oleh iklan. Misalnya, comments_count menghitung komentar pada sebuah foto, tetapi tidak menghitung komentar pada iklan yang berisi foto tersebut.
- Caption tidak menyertakan simbol @ kecuali pengguna aplikasi juga dapat melakukan tugas yang setara dengan Admin di aplikasi.
- Beberapa kolom tidak dapat digunakan pada foto di dalam album (anak).
- Media Instagram TV harus dibagikan ke Instagram pada saat publikasi (Post a Preview atau Share Preview to Feed diaktifkan) agar dapat diakses melalui API.
- Live video IG Media hanya dapat dibaca saat sedang disiarkan.

###### Persyaratan
| Tipe          | Deskripsi                                                                                                                                                                                           |
|---------------|-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Akses Token | User.                                                                                                                                                                                                 |
| Izin   | **instagram_basic** <br /> **pages_read_engagement** <br /> **pages_show_list** <br /><br /> Jika pengguna aplikasi diberi peran di Halaman melalui Business Manager, Anda juga memerlukan salah satu dari yang berikut: <br /> **ads_management** <br /> **business_management** |


###### Request Syntax

GET https://graph.facebook.com/{api-version}/{ig-media-id}
  <br />  &nbsp;&nbsp;&nbsp;&nbsp;?fields={fields}
  <br />  &nbsp;&nbsp;&nbsp;&nbsp;&access_token={access-token}

###### Parameter Path

| Placeholder   | Value                  |
|---------------|------------------------|
| **{api-version}** | Versi API.           |
| **{ig-media-id}** | Perlu. IG Media ID. |


###### Parameter String Kueri

|      Key     |   Placeholder  |                       Value                       |
|:------------:|:--------------:|:-------------------------------------------------:|
| **access_token** | **{access-token}** | Perlu. Token akses pengguna dari pengguna aplikasi.           |
| **fields**       | **{fields}**       | List dari field yang ingin dihasilkan yang dipisahkan dengan tanda koma. |

###### Fields
Public fields dan dapat di-read via ekspansi field.

| Field                     | Deskripsi                                                                                                                                                                                                                                                                                                                                                                                      |
|---------------------------|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| **caption** <br />Public            | Caption. Tidak termasuk anak album. Simbol @ dikecualikan, kecuali jika pengguna aplikasi dapat melakukan tugas yang setara dengan admin di Halaman Facebook yang terhubung ke akun Instagram yang digunakan untuk membuat caption.                                                                                                                                                                                           |
| **comments_count** <br />Public     | Jumlah komentar di media. Tidak termasuk komentar pada media album anak dan keterangan media. Termasuk reply pada komentar.                                                                                                                                                                                                                                                                    |
| **id** <br />Public                 | Media ID.                                                                                                                                                                                                                                                                                                                                                                                        |
| **ig_id** <br />Public              | Instagram media ID. Sebelumnya menggunakan dengan Legacy Instagram API, sekarang tidak digunakan lagi. Sebagai gantinya menggunakan id.                                                                                                                                                                                                                                                                                                              |
| **is_comment_enabled**        | Menunjukkan jika komentar diaktifkan atau dinonaktifkan. Tidak termasuk anak album.                                                                                                                                                                                                                                                                                                                          |
| **is_shared_to_feed** <br />Public  | Reels saja. Jika benar, berarti reel dapat muncul di tab feed dan reels. Jika salah, berarti gulungan hanya dapat muncul di tab reel. Perhatikan bahwa tidak ada nilai yang menunjukkan apakah reel benar-benar muncul di tab reels, karena reel mungkin tidak memenuhi persyaratan kelayakan atau telah dipilih oleh algoritme kami. Lihat spesifikasi reel untuk kriteria kelayakan.                   |
| **like_count**                | Jumlah likes di media, termasuk reply di komentar. Tidak termasuk likes di media anak album dan likes di pos yang dipromosikan dibuat dari media. <br /><br /> Jika ditanyakan secara tidak langsung melalui titik akhir lain atau ekspansi fields: <br />-v10.0 dan calls yang lebih lama: Nilainya adalah 0 jika pemilik media menyembunyikan jumlah like. <br />-v11.0+ calls: Field like_count dihilangkan jika pemilik media memiliki jumlah like yang tersembunyi. |
| **media_product_type** <br />Public | Lokasi media dipublikasi. Dapat berupa iklan, feed, story, atau reels.                                                                                                                                                                                                                                                                                                                           |
| **media_type** <br />Public         | Tipe media. Dapat berupa album carousel, gambar, or video.                                                                                                                                                                                                                                                                                                                                              |
| **media_url** <br />Public          | URL untuk media. Field dari media_url field URL dihilangkan dari respons jika media berisi materi berhak cipta atau telah ditandai karena pelanggaran hak cipta. Contoh materi berhak cipta dapat mencakup audio pada reels.                                                                                                                                                                     |
| **owner** <br />Public              | ID pengguna Instagram yang membuat media. Hanya di-return jika pengguna aplikasi yang membuat kueri juga membuat media; jika tidak, field dari username yang di-return sebagai gantinya.                                                                                                                                                                                                                                   |
| **permalink** <br />Public          | URL permanen ke media.                                                                                                                                                                                                                                                                                                                                                                      |
| **shortcode** <br />Public          | Shortcode ke media.                                                                                                                                                                                                                                                                                                                                                                          |
| **thumbnail_url** <br />Public      | URL dari thumbnail media. Hanya tersedia di media video.                                                                                                                                                                                                                                                                                                                                              |
| **timestamp** <br />Public          | Tanggal pembuatan berformat ISO 8601 dalam UTC (standarnya adalah UTC ±00:00).                                                                                                                                                                                                                                                                                                                                 |
| **username** <br />Public           | Username pengguna yang membuat media.                                                                                                                                                                                                                                                                                                                                                          |
| **video_title** <br />Public        | Tidak digunakan lagi. Dihilangkan dari respons.                                                                                                                                                                                                                                                                                                                                                               |

###### Edges
Public edges dapat dikembalikan melalui ekspansi field.

| Edge             | Description                                                       |
|------------------|-------------------------------------------------------------------|
| **children** <br />Public. | Merepresentasikan kumpulan objek IG Media di album IG Media. |
| **comments**         | Merepresentasikan kumpulan Komentar IG pada objek Media IG.     |
| **insights**         | Merepresentasikan metrik interaksi sosial pada objek IG Media.      |

##### Updating
**POST /{ig-media-id}**
Mengaktifkan atau menonaktifkan komentar di media IG.
--tidak menggunakan POST--

###### Limitasi
Video langsung IG media tidak didukung.

###### Persyaratan

| Tipe          | Deskripsi                                                                                                                                                                                               |
|---------------|-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Akses Token | User.                                                                                                                                                                                                     |
| Izin   | **instagram_basic** <br /> **instagram_manage_comments**<br /> **pages_show_list**<br /><br /> Jika pengguna aplikasi diberi peran di Halaman via Business Manager, Anda juga memerlukan salah satu dari yang berikut: <br />**ads_management** <br />**business_management** |

###### Request Syntax
POST https://graph.facebook.com/{api-version}/{ig-media-id}
  <br />  &nbsp;&nbsp;&nbsp;&nbsp;?comment_enabled={comment-enabled}
  <br />  &nbsp;&nbsp;&nbsp;&nbsp;&access_token={access-token}

###### Parameter Path

| Placeholder   | Value                  |
|---------------|------------------------|
| **{api-version}** | API version.           |
| **{ig-media-id}** | Perlu. IG Media ID. |

###### Parameter String Kueri

| Key             | Placeholder       | Value                                                                  |
|-----------------|-------------------|------------------------------------------------------------------------|
| **access_token**    | **{access-token}**    | Perlu. Token akses pengguna dari pengguna aplikasi.                                 |
| **comment_enabled** | **{comment-enabled}** | Perlu. Set ke true untuk mengaktifkan komentar atau false untuk menonaktifkan komentar. |