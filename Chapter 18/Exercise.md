# 📘 Chapter 18 – Reinforcement Learning

---

### 1. Apa itu Reinforcement Learning?

> RL adalah metode di mana **agent belajar dari interaksi dengan lingkungan** melalui trial-and-error.  
Berbeda dari:
- **Supervised**: ada label eksplisit  
- **Unsupervised**: cari struktur tersembunyi  
- **RL**: belajar dari reward/denda

---

### 2. 3 Aplikasi RL lain?

- **Game strategi (Catur, Go)**  
  - Env: papan, Agent: player, Reward: menang  
- **Warehouse robot**  
  - Env: gudang, Agent: robot, Action: pick/place, Reward: sukses antar  
- **Autonomous vehicle control**  
  - Env: simulasi jalan, Agent: mobil, Reward: kecepatan & keselamatan

---

### 3. Apa itu Discount Factor?

> Parameter γ ∈ [0,1] yang menimbang reward masa depan.  
γ tinggi → fokus masa depan,  
γ rendah → fokus reward cepat.

Kebijakan optimal bisa berubah jika γ berubah signifikan.

---

### 4. Cara mengukur kinerja RL agent?

> - **Average cumulative reward**  
> - **Win rate (jika game)**  
> - **Time to convergence**

---

### 5. Credit Assignment Problem

> Sulit menentukan aksi mana menyebabkan reward (terutama jika reward muncul belakangan).  
Solusi:
- Gunakan **temporal difference**
- Gunakan **eligibility traces**

---

### 6. Apa kegunaan replay buffer?

> Untuk menyimpan pengalaman lama dan sampling ulang saat training.  
Manfaat:
- Mengurangi korelasi antar episode  
- Menggunakan data lebih efisien

---

### 7. Apa itu off-policy RL?

> Metode di mana agent belajar dari data yang dihasilkan oleh kebijakan berbeda (misal: replay buffer).  
Contoh: DQN, DDPG  
Berbeda dengan **on-policy** (seperti PPO, A2C)
