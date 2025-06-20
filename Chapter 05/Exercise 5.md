# 📘 Chapter 5 – Support Vector Machines (Exercise Answers)

---

## 1. What is the fundamental idea behind Support Vector Machines?
> SVM mencoba mencari hyperplane terbaik yang **memaksimalkan margin** antara kelas-kelas. Hanya support vectors yang memengaruhi posisi hyperplane.

---

## 2. What is a support vector?
> Support vector adalah **data point yang berada paling dekat dengan hyperplane**. Mereka adalah titik-titik yang "menopang" margin dan menentukan batas klasifikasi.

---

## 3. Why is it important to scale the inputs when using SVMs?
> Karena SVM sensitif terhadap **skala fitur**. Jika fitur tidak diskalakan, jarak Euclidean tidak akan representatif, menyebabkan model bias terhadap fitur berskala besar.

---

## 4. Can an SVM classifier output a confidence score or probability?
> - Ya, bisa memberikan **confidence score** dengan metode `.decision_function()`.
> - Untuk **probabilitas**, gunakan `SVC(probability=True)` yang akan menambahkan proses **Platt Scaling** setelah training.

---

## 5. Should you use the primal or the dual form to train on a dataset with millions of instances?
> Gunakan **primal form**. Dual lebih efisien saat **jumlah fitur > jumlah sample**, tetapi primal lebih baik saat dataset sangat besar (banyak instance).

---

## 6. If RBF kernel underfits, should you increase or decrease γ and C?
> - **Tingkatkan gamma (γ)** agar kurva keputusan menjadi lebih kompleks.
> - **Tingkatkan C** agar model menghukum kesalahan lebih keras (mengurangi regularisasi).

---

## 7. How should you set the QP parameters (H, f, A, b) for soft-margin linear SVM?
> Dalam optimasi kuadratik (QP), setup-nya:
> - **H**: matriks Gram dari produk titik fitur (Xᵢ·Xⱼ)
> - **f**: vektor dengan semua elemen = -1
> - **A, b**: constraints: yᵢ(w·xᵢ + b) ≥ 1 - ξᵢ, dan ξᵢ ≥ 0
> - Biasanya disusun sebagai masalah minimisasi (1/2)‖w‖² + C∑ξᵢ




