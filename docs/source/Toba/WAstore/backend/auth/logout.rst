Logout
+++++++

Pengguna dapat melakukan logout pengguna. Endpoint berikut digunakan untuk mengelola akun yang dimiliki

GET
======

.. http:get:: /auth/logout/

    Calls Django logout method and delete the Token object assigned to the current User object. Accepts/Returns nothing.



POST
======
.. http:post:: /auth/logout/

    Calls Django logout method and delete the Token object assigned to the current User object. Accepts/Returns nothing.
