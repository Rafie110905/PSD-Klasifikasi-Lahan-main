# Aset referensi klasifikasi KNN dari PDF

File di folder ini diambil dari repository publik
[itsaalii/PSD](https://github.com/itsaalii/PSD) pada commit
`687183bddc9f78a89ef701642bde9a634a80f63c`, khususnya
`data/Klasifikasi/` dan `data/Klasifikasi/land/`.

## Dataset dan input spasial

- `dataset.csv` — 322.146 piksel, 19 kolom (fitur, label, ID poligon, dan koordinat).
- `jatim_250m.tif` — raster regional yang disebut sebagai input inferensi pada laporan.
- `jawa_timur_provinsi.geojson` — batas provinsi.
- `sawah.zip`, `bangunan.zip`, `Hutan.zip`, `Danau.zip`, `laut2.zip`,
  `Mangrove.zip` — sampel poligon per kelas.

## Hasil evaluasi dan visualisasi

- `confusion_matrix.csv` dan `laporan_klasifikasi.csv` — hasil evaluasi piksel.
- `prediksi_data_uji.csv` — ringkasan prediksi 268 poligon; 259 tercatat benar.
- `confusion_matrix.png` dan `kinerja_kelas.png` — visualisasi laporan.
- `hasil_klasifikasi_knn.html` — peta regional KNN yang sudah dihasilkan.

Angka pada CSV evaluasi sesuai dengan PDF: confusion matrix mencakup 64.430
piksel, akurasi terhitung 98,176% (dibulatkan 98,18%), macro-F1 0,944, dan
259/268 prediksi poligon benar.

## Batasan penggunaan

Folder ini merupakan aset referensi dan tidak menggantikan data atau model
dashboard di `outputs/`. File model KNN terlatih tidak tersedia di repository
sumber. Notebook sumber klasifikasi yang tersedia di sana berisi eksperimen
Random Forest, bukan pipeline KNN pada PDF; notebook tersebut tidak disalin
sebagai pipeline KNN.
