# Bike Sharing Data Analysis

Proyek analisis data penyewaan sepeda (Bike Sharing Dataset) untuk periode 2011–2012. Proyek mencakup data wrangling, EDA, visualisasi, analisis lanjutan dengan binning suhu, serta dashboard Streamlit.

## Struktur folder

```text
.
├── data/
│   ├── day.csv
│   └── hour.csv
├── dashboard/
│   ├── dashboard.py
│   ├── day_data.csv
│   └── main_data.csv
├── notebook.ipynb
├── requirements.txt
├── requirements-notebook.txt
├── README.md
└── url.txt
```

## Menjalankan secara lokal

Disarankan menggunakan Python 3.10 atau lebih baru.

1. Buat dan aktifkan virtual environment (opsional tetapi disarankan).
2. Instal dependensi sesuai kebutuhan:

   ```bash
   # hanya untuk dashboard
   pip install -r requirements.txt

   # untuk notebook (sudah mencakup dependensi dashboard)
   pip install -r requirements-notebook.txt
   ```

3. Jalankan notebook dari root folder:

   ```bash
   jupyter notebook notebook.ipynb
   ```

   Pastikan notebook dijalankan dari direktori root agar folder `data/` ditemukan. Notebook akan membuat file CSV bersih di folder `dashboard/`.

4. Jalankan dashboard:

   ```bash
   streamlit run dashboard/dashboard.py
   ```

Dashboard hanya membaca `day_data.csv` dan `main_data.csv` hasil cleaning pada folder `dashboard/`. Kedua berkas sudah tersedia pada proyek ini; bila hilang, jalankan notebook terlebih dahulu.

## Dataset

Bike Sharing Dataset, berisi `day.csv` (agregasi harian) dan `hour.csv` (agregasi per jam). Sumber dataset: [Kaggle - Bike Sharing Dataset](https://www.kaggle.com/datasets/lakshmi25npathi/bike-sharing-dataset).

## Pertanyaan bisnis

1. Selama periode 1 Januari 2011 – 31 Desember 2012, pada jam berapa rata-rata penyewaan per jam mencapai puncak pada hari kerja dibandingkan akhir pekan/hari libur, dan berapa selisih rata-rata penyewaan pada jam-jam puncak tersebut? Hasilnya digunakan untuk menyusun jadwal redistribusi sepeda.
2. Selama periode 1 Januari 2011 – 31 Desember 2012, berapa rata-rata penyewaan harian pada setiap musim dan kategori cuaca, musim mana yang tertinggi dan terendah, serta berapa persen penurunan permintaan saat cuaca hujan/salju ringan dibandingkan cuaca cerah? Hasilnya digunakan untuk perencanaan kapasitas musiman dan mitigasi saat cuaca buruk.

Analisis lanjutan (opsional) memakai binning suhu dalam derajat Celsius dan segmentasi waktu dalam sehari.

## Catatan

- Hasil analisis merupakan eksplorasi deskriptif. Hubungan antarvariabel tidak otomatis menunjukkan hubungan sebab-akibat.
