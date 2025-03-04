Tugas ini berfokus pada penerapan Machine Learning sederhana untuk memprediksi apakah suatu produk perlu di-restock atau tidak. Dalam kasus ini, kita menggunakan Decision Tree Classifier dari library scikit-learn. Dataset yang digunakan berisi data penjualan harian, termasuk jumlah produk yang terjual, sisa stok, dan harga satuan produk. Tujuan utama proyek ini adalah membuat model prediksi restock otomatis, sehingga nantinya sistem bisa memberi rekomendasi apakah stok aman atau perlu diisi ulang. Selain itu, kami juga membuat visualisasi sederhana untuk menganalisis hubungan antara jumlah terjual, stok, dan keuntungan.

Instruksi cara menjalankan code:
1. Persiapan awal dengan membuka Google Collab dan pastikan file dataset sudah diupload jika Colab. install library yang dibutuhkan dengan perintah  !pip install pandas scikit-learn matplotlib
2. Load dab bersihkan data dengan import data penjualan menggunakan pandas. Cek apakah ada data kosong, kalau ada bisa dibersihkan atau diisi default value. Konversi kolom tanggal ke format datetime agar lebih rapi.
3. Hitung total penjualan dan keuntungan dengan perintah:
   df["Total Penjualan"] = df["Jumlah Terjual"] * df["Harga Satuan"]
   df["Keuntungan"] = df["Total Penjualan"] - (df["Jumlah Terjual"] * 10000)  #asumsi biaya pokok 10.000
4. LAtih model machine learning dengan fitur yang digunakan: Jumlah Terjual dan Stok. Target: 1 jika stok kurang dari 5 (perlu restock), 0 jika tidak perlu restock. Bagi data menjadi train dan test. Latih model menggunakan DecisionTreeClassifier. Cek akurasi model setelah training.
5. Prediksi produk baru dengan contoh misalnya produk yang terjual 8 dengan sisa stok 3, menggunakan perintah:
   produk_baru = [[8, 3]]
   prediksi = model.predict(produk_baru)
   if prediksi[0] == 1:
    print("Produk perlu di-restock!")
   else:
    print("Stok masih cukup.")
6. visualisasi data dengan membuat visualisasi hubungan antara Jumlah Terjual, Stok, dan Keuntungan supaya bisa lebih mudah dianalisis.

Jadi dapat disimpulkan bagaimana alur kerja membangun sistem prediksi sederhana:
* Membaca dan mempersiapkan data.
* Menambahkan kolom baru untuk analisis lebih lanjut.
* Melatih model Decision Tree untuk prediksi.
* Mengevaluasi akurasi model.
* Mencoba prediksi manual untuk produk baru.
* Melakukan visualisasi data agar pola lebih terlihat.
