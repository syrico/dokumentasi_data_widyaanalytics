Logout
++++++

Pengguna dapat melakukan logout pengguna. Endpoint berikut digunakan untuk mengelola akun yang dimiliki

Logout List
===========

.. http:get:: /auth/logout/
    
    Mendapatkan list logout
    
    .. note::
        - Calls Django logout method and delete the Token object assigned to the current User object. Accepts/Returns nothing.
        - Accepts/Returns nothing.

Add Logout
==========

.. http:post:: /auth/logout/

    Menambahkan list logout

    .. note::
        - Calls Django logout method and delete the Token object assigned to the current User object. Accepts/Returns nothing.
        - Accepts/Returns nothing.