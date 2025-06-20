# 📘 Chapter 14 – Convolutional Neural Networks

---

### 1. What are the advantages of a CNN over a fully connected DNN for image classification?

> - **Parameter sharing** → lebih sedikit parameter  
> - **Sparsity of connections** → lebih hemat memori  
> - **Translation invariance**  
> - Cocok untuk **data spasial** seperti gambar

---

### 2. CNN dengan 3 layer (3×3 kernel, stride 2, padding “same”) – Berapa parameternya?

> Misal input 3 channel RGB:
- Layer 1: (3×3×3)×100 + 100 = **2,800**
- Layer 2: (3×3×100)×200 + 200 = **180,200**
- Layer 3: (3×3×200)×400 + 400 = **720,400**  
> **Total** ≈ **903,400 parameters**

RAM 32-bit: 903,400 × 4B = ~3.44 MB untuk 1 instance  
Mini-batch 50 → ~172 MB

---

### 3. Jika kehabisan GPU memory saat train CNN, solusinya?

> - Kurangi ukuran batch  
> - Gunakan model lebih kecil  
> - Gunakan **gradient checkpointing**  
> - Gunakan mixed-precision (float16)  
> - Pindahkan sebagian ke CPU

---

### 4. Kenapa pakai MaxPooling dibanding Conv dengan stride?

> - **Lebih efisien** (tidak belajar parameter)  
> - **Lebih stabil**  
> - Menyediakan downsampling dengan kontrol eksplisit

---

### 5. Kapan pakai Local Response Normalization (LRN)?

> - Digunakan dulu di **AlexNet**, berguna untuk menstimulasi kompetisi antar neuron channel yang berbeda.  
> - Sekarang lebih jarang dipakai, diganti BatchNorm.

---

### 6. Inovasi:
- **AlexNet**: ReLU, dropout, data augmentation, GPU splitting  
- **GoogLeNet**: Inception module (multi-scale filters)  
- **ResNet**: skip connection (residual block)  
- **SENet**: Squeeze & Excitation (per-channel attention)  
- **Xception**: depthwise separable convolution

---

### 7. What is a Fully Convolutional Network (FCN)?

> FCN tidak memiliki Dense layer.  
> Dense bisa diganti Conv dengan kernel 1×1. Berguna untuk deteksi objek & segmentasi.

---

### 8. Apa kesulitan teknis utama dalam semantic segmentation?

> - **Konsistensi resolusi spasial**  
> - **Boundary precision**  
> - **Class imbalance**  
> - Model harus prediksi **label per pixel**
