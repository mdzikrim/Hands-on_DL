# 📘 Machine Learning Chapter 1

---

## 📚 Exercises dan Jawaban

### 1. How would you define Machine Learning?
> Machine Learning adalah ilmu membuat sistem komputer agar dapat belajar dari data dan meningkatkan performa pada suatu tugas tertentu berdasarkan pengalaman.

---

### 2. Can you name four types of problems where it shines?
> Machine Learning sangat cocok digunakan untuk:
> - Masalah kompleks yang sulit dipecahkan dengan aturan eksplisit
> - Situasi di mana aturan manual terlalu banyak atau rumit
> - Sistem yang perlu beradaptasi dengan lingkungan yang berubah
> - Menemukan pola tersembunyi dalam data besar (data mining)

---

### 3. What is a labeled training set?
> Dataset pelatihan yang setiap baris datanya sudah dilabeli dengan output yang benar. Dataset ini digunakan untuk supervised learning.

---

### 4. What are the two most common supervised tasks?
> - **Classification (Klasifikasi)**: memprediksi kategori (contoh: spam atau bukan)
> - **Regression (Regresi)**: memprediksi nilai kontinu (contoh: harga rumah)

---

### 5. Can you name four common unsupervised tasks?
> - **Clustering**: mengelompokkan data (contoh: segmentasi pelanggan)
> - **Dimensionality Reduction**: mengurangi jumlah fitur (contoh: PCA)
> - **Anomaly Detection**: mendeteksi data yang menyimpang (contoh: deteksi fraud)
> - **Association Rule Learning**: menemukan hubungan antar item (contoh: market basket analysis)

---

### 6. What type of ML algorithm for a robot walking on unknown terrain?
> Menggunakan **Reinforcement Learning**, di mana agen belajar mengambil tindakan berdasarkan reward dan penalty dari lingkungan.

---

### 7. What algorithm would you use to segment your customers?
> Menggunakan **Clustering**, seperti algoritma K-Means untuk mengelompokkan pelanggan ke dalam beberapa segmen.

---

### 8. Is spam detection supervised or unsupervised?
> **Supervised learning**, karena kita memiliki data email yang sudah diberi label spam atau bukan.

---

### 9. What is an online learning system?
> Sistem yang belajar secara bertahap dari data yang masuk secara kontinu, cocok untuk sistem real-time.

---

### 10. What is out-of-core learning?
> Teknik pelatihan model pada dataset yang terlalu besar untuk dimuat sekaligus ke dalam memori, dengan cara memproses sebagian data dalam batch kecil.

---

### 11. What algorithm uses similarity for predictions?
> **Instance-Based Learning**, seperti algoritma **K-Nearest Neighbors (KNN)**, yang memprediksi berdasarkan kemiripan dengan data sebelumnya.

---

### 12. What is the difference between a model parameter and a learning algorithm’s hyperparameter?
> - **Parameter model** adalah nilai internal yang dipelajari oleh model selama proses training (contoh: koefisien dalam regresi linear).
> - **Hyperparameter** adalah parameter yang ditentukan sebelum proses training dan mengatur cara kerja algoritma (contoh: jumlah pohon dalam random forest, atau nilai C dalam SVM).

---

### 13. What do model-based learning algorithms search for? What is the most common strategy they use to succeed? How do they make predictions?
> Algoritma pembelajaran berbasis model berusaha menemukan parameter model terbaik untuk meminimalkan fungsi kesalahan (loss function).  
> Strategi yang umum digunakan adalah **optimasi fungsi biaya** (seperti menggunakan gradient descent).  
> Setelah model dilatih, prediksi dilakukan dengan memberikan data input ke fungsi model tersebut.

---

### 14. Can you name four of the main challenges in Machine Learning?
> - **Data tidak mencukupi** (insufficient data)
> - **Data tidak representatif** (sampling bias)
> - **Data berkualitas buruk** (missing values, outliers, noise)
> - **Overfitting** dan **Underfitting** model

---

### 15. If your model performs great on the training data but generalizes poorly to new instances, what is happening? Can you name three possible solutions?
> Ini adalah kasus **overfitting**: model terlalu cocok dengan data training.  
> Tiga solusi yang dapat dilakukan:
> - Gunakan model yang lebih sederhana atau regularisasi model
> - Tambah ukuran dataset (lebih banyak data training)
> - Bersihkan data dari noise atau fitur yang tidak relevan

---

### 16. What is a test set, and why would you want to use it?
> Test set adalah data yang digunakan untuk **mengukur performa akhir model** setelah training selesai.  
> Tujuannya adalah untuk mengevaluasi seberapa baik model mampu menggeneralisasi ke data baru yang belum pernah dilihat.

---

### 17. What is the purpose of a validation set?
> Validation set digunakan untuk membandingkan performa berbagai model atau konfigurasi hyperparameter.  
> Ini memungkinkan kita untuk memilih model terbaik **tanpa menyentuh test set**.

---

### 18. What is the train-dev set, when do you need it, and how do you use it?
> Train-dev set adalah subset dari data training yang digunakan untuk mengecek apakah model **overfitting pada data training** atau **gagal generalisasi** ke data yang mirip.  
> Digunakan ketika validation set dan test set memiliki karakteristik berbeda dari data training.

---

### 19. What can go wrong if you tune hyperparameters using the test set?
> Jika test set digunakan dalam tuning hyperparameter, maka model akan “belajar” dari test set, dan skor akhirnya menjadi bias.  
> Artinya, **estimasi performa pada test set menjadi terlalu optimis** dan tidak mencerminkan performa sebenarnya di dunia nyata.

---

