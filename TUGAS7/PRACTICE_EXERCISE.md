**NAMA: JULI AYU AUDIA**

**NRP:  3124521016**

**KELAS: TEKNIK INFORMATIKA A** 

----------
#### 4.1 Provide three programming examples in which multithreading provides better performance than a single-threaded solution.

##### => Web Server,  Web server multithreaded dapat menangani banyak permintaan klien secara paralel, sementara single-thread hanya bisa melayani satu permintaan dalam satu waktu. 
##### => Aplikasi GUI (Graphical User Interface),  Dengan thread terpisah untuk logika latar belakang (misalnya download file) dan untuk tampilan, aplikasi jadi lebih responsif. 
##### => Proses Komputasi Paralel (seperti sorting besar atau matrix multiplication), Tugas besar bisa dibagi ke beberapa thread untuk diproses paralel, mempercepat eksekusi dibanding satu thread.

#### 4.2 Using Amdahl’s Law, calculate the speedup gain of an application that has a 60 percent parallel component for (a) two processing cores and (b) four processing cores.

$$
\text{Speedup} = \frac{1}{(1-P) + \frac{P}{N}}
$$

Dengan:
*   $P = 0.6$ (60% paralel)
*   $N =$ jumlah core

(a) $N = 2$:
$$
\text{Speedup} = \frac{1}{(1-0.6) + \frac{0.6}{2}} = \frac{1}{0.4 + 0.3} = \frac{1}{0.7} \approx 1.43
$$

(b) $N = 4$:
$$
\text{Speedup} = \frac{1}{(1-0.6) + \frac{0.6}{4}} = \frac{1}{0.4 + 0.15} = \frac{1}{0.55} \approx 1.82
$$

#### 4.3 Does the multithreaded web server described in Section 4.1 exhibit task or data parallelism?
##### Menggunakan task parallelism, karena tiap thread menangani request yang berbeda dari klien. Tugasnya berbeda-beda, meskipun jenisnya serupa.

#### 4.4  What are two differences between user-level threads and kernel-level threads? Under what circumstances is one type better than the other?
##### User-Level Thread itu dikelola di user space, jadi lebih cepat untuk pindah antar thread-nya tanpa perlu panggilan ke kernel. Tapi, kelemahannya, thread ini tidak bisa jalan paralel di sistem multicore karena kernel cuma mengenali satu thread aja. Sementara itu, Kernel-Level Thread dikelola langsung oleh sistem operasi di ruang kernel (kernel space). Karena itu, thread ini bisa jalan paralel di multicore karena kernel tahu semua thread yang ada. Walaupun switching antar thread-nya lebih lambat karena butuh konteks-switching di kernel, Kernel-Level Thread lebih cocok untuk sistem multicore dan saat blocking I/O sering terjadi. Secara keseluruhan, User-Level Thread lebih efisien di sistem single-core, sementara Kernel-Level Thread lebih diuntungkan di sistem multicore dan saat ada masalah dengan blocking I/O.

#### 4.5 Describe the actions taken by a kernel to context-switch between kernel-level threads.
##### Proses ini melibatkan beberapa langkah penting dalam pengelolaan thread oleh sistem. Pertama, sistem akan menyimpan konteks seperti register, counter, stack pointer, dan lainnya dari thread yang sedang berjalan. Setelah itu, status thread yang sedang berjalan diperbarui dalam tabel thread/kernel untuk mencatat perubahan kondisi thread tersebut. Kemudian, scheduler akan memilih thread berikutnya yang akan dijalankan. Setelah thread baru dipilih, sistem akan memuat konteks dari thread tersebut, yang berisi data dan status yang diperlukan untuk melanjutkan eksekusinya. Akhirnya, eksekusi thread yang baru dipilih pun dimulai, dan sistem kembali menjalankan thread tersebut sesuai dengan konteks yang telah dimuat.

#### 4.6 What resources are used when a thread is created? How do they differ from those used when a process is created?
##### Thread membutuhkan stack, register, program counter, dan thread ID sendiri, tapi berbagi memori, file descriptor, dan data lainnya dengan thread lain dalam satu proses. Sementara itu, proses membutuhkan sumber daya baru seperti memori, file, dan tabel proses. Karena itu, thread lebih ringan daripada proses, membuat pembuatan dan switching-nya lebih efisien.

#### 4.7 Assume that an operating system maps user-level threads to the kernel using the many-to-many model and that the mapping is done through LWPs. Furthermore, the system allows developers to create real-time threads for use in real-time systems. Is it necessary to bind a real-time thread to an LWP? Explain.
##### Benar. Untuk thread real-time, waktu eksekusinya sangat penting. Dengan mengikat thread ke LWP (Lightweight Process), kita memastikan thread tersebut memiliki jalur langsung ke kernel, memungkinkan sistem untuk menjadwalkannya secara real-time. Tanpa pengikatan ini, thread real-time bisa tertunda oleh thread lain, karena kernel tidak mengenal thread tersebut sebagai prioritas tinggi.
