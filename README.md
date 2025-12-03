🎓 Prediksi Kelulusan Mahasiswa Menggunakan Support Vector Machine (SVM)

📌 Deskripsi Proyek
Proyek ini bertujuan untuk memprediksi status kelulusan mahasiswa berdasarkan atribut seperti IPK, jumlah SKS, lama studi, dan lainnya menggunakan algoritma Support Vector Machine (SVM). Proyek ini dikembangkan dalam rangka memenuhi tugas mata kuliah Machine Learning.

📊 Dataset
Dataset yang digunakan adalah datakelulusanmahasiswa.csv dengan atribut sebagai berikut:
- IPK (fitur numerik)
- Total SKS (fitur numerik)
- Umur (fitur numerik)
- Status Kehadiran (fitur kategorikal)
- Lama Studi (fitur numerik)
- Keaktifan Organisasi (fitur kategorikal)

Label: Lulus / Belum Lulus
Dataset dapat diakses di folder /data dalam repository ini.

🛠️ Langkah Pengerjaan
Proyek ini dikerjakan dalam 100 menit dengan langkah-langkah sebagai berikut:

1. Setup & Loading Dataset
- Import library: pandas, numpy, sklearn
- Load dataset menggunakan pd.read_csv()
- Tampilkan 5 baris pertama
- Cek missing values

2. Exploratory Data Analysis (EDA)
Statistik deskriptif
Visualisasi:
- Histogram IPK
- Countplot status kelulusan
- Analisis perbandingan distribusi IPK antara lulus dan tidak lulus

3. Preprocessing Data
- Penanganan missing values
- Encoding fitur kategorikal
- Feature scaling dengan StandardScaler
- Train-test split dengan beberapa rasio (60:40, 75:25, 80:20, 90:10)

4. Training Model SVM
Model yang dilatih:

- SVM Linear Kernel
- SVM RBF Kernel
- Hyperparameter tuning:
- C = {0.1, 1, 10}
- gamma = {'scale', 0.1, 1}
- Evaluasi dengan:
- Confusion Matrix
- Classification Report
- Accuracy, Precision, Recall, F1-Score

5. Interpretasi Model
- Identifikasi fitur paling berpengaruh
- Analisis hubungan IPK rendah dengan kecenderungan tidak lulus
- Kesimpulan prediksi model

6. Deployment Sederhana
Fungsi prediksi:
    def predict_status(ipk, sks, umur, lamastudi, ...):
    # kode prediksi menggunakan model SVM yang sudah dilatih

📈 Hasil Evaluasi Model
Berikut adalah hasil evaluasi dari dua model SVM yang dilatih:

🔹 SVM Linear Kernel

- Accuracy: 86.84%
- Precision:
- TEPAT: 0.85
- TERLAMBAT: 0.90

Recall:
- TEPAT: 0.93
- TERLAMBAT: 0.79

F1-Score:
- TEPAT: 0.89
- TERLAMBAT: 0.84

Confusion Matrix:
 [[40  3]
 [ 7 26]]
 
 True Positives (TERLAMBAT): 26
 True Negatives (TEPAT): 40
 False Positives: 3
 False Negatives: 7

🔹 SVM RBF Kernel
- Accuracy: 56.58%

Precision:
- TEPAT: 0.57
- TERLAMBAT: 0.00 (tidak ada prediksi untuk kelas ini)

Recall:
- TEPAT: 1.00
- TERLAMBAT: 0.00

F1-Score:
- TEPAT: 0.72
- TERLAMBAT: 0.00

Confusion Matrix:
 [[43  0]
 [33  0]]
 Model RBF hanya memprediksi semua sebagai kelas TEPAT
Tidak ada prediksi untuk kelas TERLAMBAT

Analisis Perbandingan Model SVM
SVM Linear unggul mutlak dengan akurasi 86.84%, precision 90%, recall 79%, dan F1-score 0.84 untuk kelas TERLAMBAT. Model ini efektif mendeteksi kedua kelas dengan hanya 10 kesalahan dari 76 sampel.
SVM RBF gagal total meski akurasi 56.58%, karena tidak pernah memprediksi kelas TERLAMBAT. Precision dan F1-score 0% menunjukkan model hanya memprediksi kelas mayoritas (TEPAT) - strategi "malas" yang tidak berguna.
Penyebab perbedaan ekstrem:
Data memiliki pola linear kuat antara IPK/IPS dengan status kelulusan
Kernel RBF dengan C=0.1 terlalu sederhana untuk dataset ini
SVM Linear lebih cocok menangkap hubungan sederhana dalam data akademik

Kesimpulan:
SVM Linear jauh lebih baik karena:
Akurasi 30% lebih tinggi
Dapat mendeteksi mahasiswa berisiko terlambat (fungsi utama sistem)
Berguna untuk aplikasi nyata bimbingan akademik
SVM RBF berbahaya jika diimplementasikan karena memberikan prediksi menyesatkan

✅ Kesimpulan
Model SVM Linear memberikan performa yang jauh lebih baik dengan akurasi 86.84% dan mampu membedakan kedua kelas (TEPAT dan TERLAMBAT) dengan baik. Sementara itu, model SVM RBF hanya memprediksi satu kelas saja, sehingga tidak cocok untuk dataset ini. Dataset ini cenderung linearly separable, sehingga kernel linear bekerja lebih optimal.

🚀 Cara Menjalankan Notebook
Clone repository ini:
git clone https://github.com/c-rich99/prediksi-kelulusan-svm.git

- Buka file SVM_kelulusan.ipynb di Google Colab atau Jupyter Notebook.
- Pastikan dataset berada di path yang sesuai (/data/datakelulusanmahasiswa.csv).
- Jalankan semua sel (Runtime → Run All).

👤 Identitas Mahasiswa
Nama: Citra Mutia 
NIM: 2457201002359
Kelas: 3A SI
Mata Kuliah: Machine Learning
Institusi: UNDA

📎 Screenshot Hasil
  https://drive.google.com/drive/folders/1VgMtfOTEfRmgX2vVs8bmtUC_yA6MkVBG?usp=sharing

🔗 Link GitHub

