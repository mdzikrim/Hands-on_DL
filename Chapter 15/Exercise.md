# 📘 Chapter 15 – Recurrent Neural Networks

---

### 1. Aplikasi RNN

- Sequence-to-sequence: **machine translation**, **speech-to-text**  
- Sequence-to-vector: **sentiment analysis**, **intent classification**  
- Vector-to-sequence: **music generation**, **image captioning**

---

### 2. Dimensi input/output RNN layer

- Input: 3D tensor → `(batch_size, timesteps, input_dim)`  
- Output (return_sequences=False): 2D tensor `(batch_size, units)`  
- Output (return_sequences=True): 3D tensor `(batch_size, timesteps, units)`

---

### 3. Deep seq2seq RNN, kapan pakai `return_sequences=True`?

- Ya, semua intermediate layers harus `return_sequences=True` agar dapat meneruskan seluruh urutan.  
- Sequence-to-vector → hanya last layer `return_sequences=False`  
- Sequence-to-sequence → semua `True`

---

### 4. Time series prediksi 7 hari dari 1 data harian → pakai arsitektur?

> **Sequence-to-sequence RNN** (many-to-many) dengan 7 output steps.  
> Bisa pakai encoder–decoder RNN atau LSTM.

---

### 5. Masalah utama saat training RNN dan solusinya:

- **Vanishing/exploding gradients** → gunakan LSTM/GRU, gradient clipping  
- **Long-term dependency** → gunakan attention atau transformer  
- **Slow training** → pakai CuDNNLSTM, parallel data loading

---

### 7. Kenapa pakai 1D conv di RNN?

> Untuk **menangkap fitur lokal dalam sequence** (misal phonemes dalam suara), **lebih cepat daripada RNN**, dan dapat digunakan sebagai feature extractor sebelum RNN.

---

### 8. Arsitektur video classification?

> Gunakan **Conv3D** atau **CNN → LSTM**, atau 3D CNN + GRU  
> Contoh: **TimeDistributed CNN + LSTM** atau **I3D**

---

### 9. Model klasifikasi SketchRNN?

> Gunakan RNN (LSTM atau GRU) pada data sequence goresan. Dataset: `tensorflow_datasets.sketch_rnn`.

