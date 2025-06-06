<div align="center">
  <h1>TUGAS SISTEM OPERASI</h1>
  <h2><strong>SISTEM BILANGAN</strong></h2>
  <img src="https://belajargiat.id/wp-content/uploads/2020/10/logo-PENS.png" alt="Pens Logo" width="350"><br>
  <h3><strong>Dosen Pengampu:</strong><br>
  Dr. Ferry Astika Saputra, S.T., M.Sc.</h3>
  <h3><strong>Disusun Oleh:</strong><br>
  Juli Ayu Audia (3124521016)</h3><br>
  <h2><strong>PROGRAM STUDI D3 TEKNIK INFORMATIKA PSDKU LAMONGAN</strong><br>
  DEPARTEMEN TEKNIK INFORMATIKA DAN KOMPUTER<br>
  POLITEKNIK ELEKTRONIKA NEGERI SURABAYA<br>
  2025</h2>
</div>




------



> [!NOTE]
>
> Here is the doc file for the full version of this.
>
> [Click here!](https://1drv.ms/w/c/b00abd963fc2cec9/EUysYPiAQTlJvBNjUmv7gIMBrn4ZRTGryTY1jMGMiENnPQ?e=W7ORzE)





## 1. Basis Bilangan

```
a. Bilangan biner adalah bilangan yang berbasis dua (2).
```



## 2. Konversi Bilangan Desimal ke Biner

a. 1234₁₀ → 10011010010₂
| Pembagian  | Hasil | Sisa |
|:----------:|:-----:|:-----:|
| 1234 ÷ 2   |  617  |    0  |
| 617 ÷ 2    |  308  |    1  |
| 308 ÷ 2    |  154  |    0  |
| 154 ÷ 2    |   77  |    0  |
| 77 ÷ 2     |   38  |    1  |
| 38 ÷ 2     |   19  |    0  |
| 19 ÷ 2     |    9  |    1  |
| 9 ÷ 2      |    4  |    1  |
| 4 ÷ 2      |    2  |    0  |
| 2 ÷ 2      |    1  |    0  |
| 1 ÷ 2      |    0  |    1  |



## 3. Konversi Bilangan Biner ke Desimal

a. 10101010₂ → 170₁₀
| Biner     | Posisi (Pangkat 2) | Perhitungan |
|:---------:|:-----------------:|:-----------:|
| 1         | 2⁷ (128)           | 1 × 128 = 128 |
| 0         | 2⁶ (64)            | 0 × 64 = 0 |
| 1         | 2⁵ (32)            | 1 × 32 = 32 |
| 0         | 2⁴ (16)            | 0 × 16 = 0 |
| 1         | 2³ (8)             | 1 × 8 = 8 |
| 0         | 2² (4)             | 0 × 4 = 0 |
| 1         | 2¹ (2)             | 1 × 2 = 2 |
| 0         | 2⁰ (1)             | 0 × 1 = 0 |
| **Total** |                   | **170** |



## 4. Konversi Bilangan Biner ke Oktal

a. 101 011 111 001₂ → 5371₈
| Biner               | Kalkulasi          | Hasil |
|:-------------------:|:--------------------------:|:-----:|
| (1×2²) + (0×2¹) + (1×2⁰) | (1×4) + (0×2) + (1×1) | 5     |
| (0×2²) + (1×2¹) + (1×2⁰) | (0×4) + (1×2) + (1×1) | 3     |
| (1×2²) + (1×2¹) + (1×2⁰) | (1×4) + (1×2) + (1×1) | 7     |
| (0×2²) + (0×2¹) + (1×2⁰) | (0×4) + (0×2) + (1×1) | 1     |



## 5. Konversi Bilangan Oktal ke Biner

a. 2170₈ → 010 001 111 000₂
| Oktal | Biner (3-bit) |
|:-----:|:------------:|
| 2     | 010          |
| 1     | 001          |
| 7     | 111          |
| 0     | 000          |



## 6. Konversi Bilangan Desimal ke Heksadesimal

a. 1780₁₀ → 06F4₁₆
| Pembagian    | Hasil | Sisa | Heksadesimal |
|:-----------:|:-----:|:----:|:-----------:|
| 1780 ÷ 16   |   111 |    4 | 4           |
| 111 ÷ 16    |     6 |   15 | F           |
| 6 ÷ 16      |     0 |    6 | 6           |
| **Final Hex** |       |      | **06F4**    |



## 7. Konversi Bilangan Heksadesimal ke Desimal
a. ABCD₁₆ → 43981₁₀
| Heksadesimal | Desimal | Posisi (pangkat 16) | Perkalian          |
|:-----------:|:------:|:------------------:|:------------------:|
| A           | 10     | 4096               | 10 × 4096 = 40960  |
| B           | 11     | 256                | 11 × 256 = 2816    |
| C           | 12     | 16                 | 12 × 16 = 192      |
| D           | 13     | 1                  | 13 × 1 = 13        |
| **Total**   |        |                    | **43981**          |



## 8. Konversi Bilangan Pecahan Desimal ke Biner

a. 0,3125₁₀ → 0,0101₂
| Desimal     | Hasil  | Bil. Bulat |
|:----------:|:------:|:----------:|
| 0,3125 × 2 | 0,625  | 0         |
| 0,625 × 2  | 1,250  | 1         |
| 0,250 × 2  | 0,500  | 0         |
| 0,500 × 2  | 1,000  | 1         |



## 9. Konversi Bilangan Desimal ke Biner

a. 11,625₁₀ → 1011,101₂
| Pembagian | Hasil | Sisa |
|:---------:|:-----:|:----:|
| 11 ÷ 2    | 5     | 1   |
| 5 ÷ 2     | 2     | 1   |
| 2 ÷ 2     | 1     | 0   |
| 1 ÷ 2     | 0     | 1   |



## 10. Konversi Bilangan Desimal ke Heksadesimal

a. 348,654₁₀ → 15C,A78₁₆
#### **Bilangan Bulat**
| Pembagian  | Hasil | Sisa | Heksadesimal |
|:----------:|:-----:|:----:|:-----------:|
| 348 ÷ 16   |  21   |  12  | C           |
| 21 ÷ 16    |   1   |   5  | 5           |
| 1 ÷ 16     |   0   |   1  | 1           |
| **Final Hex** |      |      | 15C₁₆  |

#### **Bilangan Pecahan**
| Perkalian   | Hasil  | Heksadesimal |
|:----------:|:-----:|:-----------:|
| 0,654 × 16 | 10,464 | A           |
| 0,464 × 16 |  7,424 | 7           |
| 0,424 × 16 |  6,724 | 8           |
| **Final Hex** |      | **A78₁₆**  |



## 11. Konversi Bilangan ke Desimal

a. 010100011,001111101₂ → 163,245₁₀
### Bilangan Bulat
| Biner Expression                                   | Perhitungan                     | Hasil |
|---------------------------------------------------|--------------------------------|-------|
| (0×2⁸) + (1×2⁷) + (0×2⁶) + (1×2⁵) + (0×2⁴) + (0×2³) + (1×2²) + (1×2⁰) | (128) + (0) + (32) + (0) + (0) + (0) + (2) + (1) | 163   |
### Bilangan Pecahan
| Biner Expression                                  | Perhitungan                              | Hasil        |
|--------------------------------------------------|------------------------------------------|-------------|
| (0×2⁻¹) + (0×2⁻²) + (1×2⁻³) + (1×2⁻⁴) + (1×2⁻⁵) + (1×2⁻⁶) + (1×2⁻⁷) + (0×2⁻⁸) + (1×2⁻⁹) | (0) + (0.125) + (0.0625) + (0.03125) + (0.015625) + (0.0078125) + (0) + (0.001953125) | 0.244140625 ≈ 0.245 |



## 12. Konversi Bilangan Biner ke BCD

a. 10100110000111₂ → 2987 (BCD)
| Biner Expression | Perhitungan                    | Hasil |
|-----------------|--------------------------------|-------|
| (1×2¹³) + (0×2¹²) + (1×2¹¹) + (0×2¹⁰) + (0×2⁹) + (1×2⁸) + (1×2⁷) + (0×2⁶) + (0×2⁵) + (0×2⁴) + (0×2³) + (0×2²) + (1×2¹) + (1×2⁰) | 8192 + 2048 + 256 + 128 + 7 | 2987 |


#### **Konversi Desimal ke BCD**
| Desimal | BCD   |
|:-------:|:----:|
| 2       | 0010 |
| 9       | 1001 |
| 8       | 1000 |
| 7       | 0111 |



## 13. Rubahlah bentuk BCD di bawah ini ke dalam bilangan biner

 a. 1987 → 1 1001 1000 0111
| BCD    | Desimal |
|:------:|:-------:|
| 0001   | 1      |
| 1001   | 9      |
| 1000   | 8      |
| 0111   | 7      |
| **Final Desimal** | **1987** |



## 14. Rubahlah bilangan biner di bawah ini ke dalam BCO.

a. 111111010012 → 3751
| Biner | Oktal |
|:-----:|:-----:|
| 011   | 3    |
| 111   | 7    |
| 101   | 5    |
| 001   | 1    |



## 15. Rubahlah bilangan biner di bawah ini ke dalam BCH

a. 11011111001011102 → CF2E
| Biner  | BCH  |
|:------:|:----:|
| 1101   | D   |
| 1111   | F   |
| 0010   | 2   |
| 1110   | E   |



## 16. Rubahlah Bentuk BCH di bawah ini ke dalam bilangan heksadesimal

a. F0DE → 1111 0000 1101 1110
| Heksadesimal | Biner  |
|:-----------:|:------:|
| F = 15      | 1111  |
| 0           | 0000  |
| D = 13      | 1101  |
| E = 14      | 1110  |



## 17. Nyatakan positip atau negatip bilangan biner di bawah ini

01111111 → Positip 127
| Biner Expression                             | Perhitungan                    | Hasil |
|---------------------------------------------|--------------------------------|------:|
| (0×2⁷) + (1×2⁶) + (1×2⁵) + (1×2⁴) + (1×2³) + (1×2²) + (1×2¹) + (1×2⁰) | 0 + 64 + 32 + 16 + 8 + 4 + 2 + 1 | 127   |



## 18. Nyatakan bilangan biner negatip di bawah ini ke dalam bilangan decimal

a. 10001000 → -120

| Biner Asli  | Inversi (1's Complement) | Tambah 1 (2's Complement) | Hasil  |
|:-----------:|:-----------------------:|:-------------------------:|--------|
| 10001000    | 01110111                 | 01110111 + 1 = 01111000  | -120 |

*n. cari two complement dahulu.*



## 19. Nyatakan ASCII Code di bawah ini dalam bentuk karakter

a. 4116 → A
| Heksadesimal | Perhitungan                    | Hasil (Desimal) | Karakter ASCII |
|:-----------:|:------------------------------:|:--------------:|:-------------:|
| 4116        | (4 × 16¹) + (1 × 16⁰)         | 65             | A             |



## 20. Nyatakan Karakter di bawah ini dalam ASCII code

a. a → 6116
| Karakter | Desimal | Perhitungan           | Heksadesimal |
|:--------:|:-------:|:---------------------:|:------------:|
| a        | 97      | 97 ÷ 16 = 6 sisa 1    | 61₁₆        |



## 21. Dengan Keyboard standard ASCII, pada layar monitor nampak tulisan sebagai berikut:

PRINT X 
Nyatakan Keluaran pada Keyboard tersebut.
→  P (101 0000); R (101 0010); I (100 1001); N (100 1110) T (101 0100); space ( 010 0000); X (101 1000)
| Karakter | ASCII (Decimal) | ASCII (Biner)  |
|:--------:|:--------------:|:--------------:|
| P        | 80            | 1010000        |
| R        | 82            | 1010010        |
| I        | 73            | 1001001        |
| N        | 78            | 1001110        |
| T        | 84            | 1010100        |
| Space    | 32            | 0100000        |
| X        | 88            | 1011000        |

