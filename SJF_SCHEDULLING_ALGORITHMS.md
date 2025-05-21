**NAMA: JULI AYU AUDIA 
NRP: 3124521016
KELAS: IT-A PSDKU-LA**

-----------------

# 1. SJF Without Arrival Time (Non-Preemptive)

   ```c
   #include<stdio.h>
struct proc
{
    int no,bt,ct,tat,wt;
};
struct proc read(int i)
{
    struct proc p;
    printf("\nProcess No: %d\n",i);
    p.no=i;
    printf("Enter Burst Time: ");
    scanf("%d",&p.bt);
    return p;
}
int main()
{
    struct proc p[10],tmp;
    float avgtat=0,avgwt=0;
    int n,ct=0;
    printf("<--SJF Scheduling Algorithm Without Arrival Time (Non-Preemptive)-->\n");
    printf("Enter Number of Processes: ");
    scanf("%d",&n);
    for(int i=0;i<n;i++)
        p[i]=read(i+1);
    for(int i=0;i<n-1;i++)
        for(int j=0;j<n-i-1;j++)    
            if(p[j].bt>p[j+1].bt)
            {
				tmp=p[j];
				p[j]=p[j+1];
				p[j+1]=tmp;
            }
    printf("\nProcessNo\tBT\tCT\tTAT\tWT\tRT\n");
    for(int i=0;i<n;i++)
    {
        ct+=p[i].bt;
		p[i].ct=p[i].tat=ct;
		avgtat+=p[i].tat;
        p[i].wt=p[i].tat-p[i].bt;
        avgwt+=p[i].wt;
        printf("P%d\t\t%d\t%d\t%d\t%d\t%d\n",p[i].no,p[i].bt,p[i].ct,p[i].tat,p[i].wt,p[i].wt);
    }
    avgtat/=n,avgwt/=n;
    printf("\nAverage TurnAroundTime=%f\nAverage WaitingTime=%f",avgtat,avgwt);
}
```
```
<--SJF Scheduling Algorithm Without Arrival Time (Non-Preemptive)-->
Enter Number of Processes: 4

Process No: 1
Enter Burst Time: 2

Process No: 2
Enter Burst Time: 5

Process No: 3
Enter Burst Time: 4

Process No: 4
Enter Burst Time: 4

ProcessNo	BT	CT	TAT	WT	RT
P1		2	2	2	0	0
P3		4	6	6	2	2
P4		4	10	10	6	6
P2		5	15	15	10	10

Average TurnAroundTime=8.250000
Average WaitingTime=4.500000
```
ANALISIS:
Program C ini menunjukkan cara kerja algoritma penjadwalan **Shortest Job First** non-preemptive, dengan asumsi semua proses datang di waktu nol. Program ini dimulai dengan membuat sebuah struktur data untuk menyimpan informasi tiap proses, seperti ID proses, burst time, completion time, turnaround time, dan waiting time.

Fungsi `read` digunakan untuk meminta input dari pengguna, yaitu burst time untuk setiap proses. Pada fungsi `main`, program membaca jumlah total proses dan burst time masing-masing. Lalu, digunakan algoritma bubble sort untuk mengurutkan proses berdasarkan burst time dari yang paling kecil ke yang paling besar. Setelah proses diurutkan, program menghitung completion time untuk setiap proses. Karena arrival time dianggap 0 untuk semua proses, maka turnaround time akan sama dengan completion time. Sedangkan waiting time didapat dari pengurangan antara turnaround time dan burst time.

Terakhir, program akan menampilkan tabel berisi informasi dari setiap proses, serta menghitung rata-rata turnaround time dan rata-rata waiting time dari semua proses.

# 2. SJF With Arrival Time (Non-Preemptive)
```c
#include<stdio.h>
struct proc
{
    int no,at,bt,it,ct,tat,wt;
};
struct proc read(int i)
{
    struct proc p;
    printf("\nProcess No: %d\n",i);
    p.no=i;
    printf("Enter Arrival Time: ");
    scanf("%d",&p.at);
    printf("Enter Burst Time: ");
    scanf("%d",&p.bt);
    return p;
}
int main()
{
    int  n,j,min=0;
    float avgtat=0,avgwt=0;
    struct proc p[10],temp;
    printf("<--SJF Scheduling Algorithm (Non-Preemptive)-->\n");
    printf("Enter Number of Processes: ");
    scanf("%d",&n);
    for(int i=0;i<n;i++)
        p[i]=read(i+1);
    for(int i=0;i<n-1;i++)
        for(j=0;j<n-i-1;j++)    
            if(p[j].at>p[j+1].at)
            {
            temp=p[j];
            p[j]=p[j+1];
            p[j+1]=temp;
            }
    for(j=1;j<n&&p[j].at==p[0].at;j++)
        if(p[j].bt<p[min].bt)
            min=j;
    temp=p[0];
    p[0]=p[min];
    p[min]=temp;
    p[0].it=p[0].at;
    p[0].ct=p[0].it+p[0].bt;
    for(int i=1;i<n;i++)
    {
        for(j=i+1,min=i;j<n&&p[j].at<=p[i-1].ct;j++)
            if(p[j].bt<p[min].bt)
                min=j;
        temp=p[i];
        p[i]=p[min];
        p[min]=temp;
        if(p[i].at<=p[i-1].ct)
            p[i].it=p[i-1].ct;
        else
            p[i].it=p[i].at;
        p[i].ct=p[i].it+p[i].bt;
    }
    printf("\nProcess\t\tAT\tBT\tCT\tTAT\tWT\tRT\n");
    for(int i=0;i<n;i++)
    {
        p[i].tat=p[i].ct-p[i].at;
        avgtat+=p[i].tat;
        p[i].wt=p[i].tat-p[i].bt;
        avgwt+=p[i].wt;
        printf("P%d\t\t%d\t%d\t%d\t%d\t%d\t%d\n",p[i].no,p[i].at,p[i].bt,p[i].ct,p[i].tat,p[i].wt,p[i].wt);
    }
    avgtat/=n,avgwt/=n;
    printf("\nAverage TurnAroundTime=%f\nAverage WaitingTime=%f",avgtat,avgwt);
}
```
```
<--SJF Scheduling Algorithm (Non-Preemptive)-->
Enter Number of Processes: 3

Process No: 1
Enter Arrival Time: 7
Enter Burst Time: 6

Process No: 2
Enter Arrival Time: 2
Enter Burst Time: 4

Process No: 3
Enter Arrival Time: 1
Enter Burst Time: 3

Process		AT	BT	CT	TAT	WT	RT
P3		1	3	4	3	0	0
P2		2	4	8	6	2	2
P1		7	6	14	7	1	1

Average TurnAroundTime=5.333333
Average WaitingTime=1.000000
```
ANALISIS:
Program C ini menjalankan algoritma **Shortest Job First** non-preemptive, tapi kali ini mempertimbangkan arrival time  tiap proses. Setiap proses disimpan dalam sebuah struktur data yang berisi ID proses, arrival time, burst time, start time, completion time, turnaround time, dan waiting time.

Pertama, program meminta input jumlah proses, lalu membaca burst time dan arrival time masing-masing. Setelah itu, proses-proses akan diurutkan berdasarkan arrival time. Kalau ada beberapa proses yang datang di waktu yang sama, maka proses dengan burst time paling kecil yang akan diprioritaskan.

Di bagian utama program (main loop), program akan memilih proses dengan burst time terpendek dari semua proses yang sudah datang sampai saat CPU siap bekerja. Kalau belum ada proses yang datang saat CPU kosong, maka CPU akan menunggu sampai proses berikutnya tersedia.

Untuk setiap proses yang dijalankan, program akan menghitung start time, completion time, turnaround time, dan waiting time. Setelah semua proses dijadwalkan, program menampilkan tabel berisi informasi lengkap tiap proses, lalu menghitung rata-rata turnaround time dan rata-rata waiting time sebagai ringkasan performa penjadwalan.

# 3. SRTF (Preemptive) – Case Example as per PPT
```c
#include<stdio.h>
#define MAX 9999
struct proc
{
    int no,at,bt,rt,ct,tat,wt;
};
struct proc read(int i)
{
    struct proc p;
    printf("\nProcess No: %d\n",i);
    p.no=i;
    printf("Enter Arrival Time: ");
    scanf("%d",&p.at);
    printf("Enter Burst Time: ");
    scanf("%d",&p.bt);
    p.rt=p.bt;
    return p;
}
int main()
{
    struct proc p[10],temp;
    float avgtat=0,avgwt=0;
    int n,s,remain=0,time;
    printf("<--SRTF Scheduling Algorithm (Preemptive)-->\n");
    printf("Enter Number of Processes: ");
    scanf("%d",&n);
    for(int i=0;i<n;i++)
        p[i]=read(i+1);
    for(int i=0;i<n-1;i++)
        for(int j=0;j<n-i-1;j++)    
            if(p[j].at>p[j+1].at)
            {
            temp=p[j];
            p[j]=p[j+1];
            p[j+1]=temp;
            }
    printf("\nProcess\t\tAT\tBT\tCT\tTAT\tWT\n");
    p[9].rt=MAX;
    for(time=0;remain!=n;time++)
    {
        s=9;
        for(int i=0;i<n;i++)
            if(p[i].at<=time&&p[i].rt<p[s].rt&&p[i].rt>0)
                s=i;
        p[s].rt--;
        if(p[s].rt==0)
        {
            remain++;
            p[s].ct=time+1;
            p[s].tat=p[s].ct-p[s].at;
            avgtat+=p[s].tat;
            p[s].wt=p[s].tat-p[s].bt;
            avgwt+=p[s].wt;
            printf("P%d\t\t%d\t%d\t%d\t%d\t%d\n",p[s].no,p[s].at,p[s].bt,p[s].ct,p[s].tat,p[s].wt);
        }
    }
    avgtat/=n,avgwt/=n;
    printf("\nAverage TurnAroundTime=%f\nAverage WaitingTime=%f",avgtat,avgwt);
}
```
```
<--SRTF Scheduling Algorithm (Preemptive)-->
Enter Number of Processes: 4

Process No: 1
Enter Arrival Time: 2
Enter Burst Time: 2

Process No: 2
Enter Arrival Time: 5
Enter Burst Time: 3

Process No: 3
Enter Arrival Time: 8
Enter Burst Time: 5

Process No: 4
Enter Arrival Time: 6
Enter Burst Time: 6

Process		AT	BT	CT	TAT	WT
P1		2	2	4	2	0
P2		5	3	8	3	0
P3		8	5	13	5	0
P4		6	6	19	13	7

Average TurnAroundTime=5.750000
Average WaitingTime=1.750000
```

ANALISIS:
Program C ini mensimulasikan algoritma penjadwalan Shortest Remaining Time First, yaitu versi preemptive dari algoritma SJF. Dalam program ini, setiap proses disimpan dalam sebuah struktur data yang berisi ID proses, arrival time (waktu datang), burst time (lama eksekusi), remaining time (sisa waktu eksekusi yang awalnya sama dengan burst time), completion time (waktu selesai), turnaround time, dan waiting time.

Setelah semua data proses dimasukkan oleh pengguna, program akan mengurutkan proses berdasarkan arrival time. Penjadwalan dilakukan dengan simulasi per satuan waktu menggunakan loop berbasis waktu. Di setiap satuan waktu, program akan mengecek semua proses yang sudah datang, lalu memilih proses dengan sisa waktu eksekusi tersingkat. Kalau ada proses baru yang datang dan punya remaining time lebih pendek dari proses yang sedang berjalan, maka proses yang sedang berjalan langsung dipreempt, dan CPU akan menjalankan proses baru tersebut.

Begitu sebuah proses selesai, program mencatat completion time-nya dan menghitung turnaround time (completion time - arrival time) serta waiting time (turnaround time - burst time).

Di akhir simulasi, program menampilkan tabel lengkap berisi data tiap proses, lalu menghitung dan menampilkan rata-rata turnaround time dan rata-rata waiting time, sehingga memberikan gambaran lengkap tentang performa algoritma SRTF.
