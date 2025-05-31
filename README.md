# Laporan Proyek Machine Learning - Labiba Adinda Zahwana


## Latar Belakang

**Diabetes mellitus** merupakan sekumpulan gangguan yang melibatkan faktor autoimun, metabolik, dan genetik, dengan ciri utama meningkatnya kadar gula darah (hiperglikemia). Cara pengukuran glukosa plasma dan batasan untuk menentukan kadar normal atau tidak normal telah mengalami beberapa perubahan selama beberapa dekade terakhir. Artikel ini mengulas berbagai rekomendasi terbaru dan definisi terkini terkait diabetes mellitus serta kondisi hiperglikemia tingkat sedang. Selain itu, dijelaskan juga perbedaan pendekatan diagnosis antara Amerika Serikat dengan negara-negara lain.

---

### Apa itu Diabetes?

Diabetes mellitus bukanlah satu penyakit tunggal, melainkan sekumpulan kondisi metabolik yang ditandai oleh tingginya kadar gula darah akibat defisiensi insulin, baik sebagian maupun total. Hiperglikemia kronis dapat menyebabkan komplikasi mikro-vaskular, seperti:

- Kerusakan pada retina mata
- Kerusakan ginjal
- Gangguan pada saraf tepi

Meski komplikasi ini sering muncul pada penderita diabetes, mereka **tidak dijadikan dasar diagnosis** karena perkembangan komplikasi tersebut yang relatif lambat.

---

### Bagaimana Diabetes Diklasifikasikan?

Diabetes mellitus terbagi menjadi **empat tipe utama**:

1. **Diabetes tipe 1**

   * Terjadi kerusakan sel β pankreas, umumnya akibat mekanisme autoimun inflamasi.
   * Ditandai dengan keberadaan antibodi autoimun dalam serum, seperti antibodi terhadap sel islet, GAD, insulin, IA-2, IA-2β, dan transporter seng ZnT8.
   * Biasanya mengakibatkan kekurangan insulin secara total.

2. **Diabetes tipe 2**

3. **Diabetes tipe khusus lainnya**

4. **Diabetes gestasional**

---

### Bagaimana Diagnosis Diabetes Dibuat?

Diagnosis diabetes ditegakkan bila salah satu kriteria berikut terpenuhi:

* Glukosa plasma acak ≥ 11,1 mmol/l dengan gejala khas hiperglikemia seperti:

  * Haus berlebihan (polidipsia)
  * Sering buang air kecil (poliuria)
  * Penurunan berat badan yang biasanya menandakan kekurangan insulin

* Glukosa plasma puasa (tidak makan ≥ 8 jam) ≥ 7,0 mmol/l

* Glukosa plasma ≥ 11,1 mmol/l dua jam setelah tes toleransi glukosa oral

---

### Apa itu Pre-Diabetes?

Kondisi antara normal dan diabetes disebut sebagai:

* **Impaired Fasting Glucose (IFG)**
* **Impaired Glucose Tolerance (IGT)**

Meskipun bukan penyakit klinis, istilah *pre-diabetes* digunakan untuk menggambarkan kondisi ini karena merupakan indikator risiko tinggi berkembangnya diabetes di kemudian hari serta peningkatan risiko penyakit kardiovaskular.

---

### Referensi

- [Understanding diabetes mellitus: biochemical and clinical perspectives – ScienceDirect](https://www.sciencedirect.com/science/article/abs/pii/S1357303918302627)

---

## Business Understanding

### Problem Statement

Berdasarkan latar belakang masalah yang telah dijelaskan sebelumnya, rumusan masalah (*problem statements*) dalam proyek ini adalah sebagai berikut:

1. Bagaimana cara memprediksi penyakit diabetes mellitus menggunakan algoritma machine learning?

2. Bagaimana mengembangkan model machine learning yang efektif untuk prediksi penyakit diabetes?

3. Bagaimana evaluasi kinerja model machine learning yang telah dibuat dalam memprediksi penyakit diabetes?
---
### Goals

Berdasarkan rumusan masalah yang telah dirumuskan sebelumnya, berikut adalah tujuan dari proyek machine learning ini:

1. Mempelajari penerapan algoritma machine learning dalam melakukan prediksi penyakit diabetes mellitus.

2. Memahami seluruh tahapan pengembangan model machine learning mulai dari tahap awal hingga penyelesaian, khususnya untuk prediksi diabetes mellitus.

3. Mengevaluasi dan menilai kinerja model machine learning yang telah dibangun dalam memprediksi penyakit diabetes.

---
### Solution Statements

Berdasarkan *problem statements* dan *goals* yang telah dijelaskan sebelumnya, berikut adalah *solution statements* dalam proyek machine learning ini:

1. Melaksanakan proses pengembangan model machine learning secara menyeluruh, mulai dari *Import Library*, *Data Loading*, *Exploratory Data Analysis* (EDA), *Data Preparation*, pembuatan model (*modelling*), hingga evaluasi (*evaluation*).

2. Mengembangkan model machine learning dengan menggunakan algoritma klasifikasi yang sesuai untuk memprediksi kelas (diabetes atau non-diabetes) berdasarkan dataset yang tersedia. Algoritma yang digunakan dalam proyek ini antara lain:
    - *Random Forest Classification*: algoritma ensemble learning yang menggabungkan banyak pohon keputusan (decision trees) untuk meningkatkan akurasi dan performa prediksi.

    - *XGBoost*
    Algoritma boosting yang memanfaatkan gradient boosting untuk membangun model klasifikasi dengan performa tinggi. Digunakan untuk menangani data dengan kompleksitas tinggi dan fitur yang beragam.

    - *Logistic Regression*
    Model regresi yang digunakan untuk prediksi probabilitas kelas biner, dalam hal ini prediksi status diabetes atau tidak.

    - *K-Nearest Neighbors (KNN)*
    Algoritma non-parametrik yang mengklasifikasikan data berdasarkan kedekatan jarak ke tetangga terdekat.

    - *Support Vector Machine (SVM)*
    Algoritma yang mencari hyperplane terbaik untuk memisahkan kelas dengan margin maksimal, digunakan dengan kernel radial basis function (RBF) untuk menangani data non-linear.

3. Melakukan evaluasi model untuk mengukur performa dengan menggunakan metrik evaluasi yang telah ditetapkan. Evaluasi ini bertujuan untuk menentukan seberapa baik model yang dikembangkan dalam memprediksi diabetes, sehingga dapat dipilih model machine learning yang paling efektif untuk keperluan tersebut.

---
## Data Understanding

Dataset yang digunakan dalam proyek ini adalah dataset diabetes yang memuat informasi medis pasien, termasuk beberapa parameter penting seperti kadar glukosa, tekanan darah, BMI, dan lainnya. Dataset ini mengandung data tentang apakah seseorang mengidap diabetes (Outcome 1) atau tidak (Outcome 0). Dataset tersebut berformat csv (comma-separated values) dengan ukuran 23.88 kB. Dataset tersebut terdiri dari 768 data records dengan 9 feature column.

Link dataset: [Diabetes Dataset](https://www.kaggle.com/datasets/whenamancodes/predict-diabities)

### Variabel-variabel pada dataset adalah sebagai berikut:

| Kolom                        | Deskripsi                                                           |
| ---------------------------- | ------------------------------------------------------------------- |
| **Pregnancies**              | Jumlah kehamilan yang pernah dialami                                |
| **Glucose**                  | Tingkat glukosa dalam darah                                         |
| **BloodPressure**            | Tekanan darah (dalam mm Hg)                                         |
| **SkinThickness**            | Ketebalan lipatan kulit (dalam mm)                                  |
| **Insulin**                  | Kadar insulin dalam darah (dalam mu U/ml)                           |
| **BMI**                      | Indeks massa tubuh (Body Mass Index)                                |
| **DiabetesPedigreeFunction** | Skor riwayat keturunan diabetes                                     |
| **Age**                      | Usia pasien (dalam tahun)                                           |
| **Outcome**                  | Hasil diagnosa (1 = Mengidap diabetes, 0 = Tidak mengidap diabetes) |

### Visualization & Analysis

1. **Univariate Analysis**
<br>
    <p align='center'><img src="https://raw.githubusercontent.com/labibaadinda/diabetes-predictive-analytics/main/img/plot_distribusi_outcome.png" alt="hist outcome" width="400" />
    </p>
  <p align='center'>Gambar 1. Bar Diagram Diabetes & Non-Diabetes</p> 
  Berdasarkan visualisasi grafik Bar Diagram pada gambar 1 di atas menunjukkan bahwa jumlah penderita penyakit diabetes yaitu 268 orang (34,9 %). Sedangkan jumlah orang yang non-diabetes yaitu  500 orang (65,1%) dari total keseluruhan jumlah orang dalam dataset (768 orang).


2. **Multivariate Analysis**
<br>
    <p align='center'><img src="https://raw.githubusercontent.com/labibaadinda/diabetes-predictive-analytics/main/img/histogram_col_numerik.png" alt="hist numeric col" width="400" />
    </p>
<p align='center'>Gambar 2. Visualisasi feature numerik</p>
<br>
Berdasarkan visualisasi untuk feature numerik pada dataset yang dapat dilihat pada histogram di atas, dapat diketahui beberapa informasi, yaitu : sebagaian besar orang memiliki glukosa dengan tingkat 100-150; sebagian besar orang memiliki *BloodPressure* pada tingkat 60-90; sebagian besar orang memiliki BMI berkisar dari 25-40; sebagian besar orang memiliki *DiabetesPedigreeFunction* berkisar dari 0.0 hingga 0.75; dan sebagian besar orang berumur 20-30 tahun. <br><br>

  Visualisasi pada gambar 3 di bawah menggambarkan hubungan antar fitur dalam dataset. Dari gambar tersebut, terlihat bahwa tingkat korelasi antar fitur bervariasi; beberapa fitur menunjukkan korelasi yang lemah atau bahkan tidak memiliki korelasi sama sekali, sementara beberapa fitur lain memiliki korelasi meskipun tidak terlalu kuat.
  
  <br>
    <p align='center'><img src="https://raw.githubusercontent.com/labibaadinda/diabetes-predictive-analytics/main/img/sns_pairplot.png" alt="multivariate" width="400" />
    </p>
  <p align='center'>Gambar 3. Visualisasi multivariate analysis</p>

3. **Correlation antar Fitur**
  <br>
    <p align='center'><img src="https://raw.githubusercontent.com/labibaadinda/diabetes-predictive-analytics/main/img/corr_heatmap.png" alt="correlation heatmap" width="400" />
    </p>
<p align='center'>Gambar 4. Korelasi Fitur </p>

**Analisis Korelasi Fitur Dataset Diabetes**
<br>
- Korelasi dengan Outcome (Target)

  a. *Glucose (0.47)*
    Memiliki korelasi positif sedang yang paling tinggi dengan Outcome. Artinya, semakin tinggi kadar glukosa, semakin besar kemungkinan pasien mengidap diabetes.

  b. *BMI (0.29)*
    Korelasi positif sedang, menandakan BMI yang lebih tinggi berhubungan dengan risiko diabetes lebih besar.

  c. *Age (0.24)*
    Usia juga berkorelasi positif, menunjukkan pasien yang lebih tua cenderung lebih berisiko diabetes.

  d. *Pregnancies (0.22)*
    Jumlah kehamilan menunjukkan korelasi positif lemah sampai sedang dengan diabetes.

  e. *DiabetesPedigreeFunction (0.17)*
    Korelasi positif rendah, menunjukkan riwayat keluarga diabetes sedikit berpengaruh.

  f. *Insulin (0.13), BloodPressure (0.07), SkinThickness (0.07)*
    Korelasi yang sangat lemah sampai hampir netral terhadap Outcome.


- Korelasi Antar Fitur

  a. *Pregnancies & Age (0.54)*
    Korelasi positif sedang sampai kuat, artinya wanita yang lebih tua biasanya pernah mengalami lebih banyak kehamilan.

  b. *Insulin & SkinThickness (0.44)*
    Korelasi positif sedang, keduanya terkait karena ketebalan kulit dan kadar insulin berkaitan dengan fungsi metabolisme dan resistensi insulin.

  c. *BMI & SkinThickness (0.39)*
    Korelasi positif sedang, keduanya berhubungan dengan lemak tubuh.

  d. *Glucose & Insulin (0.33)*
    Korelasi positif sedang, logis karena kadar insulin dan glukosa saling berhubungan dalam metabolisme gula darah.

  e. Korelasi antar fitur lain sebagian besar rendah hingga sedang, menunjukkan fitur relatif independen satu sama lain.


- Insight yang di dapat dari plot correlation nya

  * Fitur **Glucose**, **BMI**, **Age**, dan **Pregnancies** adalah predictor paling signifikan untuk diabetes pada dataset ini.
  * Beberapa fitur seperti **Insulin**, **SkinThickness**, dan **BloodPressure** memiliki korelasi rendah terhadap target, tapi mungkin tetap berguna dalam model kompleks.
  * Korelasi antar fitur tidak terlalu tinggi (tidak ada multikolinearitas kuat), sehingga fitur-fitur tersebut bisa digunakan bersamaan tanpa banyak redundansi.

<br>

4. **Outliers**
<br>
  Visualisasi boxplot di bawah bertujuan untuk mendeteksi adanya pencilan (outliers) dalam dataset yang digunakan pada proyek machine learning. Hal ini penting karena keberadaan outliers dapat menyebabkan bias atau menurunkan akurasi model dalam melakukan prediksi.

  <br>
    <p align='center'><img src="https://raw.githubusercontent.com/labibaadinda/diabetes-predictive-analytics/main/img/plot_outlier.png" alt="plot outlier" width="400" />
    </p>
<p align='center'>Gambar 5. Mengecek outliers</p>


## Data Preparation

*Data Preparation* adalah proses mengolah data mentah agar menjadi format yang tepat untuk analisis atau proses selanjutnya. Beberapa teknik yang digunakan dalam tahap data preparation pada proyek ini antara lain:

1. **Data Preprocessing**

**Outlier Handling**

- *Outliers* adalah nilai-nilai yang menyimpang jauh dari nilai-nilai lain dalam dataset. Nilai-nilai ini muncul sebagai anomali yang tidak mengikuti pola umum data. Outliers bisa berupa nilai yang jauh lebih tinggi atau lebih rendah dibandingkan data lainnya, dan dapat disebabkan oleh kesalahan pengukuran, kejadian yang jarang terjadi, atau faktor tak terduga lainnya.

- Tujuan dari penanganan outliers adalah untuk memastikan bahwa nilai-nilai ekstrem tersebut tidak mengganggu analisis statistik atau model machine learning yang dikembangkan. Karena outliers berpotensi memberikan informasi yang menyesatkan dan mempengaruhi hasil analisis, penting untuk menanganinya agar hasil yang diperoleh lebih akurat dan dapat diandalkan.

- Beberapa cara yang dapat digunakan untuk menangani outliers meliputi identifikasi outliers, transformasi data, penghapusan outliers, dan imputasi data. Pada proyek ini, penanganan outliers dilakukan dengan metode imputasi menggunakan pendekatan *IQR method*. Hasil dari metode imputasi ini dapat dilihat pada gambar 5 berikut:

  <br>
    <p align='center'><img src="https://raw.githubusercontent.com/labibaadinda/diabetes-predictive-analytics/main/img/plot_after_outlier_handling.png" alt="plot outlier" width="400" />
    </p>
<p align='center'>Gambar 6. Setelah outliers Handling</p>

**Imbalance Data Handling dengan metode SMOTE**
   
   - *Imbalanced data* adalah kondisi di mana distribusi jumlah kelas dalam dataset tidak merata.
   
   - Tujuan penanganan data tidak seimbang adalah untuk meningkatkan kemampuan model dalam memprediksi kelas yang jumlahnya lebih sedikit (kelas minoritas).
   
   - Ada beberapa metode untuk mengatasi masalah ini. Salah satunya adalah *oversampling*, yaitu memperbanyak sampel dari kelas minoritas agar jumlahnya menjadi seimbang dengan kelas mayoritas, baik dengan menggandakan data yang ada atau membuat data sintetis baru. Metode lain adalah *undersampling*, yaitu mengurangi jumlah sampel pada kelas mayoritas agar seimbang dengan kelas minoritas, biasanya dengan menghapus sebagian data kelas mayoritas.
   
   - Dalam proyek ini, penanganan data tidak seimbang dilakukan menggunakan metode *SMOTE* (*Synthetic Minority Over-sampling Technique*), yang membuat sampel sintetis untuk kelas minoritas (kelas "1" pada kolom *Outcome*). Dengan cara ini, jumlah kelas minoritas dapat disamakan dengan kelas mayoritas, sehingga mengurangi bias model terhadap kelas mayoritas dan meningkatkan performa model untuk memprediksi kelas minoritas.

  <br>
    <p align='center'><img src="https://raw.githubusercontent.com/labibaadinda/diabetes-predictive-analytics/main/img/plot_distribusi_ttg_oversampling.png" alt="oversampling handling" width="400" />
    </p>
<p align='center'>Gambar 7. Imbalanced data handling</p>


2. **Data Splitting**
   
   - Data Splitting adalah proses pemisahan *dataset* menjadi beberapa bagian yang berbeda untuk keperluan tertentu dalam analisis data, seperti pelatihan, validasi, dan pengujian model.
   
   - Tujuan dari tahap ini adalah membagi data menjadi dua kelompok, yaitu satu bagian untuk melatih model (set pelatihan) dan bagian lainnya untuk menguji performa model (set pengujian).
   
   - Metode yang digunakan dalam proses ini adalah *Train-test split*.

3. **Standardization**
   
   - Standardisasi merupakan proses pengubahan data agar memiliki rata-rata (*mean*) sebesar nol dan varians (*variance*) sebesar satu.
   
   - Tujuan standardisasi adalah untuk membuat distribusi data menjadi lebih terpusat di sekitar angka nol dengan variasi yang konsisten, sehingga membantu algoritma machine learning dalam memahami dan mengolah data secara lebih efektif.
   
   - Metode yang diterapkan melibatkan pengurangan setiap nilai fitur dengan rata-rata fitur tersebut, lalu membaginya dengan standar deviasi fitur tersebut. Pada kasus ini, *StandardScaler* dari scikit-learn digunakan untuk melakukan standardisasi dengan perhitungan *z-score*.

## Modeling

Pada tahap ini, dilakukan pengembangan beberapa model machine learning dengan menggunakan algoritma klasifikasi yang berbeda, antara lain:

### 1. Random Forest 

Random Forest adalah algoritma ensemble learning yang menggabungkan banyak pohon keputusan (decision trees) secara acak untuk meningkatkan akurasi dan mengurangi risiko overfitting. Model ini bekerja dengan membangun sejumlah pohon (estimators), di mana setiap pohon dilatih pada subset data dan fitur secara acak. Model ini dilatih dengan parameter utama seperti jumlah pohon (*n\_estimators*), kedalaman maksimum pohon (*max\_depth*), dan jumlah fitur maksimum yang dipertimbangkan (*max\_features*).

**Parameter utama:**

  * `n_estimators=50`: jumlah pohon keputusan yang dibangun. Pilihan ini menyeimbangkan akurasi dan waktu pelatihan.
  * `max_depth=5`: membatasi kedalaman maksimum pohon agar tidak terlalu kompleks, mengurangi risiko overfitting.
  * `max_features='sqrt'`: jumlah fitur yang dipilih secara acak saat mencari split terbaik, meningkatkan diversitas antar pohon.
  * `random_state=42`: memastikan hasil pelatihan yang konsisten dan dapat direproduksi.

### 2. XGBoost

XGBoost adalah metode boosting berbasis gradient boosting yang membangun model secara iteratif, di mana setiap pohon baru berusaha memperbaiki kesalahan prediksi dari model sebelumnya. Algoritma ini terkenal karena kemampuannya menangani data kompleks dan fitur yang beragam dengan performa tinggi.

**Parameter utama:**

  * `n_estimators=100`: jumlah total pohon yang dibangun secara bertahap.
  * `max_depth=5`: membatasi kompleksitas tiap pohon untuk menghindari overfitting.
  * `learning_rate=0.1`: tingkat pembelajaran yang mengontrol kontribusi tiap pohon, menjaga kestabilan model.
  * `use_label_encoder=False`: menyesuaikan dengan versi terbaru XGBoost, menghindari warning.
  * `eval_metric='logloss'`: metrik evaluasi yang digunakan selama pelatihan, sesuai untuk klasifikasi biner.
  * `random_state=42`: memastikan konsistensi hasil.

### 3. Logistic Regression

Logistic Regression adalah model statistik yang digunakan untuk memprediksi probabilitas kejadian biner, yaitu apakah seorang pasien mengidap diabetes atau tidak. Model ini menghitung hubungan linier antara fitur independen dan log odds dari target.

**Parameter utama:**

  * `max_iter=1000`: jumlah maksimum iterasi untuk algoritma optimasi, memastikan model konvergen pada dataset kompleks.
  * `random_state=42`: menjaga hasil pelatihan agar konsisten.




### 4. K-Nearest Neighbors (KNN)

KNN adalah algoritma non-parametrik yang mengklasifikasikan data berdasarkan kedekatan jarak ke tetangga terdekat dalam ruang fitur. Prediksi kelas ditentukan oleh mayoritas kelas dari `k` tetangga terdekat.

**Parameter utama:**

  * `n_neighbors=5`: jumlah tetangga yang diperhitungkan dalam pengambilan keputusan klasifikasi. Nilai ini seimbang antara sensitivitas dan kestabilan prediksi.


### 5. Support Vector Machine (SVM)

SVM adalah algoritma yang mencari hyperplane terbaik untuk memisahkan kelas dengan margin maksimal. Dengan kernel RBF, SVM dapat menangani data yang tidak linear secara efektif.

**Parameter utama:**

  * `probability=True`: mengaktifkan prediksi probabilitas, berguna untuk evaluasi model.
  * `random_state=42`: menjaga hasil konsisten.



## Evaluasi Model

### 1. Random Forest

<br>  
<p align='center'>  
  <img src="https://raw.githubusercontent.com/labibaadinda/diabetes-predictive-analytics/main/img/6.1-evaluation-random-forest-train.png" alt="Evaluation Random Forest Train Data" width="400" />  
</p>  
<p align='center'>Gambar 8. Evaluation Random Forest (Train Data)</p>  

<p align="center">  

| Kelas            | Precision | Recall | F1-Score | Support |
| ---------------- | --------- | ------ | -------- | ------- |
| 0                | 0.91      | 0.84   | 0.88     | 351     |
| 1                | 0.85      | 0.92   | 0.88     | 349     |
| **Accuracy**     |           |        | **0.88** | 700     |
| **Macro Avg**    | 0.88      | 0.88   | 0.88     | 700     |
| **Weighted Avg** | 0.88      | 0.88   | 0.88     | 700     |

</p>  

Pada evaluasi model Random Forest untuk data training, model menunjukkan akurasi sebesar 88,00%, menandakan model dapat memprediksi dengan benar sekitar 88% dari data pelatihan. Precision kelas 0 sebesar 0,91 berarti dari semua prediksi kelas 0, 91% adalah benar. Recall kelas 0 sebesar 0,84 menunjukkan model berhasil mendeteksi 84% dari data kelas 0 yang sebenarnya. F1-score kelas 0 sebesar 0,88 menunjukkan performa seimbang antara precision dan recall. Pada kelas 1, precision sebesar 0,85 menunjukkan prediksi kelas 1 yang cukup akurat, recall sebesar 0,92 berarti 92% data kelas 1 berhasil dikenali. F1-score kelas 1 sebesar 0,88 menandakan performa yang baik dan seimbang pada kelas ini. Secara keseluruhan, model fit dengan baik pada data training.

<br>  
<p align='center'>  
  <img src="https://raw.githubusercontent.com/labibaadinda/diabetes-predictive-analytics/main/img/6.1-evaluation-random-forest-test.png" alt="Evaluation Random Forest Test Data" width="400" />  
</p>  
<p align='center'>Gambar 9. Evaluation Random Forest (Test Data)</p>  

<p align="center">  

| Kelas            | Precision | Recall | F1-Score | Support |
| ---------------- | --------- | ------ | -------- | ------- |
| 0                | 0.79      | 0.70   | 0.74     | 149     |
| 1                | 0.73      | 0.81   | 0.77     | 151     |
| **Accuracy**     |           |        | **0.76** | 300     |
| **Macro Avg**    | 0.76      | 0.76   | 0.76     | 300     |
| **Weighted Avg** | 0.76      | 0.76   | 0.76     | 300     |

</p>  

Pada evaluasi data test, model menunjukkan akurasi 75,67%, mengalami penurunan dibanding data training. Precision dan recall menurun pada kedua kelas, menunjukkan model memiliki performa yang lebih rendah saat diuji dengan data baru. Namun demikian, performa masih cukup baik dengan F1-score kelas 0 sebesar 0,74 dan kelas 1 sebesar 0,77. Model ini menunjukkan kemampuan generalisasi yang cukup namun masih perlu peningkatan terutama pada data test.


### 2. XGBoost

<br>  
<p align='center'>  
  <img src="https://raw.githubusercontent.com/labibaadinda/diabetes-predictive-analytics/main/img/6.2-evaluation-XGBoost-train.png" alt="Evaluation XGBoost Train Data" width="400" />  
</p>  
<p align='center'>Gambar 10. Evaluation XGBoost (Train Data)</p>  

<p align="center">  

| Kelas            | Precision | Recall | F1-Score | Support |
| ---------------- | --------- | ------ | -------- | ------- |
| 0                | 0.99      | 0.99   | 0.99     | 351     |
| 1                | 0.99      | 0.99   | 0.99     | 349     |
| **Accuracy**     |           |        | **0.99** | 700     |
| **Macro Avg**    | 0.99      | 0.99   | 0.99     | 700     |
| **Weighted Avg** | 0.99      | 0.99   | 0.99     | 700     |

</p>  

Model XGBoost menunjukkan performa yang sangat baik pada data training dengan akurasi mencapai 99.14%, menandakan hampir seluruh data training dapat diprediksi dengan benar tanpa kesalahan yang berarti. Precision dan recall untuk kedua kelas mencapai 0.99, mengindikasikan model berhasil mengenali hampir seluruh data kelas 0 dan kelas 1 dengan sangat akurat. F1-score yang juga sebesar 0.99 menegaskan performa optimal model pada data training. Namun, performa luar biasa ini juga mengindikasikan kemungkinan model mengalami overfitting, yaitu terlalu menyesuaikan diri dengan data training sehingga performa pada data baru bisa menurun.

<br>  
<p align='center'>  
  <img src="https://raw.githubusercontent.com/labibaadinda/diabetes-predictive-analytics/main/img/6.2-evaluation-XGBoost-test.png" alt="Evaluation XGBoost Test Data" width="400" />  
</p>  
<p align='center'>Gambar 11. Evaluation XGBoost (Test Data)</p>  

<p align="center">  

| Kelas            | Precision | Recall | F1-Score | Support |
| ---------------- | --------- | ------ | -------- | ------- |
| 0                | 0.80      | 0.68   | 0.74     | 149     |
| 1                | 0.73      | 0.83   | 0.78     | 151     |
| **Accuracy**     |           |        | **0.76** | 300     |
| **Macro Avg**    | 0.76      | 0.76   | 0.76     | 300     |
| **Weighted Avg** | 0.76      | 0.76   | 0.76     | 300     |

</p>  

Pada evaluasi data test, model mengalami penurunan performa cukup signifikan dengan akurasi turun menjadi 76.00%. Precision kelas 0 sebesar 0.80 menunjukkan kemampuan model dalam memprediksi kelas 0 masih cukup baik, namun recall turun ke 0.68 yang menandakan beberapa data kelas 0 terlewat. F1-score kelas 0 sebesar 0.74 masih cukup memadai. Untuk kelas 1, precision menurun menjadi 0.73 dan recall meningkat menjadi 0.83, menunjukkan model lebih baik dalam mendeteksi kelas 1 namun prediksi kurang presisi. F1-score sebesar 0.78 mengindikasikan performa yang baik tapi masih ada ruang untuk peningkatan. Penurunan performa ini terutama pada data test dan pada kelas minoritas (kelas 1) mengindikasikan kemungkinan overfitting pada model.

Secara keseluruhan, model XGBoost sangat kuat dan efektif saat pelatihan dengan performa mendekati sempurna. Namun, performa pada data test menurun yang mengindikasikan kurangnya kemampuan generalisasi. Oleh karena itu, perlu dilakukan optimasi lebih lanjut seperti regularisasi, tuning hyperparameter, atau penanganan ketidakseimbangan data untuk meningkatkan performa model pada data baru.

### 3. Logistic Regression

<br>  
<p align='center'>  
  <img src="https://raw.githubusercontent.com/labibaadinda/diabetes-predictive-analytics/main/img/6.3-evaluation-LogisticRegression-train.png" alt="Evaluation Logistic Regression Train Data" width="400" />  
</p>  
<p align='center'>Gambar 12. Evaluation Logistic Regression (Train Data)</p>  

<p align="center">  

| Kelas            | Precision | Recall | F1-Score | Support |
| ---------------- | --------- | ------ | -------- | ------- |
| 0                | 0.74      | 0.77   | 0.75     | 351     |
| 1                | 0.76      | 0.72   | 0.74     | 349     |
| **Accuracy**     |           |        | **0.75** | 700     |
| **Macro Avg**    | 0.75      | 0.75   | 0.75     | 700     |
| **Weighted Avg** | 0.75      | 0.75   | 0.75     | 700     |

</p>  

Pada evaluasi model Logistic Regression untuk data training, model menunjukkan akurasi sebesar 74,71%, yang menandakan model dapat memprediksi dengan benar sekitar 75% data pelatihan. Precision kelas 0 sebesar 0,74 berarti dari semua prediksi kelas 0, 74% adalah benar. Recall kelas 0 sebesar 0,77 menunjukkan model berhasil mendeteksi 77% dari data kelas 0 yang sebenarnya. F1-score kelas 0 sebesar 0,75 menunjukkan keseimbangan baik antara precision dan recall. Pada kelas 1, precision sebesar 0,76 menunjukkan prediksi kelas 1 yang cukup akurat, recall sebesar 0,72 berarti 72% data kelas 1 berhasil dikenali. F1-score kelas 1 sebesar 0,74 menandakan performa yang cukup dan seimbang pada kelas ini. Secara keseluruhan, model fit dengan baik pada data training.

<br>  
<p align='center'>  
  <img src="https://raw.githubusercontent.com/labibaadinda/diabetes-predictive-analytics/main/img/6.3-evaluation-LogisticRegression-test.png" alt="Evaluation Logistic Regression Test Data" width="400" />  
</p>  
<p align='center'>Gambar 13. Evaluation Logistic Regression (Test Data)</p>  

<p align="center">  

| Kelas            | Precision | Recall | F1-Score | Support |
| ---------------- | --------- | ------ | -------- | ------- |
| 0                | 0.74      | 0.75   | 0.75     | 149     |
| 1                | 0.75      | 0.74   | 0.75     | 151     |
| **Accuracy**     |           |        | **0.75** | 300     |
| **Macro Avg**    | 0.75      | 0.75   | 0.75     | 300     |
| **Weighted Avg** | 0.75      | 0.75   | 0.75     | 300     |

</p>  

Pada evaluasi data test, model menunjukkan akurasi 74,67%, mengalami penurunan dibanding data training. Precision dan recall menurun pada kedua kelas, menunjukkan model memiliki performa yang lebih rendah saat diuji dengan data baru. Namun demikian, performa masih cukup baik dengan F1-score kelas 0 sebesar 0,75 dan kelas 1 sebesar 0,75. Model ini menunjukkan kemampuan generalisasi yang cukup dan stabil pada data test.

### 4. K-Nearest Neighbors (KNN)

<br>  
<p align='center'>  
  <img src="https://raw.githubusercontent.com/labibaadinda/diabetes-predictive-analytics/main/img/6.4-evaluation-knn_model-train.png" alt="Evaluation KNN Train Data" width="400" />  
</p>  
<p align='center'>Gambar 14. Evaluation KNN (Train Data)</p>  

<p align="center">  

| Kelas            | Precision | Recall | F1-Score | Support |
| ---------------- | --------- | ------ | -------- | ------- |
| 0                | 0.89      | 0.79   | 0.84     | 351     |
| 1                | 0.81      | 0.90   | 0.86     | 349     |
| **Accuracy**     |           |        | **0.85** | 700     |
| **Macro Avg**    | 0.85      | 0.85   | 0.85     | 700     |
| **Weighted Avg** | 0.85      | 0.85   | 0.85     | 700     |

</p>  

Model K-Nearest Neighbors (KNN) mampu memprediksi dengan benar sekitar 84.86% data training. Precision untuk kelas 0 adalah 0.89, artinya dari seluruh prediksi kelas 0, 89% tepat. Model ini juga berhasil mendeteksi 79% dari kelas 0 sebenarnya (recall 0.79), sehingga performa untuk kelas mayoritas cukup baik dengan f1-score 0.84 yang menunjukkan keseimbangan antara precision dan recall. Sedangkan untuk kelas 1, precision mencapai 0.81 dan recall sebesar 0.90, yang menunjukkan model menangkap 90% data kelas 1 sebenarnya. F1-score kelas 1 adalah 0.86, menunjukkan performa yang sedikit lebih baik dibanding kelas 0. Kesimpulannya, model KNN bekerja dengan baik pada data training, terutama pada kelas mayoritas dan minoritas.

<br>  
<p align='center'>  
  <img src="https://raw.githubusercontent.com/labibaadinda/diabetes-predictive-analytics/main/img/6.4-evaluation-knn_model-test.png" alt="Evaluation KNN Test Data" width="400" />  
</p>  
<p align='center'>Gambar 15. Evaluation KNN (Test Data)</p>  

<p align="center">  

| Kelas            | Precision | Recall | F1-Score | Support |
| ---------------- | --------- | ------ | -------- | ------- |
| 0                | 0.79      | 0.70   | 0.74     | 149     |
| 1                | 0.73      | 0.82   | 0.78     | 151     |
| **Accuracy**     |           |        | **0.76** | 300     |
| **Macro Avg**    | 0.76      | 0.76   | 0.76     | 300     |
| **Weighted Avg** | 0.76      | 0.76   | 0.76     | 300     |

</p>  

Pada data testing, akurasi model menurun menjadi 76.00%, menunjukkan performa yang menurun saat dihadapkan dengan data baru. Precision untuk kelas 0 turun menjadi 0.79 dan recall menjadi 0.70, sehingga model masih mampu mendeteksi sebagian besar kelas mayoritas, dengan f1-score 0.74 yang relatif stabil meski sedikit menurun. Namun, performa untuk kelas 1 menurun sedikit, dengan precision 0.73 dan recall 0.82, yang berarti model mengenali 82% data kelas 1 dengan cukup baik. F1-score kelas 1 menjadi 0.78, menandakan performa yang masih cukup baik untuk kelas minoritas pada data testing. Kesimpulannya, model KNN memiliki kemampuan generalisasi yang baik dengan performa sedikit menurun pada data test.

### 5. Support Vector Machine (SVM)

<br>  
<p align='center'>  
  <img src="https://raw.githubusercontent.com/labibaadinda/diabetes-predictive-analytics/main/img/6.5-evaluation-svm_model-train.png" alt="Evaluation SVM Train Data" width="400" />  
</p>  
<p align='center'>Gambar 16. Evaluation SVM (Train Data)</p>  

<p align="center">  

| Kelas            | Precision | Recall | F1-Score | Support |
| ---------------- | --------- | ------ | -------- | ------- |
| 0                | 0.87      | 0.83   | 0.85     | 351     |
| 1                | 0.84      | 0.87   | 0.85     | 349     |
| **Accuracy**     |           |        | **0.85** | 700     |
| **Macro Avg**    | 0.85      | 0.85   | 0.85     | 700     |
| **Weighted Avg** | 0.85      | 0.85   | 0.85     | 700     |

</p>  

Model Support Vector Machine (SVM) menunjukkan akurasi sebesar 85.00% pada data training. Precision untuk kelas 0 sebesar 0.87 menunjukkan dari seluruh prediksi kelas 0, 87% adalah benar. Recall kelas 0 sebesar 0.83 menunjukkan model berhasil mendeteksi 83% dari data kelas 0 sebenarnya. F1-score kelas 0 sebesar 0.85 menandakan performa yang baik dan seimbang pada kelas mayoritas. Untuk kelas 1, precision sebesar 0.84 dan recall sebesar 0.87 menandakan model mampu mendeteksi 87% data kelas 1 dengan akurat. F1-score kelas 1 sebesar 0.85 juga menunjukkan performa yang seimbang dan kuat. Secara keseluruhan, model bekerja dengan baik pada data training.

<br>  
<p align='center'>  
  <img src="https://raw.githubusercontent.com/labibaadinda/diabetes-predictive-analytics/main/img/6.5-evaluation-svm_model-test.png" alt="Evaluation SVM Test Data" width="400" />  
</p>  
<p align='center'>Gambar 17. Evaluation SVM (Test Data)</p>  

<p align="center">  

| Kelas            | Precision | Recall | F1-Score | Support |
| ---------------- | --------- | ------ | -------- | ------- |
| 0                | 0.80      | 0.74   | 0.77     | 149     |
| 1                | 0.76      | 0.82   | 0.79     | 151     |
| **Accuracy**     |           |        | **0.78** | 300     |
| **Macro Avg**    | 0.78      | 0.78   | 0.78     | 300     |
| **Weighted Avg** | 0.78      | 0.78   | 0.78     | 300     |

</p>  

Pada evaluasi data test, model mencapai akurasi 78.00%. Precision dan recall untuk kelas 0 masing-masing 0.80 dan 0.74, menunjukkan model cukup baik dalam memprediksi kelas mayoritas dengan F1-score 0.77 yang cukup seimbang. Untuk kelas 1, precision 0.76 dan recall 0.82 menandakan model cukup baik dalam mendeteksi data kelas minoritas dengan F1-score 0.79. Model ini menunjukkan kemampuan generalisasi yang baik meskipun terdapat sedikit penurunan performa dibandingkan data training.

---

## Kesimpulan

Berdasarkan hasil evaluasi, berikut rangkuman performa beberapa model:

<p align="center">  

| Model                        | Accuracy | F1-Score   | AUC-ROC    |
| ---------------------------- | -------- | ---------- | ---------- |
| Random Forest                | 0.7567   | 0.7712     | **0.8375** |
| XGBoost                      | 0.7600   | **0.7778** | 0.8215     |
| Logistic Regression          | 0.7467   | 0.7467     | 0.8453     |
| K-Nearest Neighbors (KNN)    | 0.7600   | 0.7750     | 0.8372     |
| Support Vector Machine (SVM) | 0.7800   | 0.7898     | 0.8443     |

</p>

* **Random Forest** unggul pada AUC-ROC tertinggi (0.8375), menandakan kemampuan terbaik membedakan pasien dengan dan tanpa diabetes secara keseluruhan, serta keseimbangan baik antara akurasi dan F1-score. Cocok untuk aplikasi prediksi klinis.

* **XGBoost** memiliki F1-Score tertinggi (0.7778), efektif menangani ketidakseimbangan kelas dan menjaga keseimbangan precision-recall. Namun AUC-ROC sedikit lebih rendah dari Random Forest.

* **Logistic Regression** sebagai model baseline menunjukkan AUC-ROC terbaik (0.8453), menjadikannya pilihan baik bila interpretabilitas penting, meskipun akurasi dan F1-score sedikit di bawah model lain.

* **SVM** memiliki akurasi (0.78) dan F1-Score (0.7898) tertinggi, tapi AUC-ROC-nya lebih rendah dari Logistic Regression dan Random Forest, menunjukkan perlu tuning lebih lanjut.

* **KNN** memiliki performa paling rendah secara umum, kurang ideal untuk dataset ini.

### Hubungan dengan Business Understanding

* **Menjawab Problem Statement:** Model mampu memprediksi status diabetes dengan baik sesuai kebutuhan analisis medis.

* **Mencapai Goals:** Evaluasi menyeluruh menggunakan metrik akurasi, F1-score, dan AUC membuktikan keberhasilan pengembangan model efektif.

---

**Kesimpulan akhir:**
Berdasarkan metrik AUC-ROC sebagai indikator utama, **Logistic Regression** terpilih sebagai model terbaik dengan skor 0.8453, walaupun SVM dan Random Forest menunjukkan akurasi dan F1-Score yang kompetitif. Pemilihan model akhir bisa mempertimbangkan kebutuhan khusus seperti interpretabilitas dan keseimbangan precision-recall.
