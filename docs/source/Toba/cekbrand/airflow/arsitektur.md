# Arsitektur

![Arsitektur Airflow][image/arsi_airflow.png]

Arsitektur airflow yang digunakan terdiri dari komponen-komponen berikut.
- **Scheduler**, yang menangani pemicuan workflow terjadwal, dan mengirimkan task ke pelaksana untuk dijalankan.
- **Executor**, yang menangani tugas yang sedang berjalan. Dalam penginstalan airflow default, ini menjalankan semua yang ada di dalam scheduler, tetapi sebagian besar executor yang cocok untuk produksi sebenarnya mendorong eksekusi tugas ke workers.
- **Webserver**, yang menyajikan user interface untuk memeriksa, memicu, dan men-debug perilaku DAG dan tugas. (Tampilan?)
- **Folder file DAG**, dibaca oleh scheduler dan executor (dan semua pekerja yang dimiliki pelaksana)
- **Database metadata**, digunakan oleh scheduler, executor, dan webserver untuk menyimpan status.


webserver: ui yang bisa kita liat di web (slide 12)
Tidak bisa atur schedule, hanya bisa di script. hanya untuk memantau 
task yang sedang jalan, yang gagal, urutannya (dependensi), dag2
bisa lbh dr 1 user
ada dokum di airflow
bawaan

Scheduler
jantung
baca file dags folder
bawaan

worker:
-yang menjalankan programnya
-SequentialExecutor, LocalExecutor, CeleryExecutor, DaskExecutor, KubernetesExecutor (ada di airflow.cfg, yang dipakai localexecutor)

airflow.cfg :
supaya airflow bisa connect ke database, config ada di airflow.cfg
sequalalchemy connection

airflow bisa dijalankan oleh 1 komputer (local/sequence) atau multiple komp sekaligus (paralel/celery) dengan masuk antrian


SequentialExecutor, LocalExecutor, CeleryExecutor, DaskExecutor, KubernetesExecutor (ada di airflow.cfg)

