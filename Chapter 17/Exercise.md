# 📘 Chapter 17 – Autoencoders and GANs

---

### 1. Main tasks for autoencoders?

> - **Dimensionality reduction**  
> - **Denoising**  
> - **Anomaly detection**  
> - **Pretraining classifier**  
> - **Data generation** (variational, adversarial)

---

### 2. Sedikit labeled, banyak unlabeled → bagaimana autoencoder membantu?

> - Train autoencoder di data tak berlabel  
> - Gunakan bagian encoder sebagai **feature extractor**  
> - Gunakan hasilnya untuk supervised classifier (dengan data berlabel)

---

### 3. Jika autoencoder reconstruct sempurna, apakah bagus?

> Tidak selalu.  
Jika **overcomplete** tanpa regularisasi, bisa "copy" input.  
Evaluasi kualitas dengan:  
- Validasi reconstruction error  
- **Usefulness of learned features** (e.g., downstream performance)

---

### 4. Undercomplete vs Overcomplete

- **Undercomplete**: bottleneck → learn compact representation  
   risiko terlalu kecil → underfit  
- **Overcomplete**: lebih banyak neuron dari input  
   risiko autoencoder belajar **identity mapping**

---

### 5. Tied weights di stacked autoencoder?

> Gunakan `W' = W.T` antar encoder dan decoder → mengurangi jumlah parameter  
Tujuan: regularisasi & stabilisasi training.

---

### 6. Apa itu generative model?

> Model yang dapat **menghasilkan data baru** (mirip data training)  
Contoh: VAE, GAN, Diffusion Model, PixelCNN

---

### 7. Apa itu GAN dan apa manfaatnya?

> GAN = Generator + Discriminator dalam permainan dua pemain  
Aplikasi:
- Gambar realistis  
- DeepFake  
- Super-resolution  
- Style transfer

---

### 8. Kesulitan dalam melatih GAN?

> - Mode collapse  
> - Tidak stabil  
> - Sulit balance Generator vs Discriminator  
Solusi: label smoothing, Wasserstein loss, spectral norm, gradient penalty
