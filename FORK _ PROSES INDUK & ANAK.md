**NAMA: JULI AYU AUDIA**
**NRP:  3124521016**
**KELAS: TEKNIK INFORMATIKA -A** 

----------------

Pada sistem operasi UNIX/Linux, `fork()` adalah sistem call penting yang digunakan untuk menciptakan proses baru. Saat dipanggil, `fork()` akan menggandakan proses yang sedang berjalan (induk), menghasilkan satu proses baru (anak) yang identik. Keduanya akan berjalan bersamaan setelah titik pemanggilan `fork()`.

Cara membedakan proses induk dan anak adalah melalui nilai kembalian dari `fork()`:
-   **0**: Proses saat ini adalah proses anak.
    
-   **Positif**: Proses induk, dengan nilai tersebut adalah PID dari anak.
- **-1**: Proses gagal dibuat.

## Contoh Penggunaan Fork
```c
#include <stdio.h>
#include <unistd.h>

int main() {
    fork();
    printf("Hello world %d\n", getpid());
    return 0;
}
```
Program di atas akan mencetak dua baris karena dua proses (induk dan anak) menjalankan perintah `printf()`.

## 3. Penjelasan Program dan Struktur Proses

### **1. fork01.cpp**

Program ini tidak menggunakan `fork()`. Hanya satu proses yang aktif dan mencetak ID proses, ID induk, serta UID pemilik. Proses dilakukan 3 kali dengan jeda 3 detik.

```
    [Shell] → [fork01]
```
### **2. fork02.cpp**
Menggunakan `fork()` untuk menduplikasi proses. Kedua proses mencetak PID dan nilai `x` yang meningkat tiap 2 detik. Nilai `x` pada masing-masing proses berjalan sendiri-sendiri.

```
[Shell] → [Parent] → [Child]
```

### **3. fork03.cpp**
`fork()` dijalankan sebelum perulangan. Hasilnya, baik proses induk maupun anak akan mencetak PID masing-masing selama lima kali.

```
[Shell] → [Parent] → [Child]
```

### **4. fork04.cpp**
Program ini memperkenalkan `wait()`, yang membuat proses induk menunggu anak selesai sebelum keluar. Proses anak mencetak PID dan keluar terlebih dahulu.

```
[Shell] → [Parent] → [Child (exit)] → [Parent (selesai)]
```

### **5. fork05.cpp**
Child menjalankan program eksternal `/bin/ls` menggunakan `execl()`. Proses induk menunggu hingga proses anak selesai. Jika `execl()` berhasil, kode setelahnya di proses anak tidak dijalankan.

```
[Shell] → [Parent] → [Child (ls -l /home)] → [Parent (selesai)]
```

### **6. fork06.cpp**

Mirip dengan `fork05.cpp`, namun program eksternal yang dijalankan adalah `fork03`. `execl("fork03", "goose", NULL)` menggantikan proses anak. Parent tetap menunggu hingga selesai.

```
[Shell] → [Parent] → [Child (fork03)] → [Parent (selesai)]
```



