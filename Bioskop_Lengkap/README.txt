<div align="center">

# 🎬 BIOSKOP KIRA

### *Your Movie, Your Seat, Your Moment.*

**A simple cinema ticket booking system built with Java.**

![Java](https://img.shields.io/badge/Java-17%2B-ED8B00?style=for-the-badge&logo=openjdk&logoColor=white)
![Interface](https://img.shields.io/badge/Interface-CLI-24292e?style=for-the-badge)
![Project](https://img.shields.io/badge/Project-Pemrograman%20Dasar-8B5CF6?style=for-the-badge)

*Pilih film favoritmu, tentukan kursi, dan selesaikan pemesanan dalam satu aplikasi terminal.*

---

**[Tentang](#-tentang-proyek) · [Fitur](#-fitur-utama) · [Cara Menjalankan](#-cara-menjalankan) · [Struktur](#-struktur-proyek) · [Konsep Java](#-konsep-java-yang-diterapkan)**

</div>

## ✨ Tentang Proyek

**Bioskop Kira** adalah aplikasi pemesanan tiket bioskop berbasis **Java Console / Command-Line Interface (CLI)**. Proyek ini dibuat sebagai latihan penerapan dasar-dasar Java dan *Object-Oriented Programming* (OOP), terutama **class, object, constructor, method, encapsulation**, dan **information hiding**.

Pengguna dapat memilih studio, film, jadwal, dan kursi, lalu memilih metode pembayaran. Setelah pembayaran dikonfirmasi secara simulasi, sistem menampilkan struk lengkap dengan waktu pembayaran dalam **WIB (Asia/Jakarta)**.

> [!NOTE]
> Aplikasi ini merupakan **simulasi untuk pembelajaran**, bukan sistem pembayaran atau pemesanan bioskop sungguhan.

## 🌟 Fitur Utama

| Fitur | Deskripsi |
|:--|:--|
| 🎞️ Katalog film | Menampilkan 5 pilihan film beserta genre dan durasi |
| 🏢 Pilihan studio | Menyediakan 5 studio dengan informasi kapasitas |
| 🕒 Jadwal tayang | Pilihan jam **10.00, 13.00, 16.00, 19.00 WIB** |
| 💺 Pemilihan kursi | Memilih kursi **A1–A10** dan mengecek ketersediaan |
| 🎟️ Pemesanan tiket | Membuat ID tiket otomatis dan mencetak detail pemesanan |
| 💳 Metode pembayaran | Pilihan **Tunai, Transfer Bank, atau QRIS** (simulasi) |
| ✅ Status pembayaran | Mencatat status *Belum Dibayar* / *Lunas* |
| 📅 Waktu transaksi | Mencatat hari, tanggal, dan jam pembayaran dalam WIB |
| 🧾 Struk transaksi | Merangkum film, studio, jadwal, kursi, serta pembayaran |

## 🖥️ Preview Program

```text
========== BIOSKOP KIRA ==========
1. Pesan Tiket
2. Lihat Daftar Studio
0. Keluar
Pilih menu: 1

--- PILIH STUDIO ---
1. ID Studio: 1
   Nama Studio: Studio 1
   Kapasitas: 30 Kursi

--- PILIH FILM ---
1. Interstellar | Sci-Fi | 169 menit
2. Inside Out 2 | Animasi | 96 menit
...

--- PILIH JADWAL ---
1. 10:00 WIB - Rp 35.000
2. 13:00 WIB - Rp 45.000
3. 16:00 WIB - Rp 45.000
4. 19:00 WIB - Rp 50.000

--- PILIH KURSI ---
A1 [O]  A2 [O]  A3 [O]  A4 [O]  A5 [O]
A6 [O]  A7 [O]  A8 [O]  A9 [O]  A10 [O]

--- METODE PEMBAYARAN ---
1. Tunai
2. Transfer Bank
3. QRIS
```

`O` = tersedia · `X` = sudah terisi

## 🚀 Cara Menjalankan

### Persyaratan

- **Java Development Kit (JDK)** yang mendukung `java.time` (disarankan **JDK 17 atau lebih baru**)
- Terminal / Command Prompt atau **Visual Studio Code** dengan ekstensi Java

### Langkah-langkah

**1.** Unduh dan ekstrak ZIP proyek, lalu buka folder berisi file-file `.java`.

**2.** Buka terminal di folder tersebut dan kompilasi:

```bash
javac *.java
```

**3.** Jalankan program:

```bash
java Main
```

**4.** Ikuti menu interaktif yang muncul di terminal.

> [!TIP]
> Di **VS Code**, buka `Main.java` dan gunakan tombol **Run Java** apabila Java Extension Pack sudah terpasang. Semua file `.java` ditempatkan dalam folder yang sama dan menggunakan **default package**.

## 🗂️ Struktur Proyek

```text
Bioskop_Kira_Lengkap/
│
├── Main.java               # Menu utama dan alur pemesanan
├── Studio.java             # Data studio dan kapasitas
├── Film.java               # Informasi film
├── jadwalFilm.java         # Tanggal, jam, dan harga tayang
├── kursi.java              # Pemilihan dan status kursi
├── tiket.java              # Pemesanan dan detail tiket
├── Pembayaran.java         # Metode dan nominal pembayaran
├── StatusPembayaran.java   # Status dan waktu pembayaran
└── README.md               # Dokumentasi proyek
```

## 🔄 Alur Pemesanan

```mermaid
flowchart TD
    A([Mulai]) --> B[Menu Utama]
    B --> C{Pilih Menu}
    C -->|Lihat Studio| D[Daftar Studio]
    D --> B
    C -->|Pesan Tiket| E[Pilih Studio dan Film]
    E --> F[Pilih Jadwal]
    F --> G[Pilih Kursi]
    G --> H{Kursi Tersedia?}
    H -->|Tidak| B
    H -->|Ya| I[Pesan Tiket]
    I --> J[Pilih Metode Pembayaran]
    J --> K{Konfirmasi?}
    K -->|Batalkan| B
    K -->|Bayar - Simulasi| L[Catat Status Lunas dan Waktu]
    L --> M[Cetak Struk]
    M --> B
    C -->|Keluar| N([Selesai])
```

## ☕ Konsep Java yang Diterapkan

| Konsep | Penerapan |
|:--|:--|
| **Class & Object** | `Film`, `Studio`, `tiket`, `Pembayaran`, dan class lainnya |
| **Constructor** | Inisialisasi objek film, studio, tiket, serta pembayaran |
| **Constructor Overloading** | Dua constructor pada `jadwalFilm` |
| **Encapsulation** | Atribut `private` dan akses melalui method |
| **Information Hiding** | Data internal tidak diakses secara langsung dari `Main` |
| **Getter & Setter** | Contohnya `getHarga()`, `getStatus()`, `setHarga()` |
| **Array 1D** | Daftar film, daftar studio, jam tayang, dan harga |
| **Array Multidimensi** | `boolean[][][] kursiTerisi` untuk status kursi |
| **Percabangan** | `if` / `else` untuk menu, pilihan, dan validasi |
| **Perulangan** | `while` serta `for` untuk menu dan daftar pilihan |
| **Method & Return Value** | Contohnya `cekKetersediaan()` dan `getTotalBayar()` |
| **Exception Handling** | `try-catch` saat membaca input angka |
| **Date & Time API** | `LocalDate`, `LocalDateTime`, `ZoneId`, `DateTimeFormatter` |

**Tentang method overloading:** versi ZIP yang didokumentasikan di sini **belum menyertakan** overload `cetakTiket(String namaPembeli)` pada `tiket.java`. Jika perubahan tersebut sudah ditambahkan ke kode, bagian tabel ini bisa diperbarui dengan **Method Overloading**.

## 📌 Catatan Pengembangan

- Status kursi hanya tersimpan **selama program berjalan**; belum tersimpan ke database.
- Kursi yang dapat dipilih saat ini adalah **A1 sampai A10**, meskipun kapasitas studio ditampilkan lebih besar.
- Status kursi dibedakan berdasarkan **studio dan jam tayang**, belum menggunakan tanggal dan film sebagai kunci yang lengkap.
- Metode pembayaran hanya **simulasi konfirmasi**; tidak ada transaksi uang sungguhan atau integrasi payment gateway.
- Tanggal tayang ditetapkan berdasarkan **tanggal saat program dijalankan** dalam zona WIB.
- Proyek ini menggunakan Java CLI, **belum menggunakan GUI atau JavaFX**.

## 🛠️ Ide Pengembangan Berikutnya

- Menambahkan **database** untuk menyimpan riwayat pemesanan.
- Menambahkan **identitas pembeli** dan *method overloading* saat mencetak tiket.
- Memperluas denah kursi sesuai kapasitas studio.
- Membuat antarmuka grafis menggunakan **JavaFX**.
- Menyempurnakan validasi tiket, pembayaran, tanggal, dan sesi penayangan.

---

<div align="center">

### 🍿 Enjoy the Show!

*Made with Java, logic, and a little bit of movie magic.*

**BIOSKOP KIRA — Java Console Project**

</div>
