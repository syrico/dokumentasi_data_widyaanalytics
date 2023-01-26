Account Media
+++++++++++++

Data media akun Instagram pengguna dapat diakses menggunakan endpoint berikut.

**Penjelasan Parameter URL**

.. list-table:: 
      :widths: 15 80
      :header-rows: 1

      * - Parameter
        - Deskripsi
      * - account_id
        - ID akun Instagram pengguna
      * - media_id
        - ID media akun Instagram pengguna

List
====

.. http:get:: /cekbrand/accounts/(int:account_id)/media

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
                "timestamp": "2022-12-26T12:57:06.111Z",
                "caption": "string",
                "like_count": 2147483647,
                "comments_count": 2147483647,
                "media_url": "string",
                "thumbnail_url": "string",
                "media_hashtag": [
                    "string"
                ],
                "insights": "string"
            }
        ]

Detail
======

.. http:get:: /cekbrand/accounts/(int:account_id)/media/(string:media_id)

    Mengembalikan data detail media akun Instagram pengguna.

    **Contoh Response**:

    .. sourcecode:: http

        HTTP/1.1 200 OK
        Content-Type: application/json

        {
            "id": "string",
            "permalink": "string",
            "media_type": "string",
            "timestamp": "2022-12-26T12:57:35.283Z",
            "caption": "string",
            "like_count": 2147483647,
            "comments_count": 2147483647,
            "media_url": "string",
            "thumbnail_url": "string",
            "media_hashtag": [
                "string"
            ],
            "insights": "string"
        }

Summary
=======

.. http:get:: /cekbrand/accounts/(int:account_id)/media/summary

    Mengembalikan data *summary* media akun Instagram pengguna.

    :query string start: tanggal awal filter data in UTC-0 (ISO 8601 format)
    :query string end: tanggal akhir filter data in UTC-0 (ISO 8601 format)
    :query string date_frame: *frame* tanggal filter data, mencakup 7, 28, 60 dan 90

    .. toggle-header::
        :header: **Contoh Response**:

        .. sourcecode:: http

            HTTP/1.1 200 OK
            Content-Type: application/json

            {
                "earliest_media": {
                    "id": "string",
                    "timestamp": "2022-12-22T12:45:05+07:00"
                },
                "highest_engagement_media": {
                    "id": "string",
                    "permalink": "string",
                    "timestamp": "2022-12-24T12:45:04+07:00",
                    "caption": "string",
                    "media_url": "string",
                    "media_type": "IMAGE",
                    "thumbnail_url": null,
                    "like_count": 13,
                    "comments_count": 0,
                    "media_hashtag": [
                        "string",
                    ],
                    "insights": [
                    {
                        "metric": "engagement",
                        "value": 13,
                        "updated_timestamp": "2022-12-26T20:44:36+07:00",
                        "datestamp": "2022-12-26"
                    },
                    {
                        "metric": "reach",
                        "value": 264,
                        "updated_timestamp": "2022-12-26T20:44:36+07:00",
                        "datestamp": "2022-12-26"
                    },
                    {
                        "metric": "impressions",
                        "value": 278,
                        "updated_timestamp": "2022-12-26T20:44:36+07:00",
                        "datestamp": "2022-12-26"
                    },
                    {
                        "metric": "saved",
                        "value": 0,
                        "updated_timestamp": "2022-12-26T20:44:36+07:00",
                        "datestamp": "2022-12-26"
                    }
                    ],
                    "engagement": 13
                },
                "highest_engagement_media_before": {
                    "id": "string",
                    "permalink": "string",
                    "timestamp": "2022-12-23T15:00:06+07:00",
                    "caption": "string",
                    "media_url": "string",
                    "media_type": "CAROUSEL_ALBUM",
                    "thumbnail_url": null,
                    "like_count": 7,
                    "comments_count": 0,
                    "media_hashtag": [
                        "string",
                    ],
                    "insights": [
                    {
                        "metric": "carousel_album_engagement",
                        "value": 8,
                        "updated_timestamp": "2022-12-26T20:44:31+07:00",
                        "datestamp": "2022-12-26"
                    },
                    {
                        "metric": "carousel_album_impressions",
                        "value": 213,
                        "updated_timestamp": "2022-12-26T20:44:31+07:00",
                        "datestamp": "2022-12-26"
                    },
                    {
                        "metric": "carousel_album_reach",
                        "value": 166,
                        "updated_timestamp": "2022-12-26T20:44:31+07:00",
                        "datestamp": "2022-12-26"
                    },
                    {
                        "metric": "saved",
                        "value": 1,
                        "updated_timestamp": "2022-12-26T20:44:31+07:00",
                        "datestamp": "2022-12-26"
                    },
                    {
                        "metric": "video_views",
                        "value": 0,
                        "updated_timestamp": "2022-12-26T20:44:31+07:00",
                        "datestamp": "2022-12-26"
                    }
                    ],
                    "engagement": 7
                },
                "highest_reach_media": {
                    "id": "string",
                    "timestamp": "2022-12-22T12:45:05+07:00",
                    "caption": "string",
                    "media_url": "string",
                    "thumbnail_url": null,
                    "like_count": 11,
                    "comments_count": 0,
                    "reach": 347
                },
                "highest_reach_media_before": null
            }

.. _fetch-comment-list:

Comments List
=============

.. http:get:: /cekbrand/accounts/(int:account_id)/media/(string:media_id)/comments

    Mengembalikan daftar data komentar media akun Instagram pengguna.

    **Contoh Response**:

    .. sourcecode:: http

        HTTP/1.1 200 OK
        Content-Type: application/json

        [
            {
                "id": "string",
                "username": "string",
                "text": "string",
                "sentiment": "string"
            }
        ]

.. _fetch-sentiment-media:

Sentiment
=========

.. http:get:: /cekbrand/accounts/(int:account_id)/media/(string:media_id)/sentiment

    Mengembalikan data sentiment media akun Instagram pengguna.

    **Contoh Response**:

    .. sourcecode:: http

        HTTP/1.1 200 OK
        Content-Type: application/json

        {
            "neg": 0,
            "pos": 0,
            "neu": 0
        }

.. _engagement-list:

Engagement List
===============

.. http:get:: /cekbrand/accounts/(int:account_id)/media/engagement

    Mengembalikan daftar data engagement media akun Instagram pengguna.

    :query string start: tanggal awal filter data in UTC-0 (ISO 8601 format)
    :query string end: tanggal akhir filter data in UTC-0 (ISO 8601 format)
    :query string date_frame: *frame* tanggal filter data, mencakup 7, 28, 60 dan 90

    **Contoh Response**:

    .. sourcecode:: http

        HTTP/1.1 200 OK
        Content-Type: application/json

        [
            {
                "count": 0,
                "like_count": 0,
                "comments_count": 0,
                "like_count_growth": 0,
                "comments_count_growth": 0,
                "updated_datestamp": "2022-12-26"
            }
        ]

Engagement Rate Standard Value
==============================

.. http:get:: /cekbrand/accounts/(int:account_id)/media/engagement-rate-standart-value

    Mengembalikan data standar engagament rate akun Instagram pengguna berdasarkan kelompok jumlah followers.

    :query string start: tanggal awal filter data in UTC-0 (ISO 8601 format)
    :query string end: tanggal akhir filter data in UTC-0 (ISO 8601 format)
    :query string date_frame: *frame* tanggal filter data, mencakup 7, 28, 60 dan 90

    **Contoh Response**:

    .. sourcecode:: http

        HTTP/1.1 200 OK
        Content-Type: application/json

        {
            "followers_range": "string",
            "standart_value": 0,
            "range_0": 0,
            "range_1": 0,
            "range_2": 0,
            "range_3": 0,
            "range_4": 0,
            "range_5": 0,
            "min_followers": 2147483647,
            "max_followers": 2147483647
        }

Engagement Average Summary
===============================

.. http:get:: /cekbrand/accounts/(int:account_id)/media/engagement/average/summary

    Mengembalikan data *summary* rerata engagament media akun Instagram pengguna.

    :query string start: tanggal awal filter data in UTC-0 (ISO 8601 format)
    :query string end: tanggal akhir filter data in UTC-0 (ISO 8601 format)
    :query string date_frame: *frame* tanggal filter data, mencakup 7, 28, 60 dan 90

    **Contoh Response**:

    .. sourcecode:: http

        HTTP/1.1 200 OK
        Content-Type: application/json

        {
            "engagement_average_rate": "0.19783231593372372%",
            "engagement_average_rate_before": "0.2678460196835679%",
            "engagement_average_rate_growth": "-0.0700137037498442%",
            "comments_average": 0.08,
            "comments_average_before": 1.5416666666666667,
            "comments_average_growth": -1.4616666666666667,
            "like_average": 15.8,
            "like_average_before": 19.958333333333332,
            "like_average_growth": -4.158333333333331
        }

.. _engagement-summary:

Engagement Summary
==================

.. http:get:: /cekbrand/accounts/(int:account_id)/media/engagement/summary

    Mengembalikan data *summary* engagement media akun Instagram pengguna.

    :query string start: tanggal awal filter data in UTC-0 (ISO 8601 format)
    :query string end: tanggal akhir filter data in UTC-0 (ISO 8601 format)
    :query string date_frame: *frame* tanggal filter data, mencakup 7, 28, 60 dan 90

    **Contoh Response**:

    .. sourcecode:: http

        HTTP/1.1 200 OK
        Content-Type: application/json

        {
            "engagement_growth_rate": "5.618537436152984%",
            "engagement_growth_rate_before": "6.55383049121914%",
            "engagement_growth_rate_growth": "-0.9352930550661558%"
        }
