# Praktikum Pertemuan 10: Kurir Directory App (`p10`)

Proyek praktikum dasar Android pemrograman mobile (Pertemuan 10) yang mengimplementasikan konsumsi RESTful GET API publik, antarmuka RecyclerView, serta pencarian real-time (*live in-memory filtering*).

---

## 🚀 Fitur Utama

- **Konsumsi RESTful API Publik**: Mengambil 10 data pengguna/kurir secara asinkron dari endpoint publik JSONPlaceholder (`https://jsonplaceholder.typicode.com/users`).
- **Square Retrofit 2 & Gson Converter**: Pemetaan data JSON bersarang (*nested JSON*) ke model Kotlin Data Class secara terstruktur menggunakan `@SerializedName`.
- **Kotlin Coroutines**: Menjalankan *network request* di latar belakang (`Dispatchers.IO`) dan memperbarui antarmuka pengguna di Main Thread (`Dispatchers.Main`).
- **RecyclerView & CardView**: Menampilkan daftar kartu kurir rapi dengan informasi nama, perusahaan, email, dan telepon.
- **Pencarian Live Real-Time (TextWatcher)**: Penyaringan data langsung berbasis memori RAM (*in-memory filter*) tanpa jeda loading dan hemat kuota.

---

## 🎯 Penyelesaian Tugas Mandiri Evaluasi

1. **Tugas 1 (Filter Ganda - Nama ATAU Perusahaan)**:
   - Modifikasi fungsi `filterNamaPengguna()` sehingga kata kunci yang diketik menyaring data berdasarkan nama pengguna **ATAU** nama perusahaan (`pengguna.name || pengguna.company.companyName`).
2. **Tugas 2 (State Kosong / Data Tidak Ditemukan)**:
   - Jika kata kunci pencarian tidak cocok dengan data manapun (contoh: mengetik `"Zulkifli"`), RecyclerView otomatis disembunyikan dan muncul pesan:
   > *"Tidak ada kurir yang cocok dengan pencarian Anda"*

---

## 🛠️ Teknologi & Dependensi

- **Bahasa**: Kotlin
- **Minimum SDK**: API 24 (Android 7.0 Nougat)
- **Target SDK**: API 37
- **Pustaka Utama**:
  - `com.squareup.retrofit2:retrofit:2.11.0`
  - `com.squareup.retrofit2:converter-gson:2.11.0`
  - `androidx.recyclerview:recyclerview:1.3.2`
  - `androidx.cardview:cardview:1.0.0`
  - `org.jetbrains.kotlinx:kotlinx-coroutines-android:1.8.0`
  - `androidx.lifecycle:lifecycle-runtime-ktx:2.8.4`
