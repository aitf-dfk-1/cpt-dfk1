# DFK Model Comparison: Qwen vs Ministral vs Gemma

Proyek ini bertujuan untuk mengevaluasi dan membandingkan performa berbagai *Large Language Models* (LLMs) dalam tugas **CPT (Continual Pre-training)** menggunakan dataset spesifik domain **DFK (Disinformasi, Fitnah, Kebencian)** dalam Bahasa Indonesia.

## Hasil Perbandingan Performa

Berdasarkan eksperimen yang dilakukan pada dataset berukuran 44k sampel (~4.48 juta token), berikut adalah metrik utama yang dihasilkan:

| Metrik | Qwen3.5-9B-Base | Ministral-3-8B-Base-2512 | gemma-4-E4B | gemma-3-4b-pt | Ministral-3-3B-Base-2512 | Qwen3.5-4b-Base |
| :--- | :---: | :---: | :---: | :---: | :---: | :---: |
| **Global Step** | 456 | 579 | 483 | 486 | 579 | x
| **Grad Norm** | 0.2898 | 0.4350 | 0.9972 | 0.31 | 0.49 | x |
| **Baseline Wiki PPL** | 4.06 | 5.24 | 3066.38 | 8.23 | 6.62 | x |
| **Final Wiki PPL** | 3.44 | 4.52 | 9.70 | 6.41 | 5.53 | x |
| **Degradation** | **-15.31%** | -13.66% | -99.68% | -19.54% | -13.78% | x |
| **Train Loss** | 2.07 | 1.68 | 3.07 | 1.90 | 1.84 | x |
| **Eval Loss** | 2.02 | 1.64 | 2.30 | 1.84 | 1.79 | x |
| **PPL (Final)** | 7.54 | 5.16 | 9.97 | 8.23 | 6.41 | x |
| **Runtime (Durasi)** | ~12.8 Jam | ~7.5 Jam | ~5.8 Jam | 9,08 Jam | 4.33 Jam | x |
| **VRAM Peak** | 31.88 GB | 20.95 GB | 35.40 GB | 22.51 GB | 13.40 GB | x |

## Tabel Perbandingan Kualitas Output 

| Prompt | **gemma-4-E4B** | **Ministral-3-8B-Base-2512** | **Qwen3.5-9B-Base** | Ministral-3-3B-Base-2512 | gemma-3-4b-pt |  Qwen3.5-4b-Base |
| :--- | :--- | :--- | :--- | :--- | :--- |:--- |
| **Disinformasi di Indonesia terutama menyebar lewat** | Disinformasi di Indonesia terutama menyebar lewat WhatsApp. Di sana, mereka juga mengungkit kejahatan yang dilakukan oleh pemerintah Indonesia di Papua. “Kami juga mengungkit kejahatan yang dilakukan oleh pemerintah Indonesia di Papua,” tulis mereka. “Kami juga mengungkit kejahatan... | Disinformasi di Indonesia terutama menyebar lewat media sosial. Sehingga, tidak mengherankan jika akun media sosial yang menyebarkan hoaks dan konten negatif diancam diblokir. Baca berita dengan sedikit iklan, klik di sini Scroll ke bawah.. | Disinformasi di Indonesia terutama menyebar lewat media sosial. Di tangan para penyebar, media sosial menjadi sarana yang efektif untuk menyebarkan informasi bohong. Namun, tidak semua informasi bohong itu disebarkan dengan sengaja. Ada yang disebarkan tanpa niat, atau bahkan tanpa mengetahui bahwa informasi itu boh.. | Disinformasi di Indonesia terutama menyebar lewat media sosial. Sejak awal pandemi Covid-19, fakta-fakta medis yang diduga disebar oleh pihak tertentu telah banyak menimbulkan ketakutan dan keresahan di masyarakat. Salah satunya yang ber... | Disinformasi di Indonesia terutama menyebar lewat media sosial. Menurut data yang dirilis oleh Kementerian Komunikasi dan Informatika (Kemkominfo) pada 2020, terdapat 1,4 juta akun media sosial yang berpotensi menyebarkan konten hoaks. Hal ini mendorong pemerintah ... | x |
| **Narasi ujaran kebencian di masa pemilu rentan memecah** | Narasi ujaran kebencian di masa pemilu rentan memecah belah masyarakat. Hal ini bisa terjadi jika kita tidak berhati-hati dalam menyebarkan berita yang belum terverifikasi. Kita bisa menjadi korban atau pelaku berita hoax. Kita bisa menjadi korban berita hoax jika kita mudah percaya tanpa melakukan cek dan pasti... | Narasi ujaran kebencian di masa pemilu rentan memecah belah persatuan bangsa. Dosen Universitas Indonesia (UI) Fathur Rahman Alaydrus mengatakan, narasi tersebut perlu dihindari agar tidak menimbulkan krisis identitas. "Tidak hanya mencipt... | Narasi ujaran kebencian di masa pemilu rentan memecah belah masyarakat, terutama ketika berfokus pada kelompok tertentu. Jika narasi tersebut berkembang, dampaknya bisa merusak proses demokrasi, menghambat partisipasi publik, dan memicu polarisasi yang sulit diatasi. Oleh karena itu, penting untuk memahami mekanisme yang dapat... | Narasi ujaran kebencian di masa pemilu rentan memecah belah masyarakat. Padahal, pemilu merupakan proses demokrasi yang seharusnya memperkuat solidaritas dan persatuan. Oleh karena itu, penting untuk mengevaluasi kembali bagaimana narasi ujaran kebencian ... | Narasi ujaran kebencian di masa pemilu rentan memecah belah masyarakat. Oleh karena itu, pemilu harus diwarnai dengan sikap toleran dan tidak memecah belah masyarakat. “Kami berharap semua pihak tetap menjaga persatuan dan kesatuan bangsa,” kata Ketua Umum Partai Gerindra Prabowo Sub... | x |
| **Berita palsu seringkali mengandung judul yang clickbait seperti** | Berita palsu seringkali mengandung judul yang clickbait seperti ini. Baca juga: 10 Judul Artikel yang Mengandung Judul Clickbait Baca juga: 10 Judul Artikel yang Mengandung Judul Clickbait Baca juga: 10 Judul Artikel yang Mengandung Judul Clickbait... | Berita palsu seringkali mengandung judul yang clickbait seperti “Mengapa KPK Membongkar Korupsi Rp 1.000 Triliun?”. Judul tersebut menimbulkan rasa penasaran dan mengarah pembaca untuk membaca lebih lanjut. Di dalam.... | Berita palsu seringkali mengandung judul yang clickbait seperti yang dikutip dari Cybernews. Judul clickbait adalah judul yang dirancang untuk menarik perhatian dan memancing pembaca untuk mengkliknya. Judul clickbait seringkali menggunakan kata-kata yang berlebihan dan tidak relevan dengan isi berita. Selain itu, berita... |  Berita palsu seringkali mengandung judul yang clickbait seperti “Mengapa Kita Harus Makan Roti, Makanan Berkarbohidrat, dan Makanan Berlemak”, yang menarik perhatian pembaca. Namun, isi dari artikel tersebut tidak hanya menyangk...| Berita palsu seringkali mengandung judul yang clickbait seperti 'Terungkap 16 Fakta Menarik dari Foto 'Wajah Diri' Prabowo' atau '5 Fakta Mengejutkan tentang Kabinet Prabowo-Gibran'. Penyebaran informasi palsu juga dapat menggunakan...| x |

### Temuan Utama
1. **Akurasi vs Degradasi:** Qwen 3.5 9B menunjukkan efisiensi yang sangat baik dalam hal *degradasi bahasa* umum (-15.31%), namun membutuhkan durasi training paling lama (12.8 jam).
2. **Efisiensi Memori:** Ministral 8B paling efisien dalam penggunaan VRAM (hanya 20.95 GB) dengan *loss* terendah (1.64 eval_loss).
3.  **Gemma:** Menunjukkan indikasi *language degradation* atau *repetitive loops*, terutama pada prompt mengenai *clickbait* di mana model mengulang frasa "Baca juga..." sebanyak tiga kali.
4.  **Ministral:** Memiliki gaya bahasa yang sangat menyerupai portal berita online. Namun, masih terdapat *noise* dari data latihan asal (seperti instruksi navigasi web "klik di sini" atau "scroll ke bawah").
5.  **Qwen:** Menunjukkan stabilitas dan alur logika yang paling baik. Model mampu menjelaskan konsep sosiopolitik (seperti polarisasi dan demokrasi) dengan diksi yang lebih formal dan tepat sasaran untuk domain DFK.

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


