# Smartphone Addiction Prediction

Repository ini digunakan untuk mencatat apa saja yang ditemukan saat kompetisi kaggle, [predicting smartphone addiction](https://www.kaggle.com/code/fikriabdillah98/predicting-smartphone-addiction), berlangsung. Kompetisi ini berlangsung pada 1 agustus hingga 31 agustus 2026. Tujuan dari kompetisi ini adalah melatih kemampuan machine learning seorang peserta dengan dataset sintetis. The submissions are evaluated on area under the ROC curve. Penulis berhasil menduduki posisi 1996/3532 dengan skor AUC 96.5% (setelah dua hari kompetisi). Hasil analisis dari penulis dapat dilihat di [Kaggle](https://www.kaggle.com/code/fikriabdillah98/predicting-smartphone-addiction).

## Goal & Dataset

Tujuan utama dari topik ini adalah mendeteksi apakah seseorang sudah dalam tahap adiksi smartphone atau belum dengan menggunakan machine learning. Dataset di kompetisi tersebut terdiri `train.csv`, `test.csv`, dan `sample_submission_csv`. Data yang diolah dari train_csv terdiri dari 13 kolom dan 691369 indeks, sedangkan `test.csv` memiliki . Kolom tersebut terdiri dari:

* age (float)
* daily_screen_time_hours (float)
* gaming_hours (float)
* work_study_hours (float)
* sleep_hours (float)
* notifications_per_day (float)
* app_opens_per_day (float)
* weekend_screen_time (float)
* gender (object)
* stress_level (object)
* academic_work_impact (object)
* addicted_label (integer)

## Exploratory Data Analysis

Deskripsi singkat pada setiap kolom dapat dilihat pada tabel bagian bawah


|  | mean | median | std | min | max |
| :--- | :---: | :---: | :---: | :---: | :---: |
| **age** | 26.608689 | 27.00 | 5.153359 | 18.00 | 35.00 |
| **daily_screen_time_hours** | 7.640771 | 7.77 | 2.725921 | 0.50 | 15.00 |
| **social_media_hours** | 2.471224 | 2.32 | 1.318143 | 0.00 | 7.85 |
| **gaming_hours** | 1.457668 | 1.33 | 0.934727 | 0.00 | 4.00 |
| **work_study_hours** | 2.365962 | 2.20 | 1.257023 | 0.00 | 6.00 |
| **sleep_hours** | 6.801704 | 6.80 | 1.236080 | 4.50 | 9.00 |
| **notifications_per_day** | 145.748066 | 150.00 | 66.014554 | 20.00 | 250.00 |
| **app_opens_per_day** | 102.656216 | 104.00 | 48.186200 | 15.00 | 180.00 |
| **weekend_screen_time** | 9.474575 | 9.58 | 2.858384 | 0.51 | 17.56 |

* Tujuan dari kolom ini adalah mendeteksi skewness dari setiap kolom numerik pada dataset. Jika dilihat secara teliti, mean and median dari hampir semua kolom berdekatan dan dapat menjadi awal indikasi bahwa hampir semua fitur memiliki kurva distribusi normal. Namun, setelah melihat jarak selisih mean atau median terhadap nilai minimum dan maksimum, maka ada beberapa kolom yang terindikasi skewness, seperti `social_media_hours` and `work_study_hours`.

<div style="text-align: center; margin: 20px auto; max-width: 500px;">
  <img src="figures/spearman_corr(1).png" alt="spearman_correlation" style="width: 100%; border-radius: 4px;">
  <p style="margin-top: 8px;"><em>Figure 1</em></p>
</div>

