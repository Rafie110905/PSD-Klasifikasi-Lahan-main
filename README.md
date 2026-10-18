# Klasifikasi Spasial Tutupan Lahan Jawa Timur

Proyek ini mengklasifikasikan tutupan lahan di Jawa Timur menggunakan citra
**Sentinel-2A Level-2A** dan algoritma **K-Nearest Neighbors (KNN)**. Ringkasan
metode dan angka di halaman ini diselaraskan dengan PDF laporan proyek.

## Kelas tutupan lahan

| Kode | Kelas |
|---:|---|
| 1 | Sawah |
| 2 | Bangunan |
| 3 | Hutan (lahan hijau) |
| 4 | Danau |
| 5 | Laut (perairan terbuka) |
| 6 | Mangrove |

## Metode

Citra Sentinel-2A Level-2A diperoleh melalui CDSE openEO. Piksel berawan
disaring menggunakan Scene Classification Layer (SCL), lalu nilai band dan
indeks spektral diekstrak pada poligon sampel. Indeks yang digunakan adalah
NDVI, NDWI, MNDWI, dan NDBI.

Dataset laporan yang kini tersedia di `data/knn_pdf_reference/dataset.csv`
berisi **322.146 piksel** dari **274 poligon sampel**. Data
dibagi secara stratified menjadi 80% data latih dan 20% data uji pada tingkat
piksel. Fitur distandarisasi dengan `StandardScaler`, lalu diklasifikasikan
menggunakan KNN dengan `n_neighbors=5`, jarak Euclidean, dan uniform voting.

## Hasil yang dilaporkan

Pada data uji 64.430 piksel, laporan mencatat akurasi **98,18%**, macro-F1
**0,944**, dan weighted-F1 **0,982**. Evaluasi agregat poligon melaporkan
259 dari 268 poligon terklasifikasi benar (**96,6%**).

| Kelas | Precision | Recall | F1-score |
|---|---:|---:|---:|
| Bangunan | 0,873 | 0,822 | 0,847 |
| Danau | 0,979 | 0,960 | 0,969 |
| Hutan | 0,963 | 0,982 | 0,972 |
| Laut | 0,993 | 0,998 | 0,995 |
| Mangrove | 0,982 | 0,978 | 0,980 |
| Sawah | 0,918 | 0,888 | 0,903 |

**Catatan evaluasi:** pembagian train/test pada laporan dilakukan per piksel,
bukan dengan menahan seluruh poligon dari data latih. Karena itu, piksel
berdekatan atau dari poligon yang sama dapat muncul di kedua bagian; angka
evaluasi tersebut perlu ditafsirkan sesuai skema ini dan tidak otomatis
mengukur generalisasi ke lokasi baru.

## Dashboard Streamlit

Dashboard Streamlit yang sudah ada sengaja tidak diubah. Aset tabel, model,
dan peta yang digunakan aplikasi saat ini berasal dari eksperimen sebelumnya
dan belum disinkronkan dengan KNN serta label kelas dalam PDF. Jangan
menganggap angka atau peta dashboard saat ini sebagai keluaran KNN di atas.

Data, hasil evaluasi, sampel poligon, raster regional, dan peta HTML KNN dari
repo sumber tersedia terpisah di [data/knn_pdf_reference/](data/knn_pdf_reference/).
Folder tersebut berisi catatan sumber dan batasan aset. Model KNN terlatih
tidak tersedia dari repo sumber.

## Menjalankan dashboard yang ada

```bash
pip install -r requirements.txt
streamlit run app.py
```

Struktur proyek mencakup `app.py` (dashboard Streamlit yang tidak diubah),
`data/` (aset proyek serta aset referensi KNN), `notebooks/` (ringkasan
metodologi dan hasil PDF), dan `outputs/` (aset dashboard yang ada).
