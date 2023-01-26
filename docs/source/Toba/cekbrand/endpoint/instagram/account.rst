Account
+++++++

Account adalah akun Instagram pengguna yang tersimpan dalam layanan CekBrand.

**Penjelasan Parameter URL**

.. list-table:: 
      :widths: 15 80
      :header-rows: 1

      * - Parameter
        - Deskripsi
      * - account_id
        - ID akun Instagram pengguna
      * - social_account_id
        - ID akun Facebook pengguna
      * - username
        - username akun Instagram

.. _fetch-ig-data:

Add/Fetch Instagram Data
========================

.. http:post:: /cekbrand/instagram-graph-api/fetch-instagram-data/(int:account_id)

    Menambahkan akun Instagram menggunakan akun Facebook yang sudah terhubung.
    Akun Instagram yang ingin ditambahkan akan mengupdate data yang sudah ada.
    Data yang di ambil menggunakan Facebook Graph API antara lain profile, insights, media dan comment.
    Selain itu endpoint ini akan menjalankan *triggger* untuk menjalankan fungsi analitik untuk metrik hashtag dan sentimen media.
    Fungsi-fungsi analitik tersebut didefiniskan sebagai submodule dari repositori berikut_.
    
    .. _berikut: https://github.com/Widya-Analytic/cekbrand

    **Contoh Request Body**:

    .. sourcecode:: json

        {
            "id": "string"
        }

    :<json string id: social account ID

    **Contoh Response**:

    .. sourcecode:: http

        HTTP/1.1 200 OK

        <<instagram account data>>

    .. toggle-header::
        :header: **Diagram Alur**

        .. figure:: ../images/uml/fetch-ig-data.png
            :alt: fetch ig data diagram
        

.. _account-list:

Account List
============

.. http:get:: /cekbrand/accounts
    
    Mengembalikan daftar semua akun Instagram pengguna.

    .. toggle-header::
        :header: **Contoh Response**:

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
                    "social_account": {
                        "id": 0,
                        "uid": "string",
                        "name": "string",
                        "email": "string"
                    },
                    "updated_timestamp": "2022-12-26T12:47:29.216Z",
                    "latest_user_data": {
                        "followers_count": 0,
                        "follows_count": 0,
                        "media_count": 0,
                        "followers_count_growth": 0,
                        "media_count_growth": 0,
                        "updated_timestamp": "2022-12-26T20:25:53+07:00",
                        "datestamp": "2022-12-26"
                    }
                }
            ]

.. _account-detail:

Account Detail
==============

.. http:get:: /cekbrand/accounts/(int:account_id)

    Mengembalikan detail data akun Instagram pengguna.

    .. toggle-header::
        :header: **Contoh Response**:

        .. sourcecode:: http

            HTTP/1.1 200 OK
            Content-Type: application/json

            {
                "biography": "string",
                "id": "string",
                "name": "string",
                "profile_picture_url": "string",
                "username": "string",
                "social_account": {
                    "id": 0,
                    "uid": "string",
                    "name": "string",
                    "email": "string"
                },
                "updated_timestamp": "2022-12-26T12:45:41.153Z+07:00",
                "latest_user_data": {
                    "followers_count": 0,
                    "follows_count": 0,
                    "media_count": 0,
                    "followers_count_growth": 0,
                    "media_count_growth": 0,
                    "updated_timestamp": "2022-12-26T20:25:53+07:00",
                    "datestamp": "2022-12-26"
                }
            }

Account Delete
==============

.. http:delete:: /cekbrand/accounts/(int:account_id)

    Mengapus (*disconnecting*) akun Instagram pengguna. Akan tetapi data terkait tidak dihapus.

.. _fetch-user-data:

User Data
=========

.. http:get:: /cekbrand/accounts/(int:account_id)/user-data

    Mengembalikan daftar data profil akun Instagram pengguna.

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
                "updated_timestamp": "2022-12-26T12:48:39.190Z+07:00",
                "datestamp": "2022-12-26"
            }
        ]

    :>json int followers_count: jumlah akun pengikut
    :>json int follows_count: jumlah akun yang diikuti
    :>json int media_count: jumlah media akun
    :>json int followers_count_growth: kenaikan jumlah akun pengikut
    :>json int media_count_growth: kenaikan jumlah media akun
    :>json string updated_timestamp: waktu data terakhir diperbaharui
    :>json string datestamp: tanggal data terakhir diperbaharui

.. _user-data-summary:

User Data Summary
=================

.. http:get:: /cekbrand/accounts/(int:account_id)/user-data/summary

    Mengembalikan data summary profil akun Instagram pengguna. Data tersebut mencakup nilai *followers growth rate* akun terkait.

    :query string start: tanggal awal filter data in UTC-0 (ISO 8601 format)
    :query string end: tanggal akhir filter data in UTC-0 (ISO 8601 format)
    :query string date_frame: *frame* tanggal filter data, mencakup 7, 28, 60 dan 90

    **Contoh Response**:

    .. sourcecode:: http

        HTTP/1.1 200 OK
        Content-Type: application/json

        {
            "followers_growth_rate": "2.1506744718757953%",
            "followers_growth_rate_before": "1.6427370327253912%",
            "followers_growth_rate_growth": "0.5079374391504041%"
        }

    :>json string followers_growth_rate: *rate* peningkatan jumlah pengikut pada rentang tanggal
    :>json string followers_growth_rate_before: *rate* peningkatan jumlah pengikut sebelum rentang tanggal
    :>json string followers_growth_rate_growth: selisih *rate* peningkatan jumlah pengikut dari sebelum rentang tanggal

Re-Authorization
================

.. http:put:: /cekbrand/instagram-graph-api/re-authorization/(int:social_account_id)

    Akun Instagram maupun Facebook yang terhubung ke layanan CekBrand memiliki masa kadaluarsa sehingga pada waktu tersebut pengguna akan diminta untuk melakukan otoriasi ulang menggunakan endpoint ini.

    **Contoh Response**:

    .. sourcecode:: http

        HTTP/1.1 200 OK

Check Instagram Business
========================

.. http:get:: /cekbrand/instagram-graph-api/instagram-business/(string:username)

    Mengembalikan data akun Instagram dengan parameter username. Data yang dikembalikan bersifat publik.

    **Contoh Response**:

    .. sourcecode:: http

        HTTP/1.1 200 OK
        Content-Type: application/json

        {
            "username": "string",
            "name": "string",
            "profile_picture_url": "https://scontent.fsrg1-1.fna.fbcdn.net/v/t51.2885-15/&oe=XXXXXX",
            "id": "17841423423423432"
        }