# Klasifikasi Penggunaan dan Penutupan Lahan Jawa Timur

Laporan ini mendokumentasikan proyek klasifikasi tutupan lahan di Jawa Timur
menggunakan citra satelit **Sentinel-2** dan metode *machine learning*. Proyek
mencakup pemahaman masalah, pengolahan data, rekayasa fitur spektral,
perbandingan model, evaluasi, serta penyajian hasil melalui peta dan dashboard.

## Hasil klasifikasi

Model mengelompokkan area menjadi enam kelas: **sawah**, **bangunan/permukiman**,
**mangrove**, **lahan hijau**, **laut**, dan **danau**. Gambar berikut
membandingkan citra RGB dengan hasil klasifikasi.

```{figure} outputs/figures/rgb_vs_klasifikasi.png
---
alt: Perbandingan citra RGB dan hasil klasifikasi penggunaan lahan
---
Citra RGB dan hasil klasifikasi penggunaan/penutupan lahan.
```

## Jelajahi proyek

- [Buka dashboard Streamlit](https://psd-klasifikasi-lahan-main-d32m2apyfjy9jndulj9eab.streamlit.app/)
- [Lihat kode dan berkas proyek di GitHub](https://github.com/Rafie110905/PSD-Klasifikasi-Lahan-main)

Gunakan daftar isi untuk membaca tahapan proyek secara berurutan, dari
*Business Understanding* sampai WebGIS dan deployment.

```{tableofcontents}
```
