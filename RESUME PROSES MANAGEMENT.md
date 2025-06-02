**NAMA: JULI AYU AUDIA 
NRP: 3124521016
KELAS: IT-A PSDKU-LA**

---------------------------------


## Transisi Mode Pengguna ke Mode Kernel
Perpindahan dari mode user ke mode kernel terjadi saat:
- Program meminta layanan sistem operasi.
- Perangkat keras memberi interupsi (contohnya klik mouse).
- Terjadi kesalahan seperti pembagian dengan nol.

---

## Manajemen Proses
- **Proses** adalah program yang sedang berjalan (aktif).
- Sistem bisa memiliki banyak proses aktif (multi-tasking).
- **Single-threaded**: satu alur eksekusi.
- **Multi-threaded**: banyak alur eksekusi dalam satu proses.

**Tugas OS dalam manajemen proses:**
- Membuat dan menghapus proses.
- Menangguhkan dan melanjutkan proses.
- Sinkronisasi dan komunikasi antar proses.
- Menangani kondisi deadlock.

---

## Manajemen Memori
Agar program dapat berjalan, instruksi dan data harus berada di memori.

**Tugas OS:**
- Melacak penggunaan memori.
- Memutuskan proses/data mana yang masuk atau keluar dari memori.
- Mengalokasikan dan membebaskan ruang memori sesuai kebutuhan.

---

## Manajemen File
OS menyediakan cara standar untuk menyimpan dan mengakses data di perangkat penyimpanan.

**Tugas OS:**
- Membuat dan menghapus file dan direktori.
- Memberi akses ke file sesuai izin.
- Memetakan file ke penyimpanan.
- Mencadangkan file ke media non-volatile.

---

## Manajemen Penyimpanan
Disk digunakan untuk menyimpan data yang tidak muat di RAM atau untuk penyimpanan jangka panjang.

**Tugas OS:**
- Mengatur ruang kosong.
- Mengelola alokasi penyimpanan.
- Menjadwalkan akses disk agar efisien.

---

## Caching (Penyimpanan Sementara)
Cache menyimpan data penting secara sementara untuk mempercepat akses.

**Cara kerja:**
- Data dicek di cache terlebih dahulu.
- Jika ditemukan, langsung digunakan.
- Jika tidak, diambil dari penyimpanan utama lalu disimpan ke cache.


