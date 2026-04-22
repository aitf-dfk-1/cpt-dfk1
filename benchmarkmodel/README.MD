# DFK Model Comparison: Qwen vs Ministral vs Gemma

Proyek ini bertujuan untuk mengevaluasi dan membandingkan performa berbagai *Large Language Models* (LLMs) dalam tugas **CPT (Continual Pre-training)** menggunakan dataset spesifik domain **DFK (Disinformasi, Fitnah, Kebencian)** dalam Bahasa Indonesia.

## Hasil Perbandingan Performa

Berdasarkan eksperimen yang dilakukan pada dataset berukuran 44k sampel (~4.48 juta token), berikut adalah metrik utama yang dihasilkan:

| Metrik | Qwen 3.5 9B | Ministral 8B | Gemma 4B |
| :--- | :---: | :---: | :---: |
| **Baseline Wiki PPL** | 4.06 | 5.24 | 3066.38 |
| **Final Wiki PPL** | 3.44 | 4.52 | 9.70 |
| **Degradation** | **-15.31%** | -13.66% | -99.68% |
| **Train Loss** | 2.07 | 1.68 | 3.07 |
| **Eval Loss** | 2.02 | 1.64 | 2.30 |
| **PPL (Final)** | 7.54 | 5.16 | 9.97 |
| **Runtime (Durasi)** | ~12.8 Jam | ~7.5 Jam | ~5.8 Jam |
| **VRAM Peak** | 31.88 GB | 20.95 GB | 35.40 GB |

### Temuan:
* **Akurasi vs Degradasi:** Qwen 3.5 9B menunjukkan efisiensi yang sangat baik dalam hal *degradasi bahasa* umum (-15.31%), namun membutuhkan durasi training paling lama (12.8 jam).
* **Efisiensi Memori:** Ministral 8B paling efisien dalam penggunaan VRAM (hanya 20.95 GB) dengan *loss* terendah (1.64 eval_loss).


## Konfigurasi Parameter (Hyperparameters)

Eksperimen ini dijalankan menggunakan library **Unsloth** untuk efisiensi memori dengan konfigurasi sebagai berikut:

* **Dataset:** 44k Samples / 21,989,498 Tokens
* **Max Sequence Length:** 2048
* **Epochs:** 3
* **Learning Rate:** 5e-5
* **Optimizer:** `adamw_8bit`
* **Batch Size:** 8 (Gradient Accumulation: 8)
* **LoRA Config:**
    * Rank (R): 16
    * Alpha: 32
    * Dropout: 0.05
    * Target Modules: `q_proj`, `k_proj`, `v_proj`, `o_proj`, `gate_proj`, `up_proj`, `down_proj`

## Tech Stack & Hardware
* **Framework:** PyTorch, Unsloth, Hugging Face Transformers.
* **Monitoring:** Weights & Biases (WandB).
* **Hardware:** NVIDIA A100 SXM4 40GB.

## Struktur Dataset
Dataset yang digunakan dalam proyek ini meliputi:
1.  **CPT Dataset:** Artikel berita dan narasi media sosial terkait Disinformasi dan Fitnah.
2.  **Validation:** Wiki Dataset (Indonesian) untuk mengukur tingkat degradasi pengetahuan umum setelah model dipelajari secara spesifik pada domain DFK.

---
**Tim 1 - Capstone Project DFK**
*Informatics Engineering, Institut Teknologi Sepuluh Nopember (ITS)*
