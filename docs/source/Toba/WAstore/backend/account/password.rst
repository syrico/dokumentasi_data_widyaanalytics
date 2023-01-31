Password Change
+++++++++++++++

Pengguna dapat melakukan pengaturan terhadap password akun yang baru. Endpoint berikut digunakan untuk mengubah password user.

Add
===

.. http:post:: /account/password/change/

    Menambahkan password baru

    .. note::
        - Accepts the following POST parameters: new_password1, new_password2 
        - Returns the success/fail message.

    
    **Contoh Response**:

    .. sourcecode:: json

        {
            "old_password": "string",
            "new_password1": "string",
            "new_password2": "string"
        }