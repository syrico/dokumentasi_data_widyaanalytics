# Analytic

Run analytics dijalankan di main.py, dengan parameter yang analog dengan update.

Untuk menjalankan main.py, terlebih dahulu dilakukan import berikut ini.

```
from cekbrand.analytics import AnalyticsEngine
```
Fungsi untuk menjalankan analytic adalah sebagai berikut.
```
analytics_engine = AnalyticsEngine(db_state='dev', airflow=False)
analytics_engine.single_instagram_user_hashtags_metrics_distribution(total_media=40,
user_id=str('17841408671998486'))
```
Parameter ``total_media`` adalah jumlah media yang akan dilakukan analytic, sedangkan ``user_id`` merupakan nama id dari user yang akan dilakukan analytic, contoh seperti di atas, jumlah media dari id 17841408671998486 yang akan di-analytic adalah sebesar 40. 
