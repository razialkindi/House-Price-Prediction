# Laporan Proyek Machine Learning - Muhammad Razi Al Kindi Nadra

## Domain Proyek

### Latar Belakang

Pasar properti merupakan salah satu sektor ekonomi yang paling vital dan dinamis di dunia. Di California, Amerika Serikat, harga rumah telah mengalami fluktuasi yang signifikan selama beberapa dekade terakhir. Menurut data dari California Association of Realtors (CAR), median harga rumah di California telah meningkat lebih dari 300% dalam 20 tahun terakhir [1]. Kompleksitas dalam menentukan harga rumah yang tepat menjadi tantangan besar bagi berbagai pihak yang berkepentingan, termasuk pembeli, penjual, agen real estate, dan institusi keuangan.

Penentuan harga rumah yang akurat sangat penting karena beberapa alasan:

1. **Bagi Pembeli**: Membantu dalam membuat keputusan pembelian yang tepat dan menghindari pembayaran berlebih
2. **Bagi Penjual**: Memastikan harga jual yang kompetitif namun tetap menguntungkan
3. **Bagi Lembaga Keuangan**: Menilai risiko kredit dan menentukan nilai agunan yang tepat
4. **Bagi Pemerintah**: Merencanakan kebijakan perumahan dan perpajakan yang efektif

### Mengapa Masalah Ini Harus Diselesaikan

Ketidakakuratan dalam prediksi harga rumah dapat menyebabkan berbagai masalah ekonomi dan sosial:

1. **Bubble Properti**: Penilaian berlebih yang sistematis dapat menyebabkan bubble yang berpotensi merugikan ekonomi secara keseluruhan, seperti yang terjadi pada krisis finansial tahun 2008 [2]
2. **Ketidakadilan Sosial**: Harga yang tidak transparan dapat menyebabkan diskriminasi dan ketidakadilan dalam akses perumahan
3. **Inefisiensi Pasar**: Informasi yang tidak simetris antara pembeli dan penjual mengurangi efisiensi pasar properti
4. **Risiko Finansial**: Bank dan lembaga keuangan dapat mengalami kerugian besar akibat penilaian agunan yang tidak akurat

### Pendekatan Machine Learning

Machine learning telah terbukti efektif dalam menyelesaikan masalah prediksi harga properti. Penelitian yang dilakukan oleh Truong et al. [3] menunjukkan bahwa algoritma ensemble seperti Random Forest dan Gradient Boosting dapat mencapai akurasi prediksi hingga 90% pada dataset properti. Studi lain oleh Park & Bae [4] mengonfirmasi bahwa pendekatan machine learning lebih unggul dibandingkan metode tradisional dalam menangkap pola non-linear dalam data properti.

Implementasi model prediksi harga rumah yang akurat dapat memberikan manfaat signifikan:

- **Transparansi Pasar**: Meningkatkan transparansi dan mengurangi kesenjangan informasi
- **Efisiensi Transaksi**: Mempercepat proses negosiasi dan transaksi
- **Pengambilan Keputusan**: Membantu stakeholder membuat keputusan berbasis data
- **Inovasi Teknologi**: Mendorong adopsi teknologi dalam industri real estate

### Referensi

[1] California Association of Realtors. (2023). "California Housing Market Statistics". CAR Research & Economics.

[2] Mian, A., & Sufi, A. (2009). "The consequences of mortgage credit expansion: Evidence from the US mortgage default crisis". The Quarterly Journal of Economics, 124(4), 1449-1496.

[3] Truong, Q., Nguyen, M., Dang, H., & Mei, B. (2020). "Housing price prediction via improved machine learning techniques". Procedia Computer Science, 174, 433-442.

[4] Park, B., & Bae, J. K. (2015). "Using machine learning algorithms for housing price prediction". Expert Systems with Applications, 42(6), 2928-2934.

## Business Understanding

### Problem Statements

Berdasarkan latar belakang yang telah diuraikan, berikut adalah rumusan masalah yang akan diselesaikan dalam proyek ini:

1. **Bagaimana cara mengembangkan model machine learning yang dapat memprediksi harga rumah di California dengan tingkat akurasi tinggi berdasarkan karakteristik rumah dan lokasi geografis?**

2. **Faktor-faktor apa saja yang paling berpengaruh dalam menentukan harga rumah di California, dan seberapa besar pengaruh masing-masing faktor tersebut?**

3. **Bagaimana perbandingan performa berbagai algoritma machine learning dalam memprediksi harga rumah, dan algoritma mana yang memberikan hasil terbaik untuk kasus ini?**

### Goals

Untuk menjawab problem statements di atas, proyek ini memiliki tujuan sebagai berikut:

1. **Mengembangkan model prediksi harga rumah yang memiliki tingkat error (RMSE) kurang dari 20% dari rata-rata harga rumah dalam dataset**, sehingga dapat memberikan estimasi harga yang dapat diandalkan untuk berbagai pihak yang berkepentingan.

2. **Mengidentifikasi dan menganalisis faktor-faktor yang memiliki pengaruh paling signifikan terhadap harga rumah**, termasuk analisis feature importance dan interpretasi hubungan antar variabel.

3. **Membandingkan performa minimal 3 algoritma machine learning yang berbeda** dan menentukan algoritma terbaik berdasarkan metrik evaluasi yang komprehensif (MAE, RMSE, R², MAPE).

### Solution Statements

Untuk mencapai tujuan yang telah ditetapkan, berikut adalah solusi yang akan diimplementasikan:

#### 1. **Implementasi Multiple Algoritma dengan Pendekatan Berbeda**

- **Linear Regression**: Sebagai baseline model untuk memahami hubungan linear antar variabel
- **Ridge Regression**: Untuk mengatasi multikolinearitas dan meningkatkan generalisasi
- **Decision Tree Regressor**: Untuk menangkap hubungan non-linear dan interaksi antar fitur
- **Random Forest Regressor**: Model ensemble untuk meningkatkan akurasi dan ketahanan
- **Gradient Boosting Regressor**: Model ensemble alternatif dengan pendekatan boosting

#### 2. **Feature Engineering yang Komprehensif**

- Membuat fitur baru seperti rasio ruangan per kamar tidur, pendapatan per ruangan, dan kepadatan populasi
- Melakukan binning untuk variabel kontinu menjadi kategorikal (kategori umur rumah, kategori pendapatan)
- Membuat klaster geografis berdasarkan latitude dan longitude
- Menangani outlier dengan metode IQR yang disesuaikan

#### 3. **Hyperparameter Tuning dengan Grid Search**

- Melakukan Grid Search dengan 5-fold cross validation pada model Random Forest
- Parameter yang dioptimasi meliputi: n_estimators, max_depth, min_samples_split, min_samples_leaf, dan max_features
- Menggunakan scoring metric negative MSE untuk optimasi

#### 4. **Evaluasi Komprehensif dengan Multiple Metrics**

- **MAE (Mean Absolute Error)**: Untuk mengukur rata-rata error absolut
- **MSE (Mean Squared Error)**: Untuk memberikan penalti lebih pada error besar
- **RMSE (Root Mean Squared Error)**: Untuk interpretasi error dalam unit yang sama dengan target
- **R² (R-squared)**: Untuk mengukur proporsi variance yang dijelaskan model
- **MAPE (Mean Absolute Percentage Error)**: Untuk mengukur error dalam persentase

#### 5. **Validasi Model dengan Cross-Validation**

- Menggunakan 5-fold cross validation untuk memastikan model tidak overfitting
- Mengevaluasi konsistensi performa model pada berbagai fold
- Menggunakan hasil cross validation sebagai indikator reliabilitas model

## Data Understanding

### Sumber Data

Dataset yang digunakan adalah **California Housing Dataset** yang tersedia melalui scikit-learn library. Dataset ini merupakan versi modifikasi dari dataset California Housing yang dikumpulkan dari sensus California tahun 1990. Dataset dapat diakses melalui:

```python
from sklearn.datasets import fetch_california_housing
```

Link dokumentasi: [California Housing Dataset - Scikit-learn](https://scikit-learn.org/stable/datasets/real_world.html#california-housing-dataset)

### Informasi Dataset

Dataset memiliki karakteristik sebagai berikut:

- **Jumlah Instance**: 20,640 sampel data
- **Jumlah Fitur**: 8 fitur numerik
- **Target Variable**: 1 (Median house value)
- **Missing Values**: Tidak ada
- **Duplicate Values**: 0

### Variabel dalam Dataset

Berikut adalah deskripsi detail setiap variabel dalam dataset:

1. **MedInc** (Median Income): Median pendapatan dalam block group (dalam puluhan ribu dolar)

- Tipe: Numerical (float)
- Range: 0.4999 - 15.0001
- Interpretasi: Pendapatan median rumah tangga di area tersebut

2. **HouseAge** (House Age): Median umur rumah dalam block group (dalam tahun)

- Tipe: Numerical (float)
- Range: 1 - 52
- Interpretasi: Usia rata-rata rumah di area tersebut

3. **AveRooms** (Average Rooms): Rata-rata jumlah ruangan per rumah tangga

- Tipe: Numerical (float)
- Range: 0.8462 - 141.9091
- Interpretasi: Total ruangan dibagi jumlah rumah tangga

4. **AveBedrms** (Average Bedrooms): Rata-rata jumlah kamar tidur per rumah tangga

- Tipe: Numerical (float)
- Range: 0.3333 - 34.0667
- Interpretasi: Total kamar tidur dibagi jumlah rumah tangga

5. **Population**: Populasi block group

- Tipe: Numerical (float)
- Range: 3 - 35,682
- Interpretasi: Total populasi yang tinggal di block group

6. **AveOccup** (Average Occupancy): Rata-rata jumlah anggota rumah tangga

- Tipe: Numerical (float)
- Range: 0.6923 - 1243.3333
- Interpretasi: Populasi dibagi jumlah rumah tangga

7. **Latitude**: Garis lintang block group

- Tipe: Numerical (float)
- Range: 32.54 - 41.95
- Interpretasi: Koordinat geografis utara-selatan

8. **Longitude**: Garis bujur block group

- Tipe: Numerical (float)
- Range: -124.35 - -114.31
- Interpretasi: Koordinat geografis barat-timur

9. **MedHouseVal** (Target): Median nilai rumah dalam block group (dalam ratusan ribu dolar)

- Tipe: Numerical (float)
- Range: 0.14999 - 5.00001
- Interpretasi: Nilai median rumah di area tersebut

### Exploratory Data Analysis

#### 1. **Distribusi Target Variable**

Analisis distribusi harga rumah menunjukkan:

- Distribusi cenderung right-skewed dengan beberapa outlier pada nilai tinggi
- Mayoritas rumah memiliki nilai antara 100,000 - 300,000
- Terdapat capping pada nilai $500,000 (5.0 dalam dataset)

#### 2. **Korelasi Antar Variabel**

Dari analisis korelasi, ditemukan:

- **MedInc** memiliki korelasi tertinggi dengan target (0.69)
- **Latitude** dan **Longitude** menunjukkan korelasi negatif moderat (-0.14 dan -0.05)
- **HouseAge** memiliki korelasi positif lemah (0.11)
- Tidak ada multikolinearitas yang signifikan antar fitur

#### 3. **Analisis Geografis**

Visualisasi geografis menunjukkan:

- Harga rumah tertinggi terkonsentrasi di area pesisir (dekat pantai)
- Area metropolitan seperti Los Angeles dan San Francisco memiliki harga lebih tinggi
- Terdapat clustering geografis yang jelas dalam distribusi harga

#### 4. **Outliers**

Analisis outliers mengidentifikasi:

- **AveRooms** dan **AveBedrms**: Beberapa nilai ekstrem yang mungkin merupakan error data
- **AveOccup**: Nilai ekstrem tinggi yang tidak realistis
- **Population**: Beberapa block group dengan populasi sangat tinggi

#### 5. **Hubungan Fitur dengan Target**

- **Income vs Price**: Hubungan positif yang kuat dan hampir linear
- **House Age vs Price**: Hubungan lemah, rumah lebih tua tidak selalu lebih murah
- **Rooms vs Price**: Hubungan positif dengan beberapa outliers
- **Geographic**: Lokasi sangat mempengaruhi harga (coastal vs inland)

### Insight dari Data Understanding

1. **Income adalah prediktor terkuat**: Median income menunjukkan korelasi tertinggi dengan harga rumah
2. **Lokasi sangat penting**: Koordinat geografis menunjukkan clustering harga yang jelas
3. **Masalah kualitas data**: Terdapat outliers yang perlu ditangani, terutama pada AveRooms dan AveOccup
4. **Potensi feature engineering**: Kombinasi fitur seperti rooms per person atau geographic clustering dapat meningkatkan performa model
5. **Target capping**: Nilai target di-cap pada $500,000 yang mungkin mempengaruhi prediksi untuk rumah mewah

## Data Preparation

### 1. Feature Engineering

Feature engineering dilakukan untuk menciptakan fitur-fitur baru yang dapat meningkatkan kemampuan prediktif model:

#### a. **Rooms per Bedroom Ratio**

```python
df_prep['RoomsPerBedroom'] = df_prep['AveRooms'] / (df_prep['AveBedrms'] + 0.001)
```

- **Alasan**: Rasio ini menunjukkan seberapa besar rumah relatif terhadap jumlah kamar tidur
- **Interpretasi**: Nilai tinggi mengindikasikan rumah dengan ruang living/dining yang lebih luas

#### b. **Income per Room**

```python
df_prep['IncomePerRoom'] = df_prep['MedInc'] / (df_prep['AveRooms'] + 0.001)
```

- **Alasan**: Mengukur daya beli relatif terhadap ukuran rumah di area tersebut
- **Interpretasi**: Area dengan income per room tinggi cenderung memiliki harga per square foot lebih tinggi

#### c. **Population Density**

```python
df_prep['PopulationDensity'] = df_prep['Population'] / (df_prep['AveOccup'] + 0.001)
```

- **Alasan**: Estimasi jumlah household dalam block group
- **Interpretasi**: Density tinggi dapat mengindikasikan area urban dengan harga lebih tinggi

#### d. **Geographic Clusters**

```python
df_prep['GeoCluster'] = pd.cut(df_prep['Latitude'], bins=5, labels=False) * 5 + \
                        pd.cut(df_prep['Longitude'], bins=5, labels=False)
```

- **Alasan**: Menangkap pola geografis dalam harga rumah
- **Interpretasi**: Setiap cluster mewakili region geografis dengan karakteristik harga serupa

#### e. **Age Categories**

```python
df_prep['AgeCategory'] = pd.cut(df_prep['HouseAge'], 
                                bins=[0, 10, 20, 30, 40, 100],
                                labels=['Very New', 'New', 'Medium', 'Old', 'Very Old'])
```

- **Alasan**: Hubungan age-price mungkin non-linear
- **Interpretasi**: Kategorisasi membantu model menangkap perbedaan preferensi untuk rumah baru vs vintage

#### f. **Income Categories**

```python
df_prep['IncomeCategory'] = pd.qcut(df_prep['MedInc'], q=5, 
                                    labels=['Very Low', 'Low', 'Medium', 'High', 'Very High'])
```

- **Alasan**: Income levels mungkin memiliki efek threshold pada harga
- **Interpretasi**: Membantu model memahami segmentasi pasar berdasarkan income

### 2. Handling Outliers

Outliers ditangani menggunakan metode IQR (Interquartile Range) dengan threshold 3*IQR untuk menghapus hanya outliers ekstrem:

```python
for feature in ['AveRooms', 'AveBedrms', 'Population', 'AveOccup']:
    Q1 = df_prep[feature].quantile(0.25)
    Q3 = df_prep[feature].quantile(0.75)
    IQR = Q3 - Q1
    lower_bound = Q1 - 3 * IQR
    upper_bound = Q3 + 3 * IQR
```

**Hasil penghapusan outliers:**

- Dataset awal: 20,640 sampel
- Setelah penghapusan outlier: 19,389 sampel
- Total dihapus: 1,251 sampel (6.06%)

**Detail outliers per fitur:**

- AveRooms: 180 outliers
- AveBedrms: 557 outliers  
- Population: 413 outliers
- AveOccup: 101 outliers

**Alasan menggunakan 3*IQR:**

- Metode standar (1.5*IQR) terlalu agresif dan menghapus banyak data valid
- 3*IQR hanya menghapus outliers yang sangat ekstrem
- Mempertahankan variasi natural dalam data

### 3. Encoding Categorical Variables

One-hot encoding digunakan untuk variabel kategorikal yang telah dibuat:

```python
age_dummies = pd.get_dummies(df_prep['AgeCategory'], prefix='Age')
income_dummies = pd.get_dummies(df_prep['IncomeCategory'], prefix='Income')
```

**Alasan menggunakan One-Hot Encoding:**

- Variabel kategorikal tidak memiliki urutan natural
- Mencegah model mengasumsikan hubungan ordinal yang tidak ada
- Memungkinkan model untuk belajar efek independen setiap kategori

### 4. Feature Selection

Pemilihan fitur dilakukan berdasarkan:

1. Domain knowledge (semua fitur original dipertahankan)
2. Engineered features yang logis
3. Encoded categorical variables

**Final feature set (22 fitur):**

- 8 fitur original
- 4 fitur numerik hasil engineering  
- 5 dummy variables untuk age category (dikurangi 1 untuk menghindari dummy trap)
- 5 dummy variables untuk income category (dikurangi 1 untuk menghindari dummy trap)
- Total: 22 fitur

### 5. Train-Test Split

Data dibagi dengan proporsi 80:20 untuk training dan testing:

```python
X_train, X_test, y_train, y_test = train_test_split(X, y, test_size=0.2, random_state=42)
```

**Hasil split:**

- Training set: 15,511 sampel (80%)
- Test set: 3,878 sampel (20%)

**Alasan proporsi 80:20:**

- Dataset cukup besar untuk memberikan test set yang representatif
- 80% training data memberikan sampel yang cukup untuk pembelajaran yang robust
- Random state=42 untuk reproducibility

### 6. Feature Scaling

RobustScaler digunakan untuk normalisasi fitur numerik:

```python
scaler = RobustScaler()
X_train_scaled[numerical_features] = scaler.fit_transform(X_train[numerical_features])
X_test_scaled[numerical_features] = scaler.transform(X_test[numerical_features])
```

**Alasan menggunakan RobustScaler:**

- Lebih robust terhadap outliers dibanding StandardScaler
- Menggunakan median dan IQR alih-alih mean dan standard deviation
- Cocok untuk data dengan outliers yang tidak dihapus sepenuhnya

**Fitur yang di-scale:**

- Semua fitur numerik (original + engineered)
- Categorical dummies tidak di-scale (sudah binary 0/1)

### Ringkasan Data Preparation

Tahapan data preparation yang dilakukan:

1. ✅ **Feature Engineering**: 6 fitur baru dibuat untuk menangkap hubungan kompleks
2. ✅ **Outlier Handling**: 1,251 extreme outliers dihapus (6.06% dari data)
3. ✅ **Categorical Encoding**: One-hot encoding untuk 2 variabel kategorikal
4. ✅ **Feature Selection**: 22 fitur final dipilih berdasarkan domain knowledge
5. ✅ **Data Splitting**: 80/20 train-test split dengan 15,511/3,878 sampel
6. ✅ **Feature Scaling**: RobustScaler untuk 12 fitur numerik

Hasil akhir adalah dataset yang bersih, kaya fitur, dan siap untuk modeling dengan:

- Tidak ada missing values
- Outliers ekstrem telah dihapus
- Fitur yang informatif dan ter-scale dengan baik
- Pemisahan yang jelas antara train dan test set

## Modeling

Pada tahap modeling, lima algoritma machine learning diimplementasikan dengan pendekatan yang berbeda untuk menangkap pola dalam data harga rumah.

### 1. Linear Regression (Baseline Model)

Linear Regression dipilih sebagai baseline model karena kesederhanaan dan kemudahan interpretasinya.

**Implementasi:**

```python
lr_model = LinearRegression()
lr_model.fit(X_train_scaled, y_train)
```

**Cara Kerja:**

- Linear Regression mencari kombinasi linear optimal dari fitur-fitur untuk memprediksi target
- Model meminimalkan sum of squared residuals: min Σ(yi - ŷi)²
- Menghasilkan koefisien (weights) untuk setiap fitur yang menunjukkan pengaruhnya terhadap harga

**Kelebihan:**

- Sederhana dan cepat untuk training
- Mudah diinterpretasi - koefisien langsung menunjukkan pengaruh fitur
- Tidak memerlukan hyperparameter tuning
- Memberikan baseline performance yang baik

**Kekurangan:**

- Hanya dapat menangkap hubungan linear
- Sensitif terhadap multikolinearitas
- Asumsi normalitas dan homoskedastisitas mungkin tidak terpenuhi
- Tidak dapat menangkap interaksi kompleks antar fitur

### 2. Ridge Regression

Ridge Regression digunakan untuk mengatasi potensi overfitting dan multikolinearitas.

**Implementasi:**

```python
ridge_model = Ridge(alpha=1.0, random_state=42)
ridge_model.fit(X_train_scaled, y_train)
```

**Parameter:**

- `alpha=1.0`: Kekuatan regularisasi
- `random_state=42`: Untuk reproducibility

**Cara Kerja:**

- Menambahkan penalty term L2 (λΣβi²) ke fungsi loss
- Menyusutkan koefisien mendekati nol tanpa membuat mereka exactly zero
- Trade-off antara bias dan variance dikontrol oleh alpha

**Kelebihan:**

- Mengatasi multikolinearitas dengan baik
- Lebih stabil dibanding Linear Regression pada high-dimensional data
- Mencegah overfitting melalui regularisasi
- Semua fitur tetap dipertahankan dalam model

**Kekurangan:**

- Masih terbatas pada hubungan linear
- Memerlukan tuning parameter alpha
- Koefisien lebih sulit diinterpretasi karena shrinkage
- Tidak melakukan feature selection otomatis

### 3. Decision Tree Regressor

Decision Tree dapat menangkap non-linearitas dan interaksi antar fitur.

**Implementasi:**

```python
dt_model = DecisionTreeRegressor(max_depth=10, min_samples_split=20, 
                                 min_samples_leaf=10, random_state=42)
dt_model.fit(X_train, y_train)
```

**Parameter yang digunakan:**

- `max_depth=10`: Membatasi kedalaman tree untuk mencegah overfitting
- `min_samples_split=20`: Minimum sampel untuk split internal node
- `min_samples_leaf=10`: Minimum sampel di leaf node
- `random_state=42`: Untuk reproducibility

**Cara Kerja:**

- Membagi data secara rekursif berdasarkan feature thresholds
- Setiap split dipilih untuk meminimalkan MSE di child nodes
- Leaf nodes berisi rata-rata nilai target dari sampel di node tersebut
- Prediksi dilakukan dengan traversing tree hingga leaf node

**Kelebihan:**

- Dapat menangkap hubungan non-linear dan interaksi
- Tidak memerlukan feature scaling
- Mudah divisualisasi dan diinterpretasi
- Dapat menangani data numerik dan kategorikal

**Kekurangan:**

- Rentan terhadap overfitting terutama pada deep trees
- Tidak stabil - perubahan kecil pada data dapat mengubah struktur tree
- Bias terhadap fitur dengan banyak levels
- Poor extrapolation - tidak dapat memprediksi di luar range training data

### 4. Random Forest Regressor (dengan Hyperparameter Tuning)

Random Forest dipilih sebagai model ensemble yang robust dan akurat.

**Implementasi dengan Grid Search:**

```python
param_grid = {
    'n_estimators': [100, 200],
    'max_depth': [10, 20, 30],
    'min_samples_split': [2, 5, 10],
    'min_samples_leaf': [1, 2, 4],
    'max_features': ['sqrt', 'log2']
}

rf = RandomForestRegressor(random_state=42, n_jobs=-1)
grid_search = GridSearchCV(estimator=rf, param_grid=param_grid,
                          cv=5, n_jobs=-1, scoring='neg_mean_squared_error')
```

**Best Parameters yang Ditemukan:**

- `n_estimators=200`: Jumlah trees dalam forest
- `max_depth=30`: Kedalaman maksimum setiap tree
- `min_samples_split=2`: Minimum sampel untuk split
- `min_samples_leaf=1`: Minimum sampel di leaf
- `max_features='sqrt'`: Jumlah fitur untuk setiap split

**Cara Kerja:**

- Membuat ensemble dari multiple decision trees
- Setiap tree dilatih pada bootstrap sample dari data (bagging)
- Setiap split hanya mempertimbangkan random subset dari fitur
- Prediksi final adalah rata-rata dari semua tree predictions
- Randomness mengurangi overfitting dan meningkatkan generalisasi

**Kelebihan:**

- Akurasi tinggi dan performa yang robust
- Mengurangi overfitting melalui ensemble averaging
- Dapat menangkap hubungan non-linear yang kompleks
- Memberikan feature importance scores
- Dapat diparalelisasi untuk training lebih cepat

**Kekurangan:**

- Lebih lambat untuk training dan prediction
- Memerlukan lebih banyak memory
- Kurang interpretable dibanding single tree
- Hyperparameter tuning bisa memakan waktu

### 5. Gradient Boosting Regressor

Gradient Boosting sebagai metode ensemble alternatif dengan pendekatan boosting.

**Implementasi:**

```python
gb_model = GradientBoostingRegressor(n_estimators=100, learning_rate=0.1,
                                     max_depth=5, random_state=42)
gb_model.fit(X_train, y_train)
```

**Parameter yang digunakan:**

- `n_estimators=100`: Jumlah boosting stages
- `learning_rate=0.1`: Parameter shrinkage
- `max_depth=5`: Kedalaman individual trees
- `random_state=42`: Untuk reproducibility

**Cara Kerja:**

- Membangun trees secara sequential, setiap tree memperbaiki errors dari ensemble sebelumnya
- Setiap tree fit pada negative gradient dari loss function
- Learning rate mengontrol kontribusi setiap tree
- Prediksi final adalah weighted sum dari semua trees

**Kelebihan:**

- Sering mencapai akurasi terbaik pada structured data
- Fleksibilitas dalam loss functions
- Penanganan natural untuk mixed data types
- Built-in feature selection melalui tree building

**Kekurangan:**

- Sensitif terhadap hyperparameters
- Lebih rentan terhadap overfitting dibanding Random Forest
- Sequential nature membuat training lebih lambat
- Memerlukan tuning yang hati-hati untuk performa optimal

### Proses Pemilihan Model

Pemilihan model terbaik dilakukan berdasarkan:

1. **Performance Metrics**: Evaluasi komprehensif menggunakan MAE, RMSE, R², dan MAPE
2. **Cross-Validation**: 5-fold CV untuk memastikan generalisasi model
3. **Training Time**: Pertimbangan praktis untuk deployment
4. **Interpretability**: Kemampuan untuk menjelaskan prediksi

Berdasarkan evaluasi, **Gradient Boosting Regressor** dipilih sebagai model terbaik karena:

- R² score tertinggi (0.8421)
- RMSE terendah (0.4643)
- MAE terendah (0.3127)
- MAPE terendah (16.82%)
- Performa konsisten dengan CV RMSE mean 0.4828

## Evaluation

### Metrik Evaluasi

Evaluasi model dilakukan menggunakan lima metrik yang saling melengkapi untuk memberikan pemahaman komprehensif tentang performa model:

#### 1. Mean Absolute Error (MAE)

**Formula:**

```javascript
MAE = (1/n) × Σ|yi - ŷi|
```

**Interpretasi:**

- MAE mengukur rata-rata magnitude error tanpa mempertimbangkan arahnya
- Dalam konteks ini, MAE menunjukkan rata-rata deviasi prediksi harga rumah dalam ratusan ribu dolar
- Robust terhadap outliers karena tidak mengkuadratkan error

#### 2. Mean Squared Error (MSE)

**Formula:**

```javascript
MSE = (1/n) × Σ(yi - ŷi)²
```

**Interpretasi:**

- MSE memberikan penalti lebih besar untuk error yang besar karena pengkuadratan
- Berguna untuk kasus di mana error besar sangat tidak diinginkan
- Unit dalam kuadrat membuat interpretasi langsung sulit

#### 3. Root Mean Squared Error (RMSE)

**Formula:**

```javascript
RMSE = √MSE = √[(1/n) × Σ(yi - ŷi)²]
```

**Interpretasi:**

- RMSE mengembalikan unit ke skala original (ratusan ribu dolar)
- Lebih sensitif terhadap error besar dibanding MAE
- Metrik standar untuk masalah regresi

#### 4. R-squared (R²)

**Formula:**

```javascript
R² = 1 - (SSres/SStot)
di mana:
SSres = Σ(yi - ŷi)²
SStot = Σ(yi - ȳ)²
```

**Interpretasi:**

- Menunjukkan proporsi variance dalam target yang dijelaskan oleh model
- Nilai 1 menunjukkan perfect fit, 0 menunjukkan model tidak lebih baik dari mean
- Independent dari scale, memudahkan perbandingan antar datasets

#### 5. Mean Absolute Percentage Error (MAPE)

**Formula:**

```javascript
MAPE = (100/n) × Σ|(yi - ŷi)/yi|
```

**Interpretasi:**

- Menunjukkan error sebagai persentase dari nilai aktual
- Memudahkan interpretasi untuk non-technical stakeholders
- Dapat bermasalah untuk nilai mendekati nol

### Hasil Evaluasi

Berikut adalah performa kelima model yang diimplementasikan:

 Model  MAE  MSE  RMSE  R²  MAPE (%)  Linear Regression  0.4746  0.4092  0.6397  0.7003  27.49  Ridge Regression  0.4746  0.4092  0.6397  0.7003  27.49  Decision Tree  0.4073  0.3720  0.6099  0.7275  21.49  Random Forest  0.3450  0.2555  0.5055  0.8128  18.94  **Gradient Boosting**  **0.3127**  **0.2155**  **0.4643**  **0.8421**  **16.82** 

### Analisis Performa Model

#### 1. **Model Linear (Linear & Ridge Regression)**

- Performa identik dengan R² = 0.7003
- RMSE tinggi (0.6397 atau $63,970) menunjukkan kesulitan menangkap kompleksitas data
- MAPE ~27.5% menunjukkan error yang signifikan
- Ridge regression tidak memberikan improvement, mengindikasikan minimal multikolinearitas

#### 2. **Model Tree-Based Menunjukkan Performa Superior**

- Decision Tree: Peningkatan signifikan (R²=0.7275) dibanding model linear
- Random Forest: Performa excellent dengan R²=0.8128
- Gradient Boosting: Performa terbaik dengan R²=0.8421

#### 3. **Gradient Boosting sebagai Model Terbaik**

- **MAE terendah**: 0.3127 (rata-rata error $31,270)
- **RMSE terendah**: 0.4643 ($46,430)
- **R² tertinggi**: 0.8421 (menjelaskan 84.21% variance)
- **MAPE terendah**: 16.82% rata-rata persentase error

### Visualisasi Hasil

#### 1. **Plot Actual vs Predicted**

Visualisasi menunjukkan:

- Model linear: Systematic underprediction untuk rumah bernilai tinggi
- Model tree-based: Fit yang lebih baik di seluruh range
- Gradient Boosting: Clustering paling rapat di sekitar garis diagonal (perfect prediction)

#### 2. **Analisis Residual untuk Gradient Boosting**

Analisis residual menunjukkan:

- **Distribusi**: Mendekati normal dengan slight right skew
- **Homoskedastisitas**: Variance relatif konstan di seluruh range prediksi
- **Tidak ada pola sistematis**: Mengindikasikan spesifikasi model yang baik

#### 3. **Feature Importance (Model Tree-Based)**

Fitur terpenting berdasarkan importance:

1. **MedInc**: Median income mendominasi prediksi
2. **Longitude & Latitude**: Lokasi geografis sangat penting
3. **AveOccup**: Kepadatan rumah tangga berpengaruh
4. **Engineered features**: RoomsPerBedroom dan IncomePerRoom menambah nilai

### Hasil Cross-Validation

5-fold cross-validation untuk Gradient Boosting:

```javascript
CV RMSE scores: [0.4829, 0.4823, 0.4628, 0.4969, 0.4892]
Mean CV RMSE: 0.4828 (+/- 0.0226)
```

**Interpretasi:**

- Performa konsisten di semua fold
- CV RMSE (0.4828) dekat dengan test RMSE (0.4643)
- Standard deviation 0.0226 menunjukkan stabilitas
- Mengindikasikan generalisasi yang baik dan minimal overfitting

### Evaluasi Terhadap Business Goals

#### Goal 1: RMSE < 20% dari rata-rata harga ❌

- Rata-rata harga dalam dataset: 2.089 ($208,900)
- Target RMSE: 0.4178 (20% dari mean)
- RMSE yang dicapai: 0.4643
- **Persentase**: 22.2% dari mean price
- **Status**: Tidak tercapai, namun mendekati target (miss sebesar 2.2%)

#### Goal 2: Identifikasi faktor penting ✅

Analisis feature importance berhasil mengidentifikasi:

- Income sebagai faktor dominan
- Lokasi (lat/lon) sangat penting
- Engineered features memberikan nilai tambah
- Karakteristik rumah (rooms, age) memiliki pengaruh moderat

#### Goal 3: Perbandingan multiple algoritma ✅

Perbandingan komprehensif dari 5 algoritma dilakukan:

- Pemenang jelas teridentifikasi (Gradient Boosting)
- Peningkatan performa dari baseline ke model terbaik: 20.1% peningkatan R²
- Trade-offs didokumentasikan untuk setiap algoritma

### Testing Model dengan Data Sampel

Testing pada 3 sampel rumah menunjukkan prediksi yang reasonable:

 Sample  MedInc  HouseAge  AveRooms  Predicted Price  Karakteristik  1  3.5  25  5.5  $173,327  Mid-income, medium age  2  5.0  10  6.2  $212,211  Higher income, newer  3  8.0  35  7.1  $343,154  High income, older 

Prediksi sejalan dengan karakteristik input dan ekspektasi pasar.

### Kesimpulan Evaluasi

1. **Performa Model**: Gradient Boosting mencapai performa terbaik dengan R² = 0.8421, meskipun sedikit melewati target RMSE

2. **Kegunaan Praktis**: 

- MAPE 16.82% dapat diterima untuk valuasi properti
- Rata-rata error $46,430 dalam konteks pasar California yang mahal masih reasonable
- Model dapat digunakan untuk valuasi awal dengan review dari expert

3. **Reliabilitas**: 

- Hasil cross-validation konsisten (std dev 2.26%)
- Tidak ada overfitting signifikan yang terdeteksi
- Model generalize dengan baik pada data yang belum pernah dilihat

4. **Interpretabilitas**: 

- Feature importance memberikan insights yang jelas
- Income dan lokasi terkonfirmasi sebagai driver utama
- Engineered features terbukti bermanfaat

5. **Area untuk Perbaikan**:

- Model sedikit underperform pada target RMSE (miss sebesar 2.2%)
- Dapat benefit dari fitur tambahan (crime rates, school quality)
- Aspek temporal tidak ditangkap (market trends, seasonality)

Meskipun target RMSE tidak sepenuhnya tercapai, model Gradient Boosting yang dikembangkan menunjukkan performa excellent dengan R² 84.21% dan dapat memberikan nilai signifikan untuk aplikasi real-world dalam pasar rumah California.

## Kesimpulan

### Ringkasan Proyek

Proyek ini berhasil mengembangkan model machine learning untuk memprediksi harga rumah di California menggunakan dataset dari sensus tahun 1990. Melalui proses sistematis dari data understanding hingga model evaluation, telah dihasilkan model Gradient Boosting yang dapat menjelaskan 84.21% variasi dalam harga rumah.

### Pencapaian Utama

1. **Performa Model**

- Model Gradient Boosting mencapai R² = 0.8421
- RMSE sebesar $46,430 atau 22.2% dari rata-rata harga
- MAE $31,270 menunjukkan rata-rata deviasi yang reasonable
- MAPE 16.82% mengindikasikan akurasi persentase yang baik

2. **Pemrosesan Data yang Excellent**

- Berhasil menangani 20,640 sampel dengan 8 fitur
- Menciptakan 6 fitur engineered yang bermakna
- Menghapus 1,251 extreme outliers (6.06%)
- Dataset final: 19,389 sampel dengan 22 fitur

3. **Perbandingan Model yang Komprehensif**

- Mengevaluasi 5 algoritma berbeda
- Melakukan hyperparameter tuning untuk Random Forest
- Progresi performa yang jelas dari model linear ke ensemble
- Gradient Boosting muncul sebagai pemenang yang jelas

4. **Insights yang Berharga**

- Median income terkonfirmasi sebagai prediktor terkuat
- Lokasi geografis (lat/lon) secara kolektif berkontribusi ~30% importance
- Fitur engineered seperti RoomsPerBedroom menambah nilai prediktif
- Umur rumah memiliki pengaruh moderat terhadap harga

### Evaluasi Target dan Pencapaian

 Target  Status  Detail  RMSE < 20% mean price  ❌ Tidak Tercapai  Dicapai 22.2% (miss sebesar 2.2%)  Identifikasi faktor kunci  ✅ Tercapai  Feature importance teridentifikasi jelas  Perbandingan 3+ algoritma  ✅ Tercapai  5 algoritma dibandingkan secara komprehensif  Model akurasi tinggi  ✅ Tercapai  R² = 0.8421 adalah excellent 

### Dampak dan Aplikasi Praktis

1. **Valuasi Properti**

- Model dapat digunakan untuk penilaian properti awal
- Rata-rata error $46,430 masih dapat diterima dalam pasar California yang mahal
- Memberikan baseline objektif untuk negosiasi

2. **Analisis Pasar**

- Mengidentifikasi key value drivers untuk keputusan investasi
- Geographic clustering mengungkap premium lokasi
- Hubungan income-to-price membantu segmentasi pasar

3. **Pembuatan Kebijakan**

- Memahami price drivers membantu kebijakan perumahan
- Disparitas geografis tersorot untuk perencanaan urban
- Pengaruh income menunjukkan tantangan affordability

### Limitasi Model

1. **Target RMSE Tidak Tercapai**

- Model sedikit underperform pada metrik target (2.2% over)
- Properti bernilai tinggi lebih sulit diprediksi dengan akurat
- Beberapa hubungan non-linear mungkin tidak sepenuhnya ditangkap

2. **Keterbatasan Data**

- Dataset dari sensus 1990 - tidak current
- Fitur penting hilang (square footage, kondisi, amenities)
- Tidak ada informasi temporal untuk market trends

3. **Cakupan Geografis**

- Terbatas pada California - tidak langsung transferable
- Dinamika coastal vs inland spesifik untuk California
- Dinamika pasar berbeda di negara bagian lain

### Rekomendasi dan Future Work

1. **Perbaikan Segera**

- Coba XGBoost atau LightGBM untuk potential performance boost
- Engineer fitur geografis yang lebih sophisticated
- Implementasi ensemble stacking dari model terbaik

2. **Enhancement Data**

- Akuisisi data perumahan yang lebih recent
- Tambahkan fitur property-specific (ukuran, lot, kondisi)
- Include data neighborhood (sekolah, crime, amenities)

3. **Teknik Advanced**

- Implementasi spatial regression untuk dependencies geografis
- Gunakan deep learning untuk automatic feature extraction
- Integrasi time series untuk dinamika pasar

4. **Strategi Deployment**

- Kembangkan API untuk prediksi real-time
- Buat confidence intervals untuk prediksi
- Implementasi monitoring untuk model drift

### Key Takeaways

1. **Efektivitas Machine Learning**: Metode tree-based ensemble secara signifikan mengungguli model linear untuk data real estate yang kompleks

2. **Nilai Feature Engineering**: Fitur yang dibuat berkontribusi bermakna terhadap performa model

3. **Pentingnya Geografis**: Fitur lokasi secara kolektif sama pentingnya dengan income

4. **Viabilitas Praktis**: Meskipun melewatkan target RMSE dengan margin kecil, model mencapai performa overall yang excellent cocok untuk penggunaan real-world

5. **Continuous Improvement**: Retraining regular dengan data updated essential untuk menjaga relevansi

### Final Thoughts

Proyek ini berhasil mendemonstrasikan aplikasi machine learning untuk valuasi real estate. Meskipun target RMSE terlewat tipis, model Gradient Boosting dengan R² = 0.8421 merepresentasikan pencapaian signifikan dalam memprediksi harga rumah California.

Gap 2.2% dari target RMSE harus dilihat dalam konteks:

- Pasar perumahan California sangat beragam dan kompleks
- Model tetap mencapai variance explanation 84.21% yang excellent
- Margin error praktis dapat diterima untuk valuasi awal

Proyek ini memberikan fondasi yang solid untuk:

- Refinement model lebih lanjut
- Ekspansi ke pasar geografis lain
- Integrasi dengan platform real estate
- Pengembangan comprehensive property analytics tools

Machine learning terbukti sangat berharga untuk mendemokratisasi valuasi properti, dan proyek ini berkontribusi pada kemajuan yang bermakna menuju tujuan tersebut.
