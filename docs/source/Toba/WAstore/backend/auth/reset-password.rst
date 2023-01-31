Reset Password
++++++++++++++

Pengguna dapat melakukan reset password akun pengguna. Endpoint berikut digunakan untuk mengelola akun yang dimiliki

Add Reset Password
==================

.. http:post:: /auth/password/reset/

    Untuk menambahkan reset password baru pengguna
    
    .. note::
        - Calls Django Auth PasswordResetForm save method.
        - Accepts the following POST parameters: email
        - Returns the success/fail message.

    **Contoh Response**:

    .. sourcecode:: json

        {
            "email": "user@example.com"
        }

Add Confirm Reset Password
==========================

.. http:post:: /auth/password/reset/confirm/

    Untuk melakukan confirm reset password
    
    .. note::
        - Password reset e-mail link is confirmed, therefore this resets the user's password.
        - Accepts the following POST parameters: token, uid, new_password1, new_password2
        -  Returns the success/fail message.

    **Contoh Response**:

    .. sourcecode:: json

        {
            "new_password1": "string",
            "new_password2": "string",
            "uid": "string",
            "token": "string"
        }

Add Authorization Token
=======================

.. http:post:: /auth/obtain-authorization-token/

    Untuk melakukan authorization token
    
    .. note::
        Returns a JSON Web Token that can be used for authenticated requests.

    **Contoh Response**:

    .. sourcecode:: json

        {
            
        }