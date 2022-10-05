# Laporan Proyek Machine Learning


Laporan Proyek Machine Learning - Zulfikar Zahir H
## Domain Proyek

Penyakit jantung adalah kondisi dimana jantung mengalami gangguan yang tidak normal. Menurut Centers for Disease Control and Prevention penyakit jantung menjadi salah satu penyebab kematian bagi Sebagian besar ras di Amerika Serikat. Faktor penyebab sakit antara lain merokok, minum alcohol, usia, stroke, penyakit asma dan lainnya. Sekitar setengah penduduk Amerika memilik setidaknya 1 dari 3 faktor dalam risiko penyakit jantung. Mendeteksi dan mencegah dari faktor yang ada tentunya akan meminimalisir terjadinya kejadian yang tidak diinginkan. Perkembangan komputasi memungkinkan untuk mendeteksi pola yang ada untuk mendeteksi sejak dini keadaan pasien.
Masalah ini cukup penting mengingat hampir setengah masyarakat di Amerika memiliki faktor penyakir jantung. Dengan melakukan konsultasi sejak dini ke dokter akan sangat membantu pasien dalam melihat kondisi tubuh, namun tidak semua orang dapat ke dokter untuk konsultasi. Masalah tersebut dapat diselesaikan dengan melihat sendiri kondisi tubuh lalu mencocokan dengan data yang telah tersedia. Komputasi machine learning akan mengubah data yang tersedia menjadi sebuah kesimpulan yang bernilai ya dan tidak terhadap pasien yang melakukan cek mandiri, dengan begitu semua orang dapat mendeteksi penyakit jantung sejak dini.

Riset faktor: 
[Hipertensi Penyakit Jantung dan Pembuluh Darah](http://p2ptm.kemkes.go.id/infographic-p2ptm/hipertensi-penyakit-jantung-dan-pembuluh-darah/faktor-pemicu-gejala-serangan-jantung)
[JAnalisa Faktor Penyakit Jantung](https://jurnal.unimus.ac.id/index.php/kedokteran/article/download/1341/1396)
Refrensi data: [www.cdc.gov](https://www.cdc.gov/brfss/annual_data/annual_2020.html) 

## Business Understanding

### Problem Statements

- Penyakit jantung menjadi masalah yang besar bagi masyarakat.
- Banyak masyarakat yang memiliki faktor penyakit jantung.
- Tidak semua orang dapat konsultasi ke dokter.

### Goals
- Masyarakat dapat mengerti betapa pentingnya penyakit jantung.
- Masyarakat dapat mencegah faktor terjadinya penyakit jantung.
- Dengan adanya model dari data, konsultasi bisa dilakukan secara mandiri.


## Data Understanding
Data yang digunakan pada project kali ini adalah data Personal Key Indicators of Heart Disease yang dikutip oleh Centers for Disease Control and Prevention melalui survey terhadap 400 ribu orang dewasa terhadap kesehatannya. 
Data: [Kaggle Personal Key Indicators of Heart Disease  ](https://www.kaggle.com/datasets/kamilpytlak/personal-key-indicators-of-heart-disease/metadata).

### Variabel-variabel pada Personal Key Indicators of Heart Disease adalah sebagai beriku :
- Heart Disease : laporan hasil responden.
- BMI : Body Mass Index .
- Smoking : apakah responden merokok setidaknya 100 batang di hidupnya.
- AlcoholDrinking : apakah responden minum alcohol.
- Stroke : apakah responden pernah atau punya stroke.
- PhysicalHealth : berapa hari terakhir Kesehatan fisik responden terganggu (0-30).
- MentalHealth : : berapa hari terakhir Kesehatan mental responden terganggu (0-30).
- DiffWalking : apakah responden memiliki kesulitan berjalan.
- Sex : jenis kelamin responden.
- AgeCategory : kategori umur responden.
- Race : ras dari responden.
- Diabetic : apakah responden memiliki diabetes.
- PhysicalActivity : apakah responden memiliki aktivitas fisik selain aktivitas regular dalam 30 hari terakhir.
- GenHealth : keadaan gen Kesehatan responden.
- SleepTime : waktu tidur responden.
- Asthma : apakah responden memiliki asma.
- KidneyDisease : apakah responden memiliki penyakit ginjal.
- SkinCancer : apakah responden memiliki kanker kulit.
**Rubrik/Kriteria Tambahan (Opsional)**:
- Melakukan beberapa tahapan yang diperlukan untuk memahami data, contohnya teknik visualisasi data atau exploratory data analysis.

## Data Preparation
Dalam Machine Learning komputer hanya menerima inputan berupa angka, dengan data yang diubah ke angka maka komputer dapat melakukn proses terhadap data itu. Dataset Heart Disease ini belum seluruhnya data angka, masih ada data jenis string. Selanjutnya masing masing kolom akan dikonversi menjadi angka di proses Data Preparation.
Teknik yang kita gunakan sebagai berikut :
- Binary Encoding, teknik ini mengubah dua nilai unik string menjadi 0 atau 1. Kolom yang diproses memiliki nilai unik 2 jenis berupa string, kolom yang digunakan adalah HeartDisease, Sex , Smoking, AlcoholDrinking, Stroke, DiffWalking,PhysicalActivity, Asthma, KidneyDisease, SkinCancer.
- One-Hot Encoding, teknik ini akan membuat kolom baru dari kolom kategorikal dimana masing masing kategori yang unik akan menjadi kolom baru. Kolom yang digunakan dalam proses ini adalah GenHeath dan Race.
- Mengganti kolom AgeCategory yang bersifat rentang data menjadi numerik.
- Data yang bertipe float diganti menjadi int64.
Ketika data sudah menjadi numerik dan tidak ada data yang kosong maka selanjutnya membagi data menjadi data training dan data test. Data training akan dimasukan ke model yang nantinya model akan di uji di data test. 

## Modeling
Project kali ini akan menggunakan 3 model, yaitu Logistic regression, Random Forest Classifier, Gradient Boost Classifier. Dengan menggunakan model yang berbeda maka akan diambil akurasi yang terbaik dari model tersebut. Masing masing model akan dijabarkan sebagai berikut:
- Logistic Regression
Model ini digunakan untuk prediksi probabilitas suatu periwtiwa dengan mencocokan data yang tersedia pada fungsi kurva logistik. Regresi ini akan mendeskripsikan variabel dependen dan independent pada skala atau interval.
Model ini tentunya memiliki kekurangan dan kelebihan dalam penerapan modelling. Kelebihan yang dimiliki model ini ialah model ini tidak mengharuskan variabel bebas dalam bentuk interval dan model ini tidak butuh batasan dari variabel bebas. Sementara kekurangan dari model ini ialah tidak bisa menyesuaikan data apabila ada missing value.
 
- Random Forest Classifier
Model RFC merupakan pengenmabangan dari CART dengan menerapkan metode bootstrap aggregating dan random feature selection. Random forest merupakan kumpulan dari banyak tree, dimana setiap tree bergantung pada nilai pixel lalu diambil secara acak dan independen.
Model ini memliki kekurangan dan kelebihan dalam penerapannya. Salah satu kelebihannya ialah dapat  menatasi noice dan missing value lalu dapat mengatur data yang sangat besar. Sementara kekurangannya ialah hyperparameter yang epat untuk suatu data
- Gradient Boost Classifier
GBC adalah algoritma ML yang mengguanakn metode ensemble dengan cara decision tree untuk mendapatkan output. GBC termasuk ensemble learning dimana mesin akan menggunakan banyak model machine learning sederhana untuk mendapatkan hasil terbaik. Cara ini memiliki kekurangan yaitu membutuhkan proses yang lama untuk mengahsilkan output dan tidak cocok untuk aplikasi real time. Kelebihan yang dimiliki adalah akurasi yang dihasilkan besar, dapat menghubungkan kompleks linier dan non-linier. 

## Evaluation
Confusion Matrix adalah perhitungan performa model untuk masalah klasifikasi ML dimana output dapat dua kelas atau lebih. Confusion Matrix merupakan tabel 2x2 dengan kombinasi berbeda dari nilai prediksi dan nilai aktual. Tabel pada Confusion Matrix memiliki isi dengan istilah True Positif, True Negatif, False Positif, dan False Negatif. Gambaran Confusion Matrix sebagai berikut :
- True Positive (TP) : Model memprediksi benar dan itu benar. Contohnya, seorang pasien dinyatakan benar sakit jantung dan pasien tersebut memang sedang sakit.

- True Negative (TN):Model memprediksi salah dan itu  benar. Contohnya, seorang pasien dinyatakan bebas sakit jantung dan pasien tersebut memang sehat.

- False Positive (FP) :  Model memprediksi benar dan itu salah . Contohnya, seorang pasien dinyatakan benar sakit jantung dan pasien tersebut memang sedang sehat.

- False Negative (FN): Model memprediksi salah dan itu salah . Contohnya, seorang pasien dinyatakan benar sakit jantung padahal pasien tersebut sedang sakit.

Dalam confusion matrix dapat diambil nilai  bahwa:
- Accuracy : melihat seberapa akurat nilai kita dalam klasifikasi.
Rumus Accuracy = (TP+TN) / (TP+FP+FN+TN)
- Precission : melihat pembagian antara True Positive yang diklasidikasi benar dengan jumlah total positif.
Rumus Precision = (TP) / (TP + FP)
- Recall : melihat keberhasilan model dalam menemukankembali informasi.
Rumus Recall = TP / (TP + FN)
- F - 1 Score : melihat perbanringan rata rata precision dan recall.
Rumus = (2 * Recall * Precision) / (Recall + Precision)
