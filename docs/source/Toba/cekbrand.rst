CekBrand
--------

System Database
~~~~~~~~~~~~~~~

Schema Instagram
^^^^^^^^^^^^^^^^

Berisi tentang data yang diambil dari instagram seperti data user, data
media, dan data-data insight dari API instagram.

.. figure:: image/instagram.png
   :alt: ER Diagram Instagram

   ER Diagram Instagram

**user**
''''''''

Berisi tentang data user yang diambil dari instagram.

+--------+-----+----+---------------------------------------------+---+
| Nama   | T   | Ti | Isi                                         | C |
| Kolom  | ipe | pe |                                             | a |
|        |     | Da |                                             | t |
|        |     | ta |                                             | a |
|        |     |    |                                             | t |
|        |     |    |                                             | a |
|        |     |    |                                             | n |
+========+=====+====+=============================================+===+
| id     | P   | v  | Nomor ID User                               |   |
|        | rim | ar |                                             |   |
|        | ary | ch |                                             |   |
|        | Key | ar |                                             |   |
+--------+-----+----+---------------------------------------------+---+
| us     | -   | v  | Username instagram                          |   |
| ername |     | ar |                                             |   |
|        |     | ch |                                             |   |
|        |     | ar |                                             |   |
+--------+-----+----+---------------------------------------------+---+
| name   | -   | v  | Display name user                           |   |
|        |     | ar |                                             |   |
|        |     | ch |                                             |   |
|        |     | ar |                                             |   |
+--------+-----+----+---------------------------------------------+---+
| bio    | -   | v  | Biography user                              |   |
| graphy |     | ar |                                             |   |
|        |     | ch |                                             |   |
|        |     | ar |                                             |   |
+--------+-----+----+---------------------------------------------+---+
| p      | -   | v  | Alamat Url Profil Picture                   |   |
| rofile |     | ar |                                             |   |
| _pictu |     | ch |                                             |   |
| re_url |     | ar |                                             |   |
+--------+-----+----+---------------------------------------------+---+
| w      | -   | v  | Alamat website user                         |   |
| ebsite |     | ar |                                             |   |
|        |     | ch |                                             |   |
|        |     | ar |                                             |   |
+--------+-----+----+---------------------------------------------+---+
| socia  | F   | i  | Id Facebook fans page                       |   |
| l_acco | ore | nt |                                             |   |
| unt_id | ign |    |                                             |   |
|        | Key |    |                                             |   |
+--------+-----+----+---------------------------------------------+---+
| updat  | -   | t  | Timestamp kapan data di update              |   |
| ed_tim |     | im |                                             |   |
| estamp |     | es |                                             |   |
|        |     | ta |                                             |   |
|        |     | mp |                                             |   |
+--------+-----+----+---------------------------------------------+---+
| has_pr | -   | bo | Keterangan apakah user bermasalah           |   |
| oblems |     | ol |                                             |   |
+--------+-----+----+---------------------------------------------+---+
| is_    | -   | bo | Keterangan apakah user id tersebut valid,   |   |
| userid |     | ol | ditandai dengan bisa/tidaknya akun tersebut |   |
| _valid |     |    | mereturn data                               |   |
+--------+-----+----+---------------------------------------------+---+

**user_data**
'''''''''''''

Berisi tentang data user dengan atribut sosial media di instagram
seperti jumlah follower, jumlah media (foto/video).

+---------------+-------------+-----------+---------------+---------+
| Nama Kolom    | Tipe        | Tipe Data | Isi           | Catatan |
+===============+=============+===========+===============+=========+
| id            | Primary Key | int       | Nomor Id      |         |
+---------------+-------------+-----------+---------------+---------+
| user_id       | Foreign Key | varchar   | Nomor ID pada |         |
|               |             |           | tabel user    |         |
+---------------+-------------+-----------+---------------+---------+
| fo            | -           | int       | Jumlah user   |         |
| llowers_count |             |           | follower      |         |
+---------------+-------------+-----------+---------------+---------+
| follows_count | -           | int       | Jumlah user   |         |
|               |             |           | following     |         |
+---------------+-------------+-----------+---------------+---------+
| media_count   | -           | int       | Jumlah media  |         |
|               |             |           | yang diupload |         |
|               |             |           | user          |         |
+---------------+-------------+-----------+---------------+---------+
| upda          | -           | timestamp | Timestamp     | Unique  |
| ted_timestamp |             |           | kapan data di |         |
|               |             |           | update        |         |
+---------------+-------------+-----------+---------------+---------+
| datestamp     | -           | date      | Datestamp     | Unique  |
|               |             |           | kapan data di |         |
|               |             |           | update        |         |
+---------------+-------------+-----------+---------------+---------+
| followers     | -           | int4      | Pertumbuhan   |         |
| _count_growth |             |           | jumlah        |         |
|               |             |           | followers     |         |
+---------------+-------------+-----------+---------------+---------+
| media         | -           | int4      | Pertumbuhan   |         |
| _count_growth |             |           | jumlah        |         |
|               |             |           | me            |         |
|               |             |           | dia/postingan |         |
+---------------+-------------+-----------+---------------+---------+

**user_competitor**
'''''''''''''''''''

Berisi tentang data id user dengan id user competitor.

+-------+------+-----+--------------------------------------------+----+
| Nama  | Tipe | T   | Isi                                        | C  |
| Kolom |      | ipe |                                            | at |
|       |      | D   |                                            | at |
|       |      | ata |                                            | an |
+=======+======+=====+============================================+====+
| id    | Pri  | ser | Nomor Id                                   |    |
|       | mary | ial |                                            |    |
|       | Key  |     |                                            |    |
+-------+------+-----+--------------------------------------------+----+
| us    | For  | v   | Nomor ID yang merujuk pada table user      |    |
| er_id | eign | arc |                                            |    |
|       | Key  | har |                                            |    |
+-------+------+-----+--------------------------------------------+----+
| com   | For  | v   | Nomor ID yang merujuk pada table user yang |    |
| petit | eign | arc | merupakan kompetitor dari suatu user       |    |
| or_id | Key  | har |                                            |    |
+-------+------+-----+--------------------------------------------+----+

**user_insight_audience_city**
''''''''''''''''''''''''''''''

Berisi tentang data insight kota & provinai dari follower suatu user.

+------------+-------------+-----------+----------------+---------+
| Nama Kolom | Tipe        | Tipe Data | Isi            | Catatan |
+============+=============+===========+================+=========+
| id         | Primary Key | bigserial | Nomor ID       |         |
+------------+-------------+-----------+----------------+---------+
| user_id    | Foreign Key | varchar   | Nomor ID yang  |         |
|            |             |           | merujuk pada   |         |
|            |             |           | table user     |         |
+------------+-------------+-----------+----------------+---------+
| city       | -           | varchar   | Nama Kota      |         |
+------------+-------------+-----------+----------------+---------+
| province   | -           | varchar   | Nama Province  |         |
+------------+-------------+-----------+----------------+---------+
| value      | -           | int       | Jumlah         |         |
|            |             |           | follower       |         |
|            |             |           | dengan kota    |         |
|            |             |           | dan provinsi   |         |
|            |             |           | tertentu       |         |
+------------+-------------+-----------+----------------+---------+

**user_insight_audience_country**
'''''''''''''''''''''''''''''''''

Berisi tentang data insight sebaran negara follower suatu user.

+---------------+-------------+-----------+---------------+---------+
| Nama Kolom    | Tipe        | Tipe Data | Isi           | Catatan |
+===============+=============+===========+===============+=========+
| id            | Primary Key | bigserial | Nomor ID      |         |
+---------------+-------------+-----------+---------------+---------+
| user_id       | Foreign Key | varchar   | Nomor ID yang |         |
|               |             |           | merujuk pada  |         |
|               |             |           | table user    |         |
+---------------+-------------+-----------+---------------+---------+
| country_code  | -           | varchar   | Kode Negara   |         |
+---------------+-------------+-----------+---------------+---------+
| value         | -           | int       | Jumlah        |         |
|               |             |           | follower      |         |
|               |             |           | dengan negara |         |
|               |             |           | tertentu      |         |
+---------------+-------------+-----------+---------------+---------+
| end_time      | -           | timestamp | Datestamp     |         |
|               |             |           | data update   |         |
|               |             |           | dari facebook |         |
+---------------+-------------+-----------+---------------+---------+
| upda          | -           | timestamp | Timestamp     |         |
| ted_timestamp |             |           | kapan data di |         |
|               |             |           | update        |         |
+---------------+-------------+-----------+---------------+---------+

**user_insight_audience_gender_age**
''''''''''''''''''''''''''''''''''''

Berisi tentang data insight sebaran jenis kelamin dan range usia
follower dari suatu user. \| Nama Kolom \| Tipe \| Tipe Data \| Isi \|
Catatan \| \|——————-|————-|———–|————————————————————–|———\| \| id \|
Primary Key \| bigserial \| Nomor ID \| \| \| user_id \| Foreign Key \|
varchar \| Nomor ID yang merujuk pada table user \| \| \| gender \| - \|
varchar \| Jenis kelamin user \| \| \| age \| - \| varchar \| Range usia
user \| \| \| value \| - \| int \| Jumlah follower dengan jenis kelamin
dan range usia tertentu \| \| \| end_time \| - \| timestamp \| Datestamp
data update dari facebook \| \| \| updated_timestamp \| - \| timestamp
\| Timestamp kapan data di update \| \|

**user_insight_audience_locale**
''''''''''''''''''''''''''''''''

Berisi tentang data insight sebaran *ISO Language Code* follower dari
suatu user.

+---------------+-------------+-----------+---------------+---------+
| Nama Kolom    | Tipe        | Tipe Data | Isi           | Catatan |
+===============+=============+===========+===============+=========+
| id            | Primary Key | bigserial | Nomor ID      |         |
+---------------+-------------+-----------+---------------+---------+
| user_id       | Foreign Key | varchar   | Nomor ID yang |         |
|               |             |           | merujuk pada  |         |
|               |             |           | table user    |         |
+---------------+-------------+-----------+---------------+---------+
| locale_code   | -           | varchar   | Kode Bahasa   |         |
+---------------+-------------+-----------+---------------+---------+
| value         | -           | int       | Jumlah        |         |
|               |             |           | follower      |         |
|               |             |           | dengan kode   |         |
|               |             |           | bahasa        |         |
|               |             |           | tertentu      |         |
+---------------+-------------+-----------+---------------+---------+
| end_time      | -           | timestamp | Datestamp     |         |
|               |             |           | data update   |         |
|               |             |           | dari facebook |         |
+---------------+-------------+-----------+---------------+---------+
| upda          | -           | timestamp | Timestamp     |         |
| ted_timestamp |             |           | kapan data di |         |
|               |             |           | update        |         |
+---------------+-------------+-----------+---------------+---------+

**user_insight_impressions**
''''''''''''''''''''''''''''

Berisi tentang data insight impression follower dari suatu user.

+-------------+-------------+-----------+-------------+-------------+
| Nama Kolom  | Tipe        | Tipe Data | Isi         | Catatan     |
+=============+=============+===========+=============+=============+
| id          | Primary Key | bigserial | Nomor ID    |             |
+-------------+-------------+-----------+-------------+-------------+
| user_id     | Foreign Key | varchar   | Nomor ID    |             |
|             |             |           | yang        |             |
|             |             |           | merujuk     |             |
|             |             |           | pada table  |             |
|             |             |           | user        |             |
+-------------+-------------+-----------+-------------+-------------+
| period      | -           | varchar   | Periode     | [Day, Week, |
|             |             |           | Perhitungan | Day28]      |
|             |             |           | Impressions |             |
+-------------+-------------+-----------+-------------+-------------+
| value       | -           | int       | Nilai       |             |
|             |             |           | Impression  |             |
|             |             |           | user        |             |
+-------------+-------------+-----------+-------------+-------------+
| end_time    | -           | timestamp | Datestamp   |             |
|             |             |           | data update |             |
|             |             |           | dari        |             |
|             |             |           | facebook    |             |
+-------------+-------------+-----------+-------------+-------------+
| update      | -           | timestamp | Timestamp   |             |
| d_timestamp |             |           | kapan data  |             |
|             |             |           | di update   |             |
+-------------+-------------+-----------+-------------+-------------+

**user_insight_online_follower**
''''''''''''''''''''''''''''''''

Berisi tentang data insight sebaran jam online follower dari suatu user.

+---------------+-------------+-----------+---------------+---------+
| Nama Kolom    | Tipe        | Tipe Data | Isi           | Catatan |
+===============+=============+===========+===============+=========+
| id            | Primary Key | int       | Nomor ID      |         |
+---------------+-------------+-----------+---------------+---------+
| user_id       | Foreign Key | varchar   | Nomor ID yang |         |
|               |             |           | merujuk pada  |         |
|               |             |           | table user    |         |
+---------------+-------------+-----------+---------------+---------+
| hour          | -           | int       | Rentang Jam   |         |
|               |             |           | dari 0-24     |         |
+---------------+-------------+-----------+---------------+---------+
| value         | -           | int       | Nilai jumlah  |         |
|               |             |           | online        |         |
|               |             |           | follower pada |         |
|               |             |           | jam tertentu  |         |
+---------------+-------------+-----------+---------------+---------+
| end_time      | -           | timestamp | Datestamp     |         |
|               |             |           | data update   |         |
|               |             |           | dari facebook |         |
+---------------+-------------+-----------+---------------+---------+
| upda          | -           | timestamp | Timestamp     |         |
| ted_timestamp |             |           | kapan data di |         |
|               |             |           | update        |         |
+---------------+-------------+-----------+---------------+---------+

**user_insight_reach**
''''''''''''''''''''''

Berisi tentang data insight nilai reach dari suatu user.

+---------+------+-----+----------------------------------+-----------+
| Nama    | Tipe | T   | Isi                              | Catatan   |
| Kolom   |      | ipe |                                  |           |
|         |      | D   |                                  |           |
|         |      | ata |                                  |           |
+=========+======+=====+==================================+===========+
| id      | Pri  | big | Nomor ID                         |           |
|         | mary | ser |                                  |           |
|         | Key  | ial |                                  |           |
+---------+------+-----+----------------------------------+-----------+
| user_id | For  | v   | Nomor ID yang merujuk pada table |           |
|         | eign | arc | user                             |           |
|         | Key  | har |                                  |           |
+---------+------+-----+----------------------------------+-----------+
| period  | -    | v   | Periode Perhitungan Reach        | [Day,     |
|         |      | arc |                                  | Week,     |
|         |      | har |                                  | Day28]    |
+---------+------+-----+----------------------------------+-----------+
| value   | -    | int | Jumlah nilai Reach user          |           |
+---------+------+-----+----------------------------------+-----------+
| e       | -    | tim | Datestamp data dihitung dari     |           |
| nd_time |      | est | tanggal berapa (dari facebook)   |           |
|         |      | amp |                                  |           |
+---------+------+-----+----------------------------------+-----------+
| upd     | -    | tim | Timestamp kapan data di update   |           |
| ated_ti |      | est |                                  |           |
| mestamp |      | amp |                                  |           |
+---------+------+-----+----------------------------------+-----------+

**media**
'''''''''

Berisi tentang data media (foto/video) setiap user.

+-------------+-------------+-------------+-------------+-------------+
| Nama Kolom  | Tipe        | Tipe Data   | Isi         | Catatan     |
+=============+=============+=============+=============+=============+
| id          | Primary Key | varchar     | Nomor ID    | Unique      |
+-------------+-------------+-------------+-------------+-------------+
| user_id     | Foreign Key | varchar     | Nomor ID    |             |
|             |             |             | yang        |             |
|             |             |             | merujuk     |             |
|             |             |             | pada table  |             |
|             |             |             | user        |             |
+-------------+-------------+-------------+-------------+-------------+
| permalink   | -           | varchar     | Alamat url  |             |
|             |             |             | media       |             |
+-------------+-------------+-------------+-------------+-------------+
| media_type  | -           | varchar     | Tipe media  | [IMAGE,     |
|             |             |             | yang        | VIDEO,      |
|             |             |             | diupload    | CAROUSEL    |
|             |             |             |             | ALBUM]      |
+-------------+-------------+-------------+-------------+-------------+
| timestamp   | -           | timestamptz | Timestamp   |             |
|             |             |             | kapan data  |             |
|             |             |             | di upload   |             |
|             |             |             | di          |             |
|             |             |             | instagram   |             |
+-------------+-------------+-------------+-------------+-------------+
| username    | -           | varchar     | Username di |             |
|             |             |             | instagram   |             |
+-------------+-------------+-------------+-------------+-------------+
| caption     |             | text        | Text        |             |
|             |             |             | caption     |             |
|             |             |             | pada suatu  |             |
|             |             |             | media       |             |
|             |             |             | (p          |             |
|             |             |             | hoto/video) |             |
+-------------+-------------+-------------+-------------+-------------+
| is_comm     |             | bool        | Boolean     |             |
| ent_enabled |             |             | apakah      |             |
|             |             |             | comment     |             |
|             |             |             | aktif /     |             |
|             |             |             | tidak       |             |
+-------------+-------------+-------------+-------------+-------------+
| com         |             | int         | Jumlah      |             |
| ments_count |             |             | komentar    |             |
|             |             |             | pada suatu  |             |
|             |             |             | media       |             |
+-------------+-------------+-------------+-------------+-------------+
| like_count  |             | int         | Jumlah Like |             |
|             |             |             | pada suatu  |             |
|             |             |             | media       |             |
+-------------+-------------+-------------+-------------+-------------+
| media_url   |             | varchar     | Alamat url  |             |
|             |             |             | media       |             |
+-------------+-------------+-------------+-------------+-------------+
| th          |             | varchar     | Alamat url  |             |
| umbnail_url |             |             | thumbnail   |             |
|             |             |             | image       |             |
+-------------+-------------+-------------+-------------+-------------+
| shortcode   |             | varchar     | Short code  |             |
|             |             |             | untuk url   |             |
+-------------+-------------+-------------+-------------+-------------+
| owner_id    |             | varchar     | Nomor ID    |             |
|             |             |             | yang sama   |             |
|             |             |             | dengan User |             |
|             |             |             | ID          |             |
+-------------+-------------+-------------+-------------+-------------+
| m           |             | varchar     | List Hastag |             |
| edia_hastag |             |             | yang        |             |
|             |             |             | dipakai     |             |
|             |             |             | pada suatu  |             |
|             |             |             | media       |             |
+-------------+-------------+-------------+-------------+-------------+
| i           |             | bool        | Boolean     |             |
| s_archieved |             |             | apakah      |             |
|             |             |             | media di    |             |
|             |             |             | archieved   |             |
|             |             |             | atau tidak  |             |
+-------------+-------------+-------------+-------------+-------------+
| update      |             | timestamptz | Timestamp   |             |
| d_timestamp |             |             | kapan data  |             |
|             |             |             | di update   |             |
+-------------+-------------+-------------+-------------+-------------+
| datestamp   |             | date        | Tanggal     |             |
|             |             |             | kapan data  |             |
|             |             |             | di update   |             |
+-------------+-------------+-------------+-------------+-------------+

**media_comment**
'''''''''''''''''

Berisi tentang data komentar pada media (foto/video) setiap user.

+--------------+-------------+------------+--------------+---------+
| Nama Kolom   | Tipe        | Tipe Data  | Isi          | Catatan |
+==============+=============+============+==============+=========+
| id           | Primary Key | varchar    | Nomor ID     | Unique  |
+--------------+-------------+------------+--------------+---------+
| username     |             | varchar    | Username     |         |
|              |             |            | yang         |         |
|              |             |            | melakukan    |         |
|              |             |            | komen        |         |
+--------------+-------------+------------+--------------+---------+
| media_id     | Foreign Key | varchar    | Nomor ID     |         |
|              |             |            | yang merujuk |         |
|              |             |            | pada table   |         |
|              |             |            | media        |         |
+--------------+-------------+------------+--------------+---------+
| text         | -           | text       | Text         |         |
|              |             |            | komentar     |         |
|              |             |            | dari suatu   |         |
|              |             |            | media        |         |
+--------------+-------------+------------+--------------+---------+
| timestamp    | -           | timestampz | Waktu        |         |
|              |             |            | komentar     |         |
|              |             |            | pada suatu   |         |
|              |             |            | media        |         |
+--------------+-------------+------------+--------------+---------+
| like_count   | -           | int4       | Jumlah Like  |         |
|              |             |            | pada suatu   |         |
|              |             |            | komentar     |         |
+--------------+-------------+------------+--------------+---------+
| hidden       | -           | bool       | Boolean      |         |
|              |             |            | apakah       |         |
|              |             |            | komentar di  |         |
|              |             |            | sembunyikan  |         |
|              |             |            | atau tidak   |         |
+--------------+-------------+------------+--------------+---------+
| updat        |             | timestampz | Timestamp    |         |
| ed_timestamp |             |            | kapan data   |         |
|              |             |            | di update    |         |
+--------------+-------------+------------+--------------+---------+

**media_like_comment**
''''''''''''''''''''''

Berisi tentang data history jumlah like dan komen media setiap user.

+--------------+-------------+------------+--------------+---------+
| Nama Kolom   | Tipe        | Tipe Data  | Isi          | Catatan |
+==============+=============+============+==============+=========+
| id           | Primary Key | varchar    | Nomor ID     |         |
+--------------+-------------+------------+--------------+---------+
| media_id     | Foreign Key | varchar    | Nomor ID     | Unique  |
|              |             |            | yang merujuk |         |
|              |             |            | pada table   |         |
|              |             |            | media        |         |
+--------------+-------------+------------+--------------+---------+
| like_count   | -           | int4       | Jumlah Like  |         |
|              |             |            | pada suatu   |         |
|              |             |            | komentar     |         |
+--------------+-------------+------------+--------------+---------+
| co           | -           | int4       | Jumlah komen |         |
| mments_count |             |            | pada suatu   |         |
|              |             |            | media        |         |
+--------------+-------------+------------+--------------+---------+
| updat        |             | timestampz | Timestamp    |         |
| ed_timestamp |             |            | kapan data   |         |
|              |             |            | di update    |         |
+--------------+-------------+------------+--------------+---------+
| datestamp    |             | timestampz | Tanggal      | Unique  |
|              |             |            | kapan data   |         |
|              |             |            | di update    |         |
+--------------+-------------+------------+--------------+---------+
| comments_    |             | int4       | Pertumbuhan  |         |
| count_growth |             |            | jumlah komen |         |
+--------------+-------------+------------+--------------+---------+
| like_        |             | int4       | Pertumbuhan  |         |
| count_growth |             |            | jumlah like  |         |
+--------------+-------------+------------+--------------+---------+

**media_insight**
'''''''''''''''''

Berisi tentang data insight seperti engagement, impressions, reach, dan
jumlah saved pada media (foto/video).

+-------+----+----+--------------------------+-------------------------+
| Nama  | Ti | Ti | Isi                      | Catatan                 |
| Kolom | pe | pe |                          |                         |
|       |    | Da |                          |                         |
|       |    | ta |                          |                         |
+=======+====+====+==========================+=========================+
| id    | P  | v  | Nomor ID                 |                         |
|       | ri | ar |                          |                         |
|       | ma | ch |                          |                         |
|       | ry | ar |                          |                         |
|       | K  |    |                          |                         |
|       | ey |    |                          |                         |
+-------+----+----+--------------------------+-------------------------+
| med   | F  | v  | Nomor ID yang merujuk    | Unique                  |
| ia_id | or | ar | pada table media         |                         |
|       | ei | ch |                          |                         |
|       | gn | ar |                          |                         |
|       | K  |    |                          |                         |
|       | ey |    |                          |                         |
+-------+----+----+--------------------------+-------------------------+
| m     | -  | v  | metric perhitungan suatu | [Engagement,            |
| etric |    | ar | media seperti            | Impressions, Reach,     |
|       |    | ch | engagement, reach, dll.  | Saved, Video_Views],    |
|       |    | ar |                          | Unique                  |
+-------+----+----+--------------------------+-------------------------+
| value | -  | i  | Nilai pada setiap setiap |                         |
|       |    | nt | metric                   |                         |
+-------+----+----+--------------------------+-------------------------+
| up    | -  | ti | Timestamp kapan data di  |                         |
| dated |    | me | update                   |                         |
| _time |    | st |                          |                         |
| stamp |    | am |                          |                         |
|       |    | pz |                          |                         |
+-------+----+----+--------------------------+-------------------------+
| date  | -  | da | Date kapan data di       | Unique                  |
| stamp |    | te | update                   |                         |
+-------+----+----+--------------------------+-------------------------+

**instagram_tokens**
''''''''''''''''''''

Berisi tentang data token instagram pada setiap user.

+--------------+-------------+-------------+--------------+---------+
| Nama Kolom   | Tipe        | Tipe Data   | Isi          | Catatan |
+==============+=============+=============+==============+=========+
| user_id      | Primary Key | varchar     | Nomor ID     |         |
+--------------+-------------+-------------+--------------+---------+
| token        | -           | text        | Token untuk  |         |
|              |             |             | autentikasi  |         |
|              |             |             | dengan       |         |
|              |             |             | instagram    |         |
+--------------+-------------+-------------+--------------+---------+
| token_secret | -           | text        | Secret Token |         |
+--------------+-------------+-------------+--------------+---------+
| expired_at   | -           | timestamptz | Waktu        |         |
|              |             |             | kadaluarsa   |         |
|              |             |             | token        |         |
+--------------+-------------+-------------+--------------+---------+

**fetch_catalogue**
'''''''''''''''''''

Berisi tentang data fetch.

========== =========== ========= ========== =======
Nama Kolom Tipe        Tipe Data Isi        Catatan
========== =========== ========= ========== =======
fetch_id   Primary Key int       Nomor ID   
fetch_name -           varchar   Nama Fetch 
========== =========== ========= ========== =======

**user_insight_visitor**
''''''''''''''''''''''''

Berisi data nilai insight visitor dengan perhitungan nilai pada hari ini
dibandingkan dengan nilai 7 hari atau 28 hari yang lalu untuk setiap
user.

+--------------+-------------+-------------+--------------+---------+
| Nama Kolom   | Tipe        | Tipe Data   | Isi          | Catatan |
+==============+=============+=============+==============+=========+
| user_id      | Foreign Key | varchar     | Nomor ID     |         |
|              |             |             | yang merujuk |         |
|              |             |             | pada table   |         |
|              |             |             | user         |         |
+--------------+-------------+-------------+--------------+---------+
| value        | -           | int4        | Jumlah       |         |
|              |             |             | visitor      |         |
+--------------+-------------+-------------+--------------+---------+
| end_time     | -           | timestamptz | Periode      |         |
|              |             |             | waktu        |         |
|              |             |             | selesai      |         |
|              |             |             | perhitungan  |         |
|              |             |             | visitor      |         |
+--------------+-------------+-------------+--------------+---------+
| datestamp    | -           | varchar     | Tanggal      | Unique  |
|              |             |             | kapan data   |         |
|              |             |             | di update    |         |
+--------------+-------------+-------------+--------------+---------+
| id           | Primary Key | bigserial   | Nomor ID     | Unique  |
+--------------+-------------+-------------+--------------+---------+
| updat        | -           | timestamptz | Timestamp    |         |
| ed_timestamp |             |             | kapan data   |         |
|              |             |             | di update    |         |
+--------------+-------------+-------------+--------------+---------+

Schema Toba_Cek_Insta
^^^^^^^^^^^^^^^^^^^^^

Berisi tentang data olahan analytics dari data awal instagram.

.. figure:: image/toba_cek_insta.png
   :alt: ER Diagram Instagram

   ER Diagram Instagram

**user_insight_engagement**
'''''''''''''''''''''''''''

Berisi data nilai engagement yang diperoleh dari penambahan jumlah like
dan jumlah comment untuk setiap user dengan periode waktu 7 hari dan 28
hari. \| Nama Kolom \| Tipe \| Tipe Data \| Isi \| Catatan \|
\|——————-|————-|———–|—————————————————|—————–\| \| id \| Primary Key \|
serial \| Nomor ID \| \| \| user_id \| Foreign Key \| varchar \| Nomor
ID yang merujuk pada table user \| Unique \| \| engagement \| - \| int
\| Nilai engagement untuk suatu user \| \| \| likes_count \| - \| int \|
Jumlah like pada suatu user \| \| \| comments_count \| - \| int \|
Jumlah komentar pada suatu user \| \| \| timeframe \| - \| int \|
Periode waktu (dalam hari) perhitungan engagement \| [7, 28], Unique \|
\| datestamp \| - \| date \| datestamp kapan data di update \| Unique \|
\| updated_timestamp \| - \| timestamp \| Timestamp kapan data di update
\| \|

**user_insight_engagement_growth**
''''''''''''''''''''''''''''''''''

Berisi data nilai growth engagement dengan perhitungan nilai engagement
pada hari ini dibandingkan dengan 7 hari atau 28 hari yang lalu untuk
setiap user.

+-----------+-------+------+------------------------------------+----+
| Nama      | Tipe  | Tipe | Isi                                | C  |
| Kolom     |       | Data |                                    | at |
|           |       |      |                                    | at |
|           |       |      |                                    | an |
+===========+=======+======+====================================+====+
| id        | Pr    | b    | Nomor ID                           |    |
|           | imary | igse |                                    |    |
|           | Key   | rial |                                    |    |
+-----------+-------+------+------------------------------------+----+
| user_id   | Fo    | var  | Nomor ID yang merujuk pada table   |    |
|           | reign | char | user                               |    |
|           | Key   |      |                                    |    |
+-----------+-------+------+------------------------------------+----+
| growth    | -     | f    | Nilai engagement growth untuk      |    |
|           |       | loat | suatu user                         |    |
+-----------+-------+------+------------------------------------+----+
| timeframe | -     | int  | Periode waktu (dalam hari)         | [  |
|           |       |      | perhitungan engagement growth      | 7, |
|           |       |      |                                    | 2  |
|           |       |      |                                    | 8] |
+-----------+-------+------+------------------------------------+----+
| datestamp | -     | date | datestamp kapan data di update     |    |
+-----------+-------+------+------------------------------------+----+
| updated_  | -     | t    | Timestamp kapan data di update     |    |
| timestamp |       | imes |                                    |    |
|           |       | tamp |                                    |    |
+-----------+-------+------+------------------------------------+----+

**user_insight_engagement_rate_growth**
'''''''''''''''''''''''''''''''''''''''

Berisi data nilai rate growth engagement dengan perhitungan nilai
engagement pada hari ini dibagi jumlah follower dibandingkan dengan
nilai 7 hari atau 28 hari yang lalu untuk setiap user.

+----------+-------+-----+--------------------------------------+----+
| Nama     | Tipe  | T   | Isi                                  | C  |
| Kolom    |       | ipe |                                      | at |
|          |       | D   |                                      | at |
|          |       | ata |                                      | an |
+==========+=======+=====+======================================+====+
| id       | Pr    | big | Nomor ID                             |    |
|          | imary | ser |                                      |    |
|          | Key   | ial |                                      |    |
+----------+-------+-----+--------------------------------------+----+
| user_id  | Fo    | v   | Nomor ID yang merujuk pada table     |    |
|          | reign | arc | user                                 |    |
|          | Key   | har |                                      |    |
+----------+-------+-----+--------------------------------------+----+
| growth   | -     | fl  | Nilai engagement rate growth untuk   |    |
|          |       | oat | suatu user                           |    |
+----------+-------+-----+--------------------------------------+----+
| t        | -     | int | Periode waktu (dalam hari)           | [  |
| imeframe |       |     | perhitungan engagement rate growth   | 7, |
|          |       |     |                                      | 2  |
|          |       |     |                                      | 8] |
+----------+-------+-----+--------------------------------------+----+
| d        | -     | d   | datestamp kapan data di update       |    |
| atestamp |       | ate |                                      |    |
+----------+-------+-----+--------------------------------------+----+
| u        | -     | tim | Timestamp kapan data di update       |    |
| pdated_t |       | est |                                      |    |
| imestamp |       | amp |                                      |    |
+----------+-------+-----+--------------------------------------+----+

**user_insight_follower_online**
''''''''''''''''''''''''''''''''

Berisi tentang data insight sebaran jam online follower dari suatu user.

+--------------+-------------+-----------+---------------+---------+
| Nama Kolom   | Tipe        | Tipe Data | Isi           | Catatan |
+==============+=============+===========+===============+=========+
| id           | Primary Key | varchar   | Nomor ID      |         |
+--------------+-------------+-----------+---------------+---------+
| user_id      | Foreign Key | varchar   | Nomor ID yang |         |
|              |             |           | merujuk pada  |         |
|              |             |           | table user    |         |
+--------------+-------------+-----------+---------------+---------+
| hours        | -           | varchar   | Rentang Jam   |         |
|              |             |           | dari 0-24     |         |
+--------------+-------------+-----------+---------------+---------+
| val          | -           | varchar   | Nilai         |         |
|              |             |           | Impression    |         |
|              |             |           | user          |         |
+--------------+-------------+-----------+---------------+---------+
| date_range   | -           | varchar   | Range tanggal |         |
|              |             |           | penghitungan  |         |
+--------------+-------------+-----------+---------------+---------+
| updated_date | -           | timestamp | Timestamp     |         |
|              |             |           | kapan data di |         |
|              |             |           | update        |         |
+--------------+-------------+-----------+---------------+---------+

**user_insight_follower_growth**
''''''''''''''''''''''''''''''''

Berisi data nilai growth jumlah follower dengan perhitungan nilai pada
hari ini dibandingkan dengan nilai 7 hari atau 28 hari yang lalu untuk
setiap user.

+--------------+-------------+-----------+--------------+----------+
| Nama Kolom   | Tipe        | Tipe Data | Isi          | Catatan  |
+==============+=============+===========+==============+==========+
| id           | Primary Key | serial    | Nomor ID     |          |
+--------------+-------------+-----------+--------------+----------+
| user_id      | Foreign Key | varchar   | Nomor ID     |          |
|              |             |           | yang merujuk |          |
|              |             |           | pada table   |          |
|              |             |           | user         |          |
+--------------+-------------+-----------+--------------+----------+
| date_stamp   | -           | date      | tanggal      |          |
|              |             |           | kapan data   |          |
|              |             |           | di update    |          |
+--------------+-------------+-----------+--------------+----------+
| timeframe    | -           | int       | Periode      | [7 , 28] |
|              |             |           | waktu        |          |
|              |             |           | perhitungan  |          |
|              |             |           | perbandingan |          |
|              |             |           | follower     |          |
+--------------+-------------+-----------+--------------+----------+
| growth       | -           | float     | Nilai growth |          |
|              |             |           | follower     |          |
|              |             |           | setiap user  |          |
+--------------+-------------+-----------+--------------+----------+
| updat        | -           | timestamp | Timestamp    |          |
| ed_timestamp |             |           | kapan data   |          |
|              |             |           | di update    |          |
+--------------+-------------+-----------+--------------+----------+

**user_insight_impressions_growth**
'''''''''''''''''''''''''''''''''''

Berisi data nilai growth impression user dengan perhitungan nilai pada
hari ini dibandingkan dengan nilai 7 hari atau 28 hari yang lalu untuk
setiap user.

+--------------+-------------+-----------+--------------+----------+
| Nama Kolom   | Tipe        | Tipe Data | Isi          | Catatan  |
+==============+=============+===========+==============+==========+
| id           | Primary Key | serial    | Nomor ID     |          |
+--------------+-------------+-----------+--------------+----------+
| user_id      | Foreign Key | varchar   | Nomor ID     |          |
|              |             |           | yang merujuk |          |
|              |             |           | pada table   |          |
|              |             |           | user         |          |
+--------------+-------------+-----------+--------------+----------+
| date_stamp   | -           | date      | tanggal      |          |
|              |             |           | kapan data   |          |
|              |             |           | di update    |          |
+--------------+-------------+-----------+--------------+----------+
| timeframe    | -           | int       | Periode      | [7 , 28] |
|              |             |           | waktu        |          |
|              |             |           | perhitungan  |          |
|              |             |           | perbandingan |          |
|              |             |           | follower     |          |
+--------------+-------------+-----------+--------------+----------+
| growth       | -           | float     | Nilai growth |          |
|              |             |           | impressions  |          |
|              |             |           | setiap user  |          |
+--------------+-------------+-----------+--------------+----------+
| updat        | -           | timestamp | Timestamp    |          |
| ed_timestamp |             |           | kapan data   |          |
|              |             |           | di update    |          |
+--------------+-------------+-----------+--------------+----------+

**user_insight_reach_growth**
'''''''''''''''''''''''''''''

Berisi data nilai growth jumlah reach user dengan perhitungan nilai pada
hari ini dibandingkan dengan nilai 7 hari atau 28 hari yang lalu untuk
setiap user.

+--------------+-------------+-----------+--------------+----------+
| Nama Kolom   | Tipe        | Tipe Data | Isi          | Catatan  |
+==============+=============+===========+==============+==========+
| id           | Primary Key | serial    | Nomor ID     |          |
+--------------+-------------+-----------+--------------+----------+
| user_id      | Foreign Key | varchar   | Nomor ID     |          |
|              |             |           | yang merujuk |          |
|              |             |           | pada table   |          |
|              |             |           | user         |          |
+--------------+-------------+-----------+--------------+----------+
| date_stamp   | -           | date      | tanggal      |          |
|              |             |           | kapan data   |          |
|              |             |           | di update    |          |
+--------------+-------------+-----------+--------------+----------+
| timeframe    | -           | int       | Periode      | [7 , 28] |
|              |             |           | waktu        |          |
|              |             |           | perhitungan  |          |
|              |             |           | perbandingan |          |
|              |             |           | follower     |          |
+--------------+-------------+-----------+--------------+----------+
| growth       | -           | float     | Nilai growth |          |
|              |             |           | impressions  |          |
|              |             |           | setiap user  |          |
+--------------+-------------+-----------+--------------+----------+
| updat        | -           | timestamp | Timestamp    |          |
| ed_timestamp |             |           | kapan data   |          |
|              |             |           | di update    |          |
+--------------+-------------+-----------+--------------+----------+

**user_insight_sentiment**
''''''''''''''''''''''''''

Berisi data nilai sentiment user (positif, negatif, dan netral) dari
komentar pada media suatu user.

+---------------+-------------+-----------+---------------+---------+
| Nama Kolom    | Tipe        | Tipe Data | Isi           | Catatan |
+===============+=============+===========+===============+=========+
| id            | Primary Key | serial    | Nomor ID      |         |
+---------------+-------------+-----------+---------------+---------+
| user_id       | Foreign Key | varchar   | Nomor ID yang |         |
|               |             |           | merujuk pada  |         |
|               |             |           | table user    |         |
+---------------+-------------+-----------+---------------+---------+
| date_stamp    | -           | date      | tanggal kapan |         |
|               |             |           | data di       |         |
|               |             |           | update        |         |
+---------------+-------------+-----------+---------------+---------+
| neu           | -           | int       | Jumlah        |         |
|               |             |           | sentiment     |         |
|               |             |           | netral        |         |
+---------------+-------------+-----------+---------------+---------+
| pos           | -           | int       | Jumlah        |         |
|               |             |           | sentiment     |         |
|               |             |           | positive      |         |
+---------------+-------------+-----------+---------------+---------+
| neg           |             | int       | Jumlah        |         |
|               |             |           | sentiment     |         |
|               |             |           | negative      |         |
+---------------+-------------+-----------+---------------+---------+
| upda          | -           | timestamp | Timestamp     |         |
| ted_timestamp |             |           | kapan data di |         |
|               |             |           | update        |         |
+---------------+-------------+-----------+---------------+---------+

**user_insight_sentiment_growth**
'''''''''''''''''''''''''''''''''

Berisi data nilai growth setiap sentiment dengan melakukan penguragan
nilai pada hari ini dibandingkan dengan nilai 7 hari atau 28 hari yang
lalu untuk setiap user.

+--------------+-------------+-----------+--------------+----------+
| Nama Kolom   | Tipe        | Tipe Data | Isi          | Catatan  |
+==============+=============+===========+==============+==========+
| id           | Primary Key | serial    | Nomor ID     |          |
+--------------+-------------+-----------+--------------+----------+
| user_id      | Foreign Key | varchar   | Nomor ID     |          |
|              |             |           | yang merujuk |          |
|              |             |           | pada table   |          |
|              |             |           | user         |          |
+--------------+-------------+-----------+--------------+----------+
| date_stamp   | -           | date      | tanggal      |          |
|              |             |           | kapan data   |          |
|              |             |           | di update    |          |
+--------------+-------------+-----------+--------------+----------+
| neu          | -           | float     | Jumlah       |          |
|              |             |           | growth       |          |
|              |             |           | sentiment    |          |
|              |             |           | netral       |          |
+--------------+-------------+-----------+--------------+----------+
| pos          | -           | float     | Jumlah       |          |
|              |             |           | growth       |          |
|              |             |           | sentiment    |          |
|              |             |           | positive     |          |
+--------------+-------------+-----------+--------------+----------+
| neg          |             | float     | Jumlah       |          |
|              |             |           | growth       |          |
|              |             |           | sentiment    |          |
|              |             |           | negative     |          |
+--------------+-------------+-----------+--------------+----------+
| updat        | -           | timestamp | Timestamp    |          |
| ed_timestamp |             |           | kapan data   |          |
|              |             |           | di update    |          |
+--------------+-------------+-----------+--------------+----------+
| timeframe    | -           | int       | Periode      | [7 , 28] |
|              |             |           | waktu        |          |
|              |             |           | perhitungan  |          |
|              |             |           | perbandingan |          |
|              |             |           | sentiment    |          |
+--------------+-------------+-----------+--------------+----------+

**user_media_largest_engagement**
'''''''''''''''''''''''''''''''''

Berisi data media yang memiliki nilai engagement terbanyak pada suatu
user dengan periode waktu 7 atau 28 hari.

+--------------+-------------+-----------+--------------+----------+
| Nama Kolom   | Tipe        | Tipe Data | Isi          | Catatan  |
+==============+=============+===========+==============+==========+
| id           | Primary Key | bigserial | Nomor ID     |          |
+--------------+-------------+-----------+--------------+----------+
| user_id      | Foreign Key | varchar   | Nomor ID     |          |
|              |             |           | yang merujuk |          |
|              |             |           | pada table   |          |
|              |             |           | user         |          |
+--------------+-------------+-----------+--------------+----------+
| media_id     | Foreign Key | varchar   | Nomor ID     |          |
|              |             |           | yang merujuk |          |
|              |             |           | pada table   |          |
|              |             |           | media        |          |
+--------------+-------------+-----------+--------------+----------+
| timeframe    | -           | int       | Periode      | [7 , 28] |
|              |             |           | waktu        |          |
|              |             |           | perhitungan  |          |
|              |             |           | engagement   |          |
|              |             |           | terbanyak    |          |
+--------------+-------------+-----------+--------------+----------+
| enga         | -           | int       | Jumlah       |          |
| gement_count |             |           | engagement   |          |
|              |             |           | media        |          |
+--------------+-------------+-----------+--------------+----------+
| updat        | -           | timestamp | Timestamp    |          |
| ed_timestamp |             |           | kapan data   |          |
|              |             |           | di update    |          |
+--------------+-------------+-----------+--------------+----------+

**user_media_largest_reach**
''''''''''''''''''''''''''''

Berisi data media yang memiliki nilai reach terbanyak pada suatu user
dengan periode waktu 7 atau 28 hari.

+--------------+-------------+-----------+--------------+----------+
| Nama Kolom   | Tipe        | Tipe Data | Isi          | Catatan  |
+==============+=============+===========+==============+==========+
| id           | Primary Key | bigserial | Nomor ID     |          |
+--------------+-------------+-----------+--------------+----------+
| user_id      | Foreign Key | varchar   | Nomor ID     |          |
|              |             |           | yang merujuk |          |
|              |             |           | pada table   |          |
|              |             |           | user         |          |
+--------------+-------------+-----------+--------------+----------+
| media_id     | Foreign Key | varchar   | Nomor ID     |          |
|              |             |           | yang merujuk |          |
|              |             |           | pada table   |          |
|              |             |           | media        |          |
+--------------+-------------+-----------+--------------+----------+
| timeframe    | -           | int       | Periode      | [7 , 28] |
|              |             |           | waktu        |          |
|              |             |           | perhitungan  |          |
|              |             |           | engagement   |          |
|              |             |           | terbanyak    |          |
+--------------+-------------+-----------+--------------+----------+
| reach_count  | -           | int       | Jumlah reach |          |
|              |             |           | suatu media  |          |
+--------------+-------------+-----------+--------------+----------+
| updat        | -           | timestamp | Timestamp    |          |
| ed_timestamp |             |           | kapan data   |          |
|              |             |           | di update    |          |
+--------------+-------------+-----------+--------------+----------+

**user_media_most_negative**
''''''''''''''''''''''''''''

Berisi data media yang memiliki sentiment negatif terbanyak pada suatu
user dengan periode waktu 7 atau 28 hari.

+--------------+-------------+-----------+--------------+----------+
| Nama Kolom   | Tipe        | Tipe Data | Isi          | Catatan  |
+==============+=============+===========+==============+==========+
| id           | Primary Key | bigserial | Nomor ID     |          |
+--------------+-------------+-----------+--------------+----------+
| user_id      | Foreign Key | varchar   | Nomor ID     |          |
|              |             |           | yang merujuk |          |
|              |             |           | pada table   |          |
|              |             |           | user         |          |
+--------------+-------------+-----------+--------------+----------+
| media_id     | Foreign Key | varchar   | Nomor ID     |          |
|              |             |           | yang merujuk |          |
|              |             |           | pada table   |          |
|              |             |           | media        |          |
+--------------+-------------+-----------+--------------+----------+
| timeframe    | -           | int       | Periode      | [7 , 28] |
|              |             |           | waktu        |          |
|              |             |           | perhitungan  |          |
|              |             |           | engagement   |          |
|              |             |           | terbanyak    |          |
+--------------+-------------+-----------+--------------+----------+
| ne           | -           | int       | Jumlah       |          |
| gative_count |             |           | sentiment    |          |
|              |             |           | negatif      |          |
|              |             |           | suatu media  |          |
+--------------+-------------+-----------+--------------+----------+
| updat        | -           | timestamp | Timestamp    |          |
| ed_timestamp |             |           | kapan data   |          |
|              |             |           | di update    |          |
+--------------+-------------+-----------+--------------+----------+

**user_media_most_positive**
''''''''''''''''''''''''''''

Berisi data media yang memiliki sentiment positif terbanyak pada suatu
user dengan periode waktu 7 atau 28 hari.

+--------------+-------------+-----------+--------------+----------+
| Nama Kolom   | Tipe        | Tipe Data | Isi          | Catatan  |
+==============+=============+===========+==============+==========+
| id           | Primary Key | bigserial | Nomor ID     |          |
+--------------+-------------+-----------+--------------+----------+
| user_id      | Foreign Key | varchar   | Nomor ID     |          |
|              |             |           | yang merujuk |          |
|              |             |           | pada table   |          |
|              |             |           | user         |          |
+--------------+-------------+-----------+--------------+----------+
| media_id     | Foreign Key | varchar   | Nomor ID     |          |
|              |             |           | yang merujuk |          |
|              |             |           | pada table   |          |
|              |             |           | media        |          |
+--------------+-------------+-----------+--------------+----------+
| timeframe    | -           | int       | Periode      | [7 , 28] |
|              |             |           | waktu        |          |
|              |             |           | perhitungan  |          |
|              |             |           | engagement   |          |
|              |             |           | terbanyak    |          |
+--------------+-------------+-----------+--------------+----------+
| po           | -           | int       | Jumlah       |          |
| sitive_count |             |           | sentiment    |          |
|              |             |           | positive     |          |
|              |             |           | suatu media  |          |
+--------------+-------------+-----------+--------------+----------+
| updat        | -           | timestamp | Timestamp    |          |
| ed_timestamp |             |           | kapan data   |          |
|              |             |           | di update    |          |
+--------------+-------------+-----------+--------------+----------+

**user_media_smallest_engagement**
''''''''''''''''''''''''''''''''''

Berisi data media yang memiliki nilai engagement paling sedikit pada
suatu user dengan periode waktu 7 atau 28 hari.

+--------------+-------------+-----------+--------------+----------+
| Nama Kolom   | Tipe        | Tipe Data | Isi          | Catatan  |
+==============+=============+===========+==============+==========+
| id           | Primary Key | bigserial | Nomor ID     |          |
+--------------+-------------+-----------+--------------+----------+
| user_id      | Foreign Key | varchar   | Nomor ID     |          |
|              |             |           | yang merujuk |          |
|              |             |           | pada table   |          |
|              |             |           | user         |          |
+--------------+-------------+-----------+--------------+----------+
| media_id     | Foreign Key | varchar   | Nomor ID     |          |
|              |             |           | yang merujuk |          |
|              |             |           | pada table   |          |
|              |             |           | media        |          |
+--------------+-------------+-----------+--------------+----------+
| timeframe    | -           | int       | Periode      | [7 , 28] |
|              |             |           | waktu        |          |
|              |             |           | perhitungan  |          |
|              |             |           | engagement   |          |
|              |             |           | terbanyak    |          |
+--------------+-------------+-----------+--------------+----------+
| enga         | -           | int       | Jumlah       |          |
| gement_count |             |           | engagement   |          |
|              |             |           | media        |          |
+--------------+-------------+-----------+--------------+----------+
| updat        | -           | timestamp | Timestamp    |          |
| ed_timestamp |             |           | kapan data   |          |
|              |             |           | di update    |          |
+--------------+-------------+-----------+--------------+----------+

**user_media_comment_sentiment**
''''''''''''''''''''''''''''''''

Berisi data sentiment setiap komentar pada suatu media.

+-------------+-------------+-----------+-------------+-------------+
| Nama Kolom  | Tipe        | Tipe Data | Isi         | Catatan     |
+=============+=============+===========+=============+=============+
| id          | Primary Key | bigserial | Nomor ID    |             |
+-------------+-------------+-----------+-------------+-------------+
| comment_id  | Foreign Key | varchar   | Nomor ID    |             |
|             |             |           | yang        |             |
|             |             |           | merujuk     |             |
|             |             |           | pada table  |             |
|             |             |           | comment     |             |
+-------------+-------------+-----------+-------------+-------------+
| media_id    | Foreign Key | varchar   | Nomor ID    |             |
|             |             |           | yang        |             |
|             |             |           | merujuk     |             |
|             |             |           | pada table  |             |
|             |             |           | media       |             |
+-------------+-------------+-----------+-------------+-------------+
| sentiment   | -           | varchar   | Sentiment   | [neu , pos, |
|             |             |           | komentar    | neg]        |
|             |             |           | suatu media |             |
+-------------+-------------+-----------+-------------+-------------+
| update      | -           | timestamp | Timestamp   |             |
| d_timestamp |             |           | kapan data  |             |
|             |             |           | di update   |             |
+-------------+-------------+-----------+-------------+-------------+

**user_hastags_metrics**
''''''''''''''''''''''''

Berisi data metrics setiap hashtag pada suatu media user.

+-------------+-------------+-------------+-------------+-------------+
| Nama Kolom  | Tipe        | Tipe Data   | Isi         | Catatan     |
+=============+=============+=============+=============+=============+
| id          | Primary Key | serial      | Nomor ID    |             |
+-------------+-------------+-------------+-------------+-------------+
| user_id     | Foreign Key | varchar     | Nomor ID    | Unique      |
|             |             |             | yang        |             |
|             |             |             | merujuk     |             |
|             |             |             | pada table  |             |
|             |             |             | user        |             |
+-------------+-------------+-------------+-------------+-------------+
| hastag      | -           | timestamptz | Hastag yang | Unique      |
|             |             |             | tertera     |             |
|             |             |             | pada        |             |
|             |             |             | caption     |             |
|             |             |             | (#Hastag)   |             |
+-------------+-------------+-------------+-------------+-------------+
| total       | -           | int         | Jumlah      | [neu , pos, |
| _engagement |             |             | engagement  | neg]        |
+-------------+-------------+-------------+-------------+-------------+
| post_count  | -           | int         | Jumlah post |             |
|             |             |             | yang        |             |
|             |             |             | menggunakan |             |
|             |             |             | hastag      |             |
|             |             |             | tertentu    |             |
+-------------+-------------+-------------+-------------+-------------+
| engageme    |             | float       | Perhitungan |             |
| nt_per_post |             |             | engagement  |             |
|             |             |             | dibagi      |             |
|             |             |             | jumlah      |             |
|             |             |             | postingan   |             |
+-------------+-------------+-------------+-------------+-------------+
| update      |             | timestamptz | Timestamp   |             |
| d_timestamp |             |             | kapan data  |             |
|             |             |             | di update   |             |
+-------------+-------------+-------------+-------------+-------------+
| datestamp   |             | date        | Date kapan  | Unique      |
|             |             |             | data di     |             |
|             |             |             | update      |             |
+-------------+-------------+-------------+-------------+-------------+
| total_reach |             | int         | Jumlah      |             |
|             |             |             | total reach |             |
+-------------+-------------+-------------+-------------+-------------+
| total_saved |             | int         | Jumlah      |             |
|             |             |             | total post  |             |
|             |             |             | yang di     |             |
|             |             |             | simpan      |             |
|             |             |             | dengan      |             |
|             |             |             | menggunakan |             |
|             |             |             | hastag      |             |
+-------------+-------------+-------------+-------------+-------------+
| rea         |             | int         | P           |             |
| ch_per_post |             |             | enghitungan |             |
|             |             |             | reach per   |             |
|             |             |             | jumlah post |             |
+-------------+-------------+-------------+-------------+-------------+
| sav         |             | int         | P           |             |
| ed_per_post |             |             | enghitungan |             |
|             |             |             | media       |             |
|             |             |             | disimpan    |             |
|             |             |             | per jumlah  |             |
|             |             |             | post        |             |
+-------------+-------------+-------------+-------------+-------------+

**user_hastags_metrics_distribution**
'''''''''''''''''''''''''''''''''''''

Berisi data distribusi metrics setiap hashtag pada suatu media user.

+--------------+-------------+-------------+--------------+---------+
| Nama Kolom   | Tipe        | Tipe Data   | Isi          | Catatan |
+==============+=============+=============+==============+=========+
| id           | Primary Key | serial      | Nomor ID     |         |
+--------------+-------------+-------------+--------------+---------+
| user_id      | Foreign Key | varchar     | Nomor ID     |         |
|              |             |             | yang merujuk |         |
|              |             |             | pada table   |         |
|              |             |             | user         |         |
+--------------+-------------+-------------+--------------+---------+
| media_id     | Foreign Key | varchar     | Nomor ID     | Unique  |
|              |             |             | yang merujuk |         |
|              |             |             | pada table   |         |
|              |             |             | media        |         |
+--------------+-------------+-------------+--------------+---------+
| hastag       | -           | timestamptz | Hastag yang  | Unique  |
|              |             |             | tertera pada |         |
|              |             |             | caption      |         |
|              |             |             | (#Hastag)    |         |
+--------------+-------------+-------------+--------------+---------+
| med          |             | timestamptz | Timestamp    | Unique  |
| ia_timestamp |             |             | kapan media  |         |
|              |             |             | di update    |         |
+--------------+-------------+-------------+--------------+---------+
| engagement   |             | int4        | Perhitungan  |         |
|              |             |             | engagement   |         |
|              |             |             | dibagi       |         |
|              |             |             | jumlah       |         |
|              |             |             | postingan    |         |
+--------------+-------------+-------------+--------------+---------+
| reach        | -           | int4        | Jumlah reach |         |
|              |             |             | post         |         |
+--------------+-------------+-------------+--------------+---------+
| impressions  |             | int4        | Jumlah       |         |
|              |             |             | impressions  |         |
+--------------+-------------+-------------+--------------+---------+
| updat        |             | timestamptz | Timestamp    |         |
| ed_timestamp |             |             | kapan data   |         |
|              |             |             | di update    |         |
+--------------+-------------+-------------+--------------+---------+
| datestamp    |             | date        | Date kapan   | Unique  |
|              |             |             | data di      |         |
|              |             |             | update       |         |
+--------------+-------------+-------------+--------------+---------+
| co           |             | int         | Jumlah       |         |
| mments_count |             |             | komentar     |         |
|              |             |             | pada suatu   |         |
|              |             |             | media        |         |
+--------------+-------------+-------------+--------------+---------+
| like_count   |             | int         | Jumlah Like  |         |
|              |             |             | pada suatu   |         |
|              |             |             | media        |         |
+--------------+-------------+-------------+--------------+---------+

**user_insight_follower_online_wording (not active)**
'''''''''''''''''''''''''''''''''''''''''''''''''''''

Berisi data insight.

+---------------+-------------+-----------+---------------+---------+
| Nama Kolom    | Tipe        | Tipe Data | Isi           | Catatan |
+===============+=============+===========+===============+=========+
| id            | Primary Key | serial    | Nomor ID      |         |
+---------------+-------------+-----------+---------------+---------+
| user_id       | Foreign Key | varchar   | Nomor ID yang |         |
|               |             |           | merujuk pada  |         |
|               |             |           | table user    |         |
+---------------+-------------+-----------+---------------+---------+
| high          | -           | varchar   |               |         |
| light_wording |             |           |               |         |
+---------------+-------------+-----------+---------------+---------+
| h             | -           | varchar   |               |         |
| ighlight_type |             |           |               |         |
+---------------+-------------+-----------+---------------+---------+
| date_range    | -           | date      | datestamp     |         |
|               |             |           | kapan data di |         |
|               |             |           | update        |         |
+---------------+-------------+-----------+---------------+---------+
| lang          | -           | varchar   | bahasa yang   |         |
|               |             |           | digunakan     |         |
+---------------+-------------+-----------+---------------+---------+
| updated_date  | -           | timestamp | Timestamp     |         |
|               |             |           | kapan data di |         |
|               |             |           | update        |         |
+---------------+-------------+-----------+---------------+---------+

**user_media_comment_sentiment (not active)**
'''''''''''''''''''''''''''''''''''''''''''''

Berisi data waktu paling aktif suatu user.

+--------------+-------------+-------------+--------------+---------+
| Nama Kolom   | Tipe        | Tipe Data   | Isi          | Catatan |
+==============+=============+=============+==============+=========+
| id           | Primary Key | serial      | Nomor ID     |         |
+--------------+-------------+-------------+--------------+---------+
| user_id      | Foreign Key | varchar     | Nomor ID     |         |
|              |             |             | yang merujuk |         |
|              |             |             | pada table   |         |
|              |             |             | user         |         |
+--------------+-------------+-------------+--------------+---------+
| waktu_       | -           | timestamptz |              |         |
| paling_aktif |             |             |              |         |
+--------------+-------------+-------------+--------------+---------+
| value_       | -           | varchar     |              |         |
| paling_aktif |             |             |              |         |
+--------------+-------------+-------------+--------------+---------+
| updated_date | -           | timestamp   | Timestamp    |         |
|              |             |             | kapan data   |         |
|              |             |             | di update    |         |
+--------------+-------------+-------------+--------------+---------+

Facebook and 3-rd Party Endpoint
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

IG Media
^^^^^^^^

Mewakili album, foto, atau video Instagram (video yang diunggah, video
live, video yang dibuat dengan aplikasi Instagram TV, reel, atau story
Instagram).

Cekbrand menggunakan 3rd-party dari pyfacebook yang memfasilitasi
pemanggilan dari masing-masing endpoint API Graph facebook.

Limitasi
''''''''

-  Kolom yang menampilkan nilai aggregat tidak menyertakan data yang
   digerakkan oleh iklan. Misalnya, comments_count menghitung komentar
   pada sebuah foto, tetapi tidak menghitung komentar pada iklan yang
   berisi foto tersebut.
-  Caption tidak menyertakan simbol @ kecuali pengguna aplikasi juga
   dapat melakukan tugas yang setara dengan Admin di aplikasi.
-  Beberapa kolom tidak dapat digunakan pada foto di dalam album (anak).
-  Media Instagram TV harus dibagikan ke Instagram pada saat publikasi
   (Post a Preview atau Share Preview to Feed diaktifkan) agar dapat
   diakses melalui API.
-  Live video IG Media hanya dapat dibaca saat sedang disiarkan.

Persyaratan
'''''''''''

+----+-----------------------------------------------------------------+
| Ti | Deskripsi                                                       |
| pe |                                                                 |
+====+=================================================================+
| A  | User.                                                           |
| ks |                                                                 |
| es |                                                                 |
| T  |                                                                 |
| ok |                                                                 |
| en |                                                                 |
+----+-----------------------------------------------------------------+
| Iz | **instagram_basic** **pages_read_engagement**                   |
| in | **pages_show_list** Jika pengguna aplikasi diberi peran di      |
|    | Halaman melalui Business Manager, kita juga memerlukan salah    |
|    | satu dari yang berikut: **ads_management**                      |
|    | **business_management**                                         |
+----+-----------------------------------------------------------------+

Request Syntax
''''''''''''''

GET https://graph.facebook.com/{api-version}/{ig-media-id}
    ?fields={fields}     &access_token={access-token}

Parameter Path
''''''''''''''

================= ===================
Placeholder       Value
================= ===================
**{api-version}** Versi API.
**{ig-media-id}** Perlu. IG Media ID.
================= ===================

Parameter String Kueri
''''''''''''''''''''''

+-----------+-------------+--------------------------------------------+
| Key       | Placeholder | Value                                      |
+===========+=============+============================================+
| **acces   | **{acce     | Perlu. Token akses pengguna dari pengguna  |
| s_token** | ss-token}** | aplikasi.                                  |
+-----------+-------------+--------------------------------------------+
| *         | *           | List yang dipisahkan dengan tanda koma     |
| *fields** | *{fields}** | dari field yang ingin dihasilkan.          |
+-----------+-------------+--------------------------------------------+

Fields
''''''

Public fields dan dapat di-read via ekspansi field.

+---+------------------------------------------------------------------+
| F | Deskripsi                                                        |
| i |                                                                  |
| e |                                                                  |
| l |                                                                  |
| d |                                                                  |
+===+==================================================================+
| * | Caption. Tidak termasuk anak album. Simbol @ dikecualikan,       |
| * | kecuali jika pengguna aplikasi dapat melakukan tugas yang setara |
| c | dengan admin di Halaman Facebook yang terhubung ke akun          |
| a | Instagram yang digunakan untuk membuat caption.                  |
| p |                                                                  |
| t |                                                                  |
| i |                                                                  |
| o |                                                                  |
| n |                                                                  |
| * |                                                                  |
| * |                                                                  |
| P |                                                                  |
| u |                                                                  |
| b |                                                                  |
| l |                                                                  |
| i |                                                                  |
| c |                                                                  |
+---+------------------------------------------------------------------+
| * | Jumlah komentar di media. Tidak termasuk komentar pada media     |
| * | album anak dan keterangan media. Termasuk reply pada komentar.   |
| c |                                                                  |
| o |                                                                  |
| m |                                                                  |
| m |                                                                  |
| e |                                                                  |
| n |                                                                  |
| t |                                                                  |
| s |                                                                  |
| _ |                                                                  |
| c |                                                                  |
| o |                                                                  |
| u |                                                                  |
| n |                                                                  |
| t |                                                                  |
| * |                                                                  |
| * |                                                                  |
| P |                                                                  |
| u |                                                                  |
| b |                                                                  |
| l |                                                                  |
| i |                                                                  |
| c |                                                                  |
+---+------------------------------------------------------------------+
| * | Media ID.                                                        |
| * |                                                                  |
| i |                                                                  |
| d |                                                                  |
| * |                                                                  |
| * |                                                                  |
| P |                                                                  |
| u |                                                                  |
| b |                                                                  |
| l |                                                                  |
| i |                                                                  |
| c |                                                                  |
+---+------------------------------------------------------------------+
| * | Instagram media ID. Sebelumnya menggunakan dengan Legacy         |
| * | Instagram API, sekarang tidak digunakan lagi. Sebagai gantinya   |
| i | menggunakan id.                                                  |
| g |                                                                  |
| _ |                                                                  |
| i |                                                                  |
| d |                                                                  |
| * |                                                                  |
| * |                                                                  |
| P |                                                                  |
| u |                                                                  |
| b |                                                                  |
| l |                                                                  |
| i |                                                                  |
| c |                                                                  |
+---+------------------------------------------------------------------+
| * | Menunjukkan jika komentar diaktifkan atau dinonaktifkan. Tidak   |
| * | termasuk anak album.                                             |
| i |                                                                  |
| s |                                                                  |
| _ |                                                                  |
| c |                                                                  |
| o |                                                                  |
| m |                                                                  |
| m |                                                                  |
| e |                                                                  |
| n |                                                                  |
| t |                                                                  |
| _ |                                                                  |
| e |                                                                  |
| n |                                                                  |
| a |                                                                  |
| b |                                                                  |
| l |                                                                  |
| e |                                                                  |
| d |                                                                  |
| * |                                                                  |
| * |                                                                  |
+---+------------------------------------------------------------------+
| * | Reels saja. Jika benar, berarti reel dapat muncul di tab feed    |
| * | dan reels. Jika salah, berarti gulungan hanya dapat muncul di    |
| i | tab reel. Perhatikan bahwa tidak ada nilai yang menunjukkan      |
| s | apakah reel benar-benar muncul di tab reels, karena reel mungkin |
| _ | tidak memenuhi persyaratan kelayakan atau telah dipilih oleh     |
| s | algoritme kami. Lihat spesifikasi reel untuk kriteria kelayakan. |
| h |                                                                  |
| a |                                                                  |
| r |                                                                  |
| e |                                                                  |
| d |                                                                  |
| _ |                                                                  |
| t |                                                                  |
| o |                                                                  |
| _ |                                                                  |
| f |                                                                  |
| e |                                                                  |
| e |                                                                  |
| d |                                                                  |
| * |                                                                  |
| * |                                                                  |
| P |                                                                  |
| u |                                                                  |
| b |                                                                  |
| l |                                                                  |
| i |                                                                  |
| c |                                                                  |
+---+------------------------------------------------------------------+
| * | Jumlah likes di media, termasuk reply di komentar. Tidak         |
| * | termasuk likes di media anak album dan likes di pos yang         |
| l | dipromosikan dibuat dari media. Jika ditanyakan secara tidak     |
| i | langsung melalui titik akhir lain atau ekspansi fields: -v10.0   |
| k | dan calls yang lebih lama: Nilainya adalah 0 jika pemilik media  |
| e | menyembunyikan jumlah like. -v11.0+ calls: Field like_count      |
| _ | dihilangkan jika pemilik media memiliki jumlah like yang         |
| c | tersembunyi.                                                     |
| o |                                                                  |
| u |                                                                  |
| n |                                                                  |
| t |                                                                  |
| * |                                                                  |
| * |                                                                  |
+---+------------------------------------------------------------------+
| * | Lokasi media dipublikasi. Dapat berupa iklan, feed, story, atau  |
| * | reels.                                                           |
| m |                                                                  |
| e |                                                                  |
| d |                                                                  |
| i |                                                                  |
| a |                                                                  |
| _ |                                                                  |
| p |                                                                  |
| r |                                                                  |
| o |                                                                  |
| d |                                                                  |
| u |                                                                  |
| c |                                                                  |
| t |                                                                  |
| _ |                                                                  |
| t |                                                                  |
| y |                                                                  |
| p |                                                                  |
| e |                                                                  |
| * |                                                                  |
| * |                                                                  |
| P |                                                                  |
| u |                                                                  |
| b |                                                                  |
| l |                                                                  |
| i |                                                                  |
| c |                                                                  |
+---+------------------------------------------------------------------+
| * | Tipe media. Dapat berupa album carousel, gambar, or video.       |
| * |                                                                  |
| m |                                                                  |
| e |                                                                  |
| d |                                                                  |
| i |                                                                  |
| a |                                                                  |
| _ |                                                                  |
| t |                                                                  |
| y |                                                                  |
| p |                                                                  |
| e |                                                                  |
| * |                                                                  |
| * |                                                                  |
| P |                                                                  |
| u |                                                                  |
| b |                                                                  |
| l |                                                                  |
| i |                                                                  |
| c |                                                                  |
+---+------------------------------------------------------------------+
| * | URL untuk media. Field dari media_url field URL dihilangkan dari |
| * | respons jika media berisi materi berhak cipta atau telah         |
| m | ditandai karena pelanggaran hak cipta. Contoh materi berhak      |
| e | cipta dapat mencakup audio pada reels.                           |
| d |                                                                  |
| i |                                                                  |
| a |                                                                  |
| _ |                                                                  |
| u |                                                                  |
| r |                                                                  |
| l |                                                                  |
| * |                                                                  |
| * |                                                                  |
| P |                                                                  |
| u |                                                                  |
| b |                                                                  |
| l |                                                                  |
| i |                                                                  |
| c |                                                                  |
+---+------------------------------------------------------------------+
| * | ID pengguna Instagram yang membuat media. Hanya di-return jika   |
| * | pengguna aplikasi yang membuat kueri juga membuat media; jika    |
| o | tidak, field dari username yang di-return sebagai gantinya.      |
| w |                                                                  |
| n |                                                                  |
| e |                                                                  |
| r |                                                                  |
| * |                                                                  |
| * |                                                                  |
| P |                                                                  |
| u |                                                                  |
| b |                                                                  |
| l |                                                                  |
| i |                                                                  |
| c |                                                                  |
+---+------------------------------------------------------------------+
| * | URL permanen ke media.                                           |
| * |                                                                  |
| p |                                                                  |
| e |                                                                  |
| r |                                                                  |
| m |                                                                  |
| a |                                                                  |
| l |                                                                  |
| i |                                                                  |
| n |                                                                  |
| k |                                                                  |
| * |                                                                  |
| * |                                                                  |
| P |                                                                  |
| u |                                                                  |
| b |                                                                  |
| l |                                                                  |
| i |                                                                  |
| c |                                                                  |
+---+------------------------------------------------------------------+
| * | Shortcode ke media.                                              |
| * |                                                                  |
| s |                                                                  |
| h |                                                                  |
| o |                                                                  |
| r |                                                                  |
| t |                                                                  |
| c |                                                                  |
| o |                                                                  |
| d |                                                                  |
| e |                                                                  |
| * |                                                                  |
| * |                                                                  |
| P |                                                                  |
| u |                                                                  |
| b |                                                                  |
| l |                                                                  |
| i |                                                                  |
| c |                                                                  |
+---+------------------------------------------------------------------+
| * | URL dari thumbnail media. Hanya tersedia di media video.         |
| * |                                                                  |
| t |                                                                  |
| h |                                                                  |
| u |                                                                  |
| m |                                                                  |
| b |                                                                  |
| n |                                                                  |
| a |                                                                  |
| i |                                                                  |
| l |                                                                  |
| _ |                                                                  |
| u |                                                                  |
| r |                                                                  |
| l |                                                                  |
| * |                                                                  |
| * |                                                                  |
| P |                                                                  |
| u |                                                                  |
| b |                                                                  |
| l |                                                                  |
| i |                                                                  |
| c |                                                                  |
+---+------------------------------------------------------------------+
| * | Tanggal pembuatan berformat ISO 8601 dalam UTC (standarnya       |
| * | adalah UTC ±00:00).                                              |
| t |                                                                  |
| i |                                                                  |
| m |                                                                  |
| e |                                                                  |
| s |                                                                  |
| t |                                                                  |
| a |                                                                  |
| m |                                                                  |
| p |                                                                  |
| * |                                                                  |
| * |                                                                  |
| P |                                                                  |
| u |                                                                  |
| b |                                                                  |
| l |                                                                  |
| i |                                                                  |
| c |                                                                  |
+---+------------------------------------------------------------------+
| * | Username pengguna yang membuat media.                            |
| * |                                                                  |
| u |                                                                  |
| s |                                                                  |
| e |                                                                  |
| r |                                                                  |
| n |                                                                  |
| a |                                                                  |
| m |                                                                  |
| e |                                                                  |
| * |                                                                  |
| * |                                                                  |
| P |                                                                  |
| u |                                                                  |
| b |                                                                  |
| l |                                                                  |
| i |                                                                  |
| c |                                                                  |
+---+------------------------------------------------------------------+
| * | Tidak digunakan lagi. Dihilangkan dari respons.                  |
| * |                                                                  |
| v |                                                                  |
| i |                                                                  |
| d |                                                                  |
| e |                                                                  |
| o |                                                                  |
| _ |                                                                  |
| t |                                                                  |
| i |                                                                  |
| t |                                                                  |
| l |                                                                  |
| e |                                                                  |
| * |                                                                  |
| * |                                                                  |
| P |                                                                  |
| u |                                                                  |
| b |                                                                  |
| l |                                                                  |
| i |                                                                  |
| c |                                                                  |
+---+------------------------------------------------------------------+

Edges
'''''

Public edges dapat dikembalikan melalui ekspansi field.

+--------------+-------------------------------------------------------+
| Edge         | Description                                           |
+==============+=======================================================+
| **children** | Merepresentasikan kumpulan objek IG Media di album IG |
| Public.      | Media.                                                |
+--------------+-------------------------------------------------------+
| **comments** | Merepresentasikan kumpulan Komentar IG pada objek     |
|              | Media IG.                                             |
+--------------+-------------------------------------------------------+
| **insights** | Merepresentasikan metrik interaksi sosial pada objek  |
|              | IG Media.                                             |
+--------------+-------------------------------------------------------+

Request Syntax 3rd-party pyfacebook
'''''''''''''''''''''''''''''''''''

def get_user_medias(self, user_id, fields=None, since_time=None,
until_time=None, count=10, limit=10, return_json=False)

Mengambil data media pengguna ig berdasarkan user_id. Penjelasan
parameter fungsi get_user_medias sebagai berikut. \| Parameter \| Tipe
Data \| Keterangan \|
\|——————–|————————————————-|————————————————————————————————————————————-\|
\| user_id \| str \| Id untuk pengguna instagram business yang ingin
kita dapatkan datanya. \| \| fields \| Optional[Union[str, List, Tuple,
Set]] \| String id yang dipisahkan koma untuk field data yang kita
inginkan. Kita juga dapat pass ini dengan list id, tuple, set. \| \|
since_time \| Optional[str] \| Batas bawah rentang waktu ke waktu
publikasi media. Formatnya adalah %Y-%m-%d. \| \| until_time \|
Optional[str] \| Batas atas rentang waktu ke waktu publikasi media.
Formatnya adalah %Y-%m-%d. \| \| count \| Optional[str] \| Jumlah kita
ingin mendapatkan media. Jika perlu mendapatkan semuanya, set ini dengan
None. \| \| limit \| int \| Setiap permintaan mengambil jumlah media
dari api. Untuk media sebaiknya tidak lebih dari 500. \| \| return_json
\| bool \| Set ke False akan mengembalikan instance dari IgProUser. \|

IG Media Insights
^^^^^^^^^^^^^^^^^

Mewakili metrik interaksi sosial pada objek IG Media.

.. _limitasi-1:

Limitasi
''''''''

-  Insight data tidak tersedia untuk media apa pun dalam album IG Media.
-  Metrik story media hanya tersedia selama 24 jam, meskipun story
   tersebut diarsipkan atau di-highlight. Untuk mendapatkan insight
   terbaru tentang sebuah story sebelum kedaluwarsa, siapkan Webhook
   untuk field **Instagram** dan subscribe ke field **story_insights**.
-  Metrik story media dengan nilai kurang dari 5 menampilkan kode
   kesalahan **10** dengan pesan **(#10) Not enough viewers for the
   media to show insights.**
-  Untuk story yang dibuat oleh user di Eropa dan Jepang, metrik
   **replies** kini return nilai **0**.
-  Untuk story, balasan yang dibuat oleh pengguna di Eropa dan Jepang
   tidak termasuk dalam penghitungan **replies**.
-  Jika insight data yang kita minta tidak ada atau saat ini tidak
   tersedia, API akan return kumpulan data kosong, bukan 0 untuk
   masing-masing metrik.
-  Data yang digunakan untuk menghitung metrik dapat ditunda hingga 48
   jam.

.. _persyaratan-1:

Persyaratan
'''''''''''

=========== ===================
Tipe        Deskripsi
=========== ===================
Akses Token User.
Izin        **instagram_basic**
=========== ===================

**instagram_manage_insights** **pages_read_engagement**
**pages_show_list** Jika pengguna aplikasi diberi peran di Halaman
melalui Business Manager, kita juga memerlukan salah satu dari yang
berikut: **ads_management** **business_management** \|

.. _request-syntax-1:

Request Syntax
''''''''''''''

GET https://graph.facebook.com/{api-version}/{ig-media-id}/insights
    ?metric={metric}     &access_token={access-token}

.. _parameter-path-1:

Parameter Path
''''''''''''''

================= ===================
Placeholder       Value
================= ===================
**{api-version}** Versi API.
**{ig-media-id}** Perlu. IG Media ID.
================= ===================

.. _parameter-string-kueri-1:

Parameter String Kueri
''''''''''''''''''''''

+-------------------------+--------------------------------------------+
| Parameter               | Value                                      |
+=========================+============================================+
| **{access-token}**      | Perlu. Akses toker dari User pengguna      |
| Type: string            | aplikasi.                                  |
+-------------------------+--------------------------------------------+
| **{metric}** Type:      | Perlu. List yang diseparasi oleh metrik    |
| Comma-separated list    | yang mau di-return.                        |
+-------------------------+--------------------------------------------+

Metrik
''''''

Metrik Album
            

+---------------+------------------------------------------------------+
| Metrik        | Deskripsi                                            |
+===============+======================================================+
| **c           | Total jumlah like dan Komentar IG pada album objek   |
| arousel_album | IG Media.                                            |
| _engagement** |                                                      |
+---------------+------------------------------------------------------+
| **ca          | Total berapa kali objek IG Media album telah         |
| rousel_album_ | dilihat.                                             |
| impressions** |                                                      |
+---------------+------------------------------------------------------+
| **carousel_   | Total jumlah akun Instagram unik yang telah melihat  |
| album_reach** | album objek IG Media.                                |
+---------------+------------------------------------------------------+
| **carousel_   | Total jumlah akun Instagram unik yang telah          |
| album_saved** | menyimpan album objek IG Media.                      |
+---------------+------------------------------------------------------+
| **ca          | Total jumlah akun Instagram unik yang telah melihat  |
| rousel_album_ | video IG Media dalam album.                          |
| video_views** |                                                      |
+---------------+------------------------------------------------------+

Metrik Foto dan Video
                     

Metrik pada media dalam album tidak didukung. Sebagai gantinya, diambil
metrik di album. \| Metrik \| Deskripsi \|
\|————-|———————————————————————————————————————————————\| \|
**engagement** \| Jumlahan dari **likes_count**, **comment_count**, dan
**saved counts** pada IG Media. \| \| **impressions** \| Total banyaknya
objek IG Media telah dilihat. \| \| **reach** \| Total akun Instagram
unik yang telah melihat objek IG Media. \| \| **saved** \| Total jumlah
akun Instagram unik yang telah melihat objek IG Media. \| \|
**video_views** \| Total berapa kali video IG Media telah dilihat. Untuk
album IG Media, berapa kali semua video dalam album telah dilihat. \|

Metrik Reels
            

+-----+----------------------------------------------------------------+
| Met | Deskripsi                                                      |
| rik |                                                                |
+=====+================================================================+
| **c | Jumlah komentar pada reel. Metrik dalam pengembangan.          |
| omm |                                                                |
| ent |                                                                |
| s** |                                                                |
+-----+----------------------------------------------------------------+
| **l | Jumlah likes di reel. Metrik dalam pengembangan.               |
| ike |                                                                |
| s** |                                                                |
+-----+----------------------------------------------------------------+
| **p |                                                                |
| lay |                                                                |
| s** |                                                                |
+-----+----------------------------------------------------------------+
| Jum |                                                                |
| lah |                                                                |
| ber |                                                                |
| apa |                                                                |
| k   |                                                                |
| ali |                                                                |
| re  |                                                                |
| els |                                                                |
| mu  |                                                                |
| lai |                                                                |
| d   |                                                                |
| ipu |                                                                |
| tar |                                                                |
| s   |                                                                |
| ete |                                                                |
| lah |                                                                |
| ta  |                                                                |
| yan |                                                                |
| gan |                                                                |
| dih |                                                                |
| itu |                                                                |
| ng. |                                                                |
| Ini |                                                                |
| d   |                                                                |
| ide |                                                                |
| fin |                                                                |
| isi |                                                                |
| kan |                                                                |
| s   |                                                                |
| eba |                                                                |
| gai |                                                                |
| s   |                                                                |
| esi |                                                                |
| vi  |                                                                |
| deo |                                                                |
| den |                                                                |
| gan |                                                                |
| pem |                                                                |
| uta |                                                                |
| ran |                                                                |
| 1   |                                                                |
| ms  |                                                                |
| a   |                                                                |
| tau |                                                                |
| le  |                                                                |
| bih |                                                                |
| dan |                                                                |
| ti  |                                                                |
| dak |                                                                |
| te  |                                                                |
| rma |                                                                |
| suk |                                                                |
| pem |                                                                |
| uta |                                                                |
| ran |                                                                |
| ula |                                                                |
| ng. |                                                                |
| Met |                                                                |
| rik |                                                                |
| da  |                                                                |
| lam |                                                                |
| p   |                                                                |
| eng |                                                                |
| emb |                                                                |
| ang |                                                                |
| an. |                                                                |
+-----+----------------------------------------------------------------+
| **r | Jumlah akun unik yang telah melihat reel setidaknya sekali.    |
| eac | Reach berbeda dengan impresi, yang dapat mencakup beberapa     |
| h** | penayangan reel oleh akun yang sama. Metrik diperkirakan dan   |
|     | dalam pengembangan.                                            |
+-----+----------------------------------------------------------------+
| **s | Jumlah penyimpanan reel. Metrik dalam pengembangan.            |
| ave |                                                                |
| d** |                                                                |
+-----+----------------------------------------------------------------+
| *   | Jumlah share dari reel. Metrik dalam pengembangan.             |
| *sh |                                                                |
| are |                                                                |
| s** |                                                                |
+-----+----------------------------------------------------------------+
| *   | Jumlah likes, simpan, komentar, dan share pada reel, dikurangi |
| *to | jumlah unlikes, tidak simpan, dan komentar yang dihapus.       |
| tal | Metrik dalam pengembangan.                                     |
| _in |                                                                |
| ter |                                                                |
| act |                                                                |
| ion |                                                                |
| s** |                                                                |
+-----+----------------------------------------------------------------+

Metrik story
            

+---+-------------------------------------------------------------------+
| M | Deskripsi                                                         |
| e |                                                                   |
| t |                                                                   |
| r |                                                                   |
| i |                                                                   |
| k |                                                                   |
+===+===================================================================+
| * | Total berapa kali seseorang keluar dari story objek IG Media.     |
| * |                                                                   |
| e |                                                                   |
| x |                                                                   |
| i |                                                                   |
| t |                                                                   |
| s |                                                                   |
| * |                                                                   |
| * |                                                                   |
+---+-------------------------------------------------------------------+
| * | Total berapa kali story objek IG Media telah dilihat.             |
| * |                                                                   |
| i |                                                                   |
| m |                                                                   |
| p |                                                                   |
| r |                                                                   |
| e |                                                                   |
| s |                                                                   |
| s |                                                                   |
| i |                                                                   |
| o |                                                                   |
| n |                                                                   |
| s |                                                                   |
| * |                                                                   |
| * |                                                                   |
+---+-------------------------------------------------------------------+
| * | Total jumlah akun Instagram unik yang telah melihat story objek   |
| * | IG Media.                                                         |
| r |                                                                   |
| e |                                                                   |
| a |                                                                   |
| c |                                                                   |
| h |                                                                   |
| * |                                                                   |
| * |                                                                   |
+---+-------------------------------------------------------------------+
| * | Total jumlah reply (Komentar IG) pada story objek IG Media. Nilai |
| * | tidak termasuk reply yang dibuat oleh pengguna di beberapa        |
| r | wilayah. Wilayah ini meliputi: Eropa mulai 1 Desember 2020 dan    |
| e | Jepang mulai 14 April 2021. Jika story dibuat oleh pengguna di    |
| p | salah satu wilayah ini, akan mengembalikan nilai 0.               |
| l |                                                                   |
| i |                                                                   |
| e |                                                                   |
| s |                                                                   |
| * |                                                                   |
| * |                                                                   |
+---+-------------------------------------------------------------------+
| * | Total jumlah tap untuk melihat foto atau video selanjutnya dari   |
| * | objek IG Media ini.                                               |
| t |                                                                   |
| a |                                                                   |
| p |                                                                   |
| s |                                                                   |
| _ |                                                                   |
| f |                                                                   |
| o |                                                                   |
| r |                                                                   |
| w |                                                                   |
| a |                                                                   |
| r |                                                                   |
| d |                                                                   |
| * |                                                                   |
| * |                                                                   |
+---+-------------------------------------------------------------------+
| * | Total jumlah tap untuk melihat foto atau video sebelumnya dari    |
| * | objek IG Media ini.                                               |
| t |                                                                   |
| a |                                                                   |
| p |                                                                   |
| s |                                                                   |
| _ |                                                                   |
| b |                                                                   |
| a |                                                                   |
| c |                                                                   |
| k |                                                                   |
| * |                                                                   |
| * |                                                                   |
+---+-------------------------------------------------------------------+

.. _request-syntax-3rd-party-pyfacebook-1:

Request Syntax 3rd-party pyfacebook
'''''''''''''''''''''''''''''''''''

def get_media_insights(self, media_id, metrics, access_token=None,
return_json=False)

Mengambil data media insights. Penjelasan parameter fungsi
get_media_insights sebagai berikut, dengan tipe data
List[Union[IgProInsight, dict]]. \| Parameter \| Tipe Data \| Keterangan
\| \|————–|——————————|—————————————————————–\| \| media_id \| str \| ID
media yang ingin kita dapatkan datanya. \| \| metrics \| Union[str,
List, Tuple, Set] \| String id yang dipisahkan koma untuk metrik yang
perlu diambil. Kita juga dapat meneruskan ini dengan list, tuple, atau
set dari id. Catatan: Jenis media yang berbeda memiliki metrik yang
berbeda. Lihat selengkapnya:
https://developers.facebook.com/docs/instagram-api/reference/media/insights#insights-2
\| \| access_token \| str \| Token akses pengguna target. Jika tidak
akan menggunakan token akses default. \| \| return_json \| bool \| Set
ke false akan mengembalikan list instance IgProInsight. Atau kembalikan
data json. Default adalah false. \|

IG User
^^^^^^^

Mewakili Akun Bisnis Instagram atau Akun Kreator Instagram.

**GET /{ig-user-id}** Mendapatkan fields dan edges pada Instagram
Business atau Akun Kreator.

.. _persyaratan-2:

Persyaratan
'''''''''''

+---+-------------------------------------------------------------------+
| T | Deskripsi                                                         |
| i |                                                                   |
| p |                                                                   |
| e |                                                                   |
+===+===================================================================+
| A | User.                                                             |
| k |                                                                   |
| s |                                                                   |
| e |                                                                   |
| n |                                                                   |
| T |                                                                   |
| o |                                                                   |
| k |                                                                   |
| e |                                                                   |
| n |                                                                   |
+---+-------------------------------------------------------------------+
| P | Jika kita meminta field **shopping_product_tag_eligibility**      |
| e | untuk tagging produk, pengguna aplikasi harus memiliki peran      |
| r | admin di Business Manager yang memiliki Instagram Shop dari       |
| a | Pengguna IG.                                                      |
| n |                                                                   |
| B |                                                                   |
| i |                                                                   |
| s |                                                                   |
| n |                                                                   |
| i |                                                                   |
| s |                                                                   |
+---+-------------------------------------------------------------------+
| I | Jika kita meminta field **shopping_product_tag_eligibility**      |
| n | untuk tagging produk, Pengguna IG harus memiliki Instagram Shop   |
| s | yang disetujui dengan katalog produk berisi produk.               |
| t |                                                                   |
| a |                                                                   |
| g |                                                                   |
| r |                                                                   |
| a |                                                                   |
| m |                                                                   |
| S |                                                                   |
| h |                                                                   |
| o |                                                                   |
| p |                                                                   |
+---+-------------------------------------------------------------------+
| I | **instagram_basic** **pages_read_engagement** **pages_show_list** |
| z | Jika pengguna aplikasi diberi peran di Halaman melalui Business   |
| i | Manager, kita juga memerlukan salah satu dari yang berikut:       |
| n | \ **ads_management** **business_management** Jika kita meminta    |
|   | field **shopping_product_tag_eligibility** untuk pemberian tag    |
|   | produk, kita juga memerlukan: **catalog_management**              |
|   | **instagram_shopping_tag_products**                               |
+---+-------------------------------------------------------------------+

.. _request-syntax-2:

Request Syntax
''''''''''''''

GET https://graph.facebook.com/{api-version}/{ig-user-id}
    ?fields={fields}     &access_token={access-token}

.. _parameter-path-2:

Parameter Path
''''''''''''''

================= ==================
Placeholder       Value
================= ==================
**{api-version}** Versi API.
**{ig-used-id}**  Perlu. IG User ID.
================= ==================

.. _parameter-string-kueri-2:

Parameter String Kueri
''''''''''''''''''''''

+-----------+-------------+--------------------------------------------+
| Key       | Placeholder | Value                                      |
+===========+=============+============================================+
| **acces   | **{acce     | Perlu. Token akses pengguna dari pengguna  |
| s_token** | ss-token}** | aplikasi.                                  |
+-----------+-------------+--------------------------------------------+
| *         | *           | List yang dipisahkan dengan tanda koma     |
| *fields** | *{fields}** | dari field IG User yang ingin dihasilkan   |
|           |             | oleh setiap IG User pada himpunan hasil.   |
+-----------+-------------+--------------------------------------------+

.. _fields-1:

Fields
''''''

Field publik dapat dikembalikan oleh edge menggunakan ekspansi field.

+-------------+--------------------------------------------------------+
| Field Nama  | Deskripsi                                              |
+=============+========================================================+
| **          | Teks dari profil bio.                                  |
| biography** |                                                        |
| Public      |                                                        |
+-------------+--------------------------------------------------------+
| **id**      | User ID dalam cakupan aplikasi.                        |
| Public      |                                                        |
+-------------+--------------------------------------------------------+
| **ig_id**   | User ID Instagram. Digunakan dengan Legacy Instagram   |
|             | API, sekarang sudah tidak digunakan lagi. Menggunakan  |
|             | id sebagai gantinya.                                   |
+-------------+--------------------------------------------------------+
| **follow    | Total jumlah Instagram user yang mengikuti user.       |
| ers_count** |                                                        |
| Public      |                                                        |
+-------------+--------------------------------------------------------+
| **foll      | Total jumlah pengguna Instagram yang diikuti user.     |
| ows_count** |                                                        |
+-------------+--------------------------------------------------------+
| **me        | Total jumlah Media IG yang dipublikasikan oleh user.   |
| dia_count** |                                                        |
| Public      |                                                        |
+-------------+--------------------------------------------------------+
| **name**    | Nama profil.                                           |
+-------------+--------------------------------------------------------+
| *           | URL gambar profil.                                     |
| *profile_pi |                                                        |
| cture_url** |                                                        |
+-------------+--------------------------------------------------------+
| **s         | Mengembalikan nilai true jika pengguna aplikasi telah  |
| hopping_pro | menyiapkan Instagram Shop dan karenanya memenuhi       |
| duct_tag_el | syarat untuk pemberian tag produk, jika tidak,         |
| igibility** | mengembalikan nilai false.                             |
+-------------+--------------------------------------------------------+
| *           | Username dari profil.                                  |
| *username** |                                                        |
| Public      |                                                        |
+-------------+--------------------------------------------------------+
| **website** | URL dari laman profil.                                 |
| Public      |                                                        |
+-------------+--------------------------------------------------------+

.. _edges-1:

Edges
'''''

+------------+---------------------------------------------------------+
| Edge       | Deskripsi                                               |
+============+=========================================================+
| **         | Mendapatkan data tentang User IG Instagram Business     |
| business_d | atau Instagram Creator IG.                              |
| iscovery** |                                                         |
+------------+---------------------------------------------------------+
| **conten   | Merepresentasikan penggunaan penerbitan konten User IG  |
| t_publishi | saat ini.                                               |
| ng_limit** |                                                         |
+------------+---------------------------------------------------------+
| **         | Mewakili metrik interaksi sosial pada User IG.          |
| insights** |                                                         |
+------------+---------------------------------------------------------+
| **li       | Merepresentasi kumpulan live video IG Media pada IG     |
| ve_media** | User.                                                   |
+------------+---------------------------------------------------------+
| **media**  | Merepresentasi kumpulan IG Media pada IG User.          |
+------------+---------------------------------------------------------+
| **media    | Mempublikasi IG Container di User ID Instagram          |
| _publish** | Business.                                               |
+------------+---------------------------------------------------------+
| **         | Create an IG Comment on an IG Comment or captioned IG   |
| mentions** | Media that an IG User has been @mentioned in by another |
|            | Instagram user.                                         |
+------------+---------------------------------------------------------+
| *          | Get data on an IG Comment in which an IG User has been  |
| *mentioned | @mentioned by another Instagram user.                   |
| _comment** |                                                         |
+------------+---------------------------------------------------------+
| **mention  | Get data on an IG Media in which an IG User has been    |
| ed_media** | @mentioned in a caption by another Instagram user.      |
+------------+---------------------------------------------------------+
| **recently | Get IG Hashtags that an IG User has searched for within |
| _searched_ | the last 7 days.                                        |
| hashtags** |                                                         |
+------------+---------------------------------------------------------+
| *          | Represents a collection of story IG Media objects on an |
| *stories** | IG User.                                                |
+------------+---------------------------------------------------------+
| **tags**   | Represents a collection of IG Media in which an IG User |
|            | has been tagged by another Instagram user.              |
+------------+---------------------------------------------------------+

.. _request-syntax-3rd-party-pyfacebook-2:

Request Syntax 3rd-party pyfacebook
'''''''''''''''''''''''''''''''''''

def get_user_info(self, user_id, fields=None, return_json=False)

Mengambil data pengguna ig dari user id. Penjelasan parameter fungsi
get_user_info sebagai berikut, dengan tipe data Optional[IgProUser,
dict]. \| Parameter \| Tipe Data \| Keterangan \|
\|————-|——————————|—————————————————————–\| \| user_id \| str \| Id
untuk instagram business user yang ingin kita dapatkan datanya. \| \|
fields \| Optional[Union[str, List, Tuple, Set]] \| String id yang
dipisahkan koma untuk metrik yang perlu diambil. Kita juga dapat
meneruskan ini dengan list, tuple, atau set dari id. \| \| return_json
\| bool \| Set ke false akan mengembalikan list instance IgProUser. \|

IG User Insights
^^^^^^^^^^^^^^^^

Merepresentasi metrik interaksi sosial pada IG User.

**GET /{ig-user-id}/insights** Mengembalikan insights tentang IG User.

.. _limitasi-2:

Limitasi
''''''''

-  Metrik **follower_count**, **online_followers**, dan semua
   **audience_\*** tidak tersedia di IG Users dengan followers kurang
   dari 100.
-  Data insights untuk metrik **online_followers** hanya tersedia selama
   30 hari terakhir.
-  Jika data insights yang kita minta tidak ada atau saat ini tidak
   tersedia, API akan mengembalikan kumpulan data kosong, bukan 0 untuk
   masing-masing metrik.
-  Metrik demografis hanya menampilkan 45 artis dengan performa teratas
   (misalnya untuk **audience_city**, hingga 45 kota dengan jumlah
   pengikut tertinggi dapat ditampilkan).
-  Hanya viewers yang data demografisnya kami miliki yang digunakan
   dalam penghitungan metrik demografis.
-  Menjumlahkan nilai metrik demografi dapat menghasilkan nilai yang
   kurang dari jumlah pengikut (lihat poin-poin sebelumnya).
-  Metrik **audience_\*** tidak mendukung parameter range **since** dan
   **until**.
-  Data yang digunakan untuk menghitung metrik mungkin tertunda hingga
   48 jam.

.. _persyaratan-3:

Persyaratan
'''''''''''

+---+------------------------------------------------------------------+
| T | Deskripsi                                                        |
| i |                                                                  |
| p |                                                                  |
| e |                                                                  |
+===+==================================================================+
| A | User                                                             |
| k |                                                                  |
| s |                                                                  |
| e |                                                                  |
| s |                                                                  |
| T |                                                                  |
| o |                                                                  |
| k |                                                                  |
| e |                                                                  |
| n |                                                                  |
+---+------------------------------------------------------------------+
| I | **instagram_basic** **instagram_manage_insights**                |
| z | **pages_read_engagement** **pages_show_list** Jika pengguna      |
| i | aplikasi diberi peran di Halaman melalui Business Manager, kita  |
| n | juga memerlukan salah satu dari: **ads_management**              |
|   | **business_management**                                          |
+---+------------------------------------------------------------------+

.. _request-syntax-3:

Request Syntax
''''''''''''''

GET https://graph.facebook.com/{api-version}/{ig-user-id}/insights
    ?metric={metric}     &period={period}     &since={since}
    &until={until}     &access_token={access-token}

.. _parameter-path-3:

Parameter Path
''''''''''''''

================= ==================
Placeholder       Value
================= ==================
**{api-version}** Versi API.
**{ig-user-id}**  Perlu. IG User ID.
================= ==================

.. _parameter-string-kueri-3:

Parameter String Kueri
''''''''''''''''''''''

+-------+--------------------------------------------------------------+
| Para  | Value                                                        |
| meter |                                                              |
+=======+==============================================================+
| **{ac | Token Akses Pengguna dari pengguna aplikasi.                 |
| cess- |                                                              |
| token |                                                              |
| }**\  |                                                              |
| Req   |                                                              |
| uired |                                                              |
| S     |                                                              |
| tring |                                                              |
+-------+--------------------------------------------------------------+
| **{m  | Daftar Metrik yang dipisahkan koma yang ingin kita           |
| etric | kembalikan. Jika meminta beberapa metrik, semuanya harus     |
| }**\  | memiliki Periode kompatibel yang sama.                       |
| Req   |                                                              |
| uired |                                                              |
| Comma |                                                              |
| -sepa |                                                              |
| rated |                                                              |
| list  |                                                              |
+-------+--------------------------------------------------------------+
| **{p  | Periode yang kompatibel dengan metrik yang kita minta.       |
| eriod |                                                              |
| }**\  |                                                              |
| Req   |                                                              |
| uired |                                                              |
| S     |                                                              |
| tring |                                                              |
+-------+--------------------------------------------------------------+
| **{   | Digunakan bersamaan dengan **{until}** untuk mendefinisikan  |
| since | Range. Jika kita menghilangkan **since** dan **until**, API  |
| }**\  | default ke range 2 hari: kemarin hingga hari ini. Catatan:   |
| Unix  | Kursor paginasi (sebelum dan sesudahnya) mengambil window    |
| time  | waktu berikutnya dari hasil, bukan kelompok hasil berikutnya |
| stamp | dalam window waktu saat ini.                                 |
+-------+--------------------------------------------------------------+
| **{   | Digunakan bersamaan dengan **{since}** untuk menentukan      |
| until | Range. Jika kita menghilangkan **since** dan **until**, API  |
| }**\  | default ke range 2 hari: kemarin hingga hari ini. Catatan:   |
| Unix  | Kursor paginasi (previous dan **next**) mengambil window     |
| time  | waktu berikutnya dari hasil, bukan kelompok hasil berikutnya |
| stamp | dalam window waktu saat ini.                                 |
+-------+--------------------------------------------------------------+

Metrik dan Periode
''''''''''''''''''

Metrik yang mendukung periode **lifetime** akan memiliki hasil yang
dikembalikan dalam susunan periode 24 jam, dengan periode yang berakhir
pada UTC−07:00. metrik **audience_\*** tidak mendukung parameter range
**since** dan **until**.

+---+---+--------------------------------------------------------------+
| M | P | Deskripsi                                                    |
| e | e |                                                              |
| t | r |                                                              |
| r | i |                                                              |
| i | o |                                                              |
| k | d |                                                              |
|   | e |                                                              |
|   | K |                                                              |
|   | o |                                                              |
|   | m |                                                              |
|   | p |                                                              |
|   | a |                                                              |
|   | t |                                                              |
|   | i |                                                              |
|   | b |                                                              |
|   | e |                                                              |
|   | l |                                                              |
+===+===+==============================================================+
| a | l | Kota pengikut yang data demografisnya kita miliki. - Tidak   |
| u | i | termasuk data hari ini. - Tidak tersedia di IG User dengan   |
| d | f | pengikut kurang dari 100. - Hanya 45 kota teratas dengan     |
| i | e | nilai tertinggi yang dikembalikan. - Tidak mendukung         |
| e | t | parameter **since** dan **until**. - Respons tidak           |
| n | i | menyertakan properti JSON **end_time**.                      |
| c | m |                                                              |
| e | e |                                                              |
| _ |   |                                                              |
| c |   |                                                              |
| i |   |                                                              |
| t |   |                                                              |
| y |   |                                                              |
+---+---+--------------------------------------------------------------+
| a | l | Negara pengikut yang data demografisnya kita miliki. - Tidak |
| u | i | termasuk data hari ini. - Tidak tersedia di IG User dengan   |
| d | f | pengikut kurang dari 100. - Hanya 45 negara teratas dengan   |
| i | e | nilai tertinggi yang dikembalikan. - Tidak mendukung         |
| e | t | parameter **since** dan **until**. - Respons tidak           |
| n | i | menyertakan properti JSON **end_time**.                      |
| c | m |                                                              |
| e | e |                                                              |
| _ |   |                                                              |
| c |   |                                                              |
| o |   |                                                              |
| u |   |                                                              |
| n |   |                                                              |
| t |   |                                                              |
| r |   |                                                              |
| y |   |                                                              |
+---+---+--------------------------------------------------------------+
| a | l | Distribusi gender dan usia pengikut yang data demografisnya  |
| u | i | kami miliki. Nilai yang mungkin: **M** (laki-laki), **F**    |
| d | f | (perempuan), **U** (tidak diketahui). - Tidak termasuk data  |
| i | e | hari ini. - Tidak tersedia di IG User dengan pengikut kurang |
| e | t | dari 100. - Tidak mendukung parameter **since** dan          |
| n | i | **until**. - Respons tidak menyertakan properti JSON         |
| c | m | **end_time**.                                                |
| e | e |                                                              |
| _ |   |                                                              |
| g |   |                                                              |
| e |   |                                                              |
| n |   |                                                              |
| d |   |                                                              |
| e |   |                                                              |
| r |   |                                                              |
| _ |   |                                                              |
| a |   |                                                              |
| g |   |                                                              |
| e |   |                                                              |
+---+---+--------------------------------------------------------------+
| a | l | Lokal menurut kode negara pengikut yang data demografisnya   |
| u | i | kita miliki. - Tidak termasuk data hari ini. - Tidak         |
| d | f | tersedia di IG User dengan pengikut kurang dari 100. - Hanya |
| i | e | 45 lokal teratas dengan nilai tertinggi yang dikembalikan. - |
| e | t | Tidak mendukung parameter **since** dan **until**. - Respons |
| n | i | tidak menyertakan properti JSON **end_time**.                |
| c | m |                                                              |
| e | e |                                                              |
| _ |   |                                                              |
| l |   |                                                              |
| o |   |                                                              |
| c |   |                                                              |
| a |   |                                                              |
| l |   |                                                              |
| e |   |                                                              |
+---+---+--------------------------------------------------------------+
| e | d | Total jumlah ketukan pada tautan email di profil IG User.    |
| m | a |                                                              |
| a | y |                                                              |
| i |   |                                                              |
| l |   |                                                              |
| _ |   |                                                              |
| c |   |                                                              |
| o |   |                                                              |
| n |   |                                                              |
| t |   |                                                              |
| a |   |                                                              |
| c |   |                                                              |
| t |   |                                                              |
| s |   |                                                              |
+---+---+--------------------------------------------------------------+
| f | d | Total jumlah pengikut baru setiap hari dalam range yang      |
| o | a | ditentukan. Mengembalikan data maksimal 30 hari. Tidak       |
| l | y | tersedia di Pengguna IG dengan pengikut kurang dari 100.     |
| l |   |                                                              |
| o |   |                                                              |
| w |   |                                                              |
| e |   |                                                              |
| r |   |                                                              |
| _ |   |                                                              |
| c |   |                                                              |
| o |   |                                                              |
| u |   |                                                              |
| n |   |                                                              |
| t |   |                                                              |
+---+---+--------------------------------------------------------------+
| g | d | Total jumlah ketukan pada tautan petunjuk arah di profil IG  |
| e | a | User.                                                        |
| t | y |                                                              |
| _ |   |                                                              |
| d |   |                                                              |
| i |   |                                                              |
| r |   |                                                              |
| e |   |                                                              |
| c |   |                                                              |
| t |   |                                                              |
| i |   |                                                              |
| o |   |                                                              |
| n |   |                                                              |
| s |   |                                                              |
| _ |   |                                                              |
| c |   |                                                              |
| l |   |                                                              |
| i |   |                                                              |
| c |   |                                                              |
| k |   |                                                              |
| s |   |                                                              |
+---+---+--------------------------------------------------------------+
| i | d | Total berapa kali IG Media dari IG User telah dilihat.       |
| m | a | Mencakup aktivitas iklan yang dihasilkan melalui API,        |
| p | y | antarmuka iklan Facebook, dan fitur Promote. Tidak termasuk  |
| r | , | view dari profil.                                            |
| e | w |                                                              |
| s | e |                                                              |
| s | e |                                                              |
| i | k |                                                              |
| o | , |                                                              |
| n | d |                                                              |
| s | a |                                                              |
|   | y |                                                              |
|   | s |                                                              |
|   | _ |                                                              |
|   | 2 |                                                              |
|   | 8 |                                                              |
+---+---+--------------------------------------------------------------+
| o | l | Total jumlah pengikut IG User yang online selama range yang  |
| n | i | ditentukan. Tidak tersedia di IG User dengan pengikut kurang |
| l | f | dari 100.                                                    |
| i | e |                                                              |
| n | t |                                                              |
| e | i |                                                              |
| _ | m |                                                              |
| f | e |                                                              |
| o |   |                                                              |
| l |   |                                                              |
| l |   |                                                              |
| o |   |                                                              |
| w |   |                                                              |
| e |   |                                                              |
| r |   |                                                              |
| s |   |                                                              |
+---+---+--------------------------------------------------------------+
| p | d | Total jumlah ketukan pada tautan panggilan di profil IG      |
| h | a | User.                                                        |
| o | y |                                                              |
| n |   |                                                              |
| e |   |                                                              |
| _ |   |                                                              |
| c |   |                                                              |
| a |   |                                                              |
| l |   |                                                              |
| l |   |                                                              |
| _ |   |                                                              |
| c |   |                                                              |
| l |   |                                                              |
| i |   |                                                              |
| c |   |                                                              |
| k |   |                                                              |
| s |   |                                                              |
+---+---+--------------------------------------------------------------+
| p | d | Total jumlah pengguna yang telah melihat profil IG User      |
| r | a | dalam periode yang ditentukan.                               |
| o | y |                                                              |
| f |   |                                                              |
| i |   |                                                              |
| l |   |                                                              |
| e |   |                                                              |
| _ |   |                                                              |
| v |   |                                                              |
| i |   |                                                              |
| e |   |                                                              |
| w |   |                                                              |
| s |   |                                                              |
+---+---+--------------------------------------------------------------+
| r | d | Total jumlah pengguna unik yang telah melihat setidaknya     |
| e | a | satu IG Media dari IG User. Tampilan berulang dan tampilan   |
| a | y | di berbagai IG Media yang dimiliki oleh IG User oleh         |
| c | , | pengguna yang sama hanya dihitung sebagai satu tampilan.     |
| h | w | Mencakup aktivitas iklan yang dihasilkan melalui API,        |
|   | e | antarmuka iklan Facebook, dan fitur Promote.                 |
|   | e |                                                              |
|   | k |                                                              |
|   | , |                                                              |
|   | d |                                                              |
|   | a |                                                              |
|   | y |                                                              |
|   | s |                                                              |
|   | _ |                                                              |
|   | 2 |                                                              |
|   | 8 |                                                              |
+---+---+--------------------------------------------------------------+
| t | d | Total jumlah ketukan pada tautan pesan teks di profil IG     |
| e | a | User.                                                        |
| x | y |                                                              |
| t |   |                                                              |
| _ |   |                                                              |
| m |   |                                                              |
| e |   |                                                              |
| s |   |                                                              |
| s |   |                                                              |
| a |   |                                                              |
| g |   |                                                              |
| e |   |                                                              |
| _ |   |                                                              |
| c |   |                                                              |
| l |   |                                                              |
| i |   |                                                              |
| c |   |                                                              |
| k |   |                                                              |
| s |   |                                                              |
+---+---+--------------------------------------------------------------+
| w | d | Total jumlah ketukan pada tautan situs web di profil IG      |
| e | a | User.                                                        |
| b | y |                                                              |
| s |   |                                                              |
| i |   |                                                              |
| t |   |                                                              |
| e |   |                                                              |
| _ |   |                                                              |
| c |   |                                                              |
| l |   |                                                              |
| i |   |                                                              |
| c |   |                                                              |
| k |   |                                                              |
| s |   |                                                              |
+---+---+--------------------------------------------------------------+

Range
'''''

Edge ini mendukung paginasi berbasis waktu, sehingga kita dapat
menyertakan parameter **since** dan **until** dengan Unix timestamps
untuk menentukan range. Misalnya, untuk mendapatkan impression selama 28
hari — setiap hari selama 10 hari terakhir — kita dapat membuat Unix
timestamps untuk 10 hari yang lalu dan hari ini, assign ke parameter
**since** dan **until**, dan menyertakannya dalam permintaan kita:
**metric=impressions&period=days_28&since=1501545600&until=1502493720**
Parameter **since** dan **until** bersifat inklusif, sehingga jika range
kita menyertakan hari yang belum berakhir (misalnya hari ini), kueri
berikutnya sepanjang hari dapat mengembalikan nilai yang meningkat. Jika
kita tidak menyertakan parameter **since** dan **until**, API akan
default ke range 2 hari: kemarin sampai hari ini.

.. _request-syntax-3rd-party-pyfacebook-3:

Request Syntax 3rd-party pyfacebook
'''''''''''''''''''''''''''''''''''

def get_user_insights(self, user_id, period, metrics, since=None,
until=None, access_token=None, return_json=False)

Mengambil user insights data dari akun instagram business. Penjelasan
parameter fungsi get_user_insights sebagai berikut, dengan tipe data
List[Union[IgProInsight, dict]]. \| Parameter \| Tipe Data \| Keterangan
\| \|————–|——————————|——————————————————————–\| \| user_id \| str \| Id
untuk instagram business user yang ingin kita dapatkan datanya. \| \|
period \| str \| Periode untuk data agregasi. Parameter yang diterima:
lifetime, day, dan days_28. \| \| metrics \| Union[str, List, Tuple,
Set] \| String id yang dipisahkan koma untuk metrik yang perlu diambil.
Kita juga dapat meneruskan ini dengan list, tuple, atau set dari id.
Catatan: Beberapa metrik tidak sesuai dengan periode. Lihat
selengkapnya:
https://developers.facebook.com/docs/instagram-api/reference/user/insights#metrics-periods\|
\| since \| Optional[int] \| Batas bawah rentang waktu untuk mengambil
data. Perlu Unix timestamps. \| \| until \| Optional[int] \| Batas atas
rentang waktu untuk mengambil data. Perlu Unix timestamps. Rentang waktu
tidak lebih dari 30 hari (2592000 detik). \| \| access_token \| str \|
Token akses pengguna target. Jika tidak akan menggunakan token akses
default. \| \| return_json \| bool \| Set ke false akan mengembalikan
list instance IgProInsight. \|

IG User Business Discovery
^^^^^^^^^^^^^^^^^^^^^^^^^^

Memungkinkan kita mendapatkan data tentang Pengguna Instagram Business
atau Creator IG lainnya.

**GET /{ig-user-id}?fields=business_discovery.username({username})**
Mengembalikan data tentang Pengguna Instagram Business atau Creator IG
lainnya. Lakukan permintaan ini pada Pengguna Instagram Business atau
Creator IG yang membuat kueri, dan identifikasi bisnis yang ditargetkan
dengan parameter **username**.

.. _limitasi-3:

Limitasi
''''''''

Data tentang Instagram Business IG User yang dikenai pembatasan usia
tidak akan dikembalikan.

.. _parameter-string-kueri-4:

Parameter String Kueri
''''''''''''''''''''''

**{username}** (required) — Nama pengguna Instagram Business atau
Creator IG User yang ingin kita dapatkan datanya.

Izin
''''

Token akses Facebook User dengan izin berikut: - **instagram_basic** -
**instagram_manage_insights** - **pages_read_engagement** atau
**pages_show_list** Jika token berasal dari User yang peran Page
diberikan melalui Business Manager, salah satu izin berikut juga
diperlukan: - ads_management - pages_read_engagement -
business_management

Ekspansi Field
''''''''''''''

Kita dapat menggunakan ekspansi field untuk mendapatkan field publik
pada IG Useryang ditargetkan. Lihat referensi IG User untuk daftar kolom
publik.

.. _request-syntax-3rd-party-pyfacebook-4:

Request Syntax 3rd-party pyfacebook
'''''''''''''''''''''''''''''''''''

def discovery_user(self, username, fields=None, return_json=False)

Mengambil info dasar pengguna bisnis lain berdasarkan username.
Penjelasan parameter fungsi discovery_user sebagai berikut, dengan tipe
data Union[IgProUser, dict]. \| Parameter \| Tipe Data \| Keterangan \|
\|————-|——————————|—————————————————————–\| \| username \| str \|
Username untuk kita ingin mengambil data. \| \| fields \| Union[str,
List, Tuple, Set] \| String id yang dipisahkan koma untuk fields data
yang perlu diambil. Kita juga dapat meneruskan ini dengan list, tuple,
atau set dari id. \| \| return_json \| bool \| Set ke false akan
mengembalikan list instance IgProUser. Atau mengembalikan data json.
Default adalah false. \|

IG Comment
^^^^^^^^^^

Merupakan komentar di IG Media.

**GET /{ig-comment-id}?fields={fields}**\  Dapatkan field dan edges pada
IG Comment.

.. _limitasi-4:

Limitasi
''''''''

-  Permintaan tidak dapat dilakukan pada komentar yang ditemukan melalui
   Mentions API kecuali jika permintaan dibuat oleh pemilik comment.
   Sebagai gantinya, gunakan simpul Mentioned Comment.
-  Komentar pada media yang dibatasi usia tidak dikembalikan.
-  Komentar yang dibuat oleh IG User yang telah dibatasi oleh pengguna
   aplikasi tidak akan dikembalikan kecuali IG User tersebut tidak
   dibatasi dan Comment tersebut disetujui.
-  Komentar pada video langsung Media IG hanya dapat dibaca saat IG
   Media tempat komentar dibuat sedang disiarkan.

.. _persyaratan-4:

Persyaratan
'''''''''''

+---+------------------------------------------------------------------+
| T | Deskripsi                                                        |
| i |                                                                  |
| p |                                                                  |
| e |                                                                  |
+===+==================================================================+
| A | User                                                             |
| k |                                                                  |
| s |                                                                  |
| e |                                                                  |
| s |                                                                  |
| T |                                                                  |
| o |                                                                  |
| k |                                                                  |
| e |                                                                  |
| n |                                                                  |
+---+------------------------------------------------------------------+
| I | **instagram_basic** **pages_read_engagement**                    |
| z | **pages_show_list** Jika pengguna aplikasi diberi peran di       |
| i | Halaman melalui Business Manager, kita juga memerlukan salah     |
| n | satu dari: **ads_management** **business_management**            |
+---+------------------------------------------------------------------+

.. _request-syntax-4:

Request Syntax
''''''''''''''

GET https://graph.facebook.com/{api-version}/{ig-comment-id}
    ?fields={fields}     &access_token={access-token}

.. _parameter-path-4:

Parameter Path
''''''''''''''

=================== =====================
Placeholder         Value
=================== =====================
**{api-version}**   Versi API.
**{ig-comment-id}** Perlu. IG Comment ID.
=================== =====================

.. _parameter-string-kueri-5:

Parameter String Kueri
''''''''''''''''''''''

+------+-------+------------------------------------------------------+
| Key  | P     | Value                                                |
|      | laceh |                                                      |
|      | older |                                                      |
+======+=======+======================================================+
| **ac | **{   | Required. Token akses pengguna dari pengguna         |
| cess | acces | aplikasi.                                            |
| _tok | s-tok |                                                      |
| en** | en}** |                                                      |
+------+-------+------------------------------------------------------+
| **   | **    | Daftar fields dari IG Comment yang dipisahkan koma   |
| fiel | {fiel | yang ingin kita kembalikan untuk setiap IG Comment   |
| ds** | ds}** | di himpunan hasil.                                   |
+------+-------+------------------------------------------------------+

.. _fields-2:

Fields
''''''

+---+------------------------------------------------------------------+---+
| N | Deskripsi                                                        |   |
| a |                                                                  |   |
| m |                                                                  |   |
| a |                                                                  |   |
| F |                                                                  |   |
| i |                                                                  |   |
| e |                                                                  |   |
| l |                                                                  |   |
| d |                                                                  |   |
+===+==================================================================+===+
| * | Objek yang berisi: \ **id** — IGSID pengguna Instagram yang      |   |
| * | membuat IG Comment. \ **username** — Nama pengguna dari pengguna |   |
| f | Instagram yang membuat IG Comment.                               |   |
| r |                                                                  |   |
| o |                                                                  |   |
| m |                                                                  |   |
| * |                                                                  |   |
| * |                                                                  |   |
+---+------------------------------------------------------------------+---+
| * | Mengindikasi apakah komentar telah disembunyikan (**true**) atau |   |
| * | tidak (**false**).                                               |   |
| h |                                                                  |   |
| i |                                                                  |   |
| d |                                                                  |   |
| d |                                                                  |   |
| e |                                                                  |   |
| n |                                                                  |   |
| * |                                                                  |   |
| * |                                                                  |   |
+---+------------------------------------------------------------------+---+
| * | IG Comment ID.                                                   |   |
| * |                                                                  |   |
| i |                                                                  |   |
| d |                                                                  |   |
| * |                                                                  |   |
| * |                                                                  |   |
+---+------------------------------------------------------------------+---+
| * | Jumlah suka di IG Comment.                                       |   |
| * |                                                                  |   |
| l |                                                                  |   |
| i |                                                                  |   |
| k |                                                                  |   |
| e |                                                                  |   |
| _ |                                                                  |   |
| c |                                                                  |   |
| o |                                                                  |   |
| u |                                                                  |   |
| n |                                                                  |   |
| t |                                                                  |   |
| * |                                                                  |   |
| * |                                                                  |   |
+---+------------------------------------------------------------------+---+
| * | Objek yang berisi: **id** — ID dari IG Media tempat IG Comment   |   |
| * | dibuat. **media_product_type** — Permukaan IG Media yang         |   |
| m | dipublikasikan (yaitu tempat IG Media muncul) tempat IG Comment  |   |
| e | dibuat.                                                          |   |
| d |                                                                  |   |
| i |                                                                  |   |
| a |                                                                  |   |
| * |                                                                  |   |
| * |                                                                  |   |
+---+------------------------------------------------------------------+---+
| * | ID dari parent IG Comment jika komentar ini dibuat di IG Comment |   |
| * | lain (yaitu balasan untuk komentar lain).                        |   |
| p |                                                                  |   |
| a |                                                                  |   |
| r |                                                                  |   |
| e |                                                                  |   |
| n |                                                                  |   |
| t |                                                                  |   |
| _ |                                                                  |   |
| i |                                                                  |   |
| d |                                                                  |   |
| * |                                                                  |   |
| * |                                                                  |   |
+---+------------------------------------------------------------------+---+
| * | Daftar balasan (IG Comment) dibuat di IG Comment.                |   |
| * |                                                                  |   |
| r |                                                                  |   |
| e |                                                                  |   |
| p |                                                                  |   |
| l |                                                                  |   |
| i |                                                                  |   |
| e |                                                                  |   |
| s |                                                                  |   |
| * |                                                                  |   |
| * |                                                                  |   |
+---+------------------------------------------------------------------+---+
| * | teks di IG Comment.                                              |   |
| * |                                                                  |   |
| t |                                                                  |   |
| e |                                                                  |   |
| x |                                                                  |   |
| t |                                                                  |   |
| * |                                                                  |   |
| * |                                                                  |   |
+---+------------------------------------------------------------------+---+
| * | Timestamp berformat ISO 8601 yang menunjukkan kapan IG Comment   |   |
| * | dibuat. Contoh: 2017-05-19T23:27:28+0000.                        |   |
| t |                                                                  |   |
| i |                                                                  |   |
| m |                                                                  |   |
| e |                                                                  |   |
| s |                                                                  |   |
| t |                                                                  |   |
| a |                                                                  |   |
| m |                                                                  |   |
| p |                                                                  |   |
| * |                                                                  |   |
| * |                                                                  |   |
+---+------------------------------------------------------------------+---+
| * | ID dari IG User yang membuat IG Comment. Hanya dikembalikan jika |   |
| * | pengguna aplikasi membuat IG Comment, jika tidak, nama pengguna  |   |
| u | akan dikembalikan.                                               |   |
| s |                                                                  |   |
| e |                                                                  |   |
| r |                                                                  |   |
| * |                                                                  |   |
| * |                                                                  |   |
+---+------------------------------------------------------------------+---+
| * | Username pengguna Instagram yang membuat IG Comment.             |   |
| * |                                                                  |   |
| u |                                                                  |   |
| s |                                                                  |   |
| e |                                                                  |   |
| r |                                                                  |   |
| n |                                                                  |   |
| a |                                                                  |   |
| m |                                                                  |   |
| e |                                                                  |   |
| * |                                                                  |   |
| * |                                                                  |   |
+---+------------------------------------------------------------------+---+

.. _edges-2:

Edges
'''''

+-----+----------------------------------------------------------------+
| E   | Deskripsi                                                      |
| dge |                                                                |
+=====+================================================================+
| **  | Dapatkan daftar komentar IG di IG Comment; Buat Komentar IG di |
| rep | IG Comment.                                                    |
| lie |                                                                |
| s** |                                                                |
+-----+----------------------------------------------------------------+

.. _request-syntax-3rd-party-pyfacebook-5:

Request Syntax 3rd-party pyfacebook
'''''''''''''''''''''''''''''''''''

def get_comments_by_media(self, media_id, fields=None, count=10,
limit=10, include_reply=True, return_json=False)

Ambil data komentar untuk id media yang diberikan. Penjelasan parameter
fungsi get_comments_by_media sebagai berikut, dengan tipe data
List[Union[IgProComment, dict]]. \| Parameter \| Tipe Data \| Keterangan
\| \|—————|—————————————-|————\| \| media_id \| str \| Id media yang
ingin kita dapatkan data komentarnya. \| \| fields \|
Optional[Union[str, List, Tuple, Set]] \| String id yang dipisahkan koma
untuk fields data yang perlu diambil. Kita juga dapat meneruskan ini
dengan list, tuple, atau set dari id. \| \| count \| Optional[int] \|
Jumlah komentar yang kita inginkan. Default adalah 10. Jika perlu
mendapatkan semua, set ini dengan None. \| \| limit \| int \| Setiap
permintaan mengambil hitungan komentar dari api. Untuk komentar
sebaiknya tidak lebih dari 50. \| \| include_reply \| bool \| Set ke
True akan menyertakan balasan ke komentar. Default adalah benar. \| \|
return_json \| bool \| Set ke false akan mengembalikan list instance
IgProComment. Atau mengembalikan data json. Default adalah false. \|

IG Comment Replies
^^^^^^^^^^^^^^^^^^

Merupakan kumpulan Komentar IG pada IG Comment untuk mendapatkan semua
balasan pada Komentar. **GET /{ig-comment-id}/replies** Mengembalikan
daftar komentar IG pada IG Comment.

.. _limitasi-5:

Limitasi
''''''''

Kita tidak bisa mendapatkan balasan untuk komentar yang telah dihapus.

.. _persyaratan-5:

Persyaratan
'''''''''''

Token akses dari User yang membuat komentar, dengan izin berikut: -
**instagram_basic** - **pages_show_list** - **page_read_engagement**

Jika token berasal dari User yang peran halamannya diberikan melalui
Business Manager, salah satu izin berikut juga diperlukan: -
**ads_management** - **pages_read_engagement** - **business_management**

.. _request-syntax-3rd-party-pyfacebook-6:

Request Syntax 3rd-party pyfacebook
'''''''''''''''''''''''''''''''''''

def get_replies_info(self, reply_ids, fields=None, return_json=False)

Mengambil info reply oleh reply id. Penjelasan parameter fungsi
get_replies_info sebagai berikut, dengan tipe data dict.

+-------+-------------------+------------------------------------------+
| Para  | Tipe Data         | Keterangan                               |
| meter |                   |                                          |
+=======+===================+==========================================+
| us    | Union[str, List,  | Id untuk instagram business user yang    |
| er_id | Tuple, Set]       | ingin kita dapatkan datanya.             |
+-------+-------------------+------------------------------------------+
| f     | Op                | String id yang dipisahkan koma untuk     |
| ields | tional[Union[str, | field data yang perlu diambil. Kita juga |
|       | List, Tuple,      | dapat meneruskan ini dengan list, tuple, |
|       | Set]]             | atau set dari id.                        |
+-------+-------------------+------------------------------------------+
| r     | bool              | Set ke false akan mengembalikan list     |
| eturn |                   | instance IgProComment. Atau              |
| _json |                   | mengembalikan data json. Default adalah  |
|       |                   | false.                                   |
+-------+-------------------+------------------------------------------+
