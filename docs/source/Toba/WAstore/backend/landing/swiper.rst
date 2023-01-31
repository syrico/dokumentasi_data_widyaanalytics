Swiper
++++++

Untuk memperoleh data *swiper*. Endpoint yang digunakan sebagai berikut.

List Swiper Slides
==================

.. http:get:: /landing/swiper/

    Mengembalikan data list *landing swiper* yang tersedia.

    .. note::
        View for listing and updating swiper slides.


    **Contoh Response**:

    .. sourcecode:: json

        [
            {
                "order": 0,
                "slide_id": "3fa85f64-5717-4562-b3fc-2c963f66afa6",
                "is_show": true
            }
        ]

Update Swiper Slides
====================

.. http:put:: /landing/swiper/

     Memperbarui data *landing swiper*.

    .. note::
        View for listing and updating swiper slides.

    **Contoh Response**:

    .. sourcecode:: json

        {
            "items": [
                {
                    "slide_id": "3fa85f64-5717-4562-b3fc-2c963f66afa6",
                    "is_show": true
                }
            ]
        }