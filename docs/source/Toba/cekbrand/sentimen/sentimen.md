# Sentiment Analysis



Sentiment analysis adalah proses analisis teks untuk menentukan apakah setiap teks tersebut memiliki sentimen positif atau negatif. Proses ini akan dilakukan menggunakan data ``media_comment`` (text) dari Schema Instagram, yaitu database yang telah di-load.

nyalakan service alfath (ssh)
ssh_start_SA = SSHOperator(task_id = 'Start_SERVICE', ssh_hook= sshHook, command="/home/widyadev/alfath/sentiment-analysis/scripts/start_sa.sh ", dag=dag)

masuknya user_media_comment_sentiment -> sentiment 


Selanjutnya, dilakukan preprocessing menggunakan library benchmark, yaitu ``preprocessing``.  Library tersebut 

analytics.py -> def update_media_sentiment
cleaning dari mas syrico
baru masuk ke servis mas alfath 
run_server.py (sentiment-analysis)
