# Sistem Case-Based Reasoning (CBR) - Sengketa Pelanggaran Merek

Repository ini berisi implementasi sistem *Case-Based Reasoning* (CBR) untuk memprediksi amar putusan pada sengketa pelanggaran merek (Hak Kekayaan Intelektual). Sistem ini menggunakan teknik *Natural Language Processing* (NLP) dengan pendekatan TF-IDF, serta membandingkan algoritma klasifikasi *Naive Bayes* dan *Support Vector Machine* (SVM) untuk proses *retrieval* dan *prediction*.

## Struktur Repository
- `/data/raw/` : Kumpulan dataset dokumen putusan mentah (.txt dan .pdf)
- `/data/processed/` : Data kasus yang telah diekstraksi metadatanya (`cases.csv`, `cases.json`)
- `/data/eval/` : Data pengujian dan hasil metrik evaluasi model
- `/data/results/` : Hasil prediksi solusi kasus (`predictions.csv`)
- `/notebooks/` : Berisi *Jupyter Notebook* untuk menjalankan pipeline *end-to-end*

## Prasyarat dan Instalasi
Pastikan Python sudah terinstall di sistem Anda. Untuk menginstal semua pustaka yang dibutuhkan, jalankan perintah berikut di terminal:

```bash
pip install -r requirements.txt

Cara Menjalankan Pipeline (End-to-End)
Sistem ini dirancang untuk dijalankan secara berurutan langkah demi langkah melalui Jupyter Notebook. Silakan eksekusi file di dalam folder /notebooks/ dengan urutan sebagai berikut:

01_Build_Case_Base.ipynb - Melakukan ekstraksi teks mentah dari PDF/TXT dan pembersihan teks (preprocessing).

02_Case_Representation.ipynb - Mengekstrak metadata (No. Perkara, Pihak, Tanggal, dll) dan melakukan feature engineering ke format terstruktur.

03_Case_Retrieval.ipynb - Vektorisasi teks (TF-IDF) dan melatih model klasifikasi untuk memetakan kasus uji.

04_Case_Solution_Reuse.ipynb - Menggunakan model untuk memprediksi solusi (Amar Putusan) berdasarkan majority vote dari top-5 kasus paling mirip.

05_Evaluation.ipynb - Menghitung performa sistem (Accuracy, Precision, Recall, F1-Score) dan membandingkan algoritma Naive Bayes dengan SVM.

