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

1. Melaksanakan proses pengembangan model machine learning secara menyeluruh, mulai dari *Import Library*, *Data Loading*, *Exploratory Data Analysis* (EDA), *Data Wrangling*, pembuatan model (*modelling*), hingga evaluasi (*evaluation*).

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
    <p align='center'><img src="https://raw.githubusercontent.com/labibaadinda/predictive_analytics/main/img/plot_distribusi_outcome.png" alt="hist outcome" width="400" />
    </p>
  <p align='center'>Gambar 1. Bar Diagram Diabetes & Non-Diabetes</p> 
  Berdasarkan visualisasi grafik Bar Diagram pada gambar 1 di atas menunjukkan bahwa jumlah penderita penyakit diabetes yaitu 268 orang (34,9 %). Sedangkan jumlah orang yang non-diabetes yaitu  500 orang (65,1%) dari total keseluruhan jumlah orang dalam dataset (768 orang).


2. **Multivariate Analysis**
<br>
    <p align='center'><img src="https://raw.githubusercontent.com/labibaadinda/predictive_analytics/main/img/histogram_col_numerik.png" alt="hist numeric col" width="400" />
    </p>
<p align='center'>Gambar 2. Visualisasi feature numerik</p>
<br>
Berdasarkan visualisasi untuk feature numerik pada dataset yang dapat dilihat pada histogram di atas, dapat diketahui beberapa informasi, yaitu : sebagaian besar orang memiliki glukosa dengan tingkat 100-150; sebagian besar orang memiliki *BloodPressure* pada tingkat 60-90; sebagian besar orang memiliki BMI berkisar dari 25-40; sebagian besar orang memiliki *DiabetesPedigreeFunction* berkisar dari 0.0 hingga 0.75; dan sebagian besar orang berumur 20-30 tahun. <br><br>

  Visualisasi pada gambar 3 di bawah menggambarkan hubungan antar fitur dalam dataset. Dari gambar tersebut, terlihat bahwa tingkat korelasi antar fitur bervariasi; beberapa fitur menunjukkan korelasi yang lemah atau bahkan tidak memiliki korelasi sama sekali, sementara beberapa fitur lain memiliki korelasi meskipun tidak terlalu kuat.
  
  <br>
    <p align='center'><img src="https://raw.githubusercontent.com/labibaadinda/predictive_analytics/main/img/sns_pairplot.png" alt="multivariate" width="400" />
    </p>
  <p align='center'>Gambar 3. Visualisasi multivariate analysis</p>

3. **Correlation antar Fitur**
  <br>
    <p align='center'><img src="https://raw.githubusercontent.com/labibaadinda/predictive_analytics/main/img/corr_heatmap.png" alt="correlation heatmap" width="400" />
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
    <p align='center'><img src="https://raw.githubusercontent.com/labibaadinda/predictive_analytics/main/img/plot_outlier.png" alt="plot outlier" width="400" />
    </p>
<p align='center'>Gambar 5. Mengecek outliers</p>


## Data Preparation

*Data preparation* adalah proses mengolah data mentah agar menjadi format yang tepat untuk analisis atau proses selanjutnya. Beberapa teknik yang digunakan dalam tahap persiapan data pada proyek ini antara lain:

1. **Penanganan outliers**
- *Outliers* adalah nilai-nilai yang menyimpang jauh dari nilai-nilai lain dalam dataset. Nilai-nilai ini muncul sebagai anomali yang tidak mengikuti pola umum data. Outliers bisa berupa nilai yang jauh lebih tinggi atau lebih rendah dibandingkan data lainnya, dan dapat disebabkan oleh kesalahan pengukuran, kejadian yang jarang terjadi, atau faktor tak terduga lainnya.

- Tujuan dari penanganan outliers adalah untuk memastikan bahwa nilai-nilai ekstrem tersebut tidak mengganggu analisis statistik atau model machine learning yang dikembangkan. Karena outliers berpotensi memberikan informasi yang menyesatkan dan mempengaruhi hasil analisis, penting untuk menanganinya agar hasil yang diperoleh lebih akurat dan dapat diandalkan.

- Beberapa cara yang dapat digunakan untuk menangani outliers meliputi identifikasi outliers, transformasi data, penghapusan outliers, dan imputasi data. Pada proyek ini, penanganan outliers dilakukan dengan metode imputasi menggunakan pendekatan *IQR method*. Hasil dari metode imputasi ini dapat dilihat pada gambar 5 berikut:

  <br>
    <p align='center'><img src="https://raw.githubusercontent.com/labibaadinda/predictive_analytics/main/img/plot_after_outlier_handling.png" alt="plot outlier" width="400" />
    </p>
<p align='center'>Gambar 6. Setelah outliers Handling</p>

2. **Handling imbalanced data**
   
   - *Imbalanced data* adalah kondisi di mana distribusi jumlah kelas dalam dataset tidak merata.
   
   - Tujuan penanganan data tidak seimbang adalah untuk meningkatkan kemampuan model dalam memprediksi kelas yang jumlahnya lebih sedikit (kelas minoritas).
   
   - Ada beberapa metode untuk mengatasi masalah ini. Salah satunya adalah *oversampling*, yaitu memperbanyak sampel dari kelas minoritas agar jumlahnya menjadi seimbang dengan kelas mayoritas, baik dengan menggandakan data yang ada atau membuat data sintetis baru. Metode lain adalah *undersampling*, yaitu mengurangi jumlah sampel pada kelas mayoritas agar seimbang dengan kelas minoritas, biasanya dengan menghapus sebagian data kelas mayoritas.
   
   - Dalam proyek ini, penanganan data tidak seimbang dilakukan menggunakan metode *SMOTE* (*Synthetic Minority Over-sampling Technique*), yang membuat sampel sintetis untuk kelas minoritas (kelas "1" pada kolom *Outcome*). Dengan cara ini, jumlah kelas minoritas dapat disamakan dengan kelas mayoritas, sehingga mengurangi bias model terhadap kelas mayoritas dan meningkatkan performa model untuk memprediksi kelas minoritas.

  <br>
    <p align='center'><img src="https://raw.githubusercontent.com/labibaadinda/predictive_analytics/main/img/plot_distribusi_ttg_oversampling.png" alt="oversampling handling" width="400" />
    </p>
<p align='center'>Gambar 7. Imbalanced data handling</p>


3. **Data Splitting**
   
   - Data Splitting adalah proses pemisahan *dataset* menjadi beberapa bagian yang berbeda untuk keperluan tertentu dalam analisis data, seperti pelatihan, validasi, dan pengujian model.
   
   - Tujuan dari tahap ini adalah membagi data menjadi dua kelompok, yaitu satu bagian untuk melatih model (set pelatihan) dan bagian lainnya untuk menguji performa model (set pengujian).
   
   - Metode yang digunakan dalam proses ini adalah *Train-test split*.

4. **Standardization**
   
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

###  1. Random Forest
  <br>
  <p align='center'>
    <img src="https://raw.githubusercontent.com/labibaadinda/predictive_analytics/main/img/6.1-evaluation-random-forest-train.png" alt="Evaluation Random Forest Train Data" width="400" />
  </p>
<p align='center'>Gambar 8. Evaluation Random Forest (Train Data)</p>

<p align="center">

| Kelas         | Precision | Recall | F1-Score | Support |
|---------------|-----------|--------|----------|---------|
| 0             | 0.88      | 0.95   | 0.91     | 349     |
| 1             | 0.90      | 0.76   | 0.82     | 188     |
| **Accuracy**  |           |        | **0.88** | 537     |
| **Macro Avg** | 0.89      | 0.85   | 0.87     | 537     |
| **Weighted Avg**| 0.89    | 0.88   | 0.88     | 537     |

</p>


Pada evaluasi model Random Forest untuk data training, model ini menunjukkan akurasi sebesar 88,45%, yang berarti mampu memprediksi dengan benar sekitar 88% dari data training. Untuk kelas 0, precision mencapai 0,88, artinya dari semua prediksi kelas 0, 88% tepat, sedangkan recall sebesar 0,95 menandakan model berhasil mendeteksi 95% dari seluruh data sebenarnya kelas 0. F1-score untuk kelas 0 sebesar 0,91 menunjukkan keseimbangan baik antara precision dan recall, yang menandakan performa yang bagus. Untuk kelas 1, precision sebesar 0,90 mengindikasikan prediksi kelas 1 yang cukup akurat, meskipun recall lebih rendah yaitu 0,76, yang berarti model hanya menangkap 76% dari data kelas 1 sebenarnya. F1-score kelas 1 sebesar 0,82 sedikit lebih rendah dibanding kelas 0, menunjukkan performa kelas 1 masih baik tetapi ada ruang untuk perbaikan. Secara keseluruhan, model fit cukup baik pada data training dengan performa sedikit lebih baik pada kelas mayoritas (kelas 0).

  <br>
  <p align='center'>
    <img src="https://raw.githubusercontent.com/labibaadinda/predictive_analytics/main/img/6.1-evaluation-random-forest-test.png" alt="Evaluation Random Forest Test Data" width="400" />
  </p>
<p align='center'>Gambar 9. Evaluation Random Forest (Test Data)</p>

<p align="center">

| Kelas         | Precision | Recall | F1-Score | Support |
|---------------|-----------|--------|----------|---------|
| 0             | 0.79      | 0.83   | 0.81     | 151     |
| 1             | 0.64      | 0.59   | 0.61     | 80      |
| **Accuracy**  |           |        | **0.74** | 231     |
| **Macro Avg** | 0.72      | 0.71   | 0.71     | 231     |
| **Weighted Avg**| 0.74    | 0.74   | 0.74     | 231     |

</p>

Pada evaluasi data test, akurasi menurun menjadi 74,46%, yang menandakan adanya penurunan performa dibandingkan data training, kemungkinan karena model mengalami overfitting atau data test memiliki karakteristik yang lebih menantang. Precision untuk kelas 0 turun menjadi 0,79, namun model masih mampu menangkap sebagian besar kelas 0 dengan recall 0,83 dan F1-score 0,81 yang masih cukup baik. Sementara itu, precision kelas 1 turun cukup signifikan menjadi 0,64, dan recall juga menurun menjadi 0,59, menunjukkan model kurang efektif dalam mendeteksi kelas minoritas pada data test. F1-score kelas 1 juga menurun menjadi 0,61, yang mengindikasikan performa kelas 1 perlu peningkatan. Kesimpulannya, meskipun model masih bekerja baik untuk kelas mayoritas pada data test, performanya kurang optimal untuk kelas minoritas.

Secara keseluruhan, model Random Forest ini cukup akurat dan stabil saat diuji pada data training. Namun, penurunan performa terutama pada kelas minoritas saat pengujian data test mengindikasikan potensi overfitting yang perlu menjadi perhatian dalam pengembangan model selanjutnya.


### 2. XGBoost
  <br>
  <p align='center'>
    <img src="https://raw.githubusercontent.com/labibaadinda/predictive_analytics/main/img/6.2-evaluation-XGBoost-train.png" alt="Evaluation XGBoost Train Data" width="400" />
  </p>
<p align='center'>Gambar 10. Evaluation XGBoost (Train Data)</p>

<p align="center">

| Kelas         | Precision | Recall | F1-Score | Support |
|---------------|-----------|--------|----------|---------|
| 0             | 0.99      | 1.00   | 1.00     | 349     |
| 1             | 0.99      | 0.99   | 0.99     | 188     |
| **Accuracy**  |           |        | **0.99** | 537     |
| **Macro Avg** | 0.99      | 0.99   | 0.99     | 537     |
| **Weighted Avg**| 0.99    | 0.99   | 0.99     | 537     |

</p>


Model XGBoost menunjukkan performa yang sangat baik pada data training dengan akurasi mencapai 99.44%, menandakan hampir seluruh data training dapat diprediksi dengan benar tanpa kesalahan yang berarti. Precision untuk kelas 0 mencapai 0.99, yang berarti dari seluruh prediksi kelas 0, 99% di antaranya benar-benar kelas 0. Recall kelas 0 sempurna pada nilai 1.00, menunjukkan model berhasil mendeteksi seluruh data asli kelas 0 tanpa ada yang terlewat. F1-score kelas 0 yang juga mencapai 1.00 menegaskan performa optimal pada kelas ini. Begitu pula pada kelas 1, precision dan recall masing-masing 0.99, yang berarti hampir semua data kelas 1 terdeteksi dengan tepat, dan f1-score sebesar 0.99 menunjukkan performa yang sangat tinggi pada kelas ini. Namun, performa luar biasa ini pada data training mengindikasikan model kemungkinan mengalami overfitting, yakni terlalu menyesuaikan diri dengan data training sehingga bisa kurang optimal pada data baru.

  <br>
  <p align='center'>
    <img src="https://raw.githubusercontent.com/labibaadinda/predictive_analytics/main/img/6.2-evaluation-XGBoost-test.png" alt="Evaluation XGBoost Test Data" width="400" />
  </p>
<p align='center'>Gambar 11. Evaluation XGBoost (Test Data)</p>

<p align="center">

| Kelas         | Precision | Recall | F1-Score | Support |
|---------------|-----------|--------|----------|---------|
| 0             | 0.81      | 0.78   | 0.80     | 151     |
| 1             | 0.62      | 0.66   | 0.64     | 80      |
| **Accuracy**  |           |        | **0.74** | 231     |
| **Macro Avg** | 0.72      | 0.72   | 0.72     | 231     |
| **Weighted Avg**| 0.75    | 0.74   | 0.74     | 231     |

</p>


Pada data test, performa model menurun cukup signifikan dengan akurasi 74.03%, yang menunjukkan model kurang mampu menggeneralisasi pola dari data training ke data baru. Precision kelas 0 masih cukup baik di angka 0.81, memperlihatkan kemampuan model memprediksi kelas 0 secara cukup akurat. Recall kelas 0 sebesar 0.78 mengindikasikan sebagian besar kelas 0 berhasil dideteksi, walaupun ada beberapa yang terlewat. F1-score kelas 0 0.80 menunjukkan performa yang memadai. Namun, untuk kelas 1, precision menurun menjadi 0.62 dan recall sebesar 0.66, yang berarti model kurang akurat dan hanya berhasil mendeteksi sekitar dua pertiga data kelas 1 dengan benar. F1-score 0.64 mengindikasikan performa kelas 1 masih bisa ditingkatkan. Penurunan performa ini terutama terlihat pada kelas minoritas (kelas 1) dan mengonfirmasi dugaan overfitting pada model saat pelatihan. Untuk meningkatkan generalisasi, diperlukan teknik regularisasi atau augmentasi data agar model tidak terlalu spesifik pada data training.

Secara keseluruhan, model XGBoost sangat kuat dan efektif saat pelatihan dengan performa mendekati sempurna. Namun, model kurang mampu menggeneralisasi dengan baik pada data baru, khususnya dalam mendeteksi kelas minoritas (kelas 1). Oleh karena itu, perlu dilakukan perbaikan dan optimasi, misalnya melalui teknik regularisasi, pengaturan hyperparameter, atau penanganan data imbalance agar performa model di data test meningkat dan hasil prediksi menjadi lebih akurat dan dapat diandalkan.


### 3. Logistic Regression
  <br>
  <p align='center'>
    <img src="https://raw.githubusercontent.com/labibaadinda/predictive_analytics/main/img/6.3-evaluation-LogisticRegression-train.png" alt="Evaluation Logistic Regression Train Data" width="400" />
  </p>
<p align='center'>Gambar 12. Evaluation Logistic Regression (Train Data)</p>

<p align="center">

| Kelas         | Precision | Recall | F1-Score | Support |
|---------------|-----------|--------|----------|---------|
| 0             | 0.80      | 0.89   | 0.84     | 349     |
| 1             | 0.74      | 0.59   | 0.65     | 188     |
| **Accuracy**  |           |        | **0.78** | 537     |
| **Macro Avg** | 0.77      | 0.74   | 0.75     | 537     |
| **Weighted Avg**| 0.78    | 0.78   | 0.78     | 537     |

</p>


Model Logistic Regression berhasil memprediksi dengan benar sekitar 78.21% data training. Precision untuk kelas 0 adalah 0.80, artinya dari seluruh prediksi kelas 0, 80% tepat. Model ini juga mampu mendeteksi 89% dari seluruh data sebenarnya kelas 0 (recall 0.89), sehingga performa untuk kelas mayoritas cukup baik dengan f1-score 0.84 yang menunjukkan keseimbangan antara precision dan recall. Untuk kelas 1, precision sedikit lebih rendah di angka 0.74, dan recall sebesar 0.59, yang mengindikasikan model masih mengalami kesulitan dalam mengenali kelas minoritas secara akurat. F1-score kelas 1 sebesar 0.65 menegaskan performa yang lebih rendah dibanding kelas 0. Secara keseluruhan, model bekerja cukup baik di data training, terutama pada kelas mayoritas.

  <br>
  <p align='center'>
    <img src="https://raw.githubusercontent.com/labibaadinda/predictive_analytics/main/img/6.3-evaluation-LogisticRegression-test.png" alt="Evaluation Logistic Regression Test Data" width="400" />
  </p>
<p align='center'>Gambar 13. Evaluation Logistic Regression (Test Data)</p>

<p align="center">

| Kelas         | Precision | Recall | F1-Score | Support |
|---------------|-----------|--------|----------|---------|
| 0             | 0.80      | 0.81   | 0.81     | 151     |
| 1             | 0.64      | 0.61   | 0.62     | 80      |
| **Accuracy**  |           |        | **0.74** | 231     |
| **Macro Avg** | 0.72      | 0.71   | 0.72     | 231     |
| **Weighted Avg**| 0.74    | 0.74   | 0.74     | 231     |

</p>


Pada data test, performa model sedikit menurun menjadi 74.46%, namun masih cukup memuaskan. Precision kelas 0 tetap stabil di angka 0.80, dan model mampu mendeteksi 81% data kelas 0 sebenarnya (recall 0.81), sehingga performa untuk kelas mayoritas tetap cukup kuat dengan f1-score 0.81. Sedangkan untuk kelas 1, precision turun menjadi 0.64 dan recall menjadi 0.61, menandakan bahwa model kurang optimal dalam mendeteksi kelas minoritas. F1-score kelas 1 di data test adalah 0.62, yang menunjukkan performa yang masih memadai namun perlu peningkatan, khususnya dalam meningkatkan sensitivitas deteksi kelas minoritas.

Secara keseluruhan, Logistic Regression berfungsi sebagai baseline yang cukup baik dengan keseimbangan akurasi dan interpretasi model yang mudah. Model ini menunjukkan performa yang lebih baik dalam mengklasifikasikan kelas mayoritas (kelas 0), tetapi mengalami kesulitan dalam mendeteksi kelas minoritas (kelas 1), yang mengindikasikan perlunya pengembangan lebih lanjut untuk meningkatkan deteksi kelas minoritas agar hasil prediksi lebih seimbang.

### 4. K-Nearest Neighbors (KNN)
  <br>
  <p align='center'>
    <img src="https://raw.githubusercontent.com/labibaadinda/predictive_analytics/main/img/6.4-evaluation-knn_model-train.png" alt="Evaluation KNN Train Data" width="400" />
  </p>
<p align='center'>Gambar 14. Evaluation KNN (Train Data)</p>

<p align="center">

| Kelas         | Precision | Recall | F1-Score | Support |
|---------------|-----------|--------|----------|---------|
| 0             | 0.83      | 0.89   | 0.85     | 349     |
| 1             | 0.75      | 0.65   | 0.70     | 188     |
| **Accuracy**  |           |        | **0.80** | 537     |
| **Macro Avg** | 0.79      | 0.77   | 0.78     | 537     |
| **Weighted Avg**| 0.80    | 0.80   | 0.80     | 537     |

</p>


Model K-Nearest Neighbors (KNN) mampu memprediksi dengan benar sekitar 80.45% data training. Precision untuk kelas 0 adalah 0.83, artinya dari seluruh prediksi kelas 0, 83% tepat. Model ini juga berhasil mendeteksi 89% dari kelas 0 sebenarnya (recall 0.89), sehingga performa untuk kelas mayoritas cukup baik dengan f1-score 0.85 yang menunjukkan keseimbangan antara precision dan recall. Sedangkan untuk kelas 1, precision mencapai 0.75 dan recall sebesar 0.65, yang menunjukkan model menangkap 65% data kelas 1 sebenarnya. F1-score kelas 1 adalah 0.70, menunjukkan performa yang sedikit lebih rendah dibanding kelas 0 namun masih cukup baik. Kesimpulannya, model KNN bekerja dengan baik pada data training, terutama pada kelas mayoritas.

  <br>
  <p align='center'>
    <img src="https://raw.githubusercontent.com/labibaadinda/predictive_analytics/main/img/6.4-evaluation-knn_model-test.png" alt="Evaluation KNN Test Data" width="400" />
  </p>
<p align='center'>Gambar 15. Evaluation KNN (Test Data)</p>

<p align="center">

| Kelas         | Precision | Recall | F1-Score | Support |
|---------------|-----------|--------|----------|---------|
| 0             | 0.77      | 0.75   | 0.76     | 151     |
| 1             | 0.55      | 0.56   | 0.56     | 80      |
| **Accuracy**  |           |        | **0.69** | 231     |
| **Macro Avg** | 0.66      | 0.66   | 0.66     | 231     |
| **Weighted Avg**| 0.69    | 0.69   | 0.69     | 231     |

</p>


Pada data testing, akurasi model menurun menjadi 68.83%, menunjukkan performa yang menurun saat dihadapkan dengan data baru. Precision untuk kelas 0 turun menjadi 0.77 dan recall menjadi 0.75, sehingga model masih mampu mendeteksi sebagian besar kelas mayoritas, dengan f1-score 0.76 yang relatif stabil meski sedikit menurun. Namun, performa untuk kelas 1 menurun signifikan, dengan precision hanya 0.55 dan recall 0.56, yang berarti banyak prediksi kelas 1 yang salah dan model hanya mengenali 56% kelas 1 yang sebenarnya. F1-score kelas 1 menjadi 0.56, menandakan performa yang relatif lemah untuk kelas minoritas pada data testing. Kesimpulannya, model KNN kurang mampu melakukan generalisasi dengan baik untuk kelas minoritas pada data testing dan membutuhkan peningkatan khusus pada deteksi kelas 1.

Model KNN menunjukkan performa baik pada data training, tetapi mengalami penurunan performa yang cukup signifikan pada data testing, terutama untuk kelas minoritas, yang mengindikasikan kebutuhan pengoptimalan lebih lanjut agar model dapat lebih robust dan seimbang dalam memprediksi kedua kelas.


### 5. Support Vector Machine (SVM)
<br>
  <p align='center'>
    <img src="https://raw.githubusercontent.com/labibaadinda/predictive_analytics/main/img/6.5-evaluation-svm_model-train.png" alt="Evaluation SVM Train Data" width="400" />
  </p>
<p align='center'>Gambar 16. Evaluation SVM (Train Data)</p>

<p align="center">

| Kelas         | Precision | Recall | F1-Score | Support |
|---------------|-----------|--------|----------|---------|
| 0             | 0.77      | 0.94   | 0.85     | 349     |
| 1             | 0.81      | 0.48   | 0.61     | 188     |
| **Accuracy**  |           |        | **0.78** | 537     |
| **Macro Avg** | 0.79      | 0.71   | 0.73     | 537     |
| **Weighted Avg**| 0.79    | 0.78   | 0.76     | 537     |

</p>


Model Support Vector Machine (SVM) memprediksi dengan benar sekitar 78.03% data training. Precision untuk kelas 0 adalah 0.77, yang berarti dari semua prediksi kelas 0, 77% tepat. Model ini sangat baik dalam mendeteksi 94% data kelas 0 sebenarnya (recall 0.94), sehingga performanya untuk kelas mayoritas cukup tinggi dengan f1-score 0.85 yang menunjukkan keseimbangan baik antara precision dan recall. Untuk kelas 1, precision mencapai 0.81, namun recall hanya 0.48, yang berarti model hanya mendeteksi kurang dari setengah data kelas 1 sebenarnya. F1-score kelas 1 sebesar 0.61 menunjukkan performa yang lebih rendah dan perlu perbaikan. Kesimpulannya, model bekerja lebih baik pada kelas mayoritas, tetapi mengalami kesulitan dalam mendeteksi kelas minoritas selama pelatihan.

  <br>
  <p align='center'>
    <img src="https://raw.githubusercontent.com/labibaadinda/predictive_analytics/main/img/6.5-evaluation-svm_model-test.png" alt="Evaluation SVM Test Data" width="400" />
  </p>
<p align='center'>Gambar 17. Evaluation SVM (Test Data)</p>

<p align="center">

| Kelas         | Precision | Recall | F1-Score | Support |
|---------------|-----------|--------|----------|---------|
| 0             | 0.78      | 0.87   | 0.82     | 151     |
| 1             | 0.68      | 0.53   | 0.59     | 80      |
| **Accuracy**  |           |        | **0.75** | 231     |
| **Macro Avg** | 0.73      | 0.70   | 0.71     | 231     |
| **Weighted Avg**| 0.74    | 0.75   | 0.74     | 231     |

</p>


Pada data testing, akurasi model sedikit menurun menjadi 74.89%, namun masih cukup stabil. Presisi kelas 0 tetap baik di angka 0.78 dan model mampu mendeteksi 87% data kelas 0 (recall 0.87), sehingga performa kelas mayoritas tetap kuat dengan f1-score 0.82 yang stabil. Untuk kelas 1, presisi turun menjadi 0.68 dan recall menjadi 0.53, yang menunjukkan model hanya berhasil mendeteksi sedikit lebih dari setengah data kelas 1 sebenarnya. F1-score kelas 1 menjadi 0.59, menandakan performa yang relatif rendah pada data testing. Kesimpulannya, model SVM kurang efektif dalam mendeteksi kelas minoritas dan perlu optimasi lebih lanjut terutama untuk meningkatkan recall dan f1-score pada kelas 1.

Model SVM cukup efektif untuk memprediksi kelas mayoritas, namun memiliki kesulitan signifikan dalam mendeteksi kelas minoritas sehingga membutuhkan peningkatan performa khusus untuk kelas 1 agar hasil prediksi lebih seimbang dan akurat.

---

### Kesimpulan 

Berdasarkan hasil evaluasi, dapat diambil beberapa poin penting terkait performa model:

| Model               | Accuracy | F1-Score | AUC-ROC    |
| ------------------- | -------- | -------- | ---------- |
| Random Forest       | 0.7446   | 0.6144   | **0.8035** |
| XGBoost             | 0.7403   |**0.6386**| 0.7946     |
| Logistic Regression | 0.7446   | 0.6242   | 0.8006     |
| KNN                 | 0.6883   | 0.5556   | 0.7268     |
| SVM                 | 0.7489   | 0.5915   | 0.7776     |


* **Random Forest** merupakan model terbaik berdasarkan nilai AUC-ROC tertinggi (0.8035), yang menunjukkan kemampuannya paling baik dalam membedakan pasien dengan diabetes dan tanpa diabetes secara keseluruhan. Model ini juga memiliki keseimbangan baik antara akurasi dan F1-Score, sehingga cocok untuk digunakan dalam aplikasi prediksi klinis.

* **XGBoost** menunjukkan performa F1-Score tertinggi (0.6386), menandakan efektivitasnya dalam menangani ketidakseimbangan kelas dan menjaga keseimbangan antara precision dan recall. Namun, AUC-ROC-nya sedikit di bawah Random Forest.

* **Logistic Regression** sebagai model baseline memberikan hasil yang kompetitif dan mudah diinterpretasikan, dengan AUC-ROC yang cukup mendekati model terbaik, menjadikannya pilihan baik jika interpretabilitas penting.

* **Support Vector Machine (SVM)** memiliki akurasi tertinggi (74.89%), namun F1-Score dan AUC-ROC-nya masih di bawah Random Forest dan XGBoost, sehingga perlu tuning lebih lanjut agar lebih optimal.

* **K-Nearest Neighbors (KNN)** menunjukkan performa paling rendah di semua metrik, kurang cocok untuk dataset dan masalah ini.


Berdasarkan evaluasi berbagai model machine learning dalam proyek prediksi penyakit diabetes, dapat disimpulkan bahwa:

- **Model yang dikembangkan telah berhasil menjawab seluruh problem statement** yang diajukan, yaitu mampu memprediksi status diabetes secara efektif menggunakan data medis pasien. Model terbaik, Random Forest, menunjukkan performa akurasi dan AUC-ROC yang memadai untuk mendukung diagnosis klinis.

- **Tujuan proyek telah tercapai dengan baik,** meliputi pemahaman penerapan algoritma machine learning, pengembangan model yang tepat, serta evaluasi kinerja secara menyeluruh menggunakan metrik akurasi, F1-score, dan AUC. Proses ini memberikan gambaran lengkap tentang kekuatan dan keterbatasan tiap model.



