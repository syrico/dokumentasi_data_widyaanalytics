# Arsitektur Umum

![Arsitektur Umum](image/umum.png)

Secara umum, proses ETL dilakukan untuk meng-update data Schema Instagram yang kemudian juga akan digunakan untuk melakukan analisis seperti sentiment analysis dan user hastags metrics distribution analysis pada Schema Toba_Cek_Insta. Proses update dan analisis dijalankan dengan penjadwalan Airflow. Proses first fetch dilakukan oleh back-end, selebohnya dilakukan dilakukan oleh tim data. 