Notification
++++++++++++

Pengaturan untuk notifikasi WNS. Endpoint berikut digunakan untuk mengelola akun yang dimiliki

Add
===

.. http:post:: /notification/push/device/wns/

    Untuk menambahkan *list* notifikasi 
    
    .. note::
        - Calls Django Auth PasswordResetForm save method.
        - Accepts the following POST parameters: email
        - Returns the success/fail message.

    **Contoh Response**:

    .. sourcecode:: json

        {
            "id": 0,
            "name": "string",
            "registration_id": "string",
            "active": true,
            "date_created": "2022-12-27T09:10:22.366Z",
            "p256dh": "string",
            "auth": "string",
            "browser": "CHROME",
            "application_id": "string"
        }