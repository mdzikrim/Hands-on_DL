# 📘 Chapter 4 – Training Models (Exercise Answers)

---

## 1. Which Linear Regression training algorithm can you use if you have a training set with millions of features?
> Gunakan **Stochastic Gradient Descent (SGD)** karena efisien untuk dataset sangat besar dan bersifat online learning.

---

## 2. Suppose the features have very different scales...
> Algoritma seperti **Gradient Descent** sangat sensitif terhadap skala fitur karena gradien menjadi miring atau tidak stabil. Solusinya adalah melakukan **feature scaling** (misal: StandardScaler).

---

## 3. Can Gradient Descent get stuck in a local minimum?
> Pada **Logistic Regression** dan **Linear Regression**, fungsi cost-nya **convex**, jadi **tidak memiliki local minimum**, hanya satu **global minimum**. Gradient Descent tidak akan terjebak.

---

## 4. Do all Gradient Descent algorithms lead to the same model?
> Ya, **dengan syarat learning rate cukup kecil dan dijalankan cukup lama**, semua variasi GD akan menuju minimum yang sama (karena loss convex).

---

## 5. If validation error keeps increasing...
> Kemungkinan terjadi **overfitting**. Solusinya adalah menggunakan **early stopping** atau teknik regularisasi (Ridge/Lasso), atau mengurangi jumlah epoch.

---

## 6. Is it a good idea to stop Mini-batch GD immediately when val error goes up?
> Tidak. Mini-batch GD mengalami **fluktuasi alami**, jadi lebih baik gunakan **early stopping dengan patience** (tunggu beberapa epoch sebelum berhenti).

---

## 7. Which GD algorithm converges fastest?
> **Stochastic Gradient Descent** biasanya mencapai solusi mendekati optimal lebih cepat, tapi fluktuatif. **Batch GD** lebih stabil. Semua bisa dikonvergenkan dengan learning rate schedule atau adaptive learning rate (e.g. Adam, RMSProp).

---

## 8. Polynomial Regression gap between training and validation error?
> Itu tanda **overfitting**. Solusi:
> - Kurangi derajat polinomial
> - Gunakan lebih banyak data
> - Terapkan regularisasi

---

## 9. Ridge Regression with high training & validation error?
> Ini adalah gejala **high bias** (underfitting). Solusinya adalah **mengurangi regularisasi (α)** agar model lebih fleksibel.

---

## 10. Why use:
### a. Ridge over plain Linear Regression?
> Untuk mengurangi overfitting dengan menambahkan regularisasi.

### b. Lasso over Ridge?
> Jika ingin **feature selection otomatis** karena Lasso mendorong beberapa koefisien menjadi nol.

### c. Elastic Net over Lasso?
> Kombinasi Ridge dan Lasso. Digunakan jika jumlah fitur > jumlah sampel, atau fitur berkorelasi tinggi.

---

## 11. Classify outdoor/indoor and daytime/nighttime?
> Gunakan **dua Logistic Regression classifier**, karena dua label tersebut **independen (multi-label classification)**, bukan eksklusif.




