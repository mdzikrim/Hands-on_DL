# 📘 Chapter 9 – Unsupervised Learning (Clustering & Gaussian Mixtures)

---

### 1. How would you define clustering? Can you name a few clustering algorithms?

> Clustering adalah teknik unsupervised learning untuk mengelompokkan data ke dalam grup (cluster) berdasarkan kemiripan.  
> Contoh algoritma: **K-Means**, **DBSCAN**, **Mean Shift**, **Agglomerative Clustering**, **Gaussian Mixture Model (GMM)**.

---

### 2. What are some of the main applications of clustering algorithms?

> - Segmentasi pelanggan
> - Kompresi gambar
> - Anomaly detection
> - Preprocessing atau feature engineering
> - Pemrosesan data spasial/geografis

---

### 3. Describe two techniques to select the right number of clusters when using K-Means.

> - **Elbow method**: plot inertia vs jumlah cluster dan cari “tekukan” kurva.
> - **Silhouette score**: skor antara -1 sampai 1 yang mengukur seberapa baik data cocok dengan cluster-nya.

---

### 4. What is label propagation? Why would you implement it, and how?

> Label propagation adalah metode semi-supervised learning di mana sebagian data diberi label, dan label disebarkan ke tetangga terdekat berdasarkan kemiripan.  
> Berguna saat hanya sebagian kecil data yang memiliki label.

---

### 5. Can you name two clustering algorithms that can scale to large datasets? And two that look for regions of high density?

> - Skalabilitas tinggi: **MiniBatchKMeans**, **Birch**
> - Deteksi daerah padat: **DBSCAN**, **Mean Shift**

---

### 6. Can you think of a use case where active learning would be useful? How would you implement it?

> Deteksi penipuan atau diagnosa medis dengan data tak berlabel.  
> Implementasi: model memilih instance dengan ketidakpastian tinggi, lalu meminta anotasi dari manusia.

---

### 7. What is the difference between anomaly detection and novelty detection?

> - **Anomaly detection**: mengenali outlier di **data training dan test**
> - **Novelty detection**: model dilatih hanya pada data normal dan mendeteksi data baru yang “aneh”

---

### 8. What is a Gaussian mixture? What tasks can you use it for?

> Gaussian mixture model (GMM) adalah model probabilistik yang memodelkan distribusi data sebagai campuran beberapa distribusi Gaussian.  
> Digunakan untuk **clustering**, **generative modeling**, dan **density estimation**.

---

### 9. Can you name two techniques to find the right number of clusters when using a Gaussian mixture model?

> - **Bayesian Information Criterion (BIC)**  
> - **Akaike Information Criterion (AIC)**
