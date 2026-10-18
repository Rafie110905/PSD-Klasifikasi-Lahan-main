# Klasifikasi Spasial Tutupan Lahan Jawa Timur

Laporan ini merangkum klasifikasi tutupan lahan Jawa Timur menggunakan citra
**Sentinel-2A Level-2A** dan algoritma **K-Nearest Neighbors (KNN)**, mengikuti
metode serta hasil pada PDF laporan proyek.

## Tujuan dan kelas

Model mengklasifikasikan enam kelas: **Sawah**, **Bangunan**, **Hutan (lahan
hijau)**, **Danau**, **Laut (perairan terbuka)**, dan **Mangrove**. Data citra
diperoleh melalui CDSE openEO. Scene Classification Layer digunakan untuk
menyaring awan, kemudian band spektral dan indeks **NDVI**, **NDWI**, **MNDWI**,
serta **NDBI** digunakan sebagai fitur.

## Pemodelan dan evaluasi

Dataset laporan tersedia di `data/knn_pdf_reference/dataset.csv` dan berisi
322.146 piksel dari 274 poligon sampel. Dataset dibagi
stratified 80:20 pada tingkat piksel, fitur distandarisasi dengan
`StandardScaler`, lalu model KNN dilatih dengan 5 tetangga, jarak Euclidean,
dan uniform voting.

Hasil data uji yang dilaporkan adalah akurasi **98,18%**, macro-F1 **0,944**,
dan weighted-F1 **0,982**. Pada evaluasi poligon, 259 dari 268 poligon
terklasifikasi benar (**96,6%**).

Pembagian train/test pada laporan dilakukan per piksel. Piksel dari poligon
yang sama dapat tersebar ke kedua bagian, sehingga skor tersebut perlu
ditafsirkan sebagai evaluasi pada skema split yang dilaporkan, bukan sebagai
jaminan performa pada lokasi yang sepenuhnya baru.

## Dashboard

Dashboard Streamlit yang sudah ada tidak diubah. Model dan visualisasi yang
digunakan dashboard belum diselaraskan dengan laporan KNN ini; angka dan peta
dashboard bukan keluaran eksperimen pada PDF.

Dataset, raster regional, batas wilayah, hasil evaluasi, dan peta KNN dari
repo sumber disimpan terpisah di [data/knn_pdf_reference/](data/knn_pdf_reference/).
Model KNN terlatih tidak tersedia dari repo sumber.

## Jelajahi proyek

- [Buka dashboard Streamlit](https://psd-klasifikasi-lahan-main-d32m2apyfjy9jndulj9eab.streamlit.app/) — versi yang sudah ada, belum diselaraskan dengan PDF.
- [Lihat kode dan berkas proyek di GitHub](https://github.com/Rafie110905/PSD-Klasifikasi-Lahan-main)

Gunakan daftar isi untuk melihat notebook dan deployment yang tersedia.

```{tableofcontents}
```
