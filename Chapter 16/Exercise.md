# 📘 Chapter 16 – Attention and Transformers

---

### 1. Pros & Cons: Stateful vs Stateless RNN

**Stateful RNN**:
- Pro: Bisa melanjutkan konteks dari batch sebelumnya
- Con: Sulit dikontrol (perlu reset), batch harus sinkron

**Stateless RNN**:
- Pro: Simpel dan umum digunakan
- Con: Tidak mempertahankan konteks antar batch

---

### 2. Kenapa pakai Encoder–Decoder RNN untuk terjemahan?

> Untuk **mengatasi perbedaan panjang** antara kalimat input dan output.  
Encoder menyimpan konteks ke state, decoder menghasilkan token berdasarkan state dan output sebelumnya.

---

### 3. Bagaimana menangani panjang variabel input/output?

- **Input**: gunakan `masking`, `padding`, atau `PackedSequence`  
- **Output**: pakai decoder RNN dengan `teacher forcing` atau beam search untuk prediksi token per token

---

### 4. Apa itu Beam Search?

> Algoritma decoding untuk **menjaga k-best sequence** dengan probabilitas tertinggi, bukan greedy one-step.  
Digunakan untuk text generation, translation.

---

### 5. Apa itu Attention?

> Attention memungkinkan model **fokus hanya pada bagian input tertentu**, alih-alih seluruh sequence.  
Meningkatkan akurasi, interpretabilitas, dan mengatasi long-term dependency.

---

### 6. Komponen terpenting Transformer?

> **Multi-head self-attention layer**.  
Mengizinkan model untuk memperhatikan bagian berbeda dari input secara paralel.

---

### 7. Kapan pakai Sampled Softmax?

> Saat vocab besar (misal >50.000), **full softmax mahal**.  
Sampled softmax hanya menghitung subset dari vocab → hemat memori & lebih cepat saat training.
