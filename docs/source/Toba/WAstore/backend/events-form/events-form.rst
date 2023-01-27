Events Form
+++++++++++

Untuk memperoleh data *events form*. Endpoint yang digunakan sebagai berikut.

List Event Form
===============

.. http:get:: /events-form/

    Mengembalikan data list *events form* yang tersedia.

    .. note::
        A viewset for viewing and editing event form instances.

    **Contoh Response**:

    .. sourcecode:: json

        [
            {
                "event": "3fa85f64-5717-4562-b3fc-2c963f66afa6",
                "questions": [
                    {
                        "id": "3fa85f64-5717-4562-b3fc-2c963f66afa6",
                        "question": "string",
                        "type": "string",
                        "options": [
                            "string"
                        ],
                        "rules": {
                            "additionalProp1": "string",
                            "additionalProp2": "string",
                            "additionalProp3": "string"
                        },
                        "order": 0
                    }
                ]
            }
        ]

Add Event Form
==============

.. http:post:: /events-form/

    Menambahkan data *event form* baru.

    .. note::
        A viewset for viewing and editing event form instances.

    **Contoh Response**:

    .. sourcecode:: json

        {
            "event": "3fa85f64-5717-4562-b3fc-2c963f66afa6",
            "questions": [
                {
                    "id": "3fa85f64-5717-4562-b3fc-2c963f66afa6",
                    "question": "string",
                    "type": "string",
                    "options": [
                        "string"
                    ],
                    "rules": {
                        "additionalProp1": "string",
                        "additionalProp2": "string",
                        "additionalProp3": "string"
                    },
                    "order": 0
                }
            ]
        }

Detail Event Form
=================

.. http:get:: /events-form/(int:event)/

    Mengembalikan data list *Event Form* yang tersedia berdasarkan ``event``.

    .. note::
        A viewset for viewing and editing event form instances.


    **Penjelasan Parameter URL**

    .. list-table::
      :widths: 15 80
      :header-rows: 1

      * - Parameter
        - Deskripsi
      * - event
        - ID yang memiliki nilai untuk mengidentifikasi *event*

    **Contoh Response**:

    .. sourcecode:: json

        {
            "event": "3fa85f64-5717-4562-b3fc-2c963f66afa6",
            "questions": [
                {
                    "id": "3fa85f64-5717-4562-b3fc-2c963f66afa6",
                    "question": "string",
                    "type": "string",
                    "options": [
                        "string"
                    ],
                    "rules": {
                        "additionalProp1": "string",
                        "additionalProp2": "string",
                        "additionalProp3": "string"
                    },
                    "order": 0
                }
            ]
        }

Update Event Form
=================

.. http:put:: /events-form/(int:event)/

    Memperbarui data list *Event Form* yang tersedia berdasarkan ``event``.

    .. note::
        A viewset for viewing and editing event form instances.

    **Penjelasan Parameter URL**

    .. list-table::
      :widths: 15 80
      :header-rows: 1

      * - Parameter
        - Deskripsi
      * - event
        - ID yang memiliki nilai untuk mengidentifikasi *event*

    **Contoh Response**:

    .. sourcecode:: json

        {
            "event": "3fa85f64-5717-4562-b3fc-2c963f66afa6",
            "questions": [
                {
                    "question": "string",
                    "type": "string",
                    "options": [
                        "string"
                    ],
                    "rules": {
                        "additionalProp1": "string",
                        "additionalProp2": "string",
                        "additionalProp3": "string"
                    }
                }
            ]
        }

Delate Event Form
=================

.. http:delete:: /events-form/(int:id)/

    Menghapus data list *Event Form* yang tersedia berdasarkan ``event``.

    .. note::
        A viewset for viewing and editing event form instances.

    **Penjelasan Parameter URL**

    .. list-table::
      :widths: 15 80
      :header-rows: 1

      * - Parameter
        - Deskripsi
      * - event
        - ID yang memiliki nilai untuk mengidentifikasi *event*

Detail Answer
=============

.. http:get:: /events-form/(int:id)/answers/

    Mengembalikan data *answers* list *Event Form* yang tersedia berdasarkan ``id``.

    .. note::
        Convenience endpoint for getting list of answer instances for a event form.

    **Penjelasan Parameter URL**

    .. list-table::
      :widths: 15 80
      :header-rows: 1

      * - Parameter
        - Deskripsi
      * - id
        - ID yang memiliki nilai untuk mengidentifikasi *answer*

    **Contoh Response**:

    .. sourcecode:: json

        {
            "eventform": "string",
            "user": 0,
            "answers": [
                {}
            ],
            "created_at": "2022-12-29T14:38:18.310Z"
        }

Update Answer
=============

.. http:put:: /events-form/(id:event)/

    Memperbarui data *answers* list *Event Form* yang tersedia berdasarkan ``id``.

    .. note::
        A viewset for viewing and editing event form instances.

    **Penjelasan Parameter URL**

    .. list-table::
      :widths: 15 80
      :header-rows: 1

      * - Parameter
        - Deskripsi
      * - event
        - ID yang memiliki nilai untuk mengidentifikasi *event*

    **Contoh Response**:

    .. sourcecode:: json

        {
            "event": "3fa85f64-5717-4562-b3fc-2c963f66afa6",
            "questions": [
                {
                    "question": "string",
                    "type": "string",
                    "options": [
                        "string"
                    ],
                    "rules": {
                        "additionalProp1": "string",
                        "additionalProp2": "string",
                        "additionalProp3": "string"
                    }
                }
            ]
        }