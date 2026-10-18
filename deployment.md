# Deployment dan status dashboard

Dokumentasi proyek dan notebook di repository ini diringkas berdasarkan PDF
Klasifikasi Spasial Tutupan Lahan Jawa Timur (KNN & Sentinel-2A). Kode
`app.py` dan dashboard Streamlit yang sudah ada sengaja tidak diubah.

## Dashboard yang ada di repository

[Buka dashboard Streamlit yang sudah ada](https://psd-klasifikasi-lahan-main-d32m2apyfjy9jndulj9eab.streamlit.app/).

Dashboard tersebut masih menggunakan implementasi dan aset eksperimen
sebelumnya. Ia belum memakai model KNN, dataset, peta, ataupun metrik yang
dilaporkan dalam PDF. Notebook di repository ini adalah ringkasan laporan dan
bukan pipeline KNN yang dapat melatih ulang model.

Untuk menjalankan versi yang ada secara lokal:

```bash
pip install -r requirements.txt
streamlit run app.py
```

## Arsitektur yang dijelaskan PDF

PDF mendeskripsikan dua visualisasi Folium: evaluasi poligon sampel dengan
penanda kesalahan klasifikasi, serta peta inferensi regional dengan layer
terpisah untuk enam kelas. PDF juga menjelaskan integrasi tampilan tersebut ke
Streamlit.

Dataset `dataset.csv`, raster `jatim_250m.tif`, peta HTML KNN, CSV evaluasi,
dan batas wilayah dari repo sumber kini disimpan terpisah di
`data/knn_pdf_reference/`. Model KNN terlatih dan aplikasi Streamlit KNN tidak
tersedia dari repo sumber. Karena itu dashboard yang ada belum otomatis
menampilkan aset tersebut; implementasi Streamlit akan disesuaikan terpisah.

## Membangun dokumentasi

Notebook dalam repository ini berisi ringkasan metodologi dan angka yang
dilaporkan PDF. Ringkasan tersebut tidak menjalankan ulang eksperimen.

```bash
pip install jupyter-book
jupyter-book build .
```

Hasil build ada di `_build/html/`.
