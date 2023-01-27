Events
+++++++

Untuk memperoleh data *events*. Endpoint yang digunakan sebagai berikut.

List Event
==========

.. http:get:: /events/

    Mengembalikan data list *events* yang tersedia.

    .. note::
        A viewset for viewing and editing event instances.


    **Contoh Response**:

    .. sourcecode:: json

        [
            {
                "id": "3fa85f64-5717-4562-b3fc-2c963f66afa6",
                "name": "string",
                "description": "string",
                "category": "string",
                "speaker": "string",
                "venue": "string",
                "venue_link": "www.ym.tY1F@Be.F.cbfizPy?x_3#E683f1.SUHN9mkJRTLadiVV#rh-UOHF)=v/5q&cBL~QlxTmC_RRZw3+MG(laX)ak@mNmrLCflqof&.ZN)au",
                "group_link": "IQGrBbZANnLnLZ:lCS:tfnjq.~9#NjP2uW-ZbJU8#ETm838qfKOnHeSrB+o@uakF_LyIJv+GkSEbNs7m7N0lrAf2:K4OYV9U_YMhh7Z1l3~k.nxg2PX:O_DSnD8c9DMP&OC93T51Q:gj-w4UQMRD+&mAdEP2Kd3(V3t~lC.tVK-q0DWUy@n#VY3zmXu7",
                "blog_link": "https://j1@ougJ@k6ielHD=PZczY3uzXlJ=3NQZ6pqh.qpcfs9#04FDdPz4X1C#LfpF88&&)AUK~v:oP0)~oJ.HgOhbOueBY0fEFo_#yqMn%UXh%eImo8.su~",
                "price": 2147483647,
                "start_date": "2022-12-29",
                "end_date": "2022-12-29",
                "start_time": "string",
                "end_time": "string",
                "poster": "string",
                "created_at": "2022-12-29T14:48:09.550Z",
                "updated_at": "2022-12-29T14:48:09.550Z",
                "deleted_at": "2022-12-29T14:48:09.550Z"
            }
        ]

Add Event
=========

.. http:post:: /events/

     Menambahkan data *events* baru.

    .. note::
        A viewset for viewing and editing event instances.

    **Contoh Response**:

    .. sourcecode:: json

        {
            "name": "string",
            "description": "string",
            "category": "string",
            "speaker": "string",
            "venue": "string",
            "venue_link": "http://OURA-N82+SG+2gjiQX8gTgGk46G2rykcr=7QkzsqDZA4TY+zU-@l+Z3dOh4iIdj~Fz1s=4NPY.nX%x4DXGZR4vdtLqcpywd7FtH_.TOnHbXy.~WdgyWK%rnrlJAqVp1_3V4B5JFwasj5cZkJsgxo=4T@4OIzbjVOiq+k=xi1OCoc@clnVyCEiob+SGM7C7O=R7GfPsChqhJ2-3##-0wCwk70BhR9jbglVzyO~.bo~sQo#CxlD)C32W%&",
            "group_link": "B#~%kYDLx9JjF2oxegDTjiU8-Ds13d3#i_HIY.fQ-~z7iTLhgb9fX.3XyOS.fpo4ChjGH3XbfNXNLCvSxyylntH5.f:CuK78mvRfSZ9law5Wan4d3#YVqzXnmCRsNML#j99vTqgZpc1q31Mu#IUixSqVg@2A@m0euZHt9PGQAc4+xk.tuslKEl8DX3CS1n5WxB:(CEc)XCzdB",
            "blog_link": "https://www.9kXP#g2Xf#~c:i9_5-XIn#AdvominK5Uqa4lgfnSQ8iBNyDSyjW7ImYGOO~vIcY64B+kPLW:L%fys+S6f~Wcn@ycIU2erVik7drmiRrHfl.50ti5XgeJf7+X#FGeN1PVAFZvjB:ja8nYA2fsUHM2.=@NOKl@Ak_z9#2+=%4aNK@J6K8:+BNQklh.zO5XBS_o9EV~IUlTbfVusVOAPgh_~foXnefMqD6TQ_=A~sViDVho0zp-U1D",
            "price": 2147483647,
            "start_date": "2022-12-29",
            "end_date": "2022-12-29",
            "start_time": "string",
            "end_time": "string",
            "deleted_at": "2022-12-29T14:49:09.430Z"
        }

Detail Event
============

.. http:get:: /events/(int:id)/

    Mengembalikan data list *Event* yang tersedia berdasarkan ``id``.

    .. note::
        A viewset for viewing and editing event form instances.


    **Penjelasan Parameter URL**

    .. list-table::
      :widths: 15 80
      :header-rows: 1

      * - Parameter
        - Deskripsi
      * - id
        - ID yang memiliki nilai untuk mengidentifikasi *event*

    **Contoh Response**:

    .. sourcecode:: json

        {
            "id": "3fa85f64-5717-4562-b3fc-2c963f66afa6",
            "name": "string",
            "description": "string",
            "category": "string",
            "speaker": "string",
            "venue": "string",
            "venue_link": "www.PQ-OwWd5IA.a_a.8EJs:WLyhs:A5MM5V6DWVIv~QATbOq#RIMaE#v@MZVRV2kmFNkYYa.B.FWumrFtH5EMr4..zKo:0b1HnAtvmvD-4D~%i3EIOm9FT7~XkKsjro1k1jPMF8GPLgRxdyQ0gnyVJ_G7g9e@RVb.WmA9+0%H6ILRoB#H@L80aJoCa6NA2sdz@qndAOmlc=yJ6eJ8xz-%BoOy84KrXeYr%7.ymeTm?qycs).Q3v_Nfv",
            "group_link": "http://@h.IU42H.@94dtfMYE%uSG6R.etu2WOM%mp7oPPw2qk+CmKPG.tlkWo27iDa=Z-NwfNzn44L_Mxwe@P@XNZwUoTm7=:0cX4#JH.rnnyqv~1~C:FWjROLMAkR+Ak:wjP-Supu2b(=6xCD",
            "blog_link": "sTc.kecpolnz/xYs3eb0vwcR.1rXko=5VT/7FP6ya?R0c(XVcy8Wv4dSAmIOkHD:FHl2f&M:RUQ%=YMcONvblsb(V_kR2ZFFAWa2v",
            "price": 2147483647,
            "start_date": "2022-12-29",
            "end_date": "2022-12-29",
            "start_time": "string",
            "end_time": "string",
            "poster": "string",
            "created_at": "2022-12-29T14:49:42.560Z",
            "updated_at": "2022-12-29T14:49:42.560Z",
            "deleted_at": "2022-12-29T14:49:42.560Z"
        }

Update Event
============

.. http:put:: /events/(int:id)/

    Memperbarui data list *Event* yang tersedia berdasarkan ``id``.

    .. note::
        A viewset for viewing and editing event form instances.

    **Penjelasan Parameter URL**

    .. list-table::
      :widths: 15 80
      :header-rows: 1

      * - Parameter
        - Deskripsi
      * - id
        - ID yang memiliki nilai untuk mengidentifikasi *event*

    **Contoh Response**:

    .. sourcecode:: json

        {
            "name": "string",
            "description": "string",
            "category": "string",
            "speaker": "string",
            "venue": "string",
            "venue_link": "LEsBS~ZJU3xqj=43z=NMeFFK4HYVsHnwxVbH3.uKX.OvuueBAi#lDAVUcdCMFl0ydveyN.O.udfqxpKvZKw@-v7Y@FLo-mltV55=l8@Xu@ZntGXoepz-2NCMvgIDyPgiWqesfoCrB+%1CG@lmGR_dKnjMPDUZ4q#hX5+Q-E_=ukrLrEz@.zbmvkt&%:Cx1VZP?3tr=SLI)3/:wAMI#MVmQOTHqhc/JDq%BS5+Za+k&_ZQ1IXi_waSaG/%497BcY",
            "group_link": "http://www.13PHsRqB6Vqob+~e=gRxG%U~1xUs5L:9R=G~WCuET73A30NMFL81hL5cC@wtQl4@g1vJd.=ZxAmmIr2:yMAKxE+kq3xqTQEkDVGV9~Nlb6PmPA8JI-E8PCCk~A:d4Cch3o~~Dql_kc4avEV0P@1gbcWU==36yV_.v#efrV@Ys-WpZa@L@LCSystjI6QgebBdK5M1e-da%dych:%%joa+A7U0K~A.km_Yf4gGeGn/9kglLR)",
            "blog_link": "www.UC@fmPw2HGrNSOwnXA8=xCHNGo.IuknE-SCYFNYP7sebD3+DCO#9rzHCcBFpwmeX57L0GeDEN.X#aTnSf#38M%_@xvro~+uZcFZr@KY_io_~IuSZY6F@DZyMAhbGr3jDM7iKFG7E:+E.yef-nq-BmAEUHo(()6v=saQyG2dRPyqEUN9VhS80L",
            "price": 2147483647,
            "start_date": "2022-12-29",
            "end_date": "2022-12-29",
            "start_time": "string",
            "end_time": "string",
            "deleted_at": "2022-12-29T14:51:10.419Z"
        }

Delate Event
============

.. http:delete:: /events/(int:id)/

    Menghapus data list *Event* yang tersedia berdasarkan ``id``.

    .. note::
        A viewset for viewing and editing event form instances.

    **Penjelasan Parameter URL**

    .. list-table::
      :widths: 15 80
      :header-rows: 1

      * - Parameter
        - Deskripsi
      * - id
        - ID yang memiliki nilai untuk mengidentifikasi *event*