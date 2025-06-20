# 📘 Chapter 11 – Training Deep Neural Networks

---

### 1. Is it OK to initialize all the weights to the same value using He initialization?

> Tidak. Walaupun He initialization bagus, **semua bobot tidak boleh sama** karena menyebabkan **semua neuron belajar hal yang sama**. Ini menghentikan manfaat pelatihan paralel pada setiap neuron.

---

### 2. Is it OK to initialize the bias terms to 0?

> Ya. Bias tidak menyebabkan simetri yang sama seperti bobot, jadi aman untuk diinisialisasi ke nol.

---

### 3. Three advantages of SELU over ReLU?

> 1. **Self-normalizing**: menjaga output tetap memiliki mean 0 dan std 1.  
> 2. **Tidak butuh BatchNorm** jika arsitektur tepat.  
> 3. **Lebih stabil** dalam jaringan dalam (deep nets) dibanding ReLU.

---

### 4. Kapan memakai SELU, leaky ReLU, ReLU, tanh, logistic, softmax?

> - **SELU**: deep nets dengan hanya Dense layer + LeCun init  
> - **Leaky ReLU**: mengatasi dead neuron  
> - **ReLU**: default cepat dan efisien  
> - **Tanh**: output range [-1,1], bisa berguna untuk encoder  
> - **Logistic**: dipakai di output untuk binary classification  
> - **Softmax**: digunakan di output untuk multiclass classification

---

### 5. Apa yang terjadi jika momentum terlalu dekat ke 1 (misal 0.99999)?

> Training menjadi **tidak stabil** dan bisa **meningkatkan osilasi**, bahkan membuat model gagal konvergen.

---

### 6. Tiga cara membuat sparse model?

> - **L1 regularization**  
> - **Weight pruning** (menghapus bobot kecil)  
> - **Training dengan sparsity constraints** (misalnya via TensorFlow Model Optimization Toolkit)

---

### 7. Apakah dropout memperlambat training? Inference?

> - Dropout bisa **memperlambat training convergence** karena introduksi noise.  
> - Tidak memperlambat inference karena dropout dimatikan saat inference.  
> - **MC Dropout**: menggunakan dropout saat inference untuk estimasi ketidakpastian → memperlambat inference jika diaktifkan.
