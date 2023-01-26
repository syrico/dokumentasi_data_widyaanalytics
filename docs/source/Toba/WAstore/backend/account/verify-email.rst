Verify Email
++++++++++++

Pengguna dapat melakukan pengaturan untuk dilakukan verifikasi email. Endpoint berikut digunakan untuk mengelola akun yang dimiliki sebagai berikut.

POST
=====

.. http:post:: /account/verify-email/

    Untuk mengirimkan key verifikasi email ke pengguna

    **Parameter**:

    .. sourcecode:: json

        {
            "key": "string"
        }


    **Contoh Response**:

    .. sourcecode:: json

        {
            "key": "string"
        }


RESEND
======

.. http:patch:: /account/verify-email/resend/

    Resend email confirmation to user up to three times