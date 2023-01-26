
Facebook Authentication
+++++++++++++++++++++++

Untuk mendapatkan data Instagram diperlukan akses terhadap akun Facebook pengguna.
Di bawah ini adalah endpoint yang digunakan dalam proses autentikasi akun Facebook.

.. _fb-auth-login:

Login
=====

.. http:get:: /user/auth/facebook/login/?process=connect

    Meminta alamat halaman otentikasi Facebook untuk melakukan *connecting* akun Facebbok dengan pengguna.

    :query string process: harus bernilai ``connect``

    **Contoh Response**:

    .. sourcecode:: http

        HTTP/1.1 200 OK

        "https://www.facebook.com/v8.0/dialog/oauth?client_id=390623xxxxxxxxx&redirect_uri=https%3A%2F%apps.toba.ai%3A8081%2Frestapi%2Fuser%2Fauth%2Ffacebook%2Fcallback%2F&scope=pages_show_list+pages_read_engagement+email+instagram_basic+instagram_manage_insights&response_type=code&state=99cSbIHiA4v3&auth_type=reauthenticate"

.. _fb-auth-login-callback:

Login Callback
==============

.. http:get:: /user/auth/facebook/login/callback

    Ini adalah endpoint *callback* yang digunakan oleh Facebook untuk mengirimkan kode otorisasi yang akan dilampirkan pada parameter query url.
    Kemudian kode tersebut akan digunakan untuk mendapatakn token akses jangka panjang.

    :query string code: merupakan kode otorisasi yang diberikan oleh Facebook.
    
    .. note::

        Jika dalam parameter query tidak ditemukan `code` maka dapat dipastikan terdapat error pada proses login Facebook atau alamat request.

    .. figure:: ../images/uml/fb-callback-login.png
            :alt: fetch ig data diagram

.. _fb-auth-callback:

Callback
========

.. http:get:: /user/auth/facebook/callback

    Endpoint ini melakukan *redirect* callback Facebook untuk diteruskan menggunakan endpoint **Login Callback** melalui frontend.
    Hal ini diperlukan karena endpoint **Login Callback** hanya dapat digunakan oleh pengguna terotentikasi.
