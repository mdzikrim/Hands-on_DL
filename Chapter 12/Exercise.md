# 📘 Chapter 12 – Custom Models and Training with TensorFlow

---

### 1. How would you describe TensorFlow in a short sentence?

> TensorFlow adalah pustaka machine learning end-to-end untuk membangun, melatih, dan menyebarkan model ML, baik statis maupun dinamis.

---

### 2. Is TensorFlow a drop-in replacement for NumPy?

> Tidak. TensorFlow mendukung tensor seperti NumPy, tetapi ditujukan untuk graph-based execution dan GPU acceleration.

---

### 3. Do you get the same result with tf.range(10) and tf.constant(np.arange(10))?

> Hasil nilainya sama, tapi tipe data dan konteks eksekusi bisa berbeda. `tf.range()` native untuk graph mode.

---

### 4. Six other TensorFlow data structures?

> - RaggedTensor  
> - SparseTensor  
> - TensorArray  
> - Dataset  
> - Variable  
> - Queue / Iterator

---

### 5. When would you use a custom loss class?

> - Function: untuk sederhana.  
> - Subclass: jika Anda ingin menyimpan state atau logika kompleks.

---

### 6. When to subclass custom metric?

> Jika ingin menyimpan state seperti `mean`, `count`, atau ingin logika `.update_state()` khusus.

---

### 7. Custom layer vs custom model?

> - Layer: reuse-able block seperti Dense atau Dropout  
> - Model: terdiri dari banyak layer, memiliki `.fit()`, `.evaluate()`

---

### 8. Kapan pakai custom training loop?

> Saat Anda perlu kontrol penuh atas training, seperti reinforcement learning, GAN, atau multi-loss.

---

### 9. Apakah custom component bisa arbitrary Python?

> Tidak. Agar bisa dipakai di graph mode, harus bisa dikonversi ke `@tf.function`.

---

### 10. Aturan agar fungsi bisa dikonversi ke TF Function?

> - Gunakan operasi TensorFlow  
> - Hindari kontrol alur Python murni (pakai tf.cond, tf.while_loop)

---

### 11. Kapan perlu model dinamis?

> Jika model berubah tiap input (misalnya RNN dengan input bervariasi). Buat dengan subclassing dan tanpa menghias `@tf.function`.

