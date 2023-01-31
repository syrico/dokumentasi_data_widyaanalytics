# Sentiment Analysis

Sentiment analysis adalah proses analisis teks untuk menentukan apakah setiap teks tersebut memiliki sentimen positif, netral, atau negatif. Proses ini akan dilakukan menggunakan data ``media_comment`` (text) dari Schema Instagram, yaitu database yang telah di-load. Selanjutnya, akan dilakukan cleaning data di file analytics.py dengan menggunakan def update_media_sentiment. Setelah itu, barulah akan masuk ke service sentiment analysis dalam file run_server.py. Hasil itulah yang akan masuk ke Schema Toba_Cek_Insta berupa data ``user_media_comment_sentiment``.

Catatan:

- Nyalakan service:

```bash
ssh_start_SA = SSHOperator(task_id = 'Start_SERVICE', ssh_hook= sshHook, command="/home/widyadev/alfath/sentiment-analysis/scripts/start_sa.sh ", dag=dag)
```

- Preprocessing dengan library benchmark, yaitu ``preprocessing``.
