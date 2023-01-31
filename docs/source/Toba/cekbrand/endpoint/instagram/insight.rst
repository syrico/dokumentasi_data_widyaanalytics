Account Insight
+++++++++++++++

Akun Instagram pengguna memiliki data beberapa jenis *insight* yang disediakan oleh Facebook Graph API.
Untuk mendapatkan data insight yang sudah tersimpan dapat menggunakan endpoint berikut.

**Penjelasan Parameter URL**

.. list-table:: 
      :widths: 15 80
      :header-rows: 1

      * - Parameter
        - Deskripsi
      * - account_id
        - ID akun Instagram pengguna
      * - country
        - Nama negara
      * - city
        - Nama kota

.. _audience-city:

Audience City
=============

.. http:get:: /cekbrand/accounts/(int:account_id)/insights/audience-city

    Mengembalikan data insight lokasi kota followers akun Instagram pengguna.

    :query string start: tanggal awal filter data in UTC-0 (ISO 8601 format)
    :query string end: tanggal akhir filter data in UTC-0 (ISO 8601 format)
    :query string date_frame: *frame* tanggal filter data, mencakup 7, 28, 60 dan 90

    **Contoh Response**:

    .. sourcecode:: http

        HTTP/1.1 200 OK
        Content-Type: application/json

        [
            {
                "city": "string",
                "province": "string",
                "value": 2147483647,
                "end_time": "2022-12-26T12:53:58.533Z+07:00",
                "updated_timestamp": "2022-12-26T12:53:58.533Z+07:00"
            }
        ]

.. _city-coordinate:

City Coordinate
========================

.. http:get:: /cekbrand/cities-coordinate/(string:country)/(string:city)

    Mengembalikan data koordinat kota.

    **Contoh Response**:

    .. sourcecode:: http

        HTTP/1.1 200 OK
        Content-Type: application/json

        {
            "city": "Bekasi",
            "city_ascii": "Bekasi",
            "lat": -6.2333,
            "lng": 107,
            "country": "Indonesia",
            "iso2": "ID",
            "iso3": "IDN",
            "admin_name": "Jawa Barat",
            "capital": "",
            "population": 2381053,
            "id": 1360006015
        }

.. _audience-country:

Audience Country
================

.. http:get:: /cekbrand/accounts/(int:account_id)/insights/audience-country

    Mengembalikan data insight lokasi negara followers akun Instagram pengguna.

    :query string start: tanggal awal filter data in UTC-0 (ISO 8601 format)
    :query string end: tanggal akhir filter data in UTC-0 (ISO 8601 format)
    :query string date_frame: *frame* tanggal filter data, mencakup 7, 28, 60 dan 90

    **Contoh Response**:

    .. sourcecode:: http

        HTTP/1.1 200 OK
        Content-Type: application/json

        [
            {
                "country_code": "string",
                "value": 2147483647,
                "end_time": "2022-12-26T12:54:20.318Z+07:00",
                "updated_timestamp": "2022-12-26T12:54:20.318Z+07:00"
            }
        ]

.. _audience-gender-age:

Audience Gender Age
===================

.. http:get:: /cekbrand/accounts/(int:account_id)/insights/audience-gender-age

    Mengembalikan data insight jenis kelamin dan umur followers akun Instagram pengguna.

    :query string start: tanggal awal filter data in UTC-0 (ISO 8601 format)
    :query string end: tanggal akhir filter data in UTC-0 (ISO 8601 format)
    :query string date_frame: *frame* tanggal filter data, mencakup 7, 28, 60 dan 90

    **Contoh Response**:

    .. sourcecode:: http

        HTTP/1.1 200 OK
        Content-Type: application/json

        [
            {
                "gender": "string",
                "age": "string",
                "value": 2147483647,
                "end_time": "2022-12-26T12:54:51.888Z+07:00",
                "updated_timestamp": "2022-12-26T12:54:51.888Z+07:00"
            }
        ]

.. _impressions-list:

Impressions List
================

.. http:get:: /cekbrand/accounts/(int:account_id)/insights/impressions

    Mengembalikan data insight impression akun Instagram pengguna.

    :query string start: tanggal awal filter data in UTC-0 (ISO 8601 format)
    :query string end: tanggal akhir filter data in UTC-0 (ISO 8601 format)
    :query string date_frame: *frame* tanggal filter data, mencakup 7, 28, 60 dan 90

    **Contoh Response**:

    .. sourcecode:: http

        HTTP/1.1 200 OK
        Content-Type: application/json

        [
            {
                "value": 2147483647,
                "end_time": "2022-12-26T12:55:13.983Z+07:00",
                "period": "string",
                "updated_timestamp": "2022-12-26T12:55:13.983Z+07:00"
            }
        ]

.. _impressions-average-summary:

Impressions Average Summary
===========================

.. http:get:: /cekbrand/accounts/(int:account_id)/insights/impressions/average/summary

    Mengembalikan data *summary* rerata impression akun Instagram pengguna.

    :query string start: tanggal awal filter data in UTC-0 (ISO 8601 format)
    :query string end: tanggal akhir filter data in UTC-0 (ISO 8601 format)
    :query string date_frame: *frame* tanggal filter data, mencakup 7, 28, 60 dan 90

    **Contoh Response**:

    .. sourcecode:: http

        HTTP/1.1 200 OK
        Content-Type: application/json

        {
            "impressions_average": 1658.8,
            "impressions_before_average": 1666.4,
            "impressions_average_growth": "-0.4560729716754763%"
        }

.. _online-followers:

Online Followers
================

.. http:get:: /cekbrand/accounts/(int:account_id)/insights/online-followers

    Mengembalikan data insight waktu aktif followers akun Instagram pengguna.

    :query string start: tanggal awal filter data in UTC-0 (ISO 8601 format)
    :query string end: tanggal akhir filter data in UTC-0 (ISO 8601 format)
    :query string date_frame: *frame* tanggal filter data, mencakup 7, 28, 60 dan 90

    **Contoh Response**:

    .. sourcecode:: http

        HTTP/1.1 200 OK
        Content-Type: application/json

        [
            {
                "hour": 2147483647,
                "value": 2147483647,
                "end_time": "2022-12-26T12:55:37.902Z+07:00",
                "updated_timestamp": "2022-12-26T12:55:37.902Z+07:00"
            }
        ]

.. _reach-list:

Reach List
==========

.. http:get:: /cekbrand/accounts/(int:account_id)/insights/reach

    Mengembalikan data insight reach followers akun Instagram pengguna.

    :query string start: tanggal awal filter data in UTC-0 (ISO 8601 format)
    :query string end: tanggal akhir filter data in UTC-0 (ISO 8601 format)
    :query string date_frame: *frame* tanggal filter data, mencakup 7, 28, 60 dan 90

    **Contoh Response**:

    .. sourcecode:: http

        HTTP/1.1 200 OK
        Content-Type: application/json

        [
            {
                "value": 2147483647,
                "end_time": "2022-12-26T12:55:59.293Z+07:00",
                "period": "string",
                "updated_timestamp": "2022-12-26T12:55:59.293Z+07:00"
            }
        ]

.. _reach-average-summary:

Reach Average Summary
=====================

.. http:get:: /cekbrand/accounts/(int:account_id)/insights/reach/average/summary

    Mengembalikan data *summary* rerata reach akun Instagram pengguna.

    :query string start: tanggal awal filter data in UTC-0 (ISO 8601 format)
    :query string end: tanggal akhir filter data in UTC-0 (ISO 8601 format)
    :query string date_frame: *frame* tanggal filter data, mencakup 7, 28, 60 dan 90

    **Contoh Response**:

    .. sourcecode:: http

        HTTP/1.1 200 OK
        Content-Type: application/json

        {
            "reach_average": 1322.2,
            "reach_average_before": 1277.8,
            "reach_average_growth": "3.4747221787447247%"
        }

.. _fetch-hashtag-ig-user-data:

Hashtag Metrics
===============

.. http:get:: /cekbrand/accounts/(int:account_id)/hashtag-metrics

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

