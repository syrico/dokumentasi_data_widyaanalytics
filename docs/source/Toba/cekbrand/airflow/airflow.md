# Apache Airflow

![Logo Apache Airflow](image/airflow.png)

Komunitas mengembangkan platform Airflow untuk memungkinkan pembuatan program, penjadwalan, dan pemantauan proses yang scalable, dinamis, extensible, dan elegan. Info lebih lanjut terkait Airflow dapat dilihat di [airflow.apache.org](https://airflow.apache.org/).


Fitur-fitur yang menjadi keuntungan dari Airflow antara lain:
- **Pure Python**. Tidak perlu lagi command-line maupun XML, sehingga memungkinkan untuk menjaga alur kerja tetap fleksibel.
- **UI berguna**. Selalu memiliki akses penuh ke status dan log dari semua tugas, baik yang sudah selesai maupun yang sedang berlangsung dengan aplikasi web kontemporer.
- **Integrasi yang robust**. Airflow menawarkan berbagai operator plug-and-play yang siap menjalankan tugas pada layanan eksternal, membuatnya mudah untuk diintegrasikan dengan infrastruktur yang ada dan diperluas ke teknologi mutakhir.
- **Mudah digunakan**. Dapat digunakan oleh siapa saja yang terbiasa dengan Python. Kemampuan pipeline tidak dibatasi oleh Apache Airflow; dapat menggunakannya untuk membuat model ML, memindahkan data, mengontrol infrastruktur, dan lainnya.
- **Open source**. Dengan PR, dapat membagikan update di mana pun, tanpa kendala dan proses yang berlarut-larut.

Kita dapat membuat dan mengelola proses menggunakan platform Airflow. Workflow direpresentasikan sebagai DAG (Directed Acyclic Graph), yang terdiri dari unit kerja terpisah yang disebut **task** yang diurutkan dengan mempertimbangkan hubungan dan aliran data.

## DAG

Ide mendasar di balik Airflow adalah DAG (Directed Acyclic Graph), yang menentukan ketergantungan antar task, dan urutan untuk mengeksekusinya dan menjalankan percobaan ulang. Task itu sendiri menjelaskan apa yang harus dilakukan, baik itu mengambil data, menjalankan analisis, memicu sistem lain, atau lebih.

Langkah awal yang perlu dilakukan adalah melakukan import yang diperlukan. Kemudian, tetapkan argumen default yang diperlukan seperti sebagai berikut.
```
default_args = {
    'owner': '...',
    'depends_on_past': False,
    'start_date': datetime(2020, 1, 13, 21, 0, tzinfo=local_tz),
    'email': ['...@gmail.com'],
    'email_on_failure': False,
    'email_on_retry': False,
    'retries': 0,
    'retry_delay': timedelta(minutes=5)
}
```

Selanjutnya adalah mendeklarasi DAG, yakni sebagai berikut.
```
dag = DAG('INSTA_DAILY_2022_PRODUCTION', default_args=default_args, schedule_interval="0 08,18 * * *", catchup=False)
```
Jadwal penjalanan DAG dalam bentuk ekspresi cron dapat dilihat dari `schedule_interval`, yang artinya update dilakukan setiap hari pada pukul 08.00 dan 18.00. Selanjutnya, dibangun konstruktor standar dengan passing dag ke operator/task apapun, contoh sebagian task yand dibuat adalah sebagai berikut.

```
t1 = DummyOperator(task_id='Start_Competitor_Update', dag=dag)
t1_1 = PythonOperator(task_id='t_Comp_Info_Static', python_callable=lambda: Competitor.update('info_static'), dag=dag)
t1_2 = PythonOperator(task_id='t_Comp_Info_Dynamic', python_callable=lambda: Competitor.update('info_dynamic'), dag=dag)
t1_3 = PythonOperator(task_id='t_Comp_Media', python_callable=lambda: Competitor.update('media'), dag=dag)

t2 = DummyOperator(task_id='Start_User_Update_Part1', dag=dag)
t2_1 = PythonOperator(task_id='t_User_Info_Static', python_callable=lambda: User.update('info_static'), dag=dag)
t2_2 = PythonOperator(task_id='t_User_Online_Followers', python_callable=lambda: User.update('online_followers'), dag=dag)
t2_3 = PythonOperator(task_id='t_User_Audience_City', python_callable=lambda: User.update('audience_city'), dag=dag)

...
```
Langkah terakhir adalah mendefinisikan dependensi task, seperti berikut ini.

```
t1 >> t1_1 >> t1_2 >> t1_3 >> t2 >> t2_1 >> t2_2 >> t2_3 >> ...
```






