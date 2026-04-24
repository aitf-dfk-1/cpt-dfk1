# DFK Model Comparison: Qwen vs Ministral vs Gemma

Proyek ini bertujuan untuk mengevaluasi dan membandingkan performa berbagai *Large Language Models* (LLMs) dalam tugas **CPT (Continual Pre-training)** menggunakan dataset spesifik domain **DFK (Disinformasi, Fitnah, Kebencian)** dalam Bahasa Indonesia.

## Hasil Perbandingan Performa

Berdasarkan eksperimen yang dilakukan pada dataset berukuran 44k sampel (~4.48 juta token), berikut adalah metrik utama yang dihasilkan:

| Metrik | Qwen3.5-9B-Base | Ministral-3-8B-Base-2512 | gemma-4-E4B | gemma-3-4b-pt | Ministral-3-3B-Base-2512 | Qwen3.5-4b-Base | Qwen3-4b-Base |
| :--- | :---: | :---: | :---: | :---: | :---: | :---: | :---: |
| **Global Step** | 456 | 579 | 486 | 486 | 579 | 456 | 456 |
| **Grad Norm** | 0.2898 | 0.4350 | 0.42 | 0.31 | 0.49 | 0.35 | 0.21 |
| **Baseline Wiki PPL** | 4.06 | 5.24 | 7.76 | 8.23 | 6.62 | 4.45 | 3.95 |
| **Final Wiki PPL** | 3.44 | 4.52 | 5.34 | 6.62 | 5.53 | 4.05 | 3.25 |
| **Degradation** | **-15.31%** | -13.66% | -31.08% | -19.54% | -13.78% | -9.12% | -17.53% |
| **Train Loss** | 2.07 | 1.68 | 1.85 | 1.90 | 1.83 | 2.22 | 1.54 |
| **Eval Loss** | 2.02 | 1.64 | 1.78 | 1.84 | 1.79 | 2.17 | 1.51 |
| **PPL (Final)** | 7.57 | 5.15 | 5.92 | 6.31 | 5.98 | 8.74 | 4.55 |
| **Runtime (Durasi)** | ~12.8 Jam | ~7.5 Jam | ~5.93 Jam | ~9,08 Jam | ~4.33 Jam | ~11.99 Jam | 5.1 Jam |
| **VRAM Peak** | 31.88 GB | 20.95 GB | 32.56 GB | 22.51 GB | 13.40 GB | 20.99 GB | 14.26 GB |

## Tabel Perbandingan Kualitas Output 

| Prompt | **gemma-4-E4B** | **Ministral-3-8B-Base-2512** | **Qwen3.5-9B-Base** | Ministral-3-3B-Base-2512 | gemma-3-4b-pt |  Qwen3.5-4b-Base | Qwen3-4b-Base |
| :--- | :--- | :--- | :--- | :--- | :--- |:--- | :--- |
| **Disinformasi di Indonesia terutama menyebar lewat** | Disinformasi di Indonesia terutama menyebar lewat media sosial. "Jadi, kita harus berhati-hati, jangan sampai kita menjadi korban dari informasi yang tidak benar," kata dia. Dia mengatakan, pihaknya akan terus berupaya untuk mengedukasi masyarakat agar tidak mudah percaya dengan informasi yang belum... | Disinformasi di Indonesia terutama menyebar lewat media sosial. Sehingga, tidak mengherankan jika akun media sosial yang menyebarkan hoaks dan konten negatif diancam diblokir. Baca berita dengan sedikit iklan, klik di sini Scroll ke bawah.. | Disinformasi di Indonesia terutama menyebar lewat media sosial. Di tangan para penyebar, media sosial menjadi sarana yang efektif untuk menyebarkan informasi bohong. Namun, tidak semua informasi bohong itu disebarkan dengan sengaja. Ada yang disebarkan tanpa niat, atau bahkan tanpa mengetahui bahwa informasi itu boh.. | Disinformasi di Indonesia terutama menyebar lewat media sosial. Sejak awal pandemi Covid-19, fakta-fakta medis yang diduga disebar oleh pihak tertentu telah banyak menimbulkan ketakutan dan keresahan di masyarakat. Salah satunya yang ber... | Disinformasi di Indonesia terutama menyebar lewat media sosial. Menurut data yang dirilis oleh Kementerian Komunikasi dan Informatika (Kemkominfo) pada 2020, terdapat 1,4 juta akun media sosial yang berpotensi menyebarkan konten hoaks. Hal ini mendorong pemerintah ... | Disinformasi di Indonesia terutama menyebar lewat media sosial. Di media sosial, masyarakat bisa menerima informasi yang tidak benar dan mempercayainya. Bahkan, banyak orang yang percaya informasi itu benar. Mereka kemudian menyebarkannya ke media sosial. Hal ini tentu berbahaya bagi masyarakat. Sebab, informasi... |  Disinformasi di Indonesia terutama menyebar lewat media sosial. Berdasarkan hasil survei yang dilakukan Universitas Indonesia (UI), Indonesia menempati urutan kedua dalam daftar negara dengan tingkat informasi palsu tertinggi. Dalam survei tersebut, Indonesia...|
| **Narasi ujaran kebencian di masa pemilu rentan memecah** | Narasi ujaran kebencian di masa pemilu rentan memecah belah persatuan bangsa. "Jangan sampai kita terpecah belah karena perbedaan pilihan politik," kata dia. | Narasi ujaran kebencian di masa pemilu rentan memecah belah persatuan bangsa. Dosen Universitas Indonesia (UI) Fathur Rahman Alaydrus mengatakan, narasi tersebut perlu dihindari agar tidak menimbulkan krisis identitas. "Tidak hanya mencipt... | Narasi ujaran kebencian di masa pemilu rentan memecah belah masyarakat, terutama ketika berfokus pada kelompok tertentu. Jika narasi tersebut berkembang, dampaknya bisa merusak proses demokrasi, menghambat partisipasi publik, dan memicu polarisasi yang sulit diatasi. Oleh karena itu, penting untuk memahami mekanisme yang dapat... | Narasi ujaran kebencian di masa pemilu rentan memecah belah masyarakat. Padahal, pemilu merupakan proses demokrasi yang seharusnya memperkuat solidaritas dan persatuan. Oleh karena itu, penting untuk mengevaluasi kembali bagaimana narasi ujaran kebencian ... | Narasi ujaran kebencian di masa pemilu rentan memecah belah masyarakat. Oleh karena itu, pemilu harus diwarnai dengan sikap toleran dan tidak memecah belah masyarakat. “Kami berharap semua pihak tetap menjaga persatuan dan kesatuan bangsa,” kata Ketua Umum Partai Gerindra Prabowo Sub... |  Narasi ujaran kebencian di masa pemilu rentan memecah belah masyarakat, terutama ketika berujung pada tindakan kekerasan. Oleh karena itu, Komisi Pemilihan Umum (KPU) RI berupaya mengawal pelaksanaan Pilkada Serentak 2024 dengan menerapkan prinsip-prinsip demokrasi yang inklusif dan toleran. Salah... | Narasi ujaran kebencian di masa pemilu rentan memecah masyarakat. Ini dikhawatirkan dapat merusak persatuan bangsa dan memperbesar ketegangan sosial. Hal itu dikemukakan Ketua Komisi III DPR RI, Ahmad Doli Kurnia...|
| **Berita palsu seringkali mengandung judul yang clickbait seperti** | Berita palsu seringkali mengandung judul yang clickbait seperti "Pemerintah Akan Gelar Rapat Khusus Soal Perpanjangan Masa Jabatan Presiden". Baca berita dengan sedikit iklan, klik di sini "Kami juga menemukan berita palsu dengan judul 'Banjir Jakarta, Warga Keluhkan... | Berita palsu seringkali mengandung judul yang clickbait seperti “Mengapa KPK Membongkar Korupsi Rp 1.000 Triliun?”. Judul tersebut menimbulkan rasa penasaran dan mengarah pembaca untuk membaca lebih lanjut. Di dalam.... | Berita palsu seringkali mengandung judul yang clickbait seperti yang dikutip dari Cybernews. Judul clickbait adalah judul yang dirancang untuk menarik perhatian dan memancing pembaca untuk mengkliknya. Judul clickbait seringkali menggunakan kata-kata yang berlebihan dan tidak relevan dengan isi berita. Selain itu, berita... |  Berita palsu seringkali mengandung judul yang clickbait seperti “Mengapa Kita Harus Makan Roti, Makanan Berkarbohidrat, dan Makanan Berlemak”, yang menarik perhatian pembaca. Namun, isi dari artikel tersebut tidak hanya menyangk...| Berita palsu seringkali mengandung judul yang clickbait seperti 'Terungkap 16 Fakta Menarik dari Foto 'Wajah Diri' Prabowo' atau '5 Fakta Mengejutkan tentang Kabinet Prabowo-Gibran'. Penyebaran informasi palsu juga dapat menggunakan...|  Berita palsu seringkali mengandung judul yang clickbait seperti "Seorang WNI di Singapura Dimintai Uang Rp 300 Juta". Judul clickbait semacam ini bisa saja membuat pembaca merasa tergiur untuk membaca berita tersebut. Namun, jika judul berita itu tidak sesuai dengan isi berita, maka... | Berita palsu seringkali mengandung judul yang clickbait seperti “Jokowi Dikabarkan Resmi Menjenguk Prabowo di RS Gatot Subroto”. Berita palsu ini menimbulkan kebingungan publik dan dapat memicu kekhawatiran atau...|

### Temuan Utama
#### 1. Efisiensi Superior: Qwen3-4B-Base
**Qwen3-4b-Base** merupakan *best performer* dalam aspek efisiensi teknis:
* **Performa:** Mencatatkan **Eval Loss terendah (1.51)** dan **Perplexity (PPL) terbaik (3.25)** di antara seluruh kandidat.
* **Resource:** Hanya membutuhkan waktu **5.1 jam** pelatihan dengan penggunaan VRAM yang sangat minim (**14.26 GB**).


#### 2. Paradoks PPL: Kualitas Narasi vs Statistik
Terdapat temuan unik pada **Qwen 3.5 9B**. Meskipun secara statistik memiliki angka PPL tertinggi (**7.57**), kualitas outputnya secara kualitatif adalah yang **paling cerdas**.
* **Diksi Dewasa:** Mampu menggunakan istilah sosiopolitik yang berat secara tepat (contoh: *"polarisasi"* dan *"partisipasi publik"*).
* **Analisis:** Nilai PPL yang tinggi dalam kasus ini bukan menunjukkan kebingungan model, melainkan tanda bahwa model memiliki variasi kosakata yang lebih kaya (*High Vocabulary Entropy*).

#### 3. Ketahanan Bahasa Indonesia Umum
**Qwen3.5-4b-Base** menunjukkan kemampuan terbaik dalam menjaga pengetahuan umum (*General Knowledge*):
* **Degradasi Rendah:** Mencatatkan angka penurunan performa bahasa umum paling kecil, yaitu hanya **-9.12%**.
* **Minim Catastrophic Forgetting:** Sukses mempelajari data spesifik DFK tanpa merusak kemampuan dasarnya dalam berbahasa Indonesia yang natural.

#### 4. Kualitas Output & Kebersihan Data (*Noise*)
Perbedaan karakter *output* antar arsitektur terlihat cukup signifikan:
* **Gemma & Ministral:** Masih membawa residu (*noise*) dari dataset *pre-training* asal (portal berita), ditandai dengan munculnya frase seperti *"klik di sini"* atau *"scroll ke bawah"*.
* **Qwen Series:** Hasil *generate* jauh lebih bersih, profesional, dan sangat peka terhadap konteks lokal Indonesia (seperti isu politik dan dinamika sosial terkini).

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


