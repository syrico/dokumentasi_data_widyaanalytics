Competitor Account
++++++++++++++++++

Akun kompetitor adalah akun Instagram yang diklaim merupakan kompetitor dari pengguna.

**Penjelasan Parameter URL**

.. list-table:: 
      :widths: 15 80
      :header-rows: 1

      * - Parameter
        - Deskripsi
      * - account_id
        - ID akun Instagram pengguna
      * - competitor_account_id
        - ID akun Instagram kompetitor pengguna

.. _add-competitor-accounts:

Add
===

.. http:post:: /cekbrand/account/(int:account_id)/competitor-accounts

    Menambahkan akun Instagram kompetitor pengguna.

    **Contoh Request Body**:

    .. sourcecode:: json

        {
            "username": "string"
        }

.. _fetch-list-ig-competitor-data:

List
====

.. http:get:: /cekbrand/account/(int:account_id)/competitor-accounts

    Mengembalikan daftar akun Instagram kompetitor pengguna.

    **Contoh Response**:

    .. sourcecode:: http

        HTTP/1.1 200 OK
        Content-Type: application/json

        [
            {
                "biography": "string",
                "id": "string",
                "name": "string",
                "profile_picture_url": "string",
                "username": "string",
                "updated_timestamp": "2022-12-26T12:50:30.066Z+07:00"
            }
        ]

.. _remove-competitor-account:

Delete
======

.. http:delete:: /cekbrand/account/(int:social_account_id)/competitor-accounts/(int:competitor_account_id)

    Menghapus (*disconnecting*) akun Instagram kompetitor pengguna.

.. _fetch-hashtag-ig-competitor-data:

Hashtag Metrics
===============

.. http:get:: /cekbrand/account/(int:account_id)/competitor-accounts/(int:competitor_account_id)/hashtag-metrics

    Mengembalikan daftar data metrik hashtag akun Instagram pengguna.

    :query string start: tanggal awal filter data in UTC-0 (ISO 8601 format)
    :query string end: tanggal akhir filter data in UTC-0 (ISO 8601 format)
    :query string date_frame: *frame* tanggal filter data, mencakup 7, 28, 60 dan 90

    **Contoh Response**:

    .. sourcecode:: http

        HTTP/1.1 200 OK
        Content-Type: application/json

        [
            {
                "hashtag": "string",
                "like_count": 0,
                "comments_count": 0
            }
        ]

.. _fetch-media-ig-competitor-data:

Media
=====

.. http:get:: /cekbrand/account/(int:account_id)/competitor-accounts/(int:competitor_account_id)/media

    Mengembalikan daftar data media akun Instagram pengguna.

    :query string start: tanggal awal filter data in UTC-0 (ISO 8601 format)
    :query string end: tanggal akhir filter data in UTC-0 (ISO 8601 format)
    :query string date_frame: *frame* tanggal filter data, mencakup 7, 28, 60 dan 90

    **Contoh Response**:

    .. sourcecode:: http

        HTTP/1.1 200 OK
        Content-Type: application/json

        [
            {
                "id": "string",
                "permalink": "string",
                "media_type": "string",
                "timestamp": "2022-12-26T12:52:16.117Z+07:00",
                "caption": "string",
                "like_count": 2147483647,
                "comments_count": 2147483647,
                "media_url": "string",
                "thumbnail_url": "string",
                "media_hashtag": [
                    "string"
                ],
                "insights": []
            }
        ]

.. _fetch-media-average-ig-competitor-data:

Media Engagement Average Summary
================================

.. http:get:: /cekbrand/account/(int:account_id)/competitor-accounts/(int:competitor_account_id)/media/engagement/average/summary

    Mengembalikan data *summary* rerata engagement media akun Instagram kompetitor pengguna.

    :query string start: tanggal awal filter data in UTC-0 (ISO 8601 format)
    :query string end: tanggal akhir filter data in UTC-0 (ISO 8601 format)
    :query string date_frame: *frame* tanggal filter data, mencakup 7, 28, 60 dan 90

    **Contoh Response**:

    .. sourcecode:: http

        HTTP/1.1 200 OK
        Content-Type: application/json

        {
            "engagement_average_rate": "0.300257343514107356%",
            "engagement_average_rate_before": "0.2343242530708156798%",
            "engagement_average_rate_growth": "-0.2342349553767460627%",
            "comments_average": 0.6,
            "comments_average_before": 2.7,
            "comments_average_growth": -1.5,
            "like_average": 24.0,
            "like_average_before": 113.0,
            "like_average_growth": -49.0
        }

.. _fetch-media-summary-ig-competitor-data:

Media Summary
=============

.. http:get:: /cekbrand/account/(int:account_id)/competitor-accounts/(int:competitor_account_id)/media/summary

    Mengembalikan data *summary* media akun Instagram kompetitor pengguna.

    :query string start: tanggal awal filter data in UTC-0 (ISO 8601 format)
    :query string end: tanggal akhir filter data in UTC-0 (ISO 8601 format)
    :query string date_frame: *frame* tanggal filter data, mencakup 7, 28, 60 dan 90

    .. toggle-header::
        :header: **Contoh Response**:

        .. sourcecode:: http

            HTTP/1.1 200 OK
            Content-Type: application/json

            {
                "best_media": {
                    "id": "18022566268422222",
                    "permalink": "https://www.instagram.com/reel/asd_234234/",
                    "timestamp": "2022-12-25T09:47:22+07:00",
                    "caption": "Merry Christmas🎄🎄\n\nIt’s the most wonderful time of the year. ...#weloveitsowemakeit #madewithlove #shareinlove #passiontoserve #feeltherealbread #bakerylife #baker #pizza #christmas #christmaseve #tunggadewicake #oleholehsurabaya #kulinersurabaya #jawatimur #bukancakepabrikan #bakerysurabaya #surabayafood",
                    "media_url": "https://video-msp1-1.cdninstagram.com/o1/v/t16/f1/m82/0C44BC7411BFAE4E0BFE8CFCC6C55F87_video_dashinit.mp4?efg=eyJ2ZW5jb2RlX3RhZyI6InZ0c192b2RfdXJsZ2VuLjcyMC5jbGlwcyJ9&_nc_ht=video-msp1-1.cdninstagram.com&_nc_cat=102&vs=850216052877139_3046300167&_nc_vs=HBksFQIYT2lnX3hwdl9yZWVsc19wZXJtYW5lbnRfcHJvZC8wQzQ0QkM3NDExQkZBRTRFMEJGRThDRkNDNkM1NUY4N192aWRlb19kYXNoaW5pdC5tcDQVAALIAQAVABgkR0JxTER4TnRSTGVONW5RQ0FMeUt3RXlDUG1VamJxX0VBQUFGFQICyAEAKAAYABsBiAd1c2Vfb2lsATEVAAAmpr7SjvTE9UAVAigCQzMsF0A0CHKwIMScGBJkYXNoX2Jhc2VsaW5lXzFfdjERAHUAAA%3D%3D&ccb=9-4&oh=00_AfB-PxD9RZ15FFtyJSXV1lSM3F-4SCcXppiEqDJQu4fICA&oe=63AB2CC9&_nc_sid=ea0b6e&_nc_rid=eda3a22980",
                    "media_type": "VIDEO",
                    "thumbnail_url": null,
                    "comments_count": 1,
                    "like_count": 126,
                    "media_hashtag": [
                        "#weloveitsowemakeit",
                        "#madewithlove",
                        "#shareinlove",
                        "#passiontoserve",
                        "#feeltherealbread",
                        "#bakerylife",
                        "#baker",
                        "#pizza",
                        "#christmas",
                        "#christmaseve",
                        "#tunggadewicake",
                        "#oleholehsurabaya",
                        "#kulinersurabaya",
                        "#jawatimur",
                        "#bukancakepabrikan",
                        "#bakerysurabaya",
                        "#surabayafood"
                    ],
                    "engagement_rate": "0.45216648271442306%"
                },
                "best_media_before": {
                    "id": "17855288639846606",
                    "permalink": "https://www.instagram.com/reel/asdas_3234/",
                    "timestamp": "2022-12-22T09:29:08+07:00",
                    "caption": "Ibu, adalah seseorang yang perannya tak dapat tergantikan .... #weloveitsowemakeit #madewithlove #shareinlove #selamathariibu #mothersday #hariibu",
                    "media_url": null,
                    "media_type": "VIDEO",
                    "thumbnail_url": null,
                    "comments_count": 0,
                    "like_count": 99,
                    "media_hashtag": [
                        "#weloveitsowemakeit",
                        "#madewithlove",
                        "#shareinlove",
                        "#selamathariibu",
                        "#mothersday",
                        "#hariibu"
                    ],
                    "engagement_rate": "0.35247623455691246%"
                }
            }

.. _fetch-user-ig-competitor-data:

User Data
=========

.. http:get:: /cekbrand/account/(int:account_id)/competitor-accounts/(int:competitor_account_id)/user-data

    Mengembalikan data akun Instagram kompetitor pengguna.

    :query string start: tanggal awal filter data in UTC-0 (ISO 8601 format)
    :query string end: tanggal akhir filter data in UTC-0 (ISO 8601 format)
    :query string date_frame: *frame* tanggal filter data, mencakup 7, 28, 60 dan 90

    **Contoh Response**:

    .. sourcecode:: http

        HTTP/1.1 200 OK
        Content-Type: application/json

        [
            {
                "followers_count": 2147483647,
                "follows_count": 2147483647,
                "media_count": 2147483647,
                "followers_count_growth": 2147483647,
                "media_count_growth": 2147483647,
                "updated_timestamp": "2022-12-26T12:52:53.198Z+07:00",
                "datestamp": "2022-12-26"
            }
        ]
