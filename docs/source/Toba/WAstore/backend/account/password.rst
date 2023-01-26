Password Change
+++++++++++++++

Pengguna dapat melakukan pengaturan terhadap password akun. Endpoint berikut digunakan untuk mengubah password user.

POST
====

.. http:post:: /account/password/change

    Accepts the following POST parameters: new_password1, new_password2 Returns the success/fail message.

    **Parameters**:

    .. sourcecode:: json

        {
            "old_password": "string",
            "new_password1": "string",
            "new_password2": "string"
        }


    **Contoh Response**:

    .. sourcecode:: json

        {
            "old_password": "string",
            "new_password1": "string",
            "new_password2": "string"
        }