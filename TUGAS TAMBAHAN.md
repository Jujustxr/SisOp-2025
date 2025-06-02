**NAMA: JULI AYU AUDIA 
NRP: 3124521016
KELAS: IT-A PSDKU-LA**

-----------------

# Contoh Proses
```
Proses | Datang | Burst | Prioritas
P1     |   0    |   4   |    2
P2     |   1    |   3   |    1
P3     |   2    |   1   |    3
```
*Semakin kecil angka prioritas, semakin penting proses tersebut.*



##  Cara Kerja Penjadwalan Prioritas (Preemptive)

- Proses dengan prioritas tertinggi (angka kecil) akan dijalankan lebih dulu.
- Jika ada proses baru yang lebih prioritas, maka proses saat ini dihentikan sementara (preempted).


## Alur Program

1. Ambil input: waktu datang, burst time, dan prioritas setiap proses.
2. Jalankan simulasi detik demi detik.
3. Setiap detik, pilih proses dengan prioritas tertinggi yang sudah datang.
4. Jalankan selama 1 detik, lalu kurangi burst-nya.
5. Jika burst = 0, proses dianggap selesai dan dicatat waktunya.
6. Setelah semua proses selesai, hitung:
   - **Turnaround Time (TAT)** = selesai - datang
   - **Waiting Time (WT)** = TAT - burst awal
7. Hitung rata-rata TAT dan WT.

---

## Gantt Chart Eksekusi
```
| 0 | 1 | 2 | 3 | 4 | 5 | 6 | 7 | 8 |
| P1| P2| P2| P2| P1| P1| P1| P3|   |
```


| Proses | Datang | Burst | Prioritas | Selesai | TAT | WT |
|--------|--------|--------|-----------|---------|-----|----|
| P1     |   0    |   4    |    2      |   7     |  7  | 3  |
| P2     |   1    |   3    |    1      |   4     |  3  | 0  |
| P3     |   2    |   1    |    3      |   8     |  6  | 5  |

###  Rata-rata:
- TAT: **5.33**
- WT: **2.67**

---

## Kode C

```c
#include <stdio.h>

typedef struct {
    int id, arrival, burst, remaining, priority;
    int finish, turnaround, waiting;
} Process;

int main() {
    Process p[3] = {
        {1, 0, 4, 4, 2},
        {2, 1, 3, 3, 1},
        {3, 2, 1, 1, 3}
    };
    int time = 0, completed = 0, n = 3;

    while (completed < n) {
        int chosen = -1;
        for (int i = 0; i < n; i++) {
            if (p[i].arrival <= time && p[i].remaining > 0 &&
               (chosen == -1 || p[i].priority < p[chosen].priority)) {
                chosen = i;
            }
        }
        if (chosen != -1) {
            p[chosen].remaining--;
            if (p[chosen].remaining == 0) {
                p[chosen].finish = time + 1;
                completed++;
            }
        }
        time++;
    }

    float totalTAT = 0, totalWT = 0;
    printf("ID | Finish | TAT | WT\\n");
    for (int i = 0; i < n; i++) {
        p[i].turnaround = p[i].finish - p[i].arrival;
        p[i].waiting = p[i].turnaround - p[i].burst;
        totalTAT += p[i].turnaround;
        totalWT += p[i].waiting;
        printf("P%d |   %d    |  %d  | %d\\n", p[i].id, p[i].finish, p[i].turnaround, p[i].waiting);
    }

    printf("Rata-rata TAT: %.2f\\n", totalTAT / n);
    printf("Rata-rata WT : %.2f\\n", totalWT / n);
    return 0;
}
```

