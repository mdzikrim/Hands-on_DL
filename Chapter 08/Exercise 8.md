### 1. What are the main motivations for reducing a dataset’s dimensionality? What are the main drawbacks?

> Motivasi:
> - Mengurangi overfitting (lebih sedikit fitur → lebih sederhana)
> - Meningkatkan kecepatan dan efisiensi komputasi
> - Memvisualisasikan data (2D/3D)
> - Memudahkan interpretasi

> Kekurangan:
> - Kehilangan informasi (informasi dalam dimensi yang dibuang bisa relevan)
> - Sulit untuk ditafsirkan secara langsung (terutama PCA/KPCA)

---

### 2. What is the curse of dimensionality?

> Ketika jumlah dimensi meningkat, volume ruang bertambah secara eksponensial → data menjadi jarang dan sulit dipelajari.  
> Akibatnya:
> - Model membutuhkan lebih banyak data
> - Jarak antar titik menjadi kurang bermakna (semua tampak sama jauhnya)

---

### 3. Once a dataset’s dimensionality has been reduced, is it possible to reverse the operation? If so, how?

> Umumnya **tidak sepenuhnya bisa dibalikkan**, karena informasi dari dimensi yang dibuang hilang.  
> Namun, **beberapa metode** (seperti PCA) dapat **membuat aproksimasi inversi** dari transformasi untuk mengembalikan data ke bentuk aslinya secara parsial.

---

### 4. Can PCA be used to reduce the dimensionality of a highly nonlinear dataset?

> Tidak secara langsung. PCA hanya efektif untuk **struktur linier**.  
> Untuk non-linier, gunakan **Kernel PCA**, t-SNE, LLE, atau metode lain.

---

### 5. Suppose you perform PCA on a 1,000-dimensional dataset, setting the explained variance ratio to 95%. How many dimensions will the resulting dataset have?

> Jawabannya tergantung pada data.  
> Namun, biasanya **diperoleh sekitar 100–300 dimensi**, cukup untuk menjelaskan 95% variansi.  
> Jumlah pastinya akan ditentukan secara otomatis oleh PCA saat digunakan dengan `n_components=0.95`.

---

### 6. In what cases would you use vanilla PCA, Incremental PCA, Randomized PCA, or Kernel PCA?

> - **PCA (vanilla)**: dataset kecil, linier, cocok untuk penggunaan umum  
> - **Incremental PCA**: dataset besar/tidak muat di RAM, proses bertahap  
> - **Randomized PCA**: percepatan komputasi dengan aproksimasi, hasil mendekati PCA asli  
> - **Kernel PCA**: jika dataset bersifat non-linier (misal spiral)

---

### 7. How can you evaluate the performance of a dimensionality reduction algorithm on your dataset?

> Beberapa cara:
> - **Visualisasi**: scatterplot hasil 2D, apakah cluster terlihat jelas
> - **Preservasi informasi**: nilai explained variance ratio (PCA)
> - **Downstream performance**: apakah akurasi model meningkat/menurun setelah reduksi dimensi

---

### 8. Does it make any sense to chain two different dimensionality reduction algorithms?

> Ya, contoh:
> - **Gunakan PCA untuk mereduksi noise terlebih dahulu**, lalu **t-SNE untuk visualisasi akhir**
> - Kombinasi teknik kadang menghasilkan performa lebih baik (misal PCA → LLE)
