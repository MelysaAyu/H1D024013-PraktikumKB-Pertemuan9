# 🧬 Praktikum KB – Pertemuan 9: Algoritma Genetika untuk Knapsack Problem

**NIM:** [isi NIM Anda]  
**Topik:** Algoritma Genetika (Genetic Algorithm)  
**Kasus:** Knapsack Problem (0/1)

---

## 📖 Tentang Modul

Modul praktikum ini membahas **Algoritma Genetika** sebagai salah satu metode optimasi berbasis populasi yang terinspirasi dari teori evolusi Darwin. Tujuan praktikum:

- Memahami dasar-dasar dan cara kerja Algoritma Genetika.
- Menerapkan Algoritma Genetika pada kasus nyata (Knapsack Problem).
- Terampil mengimplementasikan dalam bahasa Python.

---

## 🧠 Teori Singkat

### Apa itu Algoritma Genetika?
Algoritma Genetika (AG) dikembangkan oleh **John Holland** pada 1960-an. AG meniru proses seleksi alam, di mana individu terbaik akan bertahan dan menghasilkan keturunan yang lebih baik.

### Langkah-langkah AG
1. **Inisialisasi** – Membangkitkan populasi awal secara acak (kromosom biner).
2. **Evaluasi Fitness** – Menghitung nilai solusi (fitness) setiap individu.
3. **Seleksi** – Memilih orang tua berdasarkan fitness (Roulette Wheel / Tournament).
4. **Crossover** – Menggabungkan dua orang tua untuk menghasilkan anak.
5. **Mutasi** – Mengubah sedikit gen untuk menjaga keragaman.
6. **Generasi baru** – Mengulang langkah 2–5 hingga konvergen.

### Knapsack Problem
Masalah memilih barang dengan total nilai maksimum tetapi total bobot tidak melebihi kapasitas tas. Representasi kromosom: array biner (1 = barang dipilih, 0 = tidak dipilih).

---

## 📁 Struktur File Proyek
📂 folder-proyek/
│
├── InisiasiPopulasi.py # Membangkitkan populasi awal
├── EvaluasiFitness.py # Fungsi hitung fitness dengan penalti
├── selection.py # Seleksi parent (Roulette & Tournament)
├── crossover.py # Crossover (One-Point, Two-Point, Uniform)
├── mutation.py # Mutasi (Swap, Inversion, Uniform)
├── main.py # Program utama (GA loop + plotting)
├── image.png # Screenshot grafik hasil running
└── README.md # Penjelasan 

---

## 🚀 Cara Menjalankan

### Prasyarat
- Python 3.7+
- Library: `matplotlib`, `numpy`

Instal library jika belum:
```bash
pip install matplotlib numpy

Eksekusi
Pastikan semua file .py berada dalam satu folder.

Buka terminal/command prompt di folder tersebut.

Jalankan:

bash
python main.py

Parameter yang Digunakan (dalam main.py)
Parameter	Nilai	Keterangan
jumlah_generasi	50	Jumlah iterasi evolusi
jumlah_populasi	20	Jumlah individu per generasi
prob_crossover	0.5	Peluang terjadi crossover
prob_mutasi	0.1	Peluang mutasi per gen
kapasitas_tas	50	Maksimal bobot tas (knapsack)
📦 Data Barang (9 Barang)
Barang	Nilai	Bobot
Barang1	60	10
Barang2	100	20
Barang3	120	30
Barang4	90	25
Barang5	69	11
Barang6	70	9
Barang7	80	15
Barang8	90	10
Barang9	25	3
📊 Hasil Running
1. Grafik Perkembangan Fitness
https://grafik.png

Penjelasan Grafik
Sumbu X : Generasi ke-1 hingga ke-50.

Sumbu Y : Nilai fitness (total nilai barang yang terpilih).

🔵 Garis Biru (Fitness Tertinggi) : Nilai individu terbaik tiap generasi. Cenderung meningkat dan akhirnya stabil.

🟡 Garis Kuning (Fitness Terendah) : Nilai individu terburuk. Semakin ke kanan, garis ini naik karena populasi membaik.

🔴 Garis Merah (Fitness Rata-rata) : Rata-rata fitness seluruh individu. Menunjukkan kesehatan populasi.

⚫ Titik Abu-abu : Setiap titik adalah satu individu. Semakin gelap area, semakin banyak individu dengan nilai fitness serupa.

Interpretasi
Generasi awal (kiri): fitness rendah dan tersebar (algoritma masih eksplorasi).

Generasi tengah: fitness tertinggi dan rata-rata naik drastis.

Generasi akhir (kanan): ketiga garis mendatar → konvergensi. Algoritma menemukan solusi optimal atau mendekati optimal.

2. Output Teks (Contoh)
Setelah grafik ditutup, terminal akan menampilkan:

text
Nilai Fitness Terbaik: 329
Total Bobot: 50
Barang Terpilih:
- Barang2
- Barang5
- Barang6
- Barang8
Penjelasan:

Fitness terbaik = 329 adalah total nilai barang yang berhasil dimasukkan.

Total bobot = 50 (sesuai kapasitas maksimal).

Barang terpilih: Barang2 (100/20), Barang5 (69/11), Barang6 (70/9), Barang8 (90/10). Jumlah bobot = 20+11+9+10 = 50.

📝 Catatan Penting
Hasil setiap run dapat berbeda karena inisialisasi dan proses random. Ini sifat alami GA.

Untuk mendapatkan hasil yang konsisten (reproducible), tambahkan random.seed(42) di awal main.py.

Jika grafik fitness tertinggi belum stabil di akhir generasi, coba tingkatkan jumlah_generasi (misal 100).

Pastikan semua file import memiliki nama yang sama persis (huruf besar/kecil) dengan file yang ada.