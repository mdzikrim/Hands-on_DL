### 1. If you have trained five different models... is there any chance that you can combine these models to get better results?

> Ya, dengan menggunakan **ensemble learning** seperti **voting** atau **bagging**, Anda bisa mendapatkan hasil yang lebih baik daripada model individual. Hal ini terjadi karena variasi antar model bisa saling menutupi kelemahan masing-masing, asalkan kesalahan antar model tidak terlalu berkorelasi.

---

### 2. What is the difference between hard and soft voting classifiers?

> - **Hard voting**: klasifikasi berdasarkan **mayoritas label** yang diprediksi oleh semua model.  
> - **Soft voting**: klasifikasi berdasarkan **probabilitas rata-rata** dari semua model, dan memilih label dengan probabilitas tertinggi.  
> Soft voting biasanya lebih baik, **jika semua model bisa menghasilkan probabilitas yang akurat**.

---

### 3. Is it possible to speed up training of a bagging ensemble by distributing it across multiple servers?

> Ya. **Bagging, pasting, dan Random Forests** sangat cocok untuk **distribusi paralel** karena setiap model dapat dilatih secara independen.  
> Namun, **Boosting dan Stacking** sulit untuk diparalelkan karena prosesnya bersifat **sekuensial** (model berikutnya tergantung pada output model sebelumnya).

---

### 4. What is the benefit of out-of-bag (OOB) evaluation?

> OOB evaluation memungkinkan kita **mengukur performa ensemble** tanpa perlu dataset validasi tambahan.  
> Ini dilakukan dengan mengevaluasi setiap instance hanya pada model-model yang **tidak melihat instance tersebut** saat pelatihan.

---

### 5. What makes Extra-Trees more random than regular Random Forests?

> Extra-Trees menambahkan dua tingkat randomisasi:
> - Menggunakan subset fitur acak (seperti RF)
> - Memilih threshold split **secara acak**, bukan berdasarkan split terbaik  
> Efeknya adalah lebih **variatif**, lebih cepat karena tidak mencari split optimal, dan bisa **mengurangi overfitting**, meski kadang menurunkan akurasi.

---

### 6. If your AdaBoost ensemble underfits the training data, which hyperparameters should you tweak and how?

> Anda bisa:
> - **Meningkatkan jumlah estimator** (n_estimators)  
> - **Meningkatkan learning rate**, agar model baru punya dampak lebih besar  
> - Gunakan **base estimator** yang lebih kompleks (misal: pohon dengan depth lebih dalam)

---

### 7. If your Gradient Boosting ensemble overfits the training set, should you increase or decrease the learning rate?

> Anda sebaiknya **menurunkan learning rate**.  
> Learning rate besar bisa menyebabkan model terlalu cepat dan terlalu sensitif terhadap noise di data, sehingga overfit. Menurunkannya membuat proses lebih lambat dan lebih stabil.

---
