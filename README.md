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

- **Univariate Analysis**
<br>
    <p align='center'><img src="https://raw.githubusercontent.com/labibaadinda/predictive_analytics/main/img/plot_distribusi_outcome.png" alt="hist outcome" width="400" />
    </p>
  <p align='center'>Gambar 1. Bar Diagram Diabetes & Non-Diabetes</p> 
  Berdasarkan visualisasi grafik Bar Diagram pada gambar 1 di atas menunjukkan bahwa jumlah penderita penyakit diabetes yaitu 268 orang (34,9 %). Sedangkan jumlah orang yang non-diabetes yaitu  500 orang (65,1%) dari total keseluruhan jumlah orang dalam dataset (768 orang).


- **Multivariate Analysis**
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

- **Outliers**
  Visualisasi boxplot di atas bertujuan untuk mendeteksi adanya pencilan (outliers) dalam dataset yang digunakan pada proyek machine learning. Hal ini penting karena keberadaan outliers dapat menyebabkan bias atau menurunkan akurasi model dalam melakukan prediksi.

  <br>
    <p align='center'><img src="https://raw.githubusercontent.com/labibaadinda/predictive_analytics/main/img/plot_outlier.png" alt="plot outlier" width="400" />
    </p>
<p align='center'>Gambar 4. Mengecek outliers</p>


## Data Preparation

*Data preparation* adalah proses mengolah data mentah agar menjadi format yang tepat untuk analisis atau proses selanjutnya. Beberapa teknik yang digunakan dalam tahap persiapan data pada proyek ini antara lain:

1. **Penanganan outliers**
- *Outliers* adalah nilai-nilai yang menyimpang jauh dari nilai-nilai lain dalam dataset. Nilai-nilai ini muncul sebagai anomali yang tidak mengikuti pola umum data. Outliers bisa berupa nilai yang jauh lebih tinggi atau lebih rendah dibandingkan data lainnya, dan dapat disebabkan oleh kesalahan pengukuran, kejadian yang jarang terjadi, atau faktor tak terduga lainnya.

- Tujuan dari penanganan outliers adalah untuk memastikan bahwa nilai-nilai ekstrem tersebut tidak mengganggu analisis statistik atau model machine learning yang dikembangkan. Karena outliers berpotensi memberikan informasi yang menyesatkan dan mempengaruhi hasil analisis, penting untuk menanganinya agar hasil yang diperoleh lebih akurat dan dapat diandalkan.

- Beberapa cara yang dapat digunakan untuk menangani outliers meliputi identifikasi outliers, transformasi data, penghapusan outliers, dan imputasi data. Pada proyek ini, penanganan outliers dilakukan dengan metode imputasi menggunakan pendekatan *IQR method*. Hasil dari metode imputasi ini dapat dilihat pada gambar 5 berikut:

  <br>
    <p align='center'><img src="https://raw.githubusercontent.com/labibaadinda/predictive_analytics/main/img/plot_after_outlier_handling.png" alt="plot outlier" width="400" />
    </p>
<p align='center'>Gambar 5. Setelah outliers Handling</p>

2. **Handling imbalanced data**
   
   - *Imbalanced data* adalah kondisi di mana distribusi jumlah kelas dalam dataset tidak merata.
   
   - Tujuan penanganan data tidak seimbang adalah untuk meningkatkan kemampuan model dalam memprediksi kelas yang jumlahnya lebih sedikit (kelas minoritas).
   
   - Ada beberapa metode untuk mengatasi masalah ini. Salah satunya adalah *oversampling*, yaitu memperbanyak sampel dari kelas minoritas agar jumlahnya menjadi seimbang dengan kelas mayoritas, baik dengan menggandakan data yang ada atau membuat data sintetis baru. Metode lain adalah *undersampling*, yaitu mengurangi jumlah sampel pada kelas mayoritas agar seimbang dengan kelas minoritas, biasanya dengan menghapus sebagian data kelas mayoritas.
   
   - Dalam proyek ini, penanganan data tidak seimbang dilakukan menggunakan metode *SMOTE* (*Synthetic Minority Over-sampling Technique*), yang membuat sampel sintetis untuk kelas minoritas (kelas "1" pada kolom *Outcome*). Dengan cara ini, jumlah kelas minoritas dapat disamakan dengan kelas mayoritas, sehingga mengurangi bias model terhadap kelas mayoritas dan meningkatkan performa model untuk memprediksi kelas minoritas.

  <br>
    <p align='center'><img src="https://raw.githubusercontent.com/labibaadinda/predictive_analytics/main/img/plot_distribusi_ttg_oversampling.png" alt="oversampling handling" width="400" />
    </p>
<p align='center'>Gambar 6. Imbalanced data handling</p>


3. **Data Splitting**
   
   - Data Splitting adalah proses pemisahan *dataset* menjadi beberapa bagian yang berbeda untuk keperluan tertentu dalam analisis data, seperti pelatihan, validasi, dan pengujian model.
   
   - Tujuan dari tahap ini adalah membagi data menjadi dua kelompok, yaitu satu bagian untuk melatih model (set pelatihan) dan bagian lainnya untuk menguji performa model (set pengujian).
   
   - Metode yang digunakan dalam proses ini adalah *Train-test split*.

4. **Standardization**
   
   - Standardisasi merupakan proses pengubahan data agar memiliki rata-rata (*mean*) sebesar nol dan varians (*variance*) sebesar satu.
   
   - Tujuan standardisasi adalah untuk membuat distribusi data menjadi lebih terpusat di sekitar angka nol dengan variasi yang konsisten, sehingga membantu algoritma machine learning dalam memahami dan mengolah data secara lebih efektif.
   
   - Metode yang diterapkan melibatkan pengurangan setiap nilai fitur dengan rata-rata fitur tersebut, lalu membaginya dengan standar deviasi fitur tersebut. Pada kasus ini, *StandardScaler* dari scikit-learn digunakan untuk melakukan standardisasi dengan perhitungan *z-score*.

## Modeling

### Modeling dan Evaluate

Pada tahap ini, dilakukan pengembangan beberapa model machine learning dengan menggunakan algoritma klasifikasi yang berbeda, antara lain:

* **Random Forest**  
Algoritma ensemble learning yang menggabungkan banyak pohon keputusan (decision trees) untuk meningkatkan akurasi prediksi. Model ini dilatih dengan parameter utama seperti jumlah pohon (*n\_estimators*), kedalaman maksimum pohon (*max\_depth*), dan jumlah fitur maksimum yang dipertimbangkan (*max\_features*).

* **XGBoost**
  Algoritma boosting yang memanfaatkan gradient boosting untuk membangun model klasifikasi dengan performa tinggi. Digunakan untuk menangani data dengan kompleksitas tinggi dan fitur yang beragam.

* **Logistic Regression**
  Model regresi yang digunakan untuk prediksi probabilitas kelas biner, dalam hal ini prediksi status diabetes atau tidak.

* **K-Nearest Neighbors (KNN)**
  Algoritma non-parametrik yang mengklasifikasikan data berdasarkan kedekatan jarak ke tetangga terdekat.

* **Support Vector Machine (SVM)**
  Algoritma yang mencari hyperplane terbaik untuk memisahkan kelas dengan margin maksimal, digunakan dengan kernel radial basis function (RBF) untuk menangani data non-linear.

Setiap model dilatih menggunakan data latih dan kemudian dievaluasi performanya dengan data uji. Evaluasi menggunakan:

* **Confusion Matrix**: Menampilkan jumlah prediksi benar dan salah pada masing-masing kelas, divisualisasikan menggunakan heatmap.

* **Accuracy**: Persentase prediksi benar terhadap keseluruhan data.

* **Precision**: Ketepatan model dalam memprediksi kelas positif.

* **Recall**: Kemampuan model untuk menemukan seluruh data kelas positif.

* **F1-score**: Harmonik rata-rata dari precision dan recall, mengukur keseimbangan keduanya.

Visualisasi confusion matrix serta laporan klasifikasi (classification report) disajikan untuk masing-masing model pada data pelatihan dan pengujian. Ini memberikan gambaran lengkap tentang kemampuan model dalam mengenali kelas diabetes dan non-diabetes.

---

## 5. Kesimpulan

Berdasarkan hasil evaluasi, dapat diambil beberapa poin penting terkait performa model:

| Model               | Accuracy   | F1-Score   | AUC-ROC    |
| ------------------- | ---------- | ---------- | ---------- |
| Random Forest       | 74.46%     | 0.6144     | **0.8035** |
| XGBoost             | 71.86%     | 0.6108     | 0.7815     |
| Logistic Regression | 74.46%     | **0.6242** | 0.8006     |
| KNN                 | 68.83%     | 0.5556     | 0.7268     |
| SVM                 | **74.89%** | 0.5915     | 0.7776     |

* **Random Forest** menjadi model dengan nilai AUC-ROC tertinggi, yang berarti model ini paling baik dalam membedakan antara penderita diabetes dan non-diabetes secara keseluruhan.

<br>
  <br>
    <p align='center'><img src="https://raw.githubusercontent.com/labibaadinda/predictive_analytics/main/img/train_random_forest_best_auc.png" alt="random forest train data" width="400" />
    </p>
<p align='center'>Gambar 7.  Confusion Matrix Random Forest (Train)</p>
  <br>
    <p align='center'><img src="https://raw.githubusercontent.com/labibaadinda/predictive_analytics/main/img/test_random_forest_best_auc.png" alt="random forest test data" width="400" />
    </p>
<p align='center'>Gambar 8.  Confusion Matrix Random Forest(Test)</p>

* **Logistic Regression** memiliki nilai F1-score terbaik, menunjukkan keseimbangan optimal antara precision dan recall, yang sangat penting dalam konteks mendeteksi penyakit diabetes dengan menghindari prediksi salah.
<br>
  <br>
    <p align='center'><img src="https://raw.githubusercontent.com/labibaadinda/predictive_analytics/main/img/test_logistic_best_f1.png" alt="logistic regression train data" width="400" />
    </p>
<p align='center'>Gambar 9.  Confusion Matrix Logistic Regression(Train)</p>
  <br>
    <p align='center'><img src="https://raw.githubusercontent.com/labibaadinda/predictive_analytics/main/img/logistic_train_best_f1.png" alt="logistic regression test data" width="400" />
    </p>
<p align='center'>Gambar 10.  Confusion Matrix Logistic Regression(Test)</p>

* **SVM** menunjukkan nilai akurasi terbaik pada data pengujian, namun dengan nilai F1-score dan AUC sedikit lebih rendah dibandingkan Random Forest dan Logistic Regression, menandakan potensi kelemahan dalam mengidentifikasi kelas minoritas (penderita diabetes).

* **XGBoost** dan **KNN** menunjukkan performa yang lebih rendah di semua metrik evaluasi, terutama KNN yang berada pada posisi paling bawah.

Secara keseluruhan, model **Random Forest**, **Logistic Regression**, dan **SVM** memberikan performa yang kompetitif dan layak dipertimbangkan untuk diaplikasikan, tergantung prioritas metrik evaluasi yang diutamakan dalam proyek, seperti fokus pada AUC untuk kemampuan pemisahan kelas, atau F1-score untuk keseimbangan precision-recall.







