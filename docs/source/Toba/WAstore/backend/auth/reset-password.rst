Reset Password
++++++++++++++

Pengguna dapat melakukan reset password akun pengguna. Endpoint berikut digunakan untuk mengelola akun yang dimiliki

POST
====

.. http:post:: /auth/password/reset/

    Untuk melakukan reset password
    
    Calls Django Auth PasswordResetForm save method.

    Accepts the following POST parameters: email
    Returns the success/fail message.

    **Parameter**:

    .. sourcecode:: json
                
        {
            "email": "user@example.com"
        }


    **Contoh Response**:

    .. sourcecode:: json

        {
            "email": "user@example.com"
        }

POST
====

.. http:post:: /auth/password/reset/confirm/

    Untuk melakukan confirm reset password
    
    Password reset e-mail link is confirmed, therefore this resets the user's password.

    Accepts the following POST parameters: token, uid,
    new_password1, new_password2
    Returns the success/fail message.

    **Parameter**:

    .. sourcecode:: json

        {
            "new_password1": "string",
            "new_password2": "string",
            "uid": "string",
            "token": "string"
        }


    **Contoh Response**:

    .. sourcecode:: json

        {
            "new_password1": "string",
            "new_password2": "string",
            "uid": "string",
            "token": "string"
        }

POST
====

.. http:post:: /auth/obtain-authorization-token/

    Untuk melakukan authorization token
    
    Returns a JSON Web Token that can be used for authenticated requests.

    **Parameter**:

    .. sourcecode:: json

        {
            
        }


    **Contoh Response**:

    .. sourcecode:: json

        {
            
        }