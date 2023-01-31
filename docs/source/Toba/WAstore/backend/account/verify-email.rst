Verify Email
++++++++++++

Pengguna dapat melakukan pengaturan untuk dilakukan verifikasi email. Endpoint berikut digunakan untuk mengelola akun yang dimiliki sebagai berikut.

Add
===

.. http:post:: /account/verify-email/

    Menambahkan key verifikasi email.
    
    **Contoh Response**:

    .. sourcecode:: json

        {
            "key": "string"
        }


Resend Verify Email
===================

.. http:patch:: /account/verify-email/resend/

    Resend email confirmation to user up to three times