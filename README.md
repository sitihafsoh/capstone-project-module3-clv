# **Capstone Project Module 3: Customer Lifetime Value**

![Long Life](https://github.com/user-attachments/assets/f41982e5-6edc-4bdf-98f6-75afe21a7f2c)

## **Context**
PT. Long Life Insurance Indonesia adalah perusahaan asuransi yang telah berdiri sejak tahun 2010 dan telah berhasil membangun reputasi yang baik dalam industri asuransi di Indonesia. Dengan portofolio produk yang beragam, perusahaan ini telah melayani jutaan nasabah di seluruh Indonesia. Salah satu produk unggulan PT. Long Life Insurance Indonesia adalah asuransi kendaraan, yang telah menjadi pilihan utama bagi banyak pemilik kendaraan bermotor.
<br><br>
Asuransi kendaraan yang ditawarkan oleh PT. Long Life Insurance Indonesia dirancang untuk memberikan perlindungan menyeluruh pada kendaraan nasabah dari berbagai risiko, seperti kecelakaan, pencurian, bencana alam, dan kerusakan lainnya. Produk ini menawarkan berbagai pilihan coverage, mulai dari perlindungan dasar (basic) hingga perlindungan yang lebih komprehensif (extended dan premium), sehingga nasabah dapat memilih sesuai dengan kebutuhan dan anggaran masing-masing.
<br><br>
Namun saat ini PT. Long Life Insurance Indonesia sedang menghadapi tantangan dalam memaksimalkan nilai seumur hidup pelanggan (Customer Lifetime Value atau CLV) pada produk asuransi kendaraannya, yaitu adanya variabilitas nilai CLV pada pelanggan.

## **Problem Statement**
PT. Long Life Insurance Indonesia tengah menghadapi tantangan dalam memaksimalkan nilai seumur hidup pelanggan (Customer Lifetime Value atau CLV) dari produk asuransi kendaraannya. Meskipun perusahaan telah menawarkan berbagai pilihan coverage yang dirancang untuk memenuhi kebutuhan beragam pelanggan, masih terdapat variabilitas yang signifikan dalam CLV antar pelanggan. Untuk meningkatkan profitabilitas dan merancang strategi pemasaran serta retensi yang lebih efektif, diperlukan analisis mendalam untuk memahami faktor-faktor apa saja yang paling berpengaruh terhadap CLV.

## **Stakeholder**
a. Tim Keuangan
- Berkepentingan dalam memahami faktor-faktor yang mempengaruhi CLV untuk meningkatkan profitabilitas.

b. Tim Manajemen dan Pengembangan Produk
- Memerlukan wawasan untuk merancang produk dan layanan yang dapat meningkatkan CLV.

c. Tim Data Science
- Bertanggung jawab dalam melakukan analisis data dan membangun model prediktif yang akurat.

d. Tim Pemasaran
- Menggunakan hasil analisis untuk mengarahkan upaya pemasaran yang lebih efektif kepada pelanggan bernilai tinggi.

## **Goals**
a. Memahami bagaimana variabel-variabel seperti `Vehicle Class`, `Coverage`, `Renew Offer Type`, `Employment Status`, `Education`, `Number of Policies`, `Monthly Premium Auto`, `Total Claim Amount`, dan `Income` berkontribusi terhadap variasi dalam CLV pelanggan.

b. Membangun model regresi yang dapat memprediksi CLV pelanggan berdasarkan variabel-variabel yang ada, sehingga perusahaan dapat mengidentifikasi pelanggan bernilai tinggi dan menargetkan strategi pemasaran serta retensi yang tepat sasaran.

c. Menggunakan hasil analisis untuk merancang strategi peningkatan CLV, dengan tujuan memperpanjang durasi hubungan pelanggan dengan perusahaan dan meningkatkan nilai yang diperoleh dari setiap pelanggan.

d. Memberikan wawasan yang dapat diandalkan kepada tim manajemen untuk membuat keputusan yang lebih baik dalam hal pengembangan produk, penentuan harga, strategi pemasaran, dan inisiatif retensi pelanggan.

## **Analytic Approach**
Analisis regresi akan digunakan untuk memprediksi nilai seumur hidup pelanggan PT. Long Life Insurance Indonesia. Tujuannya adalah untuk mengidentifikasi faktor-faktor yang paling berpengaruh terhadap nilai pelanggan sehingga perusahaan dapat menyusun strategi pemasaran yang lebih efektif. Dengan memahami faktor-faktor ini, perusahaan dapat mengalokasikan sumber daya secara optimal, memberikan penawaran yang lebih personal, serta meningkatkan retensi pelanggan, yang pada akhirnya akan berdampak positif pada profitabilitas perusahaan.

## **Metric Evaluation**
a. MAE<br>
b. MedAE<br>
c. MAPE<br>
d. R-squared<br>

## **Best Model**
Random Forest setelah proses tuning

## **Conclusion**
Pada analisa regresi ini diperoleh kesimpulan bahwa:

a. Model terbaik yang terpilih adalah Random Forest setelah proses tuning dengan parameter `model__n_estimators: 100`,`model__min_samples_split: 5`, `model__min_samples_leaf: 4`, dan `model__max_depth: None`.

b. Proses predict test menunjukkan bahwa model regresi bekerja cukup baik dan tidak ada overfitting yang signifikan. Hal ini ditunjukkan dengan:
  - Nilai metrik MAE pada training data adalah 1625,65 dan 1604,07 pada test data
  - Nilai metrik MedAE 110,57 pada training data dan 111,23 pada test data.
  - Nilai metrik MAPE 11,98% pada training data dan 12,86% pada test data.
  - Nilai metrik R-squared 67,86% pada training data dan 65,44% pada test data.

c. Pada features comparison, fitur `Number of Policies`, `Monthly Premium Auto`, `Total Claim Amount`, `Income`, dan `Education` adalah fitur-fitur yang paling berpengaruh dalam memprediksi CLV.

d. Pada model implementation dengan sample data baru, terjadi potensi peningkatan nilai CLV sebesar \$8.137,23.

e. Berdasarkan limitasi model pada visualisasi SHAP dan LIME, masih ada potensi perbaikan pada model regresi ini dengan melakukan pemilihan model ulang, pra-premrosesandata, feature engineering, atau tuning hyperparameter.

f. Model ini dapat digunakan untuk mengoptimalkan strategi akuisisi pelanggan dan program loyalitas, dengan fokus pada pelanggan yang memiliki potensi CLV tinggi.

## **Recomendation**
Berikut adalah rekomendasi selanjutnya yang dapat digunakan oleh perusahaan:

a. Peningkatan Model:
  - Eksplorasi Model Lain: Mencoba algoritma regresi lain seperti Support Vector Regression (SVR) atau Neural Networks untuk melihat apakah dapat memberikan kinerja yang lebih baik.
  - Feature Engineering Lanjutan: Menggunakan fitur-fitur baru atau transformasi fitur yang ada untuk meningkatkan kemampuan prediksi model.
  - Hyperparameter Tuning Lebih Lanjut: Melakukan pencarian hyperparameter yang lebih ekstensif untuk menemukan kombinasi optimal yang dapat meningkatkan kinerja model.

b. Pengumpulan Data:
  - Data Pelanggan yang Lebih Lengkap: Mengumpulkan data pelanggan yang lebih rinci, seperti informasi demografis, perilaku pembelian, dan interaksi pelanggan, untuk meningkatkan akurasi prediksi.

c. Implementasi dan Pemantauan:
  - Integrasi dengan Sistem CRM: Mengintegrasikan model prediksi CLV dengan sistem Customer Relationship Management (CRM) untuk memberikan wawasan yang dapat ditindaklanjuti kepada tim penjualan dan pemasaran.
  - Pemantauan Kinerja Model: Memantau kinerja model secara berkala dan melakukan pembaruan jika diperlukan untuk memastikan akurasi prediksi tetap optimal.

d. Strategi Bisnis:
  - Segmentasi Pelanggan: Menggunakan prediksi CLV untuk mengelompokkan pelanggan berdasarkan potensi nilai mereka dan menyesuaikan strategi pemasaran dan retensi yang sesuai.
  - Personalisasi Penawaran: Menawarkan produk dan layanan yang dipersonalisasi berdasarkan prediksi CLV untuk meningkatkan kepuasan pelanggan dan memaksimalkan pendapatan.
  - Program Loyalitas: Mengembangkan program loyalitas yang ditargetkan untuk mempertahankan pelanggan bernilai tinggi dan meningkatkan CLV mereka.




