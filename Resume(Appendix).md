
# SISTEM OPERASI (INFLUENTIAL OPERATING SYSTEM)

### NAMA:Juli Ayu Audia
### NRP: 3245211016
### KELAS: Informatika-A

---
1.1.	Perkembangan Komputer
Sejarah komputer modern dimulai pada abad ke-20 dengan konsep komputer program tersimpan oleh Alan Turing dan John von Neumann. Pada 1949, Manchester Mark 1 menjadi komputer program tersimpan pertama, diikuti Ferranti Mark 1 pada 1951 sebagai komputer komersial pertama. Komputer awal berukuran besar, dioperasikan manual dengan sakelar, pita kertas, atau kartu berlubang, serta debugging langsung dari konsol. Output dicetak atau disimpan untuk pemrosesan lebih lanjut.
Perkembangan perangkat keras dan lunak memperkenalkan perangkat I/O seperti pembaca kartu, printer, dan pita magnetik. Pemrograman dipermudah dengan perakit, loader, dan kompiler (FORTRAN, COBOL), tetapi proses kompilasi, perakitan, dan pemuatan memperlambat eksekusi. Kesalahan dalam proses ini membuang waktu dan membuat CPU menganggur, mendorong optimalisasi penggunaan komputer.
Untuk meningkatkan efisiensi, sistem batch digunakan untuk mengurangi waktu penyiapan dan pengaturan ulang. Debugging dilakukan dari dump memori dan register. Monitor residen diterapkan untuk mengotomatiskan pengurutan pekerjaan, mentransfer kontrol antar tugas dengan kartu kontrol, penerjemah, loader, dan driver perangkat.
Pada 1950-1960-an, unit pita magnetik menggantikan pembaca kartu dan printer lambat, mengurangi beban komputer utama dan mempercepat pemrosesan. Spooling memungkinkan pemrosesan data tanpa intervensi CPU, menumpang-tindihkan I/O satu pekerjaan dengan komputasi lainnya. Teknik ini menjaga CPU dan perangkat I/O tetap aktif, menjadi dasar multiprogramming dalam sistem operasi modern.
Fitur yang awalnya hanya tersedia pada sistem besar seperti mainframe kini telah diadopsi oleh sistem yang lebih kecil, termasuk komputer mini, mikro, dan perangkat genggam. Contohnya, sistem operasi MULTICS yang dikembangkan antara 1965-1970 di MIT untuk komputer mainframe GE-645 menjadi dasar bagi UNIX, yang dibuat Bell Laboratories pada 1970 untuk komputer mini PDP-11. Pada 1980-an, fitur UNIX diadopsi oleh sistem operasi untuk komputer mikro seperti Microsoft Windows, Windows XP, dan macOS. Linux, yang juga mengadopsi banyak fitur serupa, kini dapat ditemukan di berbagai perangkat, termasuk PDA.

2.1.	Atlas OS
Dikembangkan pada akhir 1950-an hingga awal 1960-an, Atlas OS memperkenalkan demand paging dan manajemen memori dengan drum sebagai penyimpanan utama. Algoritma penggantian halaman mengoptimalkan memori, sementara spooling digunakan untuk pengelolaan tugas.

3.1.	XDS-940 
Dikembangkan di UC Berkeley pada 1960-an, XDS-940 adalah sistem time-sharing dengan paging untuk relokasi memori. Sistem ini mendukung berbagi memori antar proses, pembuatan subproses, serta komunikasi dalam struktur pohon melalui panggilan sistem.
4.1.	THE OS
Dirancang di Belanda pada 1960-an, THE adalah sistem batch berlapis yang menggunakan semaphore, penjadwalan CPU prioritas, paging perangkat lunak, dan algoritma bankir untuk mencegah deadlock. Venus, versi lebih cepatnya, diimplementasikan dalam mikrokode dan mendukung time-sharing.

5.1.	RC 4000 OS
Dikembangkan oleh Regnecentralen pada 1960-an, RC 4000 adalah kernel berlapis dengan proses bersamaan dan penjadwalan round-robin. Komunikasi antarproses menggunakan sistem pesan berbasis buffer dengan operasi atomik untuk sinkronisasi. Perangkat I/O diperlakukan sebagai proses dengan driver menangani interupsi.

6.1.	CTSS OS
Compatible Time-Sharing System (CTSS), dikembangkan di MIT pada 1961 untuk IBM 7090, mendukung hingga 32 pengguna interaktif. Dengan memori 32 KB, sistem ini menukar citra memori pengguna antara RAM dan drum cepat. Penjadwalan CPU menggunakan antrean umpan balik bertingkat yang menyesuaikan kuantum waktu berdasarkan eksekusi program.

7.1.	TOPS-20
Digital Equipment Corporation (DEC) berperan penting dalam sejarah sistem operasi dengan VMS dan TOPS-20. Berawal dari proyek TENEX, TOPS-20 menjadi sistem time-sharing populer di DECSYSTEM-20 karena fiturnya yang canggih dan harga terjangkau. Namun, DEC menghentikan pengembangannya untuk fokus pada VAX dan VMS, yang tetap relevan hingga kini sebagai OpenVMS.

8.1.	CP/M dan MS-DOS
Komputer rumahan awal hanya menjalankan satu program sekaligus. CP/M, dikembangkan oleh Gary Kildall, menjadi standar OS pada 1970-an. IBM kemudian memilih MS-DOS buatan Bill Gates, yang serupa dengan CP/M tetapi lebih kaya fitur. MS-DOS menjadi sistem operasi utama komputer pribadi, meski terbatas dalam fitur modern seperti memori terlindungi.

9.1.	MULTICS
Dikembangkan oleh MIT, GE, dan Bell Labs (1965–1970) sebagai penerus CTSS, MULTICS adalah sistem time-sharing berkelanjutan dengan sistem berkas bertingkat. Berjalan di GE 645, menggunakan memori segmentasi-halaman dengan alamat virtual berbasis segmen 18-bit dan offset 16-bit. Penjadwalan CPU memakai antrean umpan balik bertingkat, dengan perlindungan daftar akses dan cincin perlindungan. Ditulis dalam PL/1 dengan 300.000 baris kode, MULTICS mendukung multiprosesor dan pemeliharaan CPU tanpa menghentikan sistem.

10.1.	IBM OS/360
IBM OS/360 dirancang untuk menyatukan berbagai tipe komputer, namun menghadapi tantangan kompleksitas dan efisiensi. Memori virtual pada IBM/370 melahirkan OS/VS1 dan OS/VS2, yang berkembang menjadi MVS. Proyek seperti TSS/360 dan MULTICS gagal, tetapi pembagian waktu berhasil melalui CMS dan MVS. Seiring berkembangnya komputer pribadi, ketergantungan pada sistem besar berkurang, membawa komputasi lebih dekat ke pengguna akhir.

11.1.	Macintosh, Windows, dan Mach
Pada 1984, Apple Macintosh memperkenalkan GUI untuk pengguna rumahan, diikuti oleh Microsoft Windows pada 1985 dengan lisensi lebih luas. Seiring hadirnya CPU 32-bit dan memori terlindungi, komputer pribadi semakin canggih. Persaingan Apple dan Microsoft terus berlanjut, sementara Linux berkembang di kalangan teknis.
Sementara itu, Mach, dikembangkan di Carnegie Mellon pada 1980, dirancang untuk mendukung multiprosesing dan komputasi paralel dengan mikrokernel. Mach menjadi dasar OSF/1 (1989) dan kini digunakan dalam kernel XNU untuk macOS serta iOS.

12.1.	HYDRA & CAP
Hydra memungkinkan pengelolaan hak akses fleksibel dengan amplifikasi hak oleh prosedur tepercaya, sementara CAP menawarkan pendekatan lebih sederhana dengan dua jenis kapabilitas: data dan perangkat lunak. CAP menghemat sumber daya tetapi memerlukan pemahaman mendalam karena tidak menyediakan pustaka prosedur bawaan.

