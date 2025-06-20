# 📘 Chapter 19 – Deploying TensorFlow Models

---

### 1. What does a SavedModel contain?

> - Arsitektur model  
> - Bobot terlatih  
> - Informasi optimizer  
> - Signature & assets  
Untuk inspect: `saved_model_cli show --dir <path> --all`

---

### 2. Kapan gunakan TensorFlow Serving?

> Saat Anda butuh:
- Model server HTTP/gRPC
- Reload model otomatis (tanpa restart)
- Versi model aktif
- Performa tinggi, low-latency inference

Tools: Docker, `tensorflow_model_server`, Kubernetes

---

### 3. Deploy ke banyak TF Serving instance?

> Gunakan load balancer (misal NGINX, GCP Load Balancing)  
Skalakan instance server model, routing client via API Gateway

---

### 4. gRPC vs REST?

- **gRPC**: binary protocol, lebih cepat & ringan (saran untuk mobile/backend)  
- **REST**: JSON, lebih mudah debug & digunakan dari browser

---

### 5. Cara TFLite mengecilkan model?

> - **Post-training quantization**  
> - **Float16 quantization**  
> - **Pruning + clustering**  
> - **Knowledge distillation**

---

### 6. Quantization-aware training?

> Simulasikan quantization saat training → akurasi tetap tinggi setelah konversi ke int8.  
Diperlukan untuk device edge/embedded.

---

### 7. Model vs Data Parallelism?

- **Model parallelism**: pisah layer ke device berbeda  
- **Data parallelism**: model yang sama, batch berbeda di device berbeda  
→ lebih umum: data parallelism (misal MirroredStrategy)

---

### 8. Distributed strategy?

> Gunakan `tf.distribute.Strategy`, seperti:
- `MirroredStrategy`: multi-GPU 1 mesin  
- `MultiWorkerMirroredStrategy`: banyak mesin  
- `TPUStrategy`: training di TPU  
Pilihan tergantung hardware dan latency yang ditoleransi.
