# CryptoKISS - Keep It Simple & Smart

CryptoKISS adalah aplikasi Android sederhana yang dirancang untuk berinteraksi dengan AI chatbot yang didukung oleh Google Gemini. Proyek ini memenuhi tugas pembuatan program sederhana dengan database SQLite, yang diimplementasikan untuk mengelola "persona" atau *system prompt* dari chatbot yang bisa dibuat sendiri oleh pengguna.

Tujuan utamanya adalah menciptakan platform di mana pengguna tidak hanya bisa mengobrol dengan AI, tetapi juga bisa membuat, menyimpan, dan menggunakan berbagai macam chatbot dengan kepribadian yang berbeda-beda sesuai keinginan mereka.

## ✨ Fitur Utama

- **Splash Screen**: Tampilan pembuka aplikasi yang profesional.
- **Menu Utama**: Navigasi yang jelas dengan dua pilihan utama.
- **Kelola Chatbot (CRUD)**:
    - **Create**: Membuat persona bot baru dengan memberikan nama dan *system prompt* kustom.
    - **Read**: Menampilkan daftar semua bot yang telah dibuat.
    - **Update**: Mengedit nama dan prompt dari bot yang sudah ada.
    - **Delete**: Menghapus bot dari daftar.
- **Database Lokal**: Semua data prompt bot disimpan secara lokal dan persisten menggunakan **SQLite**.
- **Gunakan Chatbot**:
    - Memilih bot dari daftar yang telah dibuat (termasuk bot default).
    - Memulai sesi percakapan dengan AI yang akan mengikuti *system prompt* dari bot yang dipilih.
- **Interaksi AI Dinamis**: Judul halaman chat dan kepribadian AI berubah secara dinamis sesuai dengan bot yang digunakan.
- **Penanganan API Key yang Aman**: API Key Google Gemini disimpan dengan aman di `local.properties` dan tidak terekspos di dalam kode.

## 🛠️ Teknologi yang Digunakan

- **Bahasa**: Kotlin
- **Arsitektur**: Activity-based (dasar)
- **UI**: XML Layouts dengan Material Design Components
- **Database**: SQLite (menggunakan `SQLiteOpenHelper` bawaan Android)
- **Asynchronous**: Kotlin Coroutines & `lifecycleScope`
- **AI**: Google Gemini API

## 🚀 Cara Menjalankan Proyek

Untuk menjalankan proyek ini di komputer Anda, ikuti langkah-langkah berikut:

1.  **Clone atau Unduh Proyek**
    -   Jika proyek ada di Git, gunakan `git clone`.
    -   Jika tidak, cukup salin folder proyek ke komputer Anda.

2.  **Buka di Android Studio**
    -   Buka Android Studio.
    -   Pilih `Open an Existing Project` dan arahkan ke folder proyek yang sudah Anda siapkan.

3.  **Buat File `local.properties`**
    -   Di panel `Project` Android Studio (tampilan Android), cari file bernama `local.properties`.
    -   Jika file tersebut tidak ada, klik kanan pada `Gradle Scripts` -> `New` -> `File`. Beri nama file `local.properties`.

4.  **Tambahkan API Key Gemini**
    -   Buka file `local.properties` yang baru saja Anda buat.
    -   Tambahkan baris berikut, ganti `API_KEY_ANDA` dengan API key Anda yang valid:
        ```properties
        GEMINI_API_KEY="API_KEY_ANDA"
        ```

5.  **Sinkronkan Proyek dengan Gradle**
    -   Setelah menambahkan API key, akan muncul sebuah *banner* di bagian atas editor yang menyarankan untuk sinkronisasi. Klik **"Sync Now"**.
    -   Jika tidak muncul, Anda bisa klik ikon gajah dengan panah biru (Sync Project with Gradle Files) di toolbar.

6.  **Jalankan Aplikasi**
    -   Pilih perangkat (emulator atau perangkat fisik).
    -   Klik tombol **Run 'app'** (ikon ► hijau).

## 📖 Cara Menggunakan Aplikasi

Alur penggunaan aplikasi ini sangat sederhana:

1.  **Splash Screen**: Saat aplikasi pertama kali dibuka, Anda akan disambut oleh logo aplikasi selama 2 detik.

2.  **Menu Utama**: Setelah itu, Anda akan diarahkan ke menu utama yang berisi dua pilihan:
    -   **Buat & Kelola Chatbot**: Untuk mengatur koleksi persona bot Anda.
    -   **Gunakan Chatbot**: Untuk mulai mengobrol dengan bot yang sudah ada.

3.  **Buat & Kelola Chatbot (CRUD)**
    -   Klik tombol `+` (Floating Action Button) di pojok kanan bawah untuk membuat bot baru.
    -   Isi **Nama Bot** dan **System Prompt**-nya di dialog yang muncul, lalu klik "Simpan".
    -   Bot yang baru Anda buat akan muncul di daftar.
    -   Gunakan tombol **Edit** (ikon pensil) untuk mengubah nama atau prompt bot.
    -   Gunakan tombol **Hapus** (ikon tong sampah) untuk menghapus bot.

4.  **Gunakan Chatbot**
    -   Di menu ini, Anda akan melihat daftar semua bot yang telah Anda buat, ditambah satu bot default bernama "Crypto Assistant (Default)".
    -   Klik pada salah satu kartu bot untuk memulai sesi obrolan.
    -   Halaman chat akan terbuka, dengan judul yang sesuai dengan nama bot yang Anda pilih, dan AI akan merespons sesuai dengan *system prompt* yang telah Anda atur. Selamat mengobrol!
