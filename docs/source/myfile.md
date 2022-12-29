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

### Facebook and 3-rd Party Endpoint

#### IG Media
Mewakili album, foto, atau video Instagram (video yang diunggah, video live, video yang dibuat dengan aplikasi Instagram TV, reel, atau story Instagram).

Cekbrand menggunakan 3rd-party dari pyfacebook yang memfasilitasi pemanggilan dari masing-masing endpoint API Graph facebook.

##### Limitasi
- Kolom yang menampilkan nilai aggregat tidak menyertakan data yang digerakkan oleh iklan. Misalnya, comments_count menghitung komentar pada sebuah foto, tetapi tidak menghitung komentar pada iklan yang berisi foto tersebut.
- Caption tidak menyertakan simbol @ kecuali pengguna aplikasi juga dapat melakukan tugas yang setara dengan Admin di aplikasi.
- Beberapa kolom tidak dapat digunakan pada foto di dalam album (anak).
- Media Instagram TV harus dibagikan ke Instagram pada saat publikasi (Post a Preview atau Share Preview to Feed diaktifkan) agar dapat diakses melalui API.
- Live video IG Media hanya dapat dibaca saat sedang disiarkan.

##### Persyaratan
| Tipe          | Deskripsi                                                                                                                                                                                           |
|---------------|-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Akses Token | User.                                                                                                                                                                                                 |
| Izin   | **instagram_basic** <br /> **pages_read_engagement** <br /> **pages_show_list** <br /><br /> Jika pengguna aplikasi diberi peran di Halaman melalui Business Manager, kita juga memerlukan salah satu dari yang berikut: <br /> **ads_management** <br /> **business_management** |


##### Request Syntax

GET https://graph.facebook.com/{api-version}/{ig-media-id}
  <br />  &nbsp;&nbsp;&nbsp;&nbsp;?fields={fields}
  <br />  &nbsp;&nbsp;&nbsp;&nbsp;&access_token={access-token}

##### Parameter Path

| Placeholder   | Value                  |
|---------------|------------------------|
| **{api-version}** | Versi API.           |
| **{ig-media-id}** | Perlu. IG Media ID. |


##### Parameter String Kueri

|      Key     |   Placeholder  |                       Value                       |
|:------------:|:--------------:|:-------------------------------------------------:|
| **access_token** | **{access-token}** | Perlu. Token akses pengguna dari pengguna aplikasi.           |
| **fields**       | **{fields}**       | List yang dipisahkan dengan tanda koma dari field yang ingin dihasilkan. |

##### Fields
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

##### Edges
Public edges dapat dikembalikan melalui ekspansi field.

| Edge             | Description                                                       |
|------------------|-------------------------------------------------------------------|
| **children** <br />Public. | Merepresentasikan kumpulan objek IG Media di album IG Media. |
| **comments**         | Merepresentasikan kumpulan Komentar IG pada objek Media IG.     |
| **insights**         | Merepresentasikan metrik interaksi sosial pada objek IG Media.      |


##### Request Syntax 3rd-party pyfacebook

def get_user_medias(self,
  user_id, fields=None, since_time=None, until_time=None,  count=10, limit=10, return_json=False)
        
Mengambil data media pengguna ig berdasarkan user_id. Penjelasan parameter fungsi get_user_medias sebagai berikut.
|     Parameter      |     Tipe Data                                   |     Keterangan                                                                                                                      |
|--------------------|-------------------------------------------------|-------------------------------------------------------------------------------------------------------------------------------------|
|     user_id        |     str                                         |     Id untuk   pengguna instagram business yang ingin kita dapatkan datanya.                                                        |
|     fields         |     Optional[Union[str,   List, Tuple, Set]]    |     String id   yang dipisahkan koma untuk field data yang kita inginkan. Kita juga dapat pass   ini dengan list id, tuple, set.    |
|     since_time     |     Optional[str]                               |     Batas bawah rentang waktu ke waktu publikasi media. Formatnya adalah %Y-%m-%d.                                                |
|     until_time     |     Optional[str]                               |     Batas atas rentang waktu ke waktu publikasi media. Formatnya adalah %Y-%m-%d.                                                 |
|     count          |     Optional[str]                               |     Jumlah kita ingin mendapatkan media. Jika perlu mendapatkan semuanya, set ini dengan None.                                    |
|     limit          |     int                                         |     Setiap   permintaan mengambil jumlah media dari api. Untuk media sebaiknya tidak lebih   dari 500.                              |
|     return_json    |     bool                                        |     Set ke False   akan mengembalikan instance dari IgProUser.                                                                      |

#### IG Media Insights
Mewakili metrik interaksi sosial pada objek IG Media.

##### Limitasi
- Insight data tidak tersedia untuk media apa pun dalam album IG Media.
- Metrik story media hanya tersedia selama 24 jam, meskipun story tersebut diarsipkan atau di-highlight. Untuk mendapatkan insight terbaru tentang sebuah story sebelum kedaluwarsa, siapkan Webhook untuk field **Instagram** dan subscribe ke field **story_insights**.
- Metrik story media dengan nilai kurang dari 5 menampilkan kode kesalahan **10** dengan pesan **(#10) Not enough viewers for the media to show insights.**
- Untuk story yang dibuat oleh user di Eropa dan Jepang, metrik **replies** kini return nilai **0**.
- Untuk story, balasan yang dibuat oleh pengguna di Eropa dan Jepang tidak termasuk dalam penghitungan **replies**.
- Jika insight data yang kita minta tidak ada atau saat ini tidak tersedia, API akan return kumpulan data kosong, bukan 0 untuk masing-masing metrik.
- Data yang digunakan untuk menghitung metrik dapat ditunda hingga 48 jam.

##### Persyaratan
| Tipe          | Deskripsi                                                                                                                                                                                           |
|---------------|-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Akses Token | User.                                                                                                                                                                                                 |
| Izin   | **instagram_basic** <br /> 
**instagram_manage_insights** <br /> 
**pages_read_engagement** <br /> **pages_show_list** <br /><br /> Jika pengguna aplikasi diberi peran di Halaman melalui Business Manager, kita juga memerlukan salah satu dari yang berikut: <br /> **ads_management** <br /> **business_management** |

##### Request Syntax

GET https://graph.facebook.com/{api-version}/{ig-media-id}/insights
  <br />  &nbsp;&nbsp;&nbsp;&nbsp;?metric={metric}
  <br />  &nbsp;&nbsp;&nbsp;&nbsp;&access_token={access-token}

##### Parameter Path

 Placeholder   | Value                  |
|---------------|------------------------|
| **{api-version}** | Versi API.           |
| **{ig-media-id}** | Perlu. IG Media ID. |

##### Parameter String Kueri

| Parameter                           | Value                                                        |
|-------------------------------------|--------------------------------------------------------------|
| **{access-token}** <br />Type: string         | Perlu. Akses toker dari User pengguna aplikasi.                      |
| **{metric}** <br />Type: Comma-separated list | Perlu. List yang diseparasi oleh metrik yang mau di-return. |

##### Metrik

###### Metrik Album

| Metrik                     | Deskripsi                                                                                 |
|----------------------------|---------------------------------------------------------------------------------------------|
| **carousel_album_engagement**  | Total jumlah like dan Komentar IG pada album objek IG Media.                         |
| **carousel_album_impressions** | Total berapa kali objek IG Media album telah dilihat.                              |
| **carousel_album_reach**       | Total jumlah akun Instagram unik yang telah melihat album objek IG Media.         |
| **carousel_album_saved**       | Total jumlah akun Instagram unik yang telah menyimpan album objek IG Media.        |
| **carousel_album_video_views** | Total jumlah akun Instagram unik yang telah melihat video IG Media dalam album. |

###### Metrik Foto dan Video
Metrik pada media dalam album tidak didukung. Sebagai gantinya, diambil metrik di album.
| Metrik      | Deskripsi                                                                                                                                 |
|-------------|---------------------------------------------------------------------------------------------------------------------------------------------|
| **engagement**  | Jumlahan dari **likes_count**, **comment_count**, dan **saved counts** pada IG Media.                                                                        |
| **impressions** | Total banyaknya objek IG Media telah dilihat.                                                                                    |
| **reach**       | Total akun  Instagram unik yang telah melihat objek IG Media.                                                               |
| **saved**       | Total jumlah akun Instagram unik yang telah melihat objek IG Media.                                                              |
| **video_views** | Total berapa kali video IG Media telah dilihat. Untuk album IG Media, berapa kali semua video dalam album telah dilihat. |

###### Metrik Reels

| Metrik             | Deskripsi                                                                                                                                                                                                   |
|--------------------|---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| **comments**           | Jumlah komentar pada reel. Metrik dalam pengembangan.                                                                                                                                                        |
| **likes**              | Jumlah likes di reel. Metrik dalam pengembangan.                                                                                                                                                           |
| **plays**              | 
Jumlah berapa kali reels mulai diputar setelah tayangan dihitung. Ini didefinisikan sebagai sesi video dengan pemutaran 1 ms atau lebih dan tidak termasuk pemutaran ulang. Metrik dalam pengembangan. |
| **reach**              | Jumlah akun unik yang telah melihat reel setidaknya sekali. Reach berbeda dengan impresi, yang dapat mencakup beberapa penayangan reel oleh akun yang sama. Metrik diperkirakan dan dalam pengembangan. |
| **saved**              | Jumlah penyimpanan reel. Metrik dalam pengembangan.                                                                                                                                                           |
| **shares**             | Jumlah share dari reel. Metrik dalam pengembangan.                                                                                                                                                         |
| **total_interactions** | Jumlah likes, simpan, komentar, dan share pada reel, dikurangi jumlah unlikes, tidak simpan, dan komentar yang dihapus. Metrik dalam pengembangan.                                                                  |

###### Metrik story

| Metrik       | Deskripsi                                                                                                                                                                                                                                                                                                    |
|--------------|----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| **exits**        | Total berapa kali seseorang keluar dari story objek IG Media.                                                                                                                                                                                                                                                |
| **impressions**  | Total berapa kali story objek IG Media telah dilihat.                                                                                                                                                                                                                                                 |
| **reach**        | Total jumlah akun Instagram unik yang telah melihat story objek IG Media.                                                                                                                                                                                                                            |
| **replies**      | Total jumlah reply (Komentar IG) pada story objek IG Media. Nilai tidak termasuk reply yang dibuat oleh pengguna di beberapa wilayah. Wilayah ini meliputi: Eropa mulai 1 Desember 2020 dan Jepang mulai 14 April 2021. Jika story dibuat oleh pengguna di salah satu wilayah ini, akan mengembalikan nilai 0. |
| **taps_forward** | Total jumlah tap untuk melihat foto atau video selanjutnya dari objek IG Media ini.                                                                                                                                                                                                                                  |
| **taps_back**    | Total jumlah tap untuk melihat foto atau video sebelumnya dari objek IG Media ini.                                                                                                                                                                                                                            |

##### Request Syntax 3rd-party pyfacebook

def get_media_insights(self, media_id, metrics, access_token=None, return_json=False)
        
Mengambil data media insights. Penjelasan parameter fungsi get_media_insights sebagai berikut, dengan tipe data List[Union[IgProInsight, dict]].
| Parameter    | Tipe Data                    | Keterangan                                                      |
|--------------|------------------------------|-----------------------------------------------------------------|
| media_id     | str                          | ID media yang ingin kita dapatkan datanya.                    |
| metrics      | Union[str, List, Tuple, Set] | String id yang dipisahkan koma untuk metrik yang perlu diambil. Kita juga dapat meneruskan ini dengan list, tuple, atau set dari id. <br />Catatan: Jenis media yang berbeda memiliki metrik yang berbeda. <br />Lihat selengkapnya: https://developers.facebook.com/docs/instagram-api/reference/media/insights#insights-2 |
| access_token | str                          | Token akses pengguna target. Jika tidak akan menggunakan token akses default. |
| return_json  | bool                         | Set ke false akan mengembalikan list instance IgProInsight. Atau kembalikan data json. Default adalah false.   |

#### IG User

Mewakili Akun Bisnis Instagram atau Akun Kreator Instagram. 

**GET /{ig-user-id}**
Mendapatkan fields dan edges pada Instagram Business atau Akun Kreator.

##### Persyaratan

| Tipe           | Deskripsi                                                                                                                                                                                                                                                                                                                                                        |
|----------------|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Aksen Token  | User.                                                                                                                                                                                                                                                                                                                                                              |
| Peran Bisnis | Jika kita meminta field **shopping_product_tag_eligibility** untuk tagging produk, pengguna aplikasi harus memiliki peran admin di Business Manager yang memiliki Instagram Shop dari Pengguna IG.                                                                                                                                                                        |
| Instagram Shop | Jika kita meminta field **shopping_product_tag_eligibility** untuk tagging produk, Pengguna IG harus memiliki Instagram Shop yang disetujui dengan katalog produk berisi produk.                                                                                                                                                                                 |
| Izin    | **instagram_basic** <br /> **pages_read_engagement** <br /> **pages_show_list** <br /> Jika pengguna aplikasi diberi peran di Halaman melalui Business Manager, kita juga memerlukan salah satu dari yang berikut: <br />**ads_management** <br /> **business_management** <br /> Jika kita meminta field **shopping_product_tag_eligibility** untuk pemberian tag produk, kita juga memerlukan: <br /> **catalog_management** <br /> **instagram_shopping_tag_products** <br /> |

##### Request Syntax

GET https://graph.facebook.com/{api-version}/{ig-user-id}
  <br />  &nbsp;&nbsp;&nbsp;&nbsp;?fields={fields}
  <br />  &nbsp;&nbsp;&nbsp;&nbsp;&access_token={access-token}

##### Parameter Path

| Placeholder   | Value                  |
|---------------|------------------------|
| **{api-version}** | Versi API.           |
| **{ig-used-id}** | Perlu. IG User ID. |

##### Parameter String Kueri

|      Key     |   Placeholder  |                       Value                       |
|:------------:|:--------------:|:-------------------------------------------------:|
| **access_token** | **{access-token}** | Perlu. Token akses pengguna dari pengguna aplikasi.           |
| **fields**       | **{fields}**       | List yang dipisahkan dengan tanda koma dari field IG User yang ingin dihasilkan oleh setiap IG User pada himpunan hasil.|

##### Fields
Field publik dapat dikembalikan oleh edge menggunakan ekspansi field.

| Field Nama                       | Deskripsi                                                                                                                      |
|----------------------------------|-----------------------------------------------------------------------------------------------------------------------------------|
| **biography** Public                 | Teks dari profil bio.                                                                                                                 |
| **id** <br /> Public                        |User ID dalam cakupan aplikasi.                                                                                                               |
| **ig_id**                            | User ID Instagram. Digunakan dengan Legacy Instagram API, sekarang sudah tidak digunakan lagi. Menggunakan id sebagai gantinya.                                                |
| **followers_count** <br /> Public           | Total jumlah Instagram user yang mengikuti user.                                                                  |
| **follows_count**                    | Total jumlah pengguna Instagram yang diikuti user.                                                                            |
| **media_count** <br /> Public               | Total jumlah Media IG yang dipublikasikan oleh user.                                                                                  |
| **name**                             | Nama profil.                                                                                                                   |
| **profile_picture_url**              | URL gambar profil.                                                                                                              |
| **shopping_product_tag_eligibility** | Mengembalikan nilai true jika pengguna aplikasi telah menyiapkan Instagram Shop dan karenanya memenuhi syarat untuk pemberian tag produk, jika tidak, mengembalikan nilai false. |
| **username** <br /> Public                  | Username dari profil.                                                                                                                 |
| **website** <br /> Public                   | URL dari laman profil.                                                                                                              |

##### Edges

| Edge                       | Deskripsi                                                                                                                   |
|----------------------------|-------------------------------------------------------------------------------------------------------------------------------|
| **business_discovery**         | Mendapatkan data tentang User IG Instagram Business atau Instagram Creator IG.                                                        |
| **content_publishing_limit**   | Merepresentasikan penggunaan penerbitan konten User IG saat ini.                                                                     |
| **insights**                   | Mewakili metrik interaksi sosial pada User IG.                                                                          |
| **live_media**                 | Merepresentasi kumpulan live video IG Media pada IG User.                                                                 |
| **media**                      | Merepresentasi kumpulan IG Media pada IG User.                                                                           |
| **media_publish**              | Mempublikasi IG Container di User ID Instagram Business.                                                                     |
| **mentions**                   | Create an IG Comment on an IG Comment or captioned IG Media that an IG User has been @mentioned in by another Instagram user. |
| **mentioned_comment**          | Get data on an IG Comment in which an IG User has been @mentioned by another Instagram user.                                  |
| **mentioned_media**            | Get data on an IG Media in which an IG User has been @mentioned in a caption by another Instagram user.                       |
| **recently_searched_hashtags** | Get IG Hashtags that an IG User has searched for within the last 7 days.                                                      |
| **stories**                    | Represents a collection of story IG Media objects on an IG User.                                                              |
| **tags**                       | Represents a collection of IG Media in which an IG User has been tagged by another Instagram user.                            |

##### Request Syntax 3rd-party pyfacebook

def get_user_info(self, user_id, fields=None, return_json=False)

Mengambil data pengguna ig dari user id. Penjelasan parameter fungsi get_user_info sebagai berikut, dengan tipe data Optional[IgProUser, dict].
| Parameter   | Tipe Data                    | Keterangan                                                      |
|-------------|------------------------------|-----------------------------------------------------------------|
| user_id     | str                          | Id untuk instagram business user yang ingin kita dapatkan datanya.                    |
| fields      | Optional[Union[str, List, Tuple, Set]] | String id yang dipisahkan koma untuk metrik yang perlu diambil. Kita juga dapat meneruskan ini dengan list, tuple, atau set dari id. |
| return_json | bool                         | Set ke false akan mengembalikan list instance IgProUser.    |

#### IG User Insights

Merepresentasi metrik interaksi sosial pada IG User.

**GET /{ig-user-id}/insights** <br />
Mengembalikan insights tentang IG User.

##### Limitasi
- Metrik **follower_count**, **online_followers**, dan semua **audience_\*** tidak tersedia di IG Users dengan followers kurang dari 100. 
- Data insights untuk metrik **online_followers** hanya tersedia selama 30 hari terakhir.
-  Jika data insights yang kita minta tidak ada atau saat ini tidak tersedia, API akan mengembalikan kumpulan data kosong, bukan 0 untuk masing-masing metrik.
- Metrik demografis hanya menampilkan 45 artis dengan performa teratas (misalnya untuk **audience_city**, hingga 45 kota dengan jumlah pengikut tertinggi dapat ditampilkan).
- Hanya viewers yang data demografisnya kami miliki yang digunakan dalam penghitungan metrik demografis.
- Menjumlahkan nilai metrik demografi dapat menghasilkan nilai yang kurang dari jumlah pengikut (lihat poin-poin sebelumnya).
- Metrik **audience_\*** tidak mendukung parameter range **since** dan **until**.
- Data yang digunakan untuk menghitung metrik mungkin tertunda hingga 48 jam.

##### Persyaratan

| Tipe          | Deskripsi                                                                                                                                                                                                            |
|---------------|------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Akses Token | User                                                                                                                                                                                                                   |
| Izin   | **instagram_basic** <br /> **instagram_manage_insights** <br /> **pages_read_engagement** <br /> **pages_show_list** <br /><br /> Jika pengguna aplikasi diberi peran di Halaman melalui Business Manager, kita juga memerlukan salah satu dari: **ads_management** <br /> **business_management** <br /> |

##### Request Syntax

GET https://graph.facebook.com/{api-version}/{ig-user-id}/insights
  <br />  &nbsp;&nbsp;&nbsp;&nbsp;?metric={metric}
  <br />  &nbsp;&nbsp;&nbsp;&nbsp;&period={period}
  <br />  &nbsp;&nbsp;&nbsp;&nbsp;&since={since}
  <br />  &nbsp;&nbsp;&nbsp;&nbsp;&until={until}
  <br />  &nbsp;&nbsp;&nbsp;&nbsp;&access_token={access-token}

##### Parameter Path

| Placeholder   | Value                  |
|---------------|------------------------|
| **{api-version}** | Versi API.           |
| **{ig-user-id}** | Perlu. IG User ID. |

##### Parameter String Kueri

| Parameter                              | Value                                                                                                                                                                                                                                                                                              |
|----------------------------------------|----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| **{access-token}**<br /> Required<br /> String         | Token Akses Pengguna dari pengguna aplikasi.                                                                                                                                                                                                                                                                  |
| **{metric}**<br /> Required<br /> Comma-separated list | Daftar Metrik yang dipisahkan koma yang ingin kita kembalikan. Jika meminta beberapa metrik, semuanya harus memiliki Periode kompatibel yang sama.                                                                                                                                                   |
| **{period}**<br /> Required<br /> String               | Periode yang kompatibel dengan metrik yang kita minta.                                                                                                                                                                                                                                   |
| **{since}**<br /> Unix timestamp                 | Digunakan bersamaan dengan **{until}** untuk mendefinisikan Range. Jika kita menghilangkan **since** dan **until**, API default ke range 2 hari: kemarin hingga hari ini. Catatan: Kursor paginasi (sebelum dan sesudahnya) mengambil window waktu berikutnya dari hasil, bukan kelompok hasil berikutnya dalam window waktu saat ini. |
| **{until}**<br /> Unix timestamp                 | Digunakan bersamaan dengan **{since}** untuk menentukan Range. Jika kita menghilangkan **since** dan **until**, API default ke range 2 hari: kemarin hingga hari ini. Catatan: Kursor paginasi (previous dan **next**) mengambil window waktu berikutnya dari hasil, bukan kelompok hasil berikutnya dalam window waktu saat ini. |

##### Metrik dan Periode

Metrik yang mendukung periode **lifetime** akan memiliki hasil yang dikembalikan dalam susunan periode 24 jam, dengan periode yang berakhir pada UTC−07:00. metrik **audience_\*** tidak mendukung parameter range **since** dan **until**.

| Metrik                | Periode Kompatibel  | Deskripsi                                                                                                                                                                                                                                                                                                                          |
|-----------------------|--------------------|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| audience_city         | lifetime           | Kota pengikut yang data demografisnya kita miliki. <br /><br /> - Tidak termasuk data hari ini. <br /> - Tidak tersedia di IG User dengan pengikut kurang dari 100. <br /> - Hanya 45 kota teratas dengan nilai tertinggi yang dikembalikan. <br /> - Tidak mendukung parameter **since** dan **until**. <br /> - Respons tidak menyertakan properti JSON **end_time**.                             |
| audience_country      | lifetime           | Negara pengikut yang data demografisnya kita miliki. <br /><br /> - Tidak termasuk data hari ini.<br /> - Tidak tersedia di IG User dengan pengikut kurang dari 100.<br /> - Hanya 45 negara teratas dengan nilai tertinggi yang dikembalikan.<br /> - Tidak mendukung parameter **since** dan **until**.<br /> - Respons tidak menyertakan properti JSON **end_time**.                       |
| audience_gender_age   | lifetime           | Distribusi gender dan usia pengikut yang data demografisnya kami miliki. Nilai yang mungkin: **M** (laki-laki), **F** (perempuan), **U** (tidak diketahui).<br /><br /> - Tidak termasuk data hari ini.<br /> - Tidak tersedia di IG User dengan pengikut kurang dari 100.<br /> - Tidak mendukung parameter **since** dan **until**.<br /> - Respons tidak menyertakan properti JSON **end_time**. |
| audience_locale       | lifetime           | Lokal menurut kode negara pengikut yang data demografisnya kita miliki.<br /><br /> - Tidak termasuk data hari ini.<br /> - Tidak tersedia di IG User dengan pengikut kurang dari 100. <br /> - Hanya 45 lokal teratas dengan nilai tertinggi yang dikembalikan. <br /> - Tidak mendukung parameter **since** dan **until**. <br /> - Respons tidak menyertakan properti JSON **end_time**.          |
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

##### Range

Edge ini mendukung paginasi berbasis waktu, sehingga kita dapat menyertakan parameter **since** dan **until** dengan Unix timestamps untuk menentukan range. Misalnya, untuk mendapatkan impression selama 28 hari — setiap hari selama 10 hari terakhir — kita dapat membuat Unix timestamps untuk 10 hari yang lalu dan hari ini, assign ke parameter **since** dan **until**, dan menyertakannya dalam permintaan kita: <br />
**metric=impressions&period=days_28&since=1501545600&until=1502493720**
<br />Parameter **since** dan **until** bersifat inklusif, sehingga jika range kita menyertakan hari yang belum berakhir (misalnya hari ini), kueri berikutnya sepanjang hari dapat mengembalikan nilai yang meningkat. Jika kita tidak menyertakan parameter **since** dan **until**, API akan default ke range 2 hari: kemarin sampai hari ini.

##### Request Syntax 3rd-party pyfacebook 

def get_user_insights(self, user_id, period, metrics, since=None, until=None, access_token=None, return_json=False)

Mengambil user insights data dari akun instagram business. Penjelasan parameter fungsi get_user_insights sebagai berikut, dengan tipe data List[Union[IgProInsight, dict]].
| Parameter    | Tipe Data                    | Keterangan                                                         |
|--------------|------------------------------|--------------------------------------------------------------------|
| user_id      | str                          | Id untuk instagram business user yang ingin kita dapatkan datanya.     |
| period       | str                          | Periode untuk data agregasi. Parameter yang diterima: lifetime, day, dan days_28.                                    |
| metrics      | Union[str, List, Tuple, Set] | String id yang dipisahkan koma untuk metrik yang perlu diambil. Kita juga dapat meneruskan ini dengan list, tuple, atau set dari id. <br/>Catatan: Beberapa metrik tidak sesuai dengan periode.  <br/>Lihat selengkapnya: https://developers.facebook.com/docs/instagram-api/reference/user/insights#metrics-periods|
| since        | Optional[int]                | Batas bawah rentang waktu untuk mengambil data. Perlu Unix timestamps. |
| until        | Optional[int]                | Batas atas rentang waktu untuk mengambil data. Perlu Unix timestamps. Rentang waktu tidak lebih dari 30 hari (2592000 detik). |
| access_token | str                          | Token akses pengguna target. Jika tidak akan menggunakan token akses default.    |
| return_json  | bool                         | Set ke false akan mengembalikan list instance IgProInsight.       |

#### IG User Business Discovery
Memungkinkan kita mendapatkan data tentang Pengguna Instagram Business atau Creator IG lainnya.

**GET /{ig-user-id}?fields=business_discovery.username({username})** <br />
Mengembalikan data tentang Pengguna Instagram Business atau Creator IG lainnya. Lakukan permintaan ini pada Pengguna Instagram Business atau Creator IG yang membuat kueri, dan identifikasi bisnis yang ditargetkan dengan parameter **username**.

##### Limitasi

Data tentang Instagram Business IG User yang dikenai pembatasan usia tidak akan dikembalikan. 

##### Parameter String Kueri
**{username}** (required) — Nama pengguna Instagram Business atau Creator IG User yang ingin kita dapatkan datanya.

##### Izin

Token akses Facebook User dengan izin berikut:
- **instagram_basic**
- **instagram_manage_insights**
- **pages_read_engagement** atau **pages_show_list**
<br />
Jika token berasal dari User yang peran Page diberikan melalui Business Manager, salah satu izin berikut juga diperlukan:
- ads_management
- pages_read_engagement
- business_management 

##### Ekspansi Field
Kita dapat menggunakan ekspansi field untuk mendapatkan field publik pada IG Useryang ditargetkan. Lihat referensi IG User untuk daftar kolom publik.

##### Request Syntax 3rd-party pyfacebook 

def discovery_user(self, username, fields=None, return_json=False)
                       
Mengambil info dasar pengguna bisnis lain berdasarkan username. Penjelasan parameter fungsi discovery_user sebagai berikut, dengan tipe data Union[IgProUser, dict].
| Parameter   | Tipe Data                    | Keterangan                                                      |
|-------------|------------------------------|-----------------------------------------------------------------|
| username     | str                          | Username untuk kita ingin mengambil data.                    |
| fields      | Union[str, List, Tuple, Set] | String id yang dipisahkan koma untuk fields data yang perlu diambil. Kita juga dapat meneruskan ini dengan list, tuple, atau set dari id. |
| return_json | bool                         | Set ke false akan mengembalikan list instance IgProUser. Atau mengembalikan data json. Default adalah false. |

#### IG Comment
Merupakan komentar di IG Media.

**GET /{ig-comment-id}?fields={fields}**<br />
Dapatkan field dan edges pada IG Comment.

##### Limitasi
- Permintaan tidak dapat dilakukan pada komentar yang ditemukan melalui Mentions API kecuali jika permintaan dibuat oleh pemilik comment. Sebagai gantinya, gunakan simpul Mentioned Comment.
- Komentar pada media yang dibatasi usia tidak dikembalikan.
- Komentar yang dibuat oleh IG User yang telah dibatasi oleh pengguna aplikasi tidak akan dikembalikan kecuali IG User tersebut tidak dibatasi dan Comment tersebut disetujui.
- Komentar pada video langsung Media IG hanya dapat dibaca saat IG Media tempat komentar dibuat sedang disiarkan.

##### Persyaratan

| Tipe          | Deskripsi                                                                                                                                                                                                            |
|---------------|------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Akses Token | User                                                                                                                                                                                                                   |
| Izin   | **instagram_basic** <br /> **pages_read_engagement** <br /> **pages_show_list** <br /><br /> Jika pengguna aplikasi diberi peran di Halaman melalui Business Manager, kita juga memerlukan salah satu dari: **ads_management** <br /> **business_management** <br /> | 

##### Request Syntax
GET https://graph.facebook.com/{api-version}/{ig-comment-id}
  <br />  &nbsp;&nbsp;&nbsp;&nbsp;?fields={fields}
  <br />  &nbsp;&nbsp;&nbsp;&nbsp;&access_token={access-token}

##### Parameter Path

| Placeholder   | Value                  |
|---------------|------------------------|
| **{api-version}** | Versi API.           |
| **{ig-comment-id}** | Perlu. IG Comment ID. |

##### Parameter String Kueri
| Key          | Placeholder    | Value                                                                                              |
|--------------|----------------|----------------------------------------------------------------------------------------------------|
| **access_token** | **{access-token}** | Required. Token akses pengguna dari pengguna aplikasi.                                                            |
| **fields**       | **{fields}**       | Daftar fields dari IG Comment yang dipisahkan koma yang ingin kita kembalikan untuk setiap IG Comment di himpunan hasil. |                

##### Fields

| Nama Field | Deskripsi                                                                                                                                                                                                    |   |
|------------|----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|---|
| **from**       | Objek yang berisi: <br />**id** — IGSID pengguna Instagram yang membuat IG Comment. <br />**username** — Nama pengguna dari pengguna Instagram yang membuat IG Comment.                                                       |   |
| **hidden**     | Mengindikasi apakah komentar telah disembunyikan (**true**) atau tidak (**false**).                                                                                                                                                    |   |
| **id**         | IG Comment ID.                                                                                                                                                                                                 |   |
| **like_count** | Jumlah suka di IG Comment.                                                                                                                                                                             |   |
| **media**      | Objek yang berisi: <br /> **id** — ID dari IG Media tempat IG Comment dibuat. <br /> **media_product_type** — Permukaan IG Media yang dipublikasikan (yaitu tempat IG Media muncul) tempat IG Comment dibuat. |   |
| **parent_id**  | ID dari parent IG Comment jika komentar ini dibuat di IG Comment lain (yaitu balasan untuk komentar lain).                                                                                                |   |
| **replies**    | Daftar balasan (IG Comment) dibuat di IG Comment.                                                                                                                                                        |   |
| **text**       | teks di IG Comment.                                                                                                                                                                                               |   |
| **timestamp**  | Timestamp berformat ISO 8601 yang menunjukkan kapan IG Comment dibuat. Contoh: 2017-05-19T23:27:28+0000.                                                                                                        |   |
| **user**       | ID dari IG User yang membuat IG Comment. Hanya dikembalikan jika pengguna aplikasi membuat IG Comment, jika tidak, nama pengguna akan dikembalikan.                                                                   |   |
| **username**   | Username pengguna Instagram yang membuat IG Comment.                                                                                                                                                         |   |

##### Edges

| Edge    | Deskripsi                                                                         |
|---------|-------------------------------------------------------------------------------------|
| **replies** | Dapatkan daftar komentar IG di IG Comment; Buat Komentar IG di IG Comment. |

##### Request Syntax 3rd-party pyfacebook

def get_comments_by_media(self, media_id, fields=None, count=10, limit=10, include_reply=True, return_json=False)

Ambil data komentar untuk id media yang diberikan. Penjelasan parameter fungsi get_comments_by_media sebagai berikut, dengan tipe data List[Union[IgProComment, dict]].
| Parameter     | Tipe Data                              | Keterangan |
|---------------|----------------------------------------|------------|
| media_id      | str                                    | Id media yang ingin kita dapatkan data komentarnya. |
| fields        | Optional[Union[str, List, Tuple, Set]] | String id yang dipisahkan koma untuk fields data yang perlu diambil. Kita juga dapat meneruskan ini dengan list, tuple, atau set dari id. |
| count         | Optional[int]                          | Jumlah komentar yang kita inginkan. Default adalah 10. Jika perlu mendapatkan semua, set ini dengan None. |
| limit         | int                                    | Setiap permintaan mengambil hitungan komentar dari api. Untuk komentar sebaiknya tidak lebih dari 50. |
| include_reply | bool                                   | Set ke True akan menyertakan balasan ke komentar. Default adalah benar. |
| return_json   | bool                                   | Set ke false akan mengembalikan list instance IgProComment. Atau mengembalikan data json. Default adalah false. |

#### IG Comment Replies

Merupakan kumpulan Komentar IG pada IG Comment untuk mendapatkan semua balasan pada Komentar.<br />
**GET /{ig-comment-id}/replies** <br />
Mengembalikan daftar komentar IG pada IG Comment.

##### Limitasi

Kita tidak bisa mendapatkan balasan untuk komentar yang telah dihapus.

##### Persyaratan

Token akses dari User yang membuat komentar, dengan izin berikut:
- **instagram_basic**
- **pages_show_list**
- **page_read_engagement**

Jika token berasal dari User yang peran halamannya diberikan melalui Business Manager, salah satu izin berikut juga diperlukan:
- **ads_management**
- **pages_read_engagement**
- **business_management**


##### Request Syntax 3rd-party pyfacebook

def get_replies_info(self, reply_ids, fields=None, return_json=False)

Mengambil info reply oleh reply id. Penjelasan parameter fungsi get_replies_info sebagai berikut, dengan tipe data dict.

| Parameter   | Tipe Data                    | Keterangan                                                      |
|-------------|------------------------------|-----------------------------------------------------------------|
| user_id     | Union[str, List, Tuple, Set] | Id untuk instagram business user yang ingin kita dapatkan datanya.                    |
| fields      | Optional[Union[str, List, Tuple, Set]] | String id yang dipisahkan koma untuk field data yang perlu diambil. Kita juga dapat meneruskan ini dengan list, tuple, atau set dari id. |
| return_json | bool                         | Set ke false akan mengembalikan list instance IgProComment. Atau mengembalikan data json. Default adalah false. |
