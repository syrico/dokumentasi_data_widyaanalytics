Slide
+++++

Untuk memperoleh data *slide*. Endpoint yang digunakan sebagai berikut.

List Slide
==========

.. http:get:: /landing/swiper/slides/

    Mengembalikan data list *slide* yang tersedia.

    .. note::
        A viewset for viewing and editing swiper slide instances.


    **Contoh Response**:

    .. sourcecode:: json

        [
            {
                "id": "3fa85f64-5717-4562-b3fc-2c963f66afa6",
                "category": "product",
                "title": "string",
                "subtitle": "string",
                "description": "string",
                "button_text": "string",
                "event_speaker": "string",
                "event_speaker_origin": "string",
                "event_registration_link": "www.BCLY2LPN+m2to3PJPQOLOloxP=jPii1_k15=3bnHzdPJK0f9bR6pm9E@HKw9gE:z0=NDkbIdCK2jU=4K.KQFF%aA=Dx9XeKQN_WJtmNM0N-1EtC-M_gzrgIGBbK8@qH0j-3RqoSBx3NhGgcdyFiLZhDjfd6.hxDWtLI603nZb-.MY.lic8wxFHG=22wMy6Lwg.#=_~)6#:#CS3NU9=#kGnD5I/d-O",
                "event_start": "2022-12-29T15:13:55.896Z",
                "event_end": "2022-12-29T15:13:55.896Z",
                "event_is_online": true,
                "video_duration": 2147483647,
                "video_link": "https://XXQqVDOeyW.R6jGPQSH6aLW0BfuHQA.dkuzimXYcdNACr/(+jLj8.9YuZZEJ+3~rT6P(7=5Ev(fJ-5AptJMD8s",
                "product_link": "https://1Zc1pZlTE4XORKpj~J#HBF6fTzfzQ.C9+Jw9.lqbfeya65GDDY(DETXvRZc9XN",
                "font_color": "#AA2Eae",
                "background_colors": {},
                "is_active": true,
                "created_at": "2022-12-29T15:13:55.898Z",
                "updated_at": "2022-12-29T15:13:55.898Z",
                "image": "string"
            }
        ]

Add Slide
=========

.. http:post:: /landing/swiper/slides/

    Menambahkan data *slide* baru.

    .. note::
        A viewset for viewing and editing swiper slide instances.

    **Contoh Response**:

    .. sourcecode:: json

        {
            "id": "3fa85f64-5717-4562-b3fc-2c963f66afa6",
            "category": "product",
            "title": "string",
            "subtitle": "string",
            "description": "string",
            "button_text": "string",
            "event_speaker": "string",
            "event_speaker_origin": "string",
            "event_registration_link": "http://UuXoy6lXb-fbzoCwwFLdaY@u@zLA3ey@tcJm~S8Hx45u+L9O~7_A#NVjpIjZ6740#X.wAl1RdNyqVs.lo)~D7L3sDg20wGpcM2hK7E4.9GV%P1g=?1nCXTK=2_",
            "event_start": "2022-12-29T15:15:24.174Z",
            "event_end": "2022-12-29T15:15:24.174Z",
            "event_is_online": true,
            "video_duration": 2147483647,
            "video_link": "B0LOolTOSkLrLhn-.:gTgf%Lg5wQmK9#+JvrSVuTkpdyvBYWDGKNciFjoCXNeDPE-LbiwGxp63I~JD:U0XDsM2GNXxNwD9TPMYBQzM0mjfmnn1=-JdVsacYX0VZmu_Iw%jyfH@984p2pfMxdx=33Af9p.kpdwRctepQjeiJEVV7FFCW7rGhFyY&ssWGU+-p&bozoGX8L@aj1x/Ac@Qzh7C1.1+OTK",
            "product_link": "Io=tXGE1xEpai~0IlW9Ee.qA3RasH+r_aAmYz=Um:D2Ll12:uX_MX.pWk_%l%m_%xCxLV:9cIsu-OCnb1f1s2d_6rKoSRgPWCeYV_D.8zOD@2NaazVYpYHA4tVeCDjD@Qh.jscNMz~REVtCJ@itrGEBN9OgMihCAz:NJ=g-1z10YZA1Ig.tapz7CBWhne927u+F+BjCrxnc/.H9o~8t3I?7gO-0MKUs(0FeyxkYWWlU#:+NS5YemUxDyV0T?@JF",
            "font_color": "#EF0",
            "background_colors": {},
            "is_active": true,
            "created_at": "2022-12-29T15:15:24.178Z",
            "updated_at": "2022-12-29T15:15:24.178Z",
            "image": "string"
        }

Detail Slide
============

.. http:get:: /landing/swiper/slides/(int:id)/

    Mengembalikan data list *slide* yang tersedia berdasarkan ``id``.

    .. note::
        A viewset for viewing and editing swiper slide instances.

    **Penjelasan Parameter URL**

    .. list-table::
      :widths: 15 80
      :header-rows: 1

      * - Parameter
        - Deskripsi
      * - id
        - ID yang memiliki nilai untuk mengidentifikasi *slides*

    **Contoh Response**:

    .. sourcecode:: json

        {
            "id": "3fa85f64-5717-4562-b3fc-2c963f66afa6",
            "category": "product",
            "title": "string",
            "subtitle": "string",
            "description": "string",
            "button_text": "string",
            "event_speaker": "string",
            "event_speaker_origin": "string",
            "event_registration_link": "https://GE17~R9yvq5wjvsssg4eOjt::q~1BySBslDy@ADR8%.nmBfRI-L3Gcrr+os%OsfsgR_-fAETzMf1Uj=ly76lKDCv.J2H@Q@mivdST~Jz4gCo_xFlKuRDcm8kTgbXf9pJ7rR1a4H.tuwzlaKz/f~W=F",
            "event_start": "2022-12-29T15:16:10.613Z",
            "event_end": "2022-12-29T15:16:10.613Z",
            "event_is_online": true,
            "video_duration": 2147483647,
            "video_link": "yR98iBYVSldtGEuY%C30o6M~t2ssbmZSoWxdZHEflgtvbkV3#g9n@88LFrYs0~0.O3#TXE0.ngrU#o5f.jb6QA-@gStA~nv0u5.chYrIaW1LbTgYKk.ddvkhd/h6&2roAjsyu-Uw0n%-E-Mc@f=8fwZn1IOpXMM",
            "product_link": "www.VvoMseebp-4V@f:LDo0:zlk6l1.qqqof2=4fSQnHU2WDHMeiTg+8P2uGlJfwHkniRJmgVTegdCmK=+",
            "font_color": "#840",
            "background_colors": {},
            "is_active": true,
            "created_at": "2022-12-29T15:16:10.615Z",
            "updated_at": "2022-12-29T15:16:10.615Z",
            "image": "string"
        }

Update Slide
============

.. http:put:: /landing/swiper/slides/(int:id)/

    Memperbarui data list *slide* yang tersedia berdasarkan ``id``.

    .. note::
        A viewset for viewing and editing swiper slide instances.

    **Penjelasan Parameter URL**

    .. list-table::
      :widths: 15 80
      :header-rows: 1

      * - Parameter
        - Deskripsi
      * - id
        - ID yang memiliki nilai untuk mengidentifikasi *slide*

    **Contoh Response**:

    .. sourcecode:: json

        {
            "category": "product",
            "title": "string",
            "subtitle": "string",
            "description": "string",
            "button_text": "string",
            "event_speaker": "string",
            "event_speaker_origin": "string",
            "event_registration_link": "https://ynW8E#oAUp3WQ%-A_YKH.p+L3BRvdpuxm92ILq9Qo.dlkf.tDDl%=+c8pVXzFRRH#Q:EYchU23eq_ngvjBlSYFifzV5ju-1Y9@ABoxI?#CUPbIDWQPm2aJTo",
            "event_start": "2022-12-29T15:17:49.066Z",
            "event_end": "2022-12-29T15:17:49.066Z",
            "event_is_online": true,
            "video_duration": 2147483647,
            "video_link": "https://fkwANuuG:py.nhsCFq+Ur=Cx9S6W3mqjOJ6%kSqL44swtSWZBWxxWTXj9%-HdKcF8UnuwHS9eJJId7oesR1d=j#rAPX2.eaxp-+Y.sQAhulVqX_biTVe",
            "product_link": "www.JSj0P+.EFI9BVl3xJjP-I29TAHcU3KveW@y@myeVGVlP98Hl7DsbAu7ILP=MSC~INAuj2xhdGO3Y8IR7pt0z-ne_y7hFJP0_njsUy5u1Cf.PM-BhQnwz_0kx7PnmMcj15CHy%:YODUO8ObV4ylAjqzy.ebcj.Zx3d&G:aCxF%=tygZDxXdzEA9@)Nyz_?x70yksGMGLfR55O?XpLuGrqF%MujpBR&",
            "font_color": "#aB8",
            "background_colors": {},
            "is_active": true
        }

Delate Event
============

.. http:delete:: /landing/swiper/slides/(int:id)/

    Menghapus data list *slide* yang tersedia berdasarkan ``id``.

    .. note::
        A viewset for viewing and editing swiper slide instances.

    **Penjelasan Parameter URL**

    .. list-table::
        :widths: 15 80
        :header-rows: 1

      * - Parameter
        - Deskripsi
      * - id
        - ID yang memiliki nilai untuk mengidentifikasi *slide*