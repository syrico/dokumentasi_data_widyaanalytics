Payments
+++++++

Untuk dilakukan pertukaran data dengan Midtrans dalam melakukan pembayaran. Endpoint berikut digunakan untuk mengelola akun yang dimiliki

GET
=====

.. http:get:: /payments/callback/

    Payment re-callback from Midtrans snap transaction

POST
=====

.. http:post:: /payments/notification/handling/

    Notification auto update from Midtrans

   **Parameter**:

   .. sourcecode:: json
        	
        {
            "order_id": "string",
            "status_code": "string",
            "gross_amount": "string",
            "signature_key": "string"
        }


   **Contoh Response**:

   .. sourcecode:: json

        {
            "order_id": "string",
            "status_code": "string",
            "gross_amount": "string",
            "signature_key": "string"
        }