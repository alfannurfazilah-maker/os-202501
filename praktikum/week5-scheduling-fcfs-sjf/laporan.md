
# Laporan Praktikum Minggu 5
Topik: Penjadwalan CPU – FCFS dan SJF
---

## Identitas
- **Nama**  : Alfan Nur Fadzilah  
- **NIM**   : 250320575
- **Kelas** : 1DSRA

---

## Tujuan
1. Menghitung waiting time dan turnaround time untuk algoritma FCFS dan SJF.
2. Menyajikan hasil perhitungan dalam tabel yang rapi dan mudah dibaca.
3. Membandingkan performa FCFS dan SJF berdasarkan hasil analisis.
4. Menjelaskan kelebihan dan kekurangan masing-masing algoritma.
5. Menyimpulkan kapan algoritma FCFS atau SJF lebih sesuai digunakan.

---

## Dasar Teori
Penjadwalan CPU adalah proses menentukan urutan eksekusi proses agar CPU digunakan efisien. Pada FCFS (First Come, First Served), proses yang datang lebih dulu dijalankan lebih dulu, bersifat non-preemptive, sederhana namun bisa menyebabkan proses lama membuat proses cepat menunggu (convoy effect). Sedangkan SJF (Shortest Job First) menjalankan proses dengan waktu eksekusi paling singkat lebih dulu, dapat bersifat preemptive atau non-preemptive, efisien karena waktu tunggu rata-rata kecil, tetapi sulit diterapkan karena perlu tahu lama proses dan bisa menyebabkan starvation.

---

## Langkah Praktikum
1. **Siapkan Data Proses**
   Gunakan tabel proses berikut sebagai contoh (boleh dimodifikasi dengan data baru):
   | Proses | Burst Time | Arrival Time |
   |:--:|:--:|:--:|
   | P1 | 6 | 0 |
   | P2 | 8 | 1 |
   | P3 | 7 | 2 |
   | P4 | 3 | 3 |

2. **Eksperimen 1 – FCFS (First Come First Served)**
   - Urutkan proses berdasarkan *Arrival Time*.  
   - Hitung nilai berikut untuk tiap proses:
     ```
     Waiting Time (WT) = waktu mulai eksekusi - Arrival Time
     Turnaround Time (TAT) = WT + Burst Time
     ```
   - Hitung rata-rata Waiting Time dan Turnaround Time.  
   - Buat Gantt Chart sederhana:  
     ```
     | P1 | P2 | P3 | P4 |
     0    6    14   21   24
     ```

3. **Eksperimen 2 – SJF (Shortest Job First)**
   - Urutkan proses berdasarkan *Burst Time* terpendek (dengan memperhatikan waktu kedatangan).  
   - Lakukan perhitungan WT dan TAT seperti langkah sebelumnya.  
   - Bandingkan hasil FCFS dan SJF pada tabel berikut:

     | Algoritma | Avg Waiting Time | Avg Turnaround Time | Kelebihan | Kekurangan |
     |------------|------------------|----------------------|------------|-------------|
     | FCFS | 8.75 | 14.75 | Sederhana dan mudah diterapkan | Tidak efisien untuk proses panjang |
     | SJF | 6.25 | 12.25 | Optimal untuk job pendek | Menyebabkan *starvation* pada job panjang |

4. **Eksperimen 3 – Visualisasi Spreadsheet (Opsional)**
   - Gunakan Excel/Google Sheets untuk membuat perhitungan otomatis:
     - Kolom: Arrival, Burst, Start, Waiting, Turnaround, Finish.
     - Gunakan formula dasar penjumlahan/subtraksi.
   - Screenshot hasil perhitungan dan simpan di:
     ```
     praktikum/week5-scheduling-fcfs-sjf/screenshots/
     ```

5. **Analisis**
   - Bandingkan hasil rata-rata WT dan TAT antara FCFS & SJF.  
   - Jelaskan kondisi kapan SJF lebih unggul dari FCFS dan sebaliknya.  
   - Tambahkan kesimpulan singkat di akhir laporan.

6. **Commit & Push**
   ```bash
   git add .
   git commit -m "Minggu 5 - CPU Scheduling FCFS & SJF"
   git push origin main
---

## Kode / Perintah
  ```
     Waiting Time (WT) = waktu mulai eksekusi - Arrival Time
     Turnaround Time (TAT) = WT + Burst Time
  ```

---

## Hasil Eksekusi

![Screenshot hasil](<screenshots/week 5.png>)

---

## Analisis
- Bandingkan hasil rata-rata WT dan TAT antara FCFS & SJF.
| Algoritma | Avg Waiting Time | Avg Turnaround Time | Kelebihan | Kekurangan |
     |------------|------------------|----------------------|------------|-------------|
     | FCFS | 8.75 | 14.75 | Sederhana dan mudah diterapkan | Tidak efisien untuk proses panjang |
     | SJF | 6.25 | 12.25 | Optimal untuk job pendek | Menyebabkan *starvation* pada job panjang |
- Jelaskan kondisi kapan SJF lebih unggul dari FCFS dan sebaliknya.
  
  SJF lebih unggul saat sebagian besar proses memiliki waktu eksekusi (burst time) yang berbeda-beda, terutama jika ada proses pendek yang datang lebih awal.
Karena SJF memprioritaskan proses dengan burst time paling kecil, maka waktu tunggu total bisa ditekan.

  FCFS lebih baik pada kondisi semua proses memiliki burst time yang hampir sama, atau sistem interaktif di mana urutan kedatangan harus adil dan tidak boleh ada proses “terlantar”.
- Tambahkan kesimpulan singkat di akhir laporan.

---

## Kesimpulan
Algoritma SJF menghasilkan performa lebih efisien dibandingkan FCFS karena mampu menurunkan waktu tunggu dan waktu penyelesaian rata-rata.
Namun, SJF memiliki kelemahan berupa kemungkinan starvation (proses panjang menunggu terlalu lama), sedangkan FCFS lebih adil dan sederhana, tetapi tidak selalu efisien untuk proses yang bervariasi panjangnya.

---
## Tugas
1. Hitung waiting time dan turnaround time dari minimal 2 skenario FCFS dan SJF.

**Skenario 1**
 **FCFS**

| Proses | Burst | Arrival | Start | Finish | WT | TAT |
|:------:|:------:|:--------:|:------:|:-------:|:--:|:--:|
| P1 | 6 | 0 | 0 | 6 | 0 | 6 |
| P2 | 8 | 1 | 6 | 14 | 5 | 13 |
| P3 | 7 | 2 | 14 | 21 | 12 | 19 |
| P4 | 3 | 3 | 21 | 24 | 18 | 21 |

**Rata-rata WT:** 8.75  
**Rata-rata TAT:** 14.75

 **FCFS**

| Proses | Burst | Arrival | Start | Finish | WT | TAT |
|:------:|:------:|:--------:|:------:|:-------:|:--:|:--:|
| P1 | 6 | 0 | 0 | 6 | 0 | 6 |
| P2 | 8 | 1 | 6 | 14 | 5 | 13 |
| P3 | 7 | 2 | 14 | 21 | 12 | 19 |
| P4 | 3 | 3 | 21 | 24 | 18 | 21 |

**Rata-rata WT:** 6.25  
**Rata-rata TAT:** 12.25  

**Skenario 2**

**FCFS**

| Proses | Burst | Arrival | Start | Finish | WT | TAT |
|:------:|:------:|:--------:|:------:|:-------:|:--:|:--:|
| P1 | 4 | 0 | 0 | 4 | 0 | 4 |
| P2 | 3 | 1 | 4 | 7 | 3 | 6 |
| P3 | 1 | 2 | 7 | 8 | 5 | 6 |
| P4 | 2 | 3 | 8 | 10 | 5 | 7 |

**Rata-rata WT:** 3.25  
**Rata-rata TAT:** 5.75  

**SJF**

| Proses | Burst | Arrival | Start | Finish | WT | TAT |
|:------:|:------:|:--------:|:------:|:-------:|:--:|:--:|
| P1 | 4 | 0 | 0 | 4 | 0 | 4 |
| P3 | 1 | 2 | 4 | 5 | 2 | 3 |
| P4 | 2 | 3 | 5 | 7 | 2 | 4 |
| P2 | 3 | 1 | 7 | 10 | 6 | 9 |

**Rata-rata WT:** 2.5  
**Rata-rata TAT:** 5.0  

2. Sajikan hasil perhitungan dalam tabel perbandingan (FCFS vs SJF).

 | Algoritma | Avg WT (Skenario 1) | Avg TAT (Skenario 1) | Avg WT (Skenario 2) | Avg TAT (Skenario 2) |
|:-----------|:------------------:|:--------------------:|:------------------:|:--------------------:|
| **FCFS** | 8.75 | 14.75 | 3.25 | 5.75 |
| **SJF** | 6.25 | 12.25 | 2.50 | 5.00 |

3. Analisis kelebihan dan kelemahan tiap algoritma.

- **SJF (Shortest Job First)** lebih unggul pada kondisi di mana proses pendek datang lebih awal atau berselang-seling dengan proses panjang.  
  Ini karena proses pendek diprioritaskan, sehingga total waktu tunggu berkurang.
- **FCFS (First Come First Served)** lebih adil dan mudah diterapkan, tetapi cenderung tidak efisien saat ada proses panjang di awal karena proses lain menunggu terlalu lama (**convoy effect**).
- SJF bisa menyebabkan **starvation**, yaitu proses panjang menunggu terlalu lama bila selalu ada proses pendek yang datang belakangan.


4. Simpan seluruh hasil dan analisis ke laporan.md

---

## Quiz
1. Apa perbedaan utama antara FCFS dan SJF?
   
**Jawaban:**
   
Perbedaan utama antara FCFS dan SJF terletak pada cara menentukan urutan eksekusi proses.

FCFS (First Come, First Served) menjadwalkan proses berdasarkan urutan kedatangan — siapa yang datang dulu, dijalankan dulu.

SJF (Shortest Job First) menjadwalkan proses berdasarkan lama waktu eksekusi (burst time) — proses dengan waktu terpendek dijalankan lebih dulu.

2. Mengapa SJF dapat menghasilkan rata-rata waktu tunggu minimum?.
 
**Jawaban:**

SJF menghasilkan rata-rata waktu tunggu minimum karena algoritma ini selalu menjalankan proses dengan waktu eksekusi paling singkat terlebih dahulu, sehingga proses-proses cepat tidak perlu menunggu lama di belakang proses yang lebih lama. Dengan begitu, total waktu tunggu semua proses menjadi lebih kecil dibanding algoritma lain.

3. Apa kelemahan SJF jika diterapkan pada sistem interaktif?.

**Jawaban:**  

Kelemahan SJF pada sistem interaktif adalah sulitnya memperkirakan lama waktu eksekusi proses (burst time) dan terjadinya starvation, yaitu proses yang berdurasi panjang bisa terus tertunda jika selalu ada proses pendek yang datang lebih dulu. Akibatnya, sistem menjadi kurang responsif dan tidak adil bagi proses-proses besar.

---

## Refleksi Diri
Tuliskan secara singkat:
- Apa bagian yang paling menantang minggu ini?  semua bagian menantang
- Bagaimana cara Anda mengatasinya?  mencari tau di AI

---

**Credit:**  
_Template laporan praktikum Sistem Operasi (SO-202501) – Universitas Putra Bangsa_
