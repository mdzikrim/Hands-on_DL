# 📘 Chapter 13 – Loading and Preprocessing Data

---

### 1. Why would you want to use the Data API?

> Agar data pipeline efisien, dapat digunakan dengan GPU/TPU secara asinkron, mendukung batching, prefetching, caching, dan transformasi custom.

---

### 2. What are the benefits of splitting a large dataset into multiple files?

> - Memungkinkan **parallelism** dalam loading  
> - Lebih fleksibel saat **streaming**, **resumable training**, dan **sharding untuk distribusi**

---

### 3. How do you know the input pipeline is a bottleneck?

> Cek GPU utilization dan lihat apakah GPU **idle**.  
> Gunakan **TensorBoard profiler** → jika step time tinggi saat GPU idle, berarti bottleneck di input.

---

### 4. Can you save any binary data to TFRecord?

> Ya, selama dikonversi ke **serialized proto buffer** (misal: `tf.io.serialize_tensor()`).

---

### 5. Why bother using Example proto format?

> Standar TF → lebih **kompatibel dengan tool ekosistem TensorFlow**, seperti TensorBoard dan TFServing.

---

### 6. Kapan perlu aktifkan kompresi saat memakai TFRecord?

> Saat storage terbatas, atau I/O bandwidth lambat.  
> Tidak dilakukan default karena bisa menambah **overhead CPU** jika tidak dibutuhkan.

---

### 7. Proses preprocessing bisa dilakukan di?

> - Saat menulis file (cepat saat training, tidak fleksibel)  
> - Dalam `tf.data` pipeline (lebih fleksibel)  
> - Di model (memudahkan **serving**, tapi beban komputasi naik)

---

### 8. Teknik encoding untuk kategori & teks?

> Kategori: one-hot, integer encoding, embedding  
> Teks: tokenization, n-grams, hashing, TextVectorization
