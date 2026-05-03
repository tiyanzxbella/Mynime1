# Panduan Membangun Aplikasi (APK) AnimeKita

Proyek ini sekarang mendukung mode **Web** dan **Aplikasi Android Native**.

## Apakah harus pakai Kotlin?
Sebenarnya tidak wajib jika hanya ingin membuat web, tapi untuk membuat **Aplikasi Android (APK)** yang stabil dan performanya bagus, menggunakan Kotlin (atau Java) di dalam modul Android adalah cara yang paling direkomendasikan.

Saya sudah menyiapkan modul Android lengkap dengan Kotlin agar Anda bisa langsung membuildnya menjadi APK.

---

## Cara Membangun APK

### 1. Menggunakan Acode (dengan plugin Terminal)
Jika Anda menggunakan Acode, pastikan Anda sudah menginstal plugin **AcodeX** atau terminal lainnya.

1.  Buka proyek ini di Acode.
2.  Jalankan perintah ini untuk menyalin file web ke dalam folder aset aplikasi:
    ```bash
    npm run sync-assets
    ```
3.  Jika Anda memiliki plugin build Android, Anda bisa langsung melakukan build. Jika tidak, gunakan cara di bawah ini.

### 2. Menggunakan Android IDE (AIDE atau AndroidIDE)
Ini adalah cara termudah di HP Android:
1.  Buka aplikasi **AndroidIDE** (disarankan daripada AIDE lama).
2.  Buka folder proyek ini.
3.  Tunggu sinkronisasi Gradle selesai.
4.  Klik tombol **Build** atau **Run**.

### 3. Menggunakan Termux
Jika Anda terbiasa dengan baris perintah:
1.  Instal JDK dan Gradlew:
    ```bash
    pkg install openjdk-17
    ```
2.  Sinkronkan aset:
    ```bash
    npm run sync-assets
    ```
3.  Build APK:
    ```bash
    chmod +x gradlew
    ./gradlew assembleDebug
    ```
4.  APK akan ada di: `app/build/outputs/apk/debug/app-debug.apk`

---

## Catatan Penting
- **Pembaruan Web**: Setiap kali Anda mengubah `index.html` atau file CSS/JS, Anda harus menjalankan `npm run sync-assets` lagi agar tampilan di APK ikut berubah.
- **Izin Internet**: Aplikasi sudah dikonfigurasi untuk mengizinkan akses internet agar bisa melakukan streaming anime.

Selamat mencoba!
