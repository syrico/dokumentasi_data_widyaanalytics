Payments
++++++++

Untuk dilakukan pertukaran data dengan Midtrans dalam melakukan pembayaran. Endpoint berikut digunakan untuk mengelola akun yang dimiliki

Callback Payments
=================

.. http:get:: /payments/callback/
    
    Memperoleh list untuk *callback* dari Midtrans
    
    .. note::
        *Payment re-callback from Midtrans snap transaction*

Add Notification
================

.. http:post:: /payments/notification/handling/

    Menambahkan notifikasi *payments* dari Midtrans

    .. note::
        Notification auto update from Midtrans

    **Contoh Response**:

    .. sourcecode:: json

        {
            "order_id": "string",
            "status_code": "string",
            "gross_amount": "string",
            "signature_key": "string"
        }