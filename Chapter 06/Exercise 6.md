# 📘 Chapter 6 – Decision Trees (Exercises 1–6)

---

## 1. What is the approximate depth of a Decision Tree trained (without restrictions) on a training set with one million instances?
> Kedalaman kira-kira sekitar **log₂(1.000.000) ≈ 20**, karena pohon akan terus membagi data hingga tiap instance menjadi leaf tersendiri dalam kasus tanpa batasan.

---

## 2. Is a node’s Gini impurity generally lower or greater than its parent’s? Is it *generally* lower/greater, or *always* lower/greater?
> Gini impurity pada anak node **umumnya (generally) lebih rendah** daripada parent-nya, karena pembagian (split) bertujuan untuk meminimalkan impurity. Namun tidak **selalu** lebih rendah, tergantung pada bagaimana data terbagi.

---

## 3. If a Decision Tree is overfitting the training set, is it a good idea to try decreasing `max_depth`?
> Ya, mengurangi `max_depth` adalah salah satu cara untuk **mengurangi overfitting**, karena membatasi kompleksitas pohon.

---

## 4. If a Decision Tree is underfitting the training set, is it a good idea to try scaling the input features?
> Tidak. **Scaling tidak memberikan pengaruh signifikan terhadap Decision Tree**, karena pembagian fitur didasarkan pada threshold absolut, bukan jarak atau ukuran relatif antar fitur.

---

## 5. If it takes one hour to train a Decision Tree on a training set containing 1 million instances, roughly how much time will it take to train another Decision Tree on a training set containing 10 million instances?
> Kompleksitas training tree adalah **O(n × log n)**. Jika 1 juta butuh 1 jam, maka 10 juta diperkirakan butuh:
> `10 × log(10 juta) / log(1 juta) ≈ 10 × 1.1 = 11 jam` (kurang lebih).

---

## 6. If your training set contains 100,000 instances, will setting `presort=True` speed up training?
> Tidak. `presort=True` hanya bermanfaat untuk dataset **sangat kecil**. Untuk 100.000 data, efeknya bisa malah **memperlambat training**. Juga, `presort` kini telah **deprecated** di versi terbaru scikit-learn.

---
