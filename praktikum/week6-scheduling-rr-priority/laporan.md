
# Laporan Praktikum Minggu 6
Topik: Penjadwalan CPU – Round Robin (RR) dan Priority Scheduling

---

## Identitas
- **Nama**  : Alfan Nur Fadzilah]  
- **NIM**   : 250320575 
- **Kelas** : 1DSRA

---

## Tujuan
1. Menghitung waiting time dan turnaround time pada algoritma RR dan Priority.
2. Menyusun tabel hasil perhitungan dengan benar dan sistematis.
3. Membandingkan performa algoritma RR dan Priority.
4. Menjelaskan pengaruh time quantum dan prioritas terhadap keadilan eksekusi proses.
5. Menarik kesimpulan mengenai efisiensi dan keadilan kedua algoritma.

---

## Dasar Teori
Round Robin (RR):
- Setiap proses mendapat jatah waktu kecil (time quantum) secara bergiliran.
- Jika time quantum habis sebelum proses selesai, proses dipindah ke akhir antrean ready queue.
- Cocok untuk sistem time-sharing karena memberikan keadilan (fairness).
- Performa sangat bergantung pada besar kecilnya quantum.

Priority Scheduling:
- Setiap proses diberi prioritas. CPU selalu memilih proses dengan prioritas tertinggi terlebih dahulu.
- Ada dua jenis: preemptive (dapat menginterupsi proses lain) dan non-preemptive (tidak menginterupsi).
- Risiko utama: starvation (proses prioritas rendah tidak pernah jalan), biasanya diatasi dengan aging.

---

## Langkah Praktikum
1. **Siapkan Data Proses**
   Gunakan contoh data berikut (boleh dimodifikasi sesuai kebutuhan):
   | Proses | Burst Time | Arrival Time | Priority |
   |:--:|:--:|:--:|:--:|
   | P1 | 5 | 0 | 2 |
   | P2 | 3 | 1 | 1 |
   | P3 | 8 | 2 | 4 |
   | P4 | 6 | 3 | 3 |

2. **Eksperimen 1 – Round Robin (RR)**
   - Gunakan *time quantum (q)* = 3.  
   - Hitung *waiting time* dan *turnaround time* untuk tiap proses.  
   - Simulasikan eksekusi menggunakan Gantt Chart (manual atau spreadsheet).  
     ```
     | P1 | P2 | P3 | P4 | P1 | P3 | ...
     0    3    6    9   12   15   18  ...
     ```
   - Catat sisa *burst time* tiap putaran.

3. **Eksperimen 2 – Priority Scheduling (Non-Preemptive)**
   - Urutkan proses berdasarkan nilai prioritas (angka kecil = prioritas tinggi).  
   - Lakukan perhitungan manual untuk:
     ```
     WT[i] = waktu mulai eksekusi - Arrival[i]
     TAT[i] = WT[i] + Burst[i]
     ```
   - Buat tabel perbandingan hasil RR dan Priority.

4. **Eksperimen 3 – Analisis Variasi Time Quantum (Opsional)**
   - Ubah *quantum* menjadi 2 dan 5.  
   - Amati perubahan nilai rata-rata *waiting time* dan *turnaround time*.  
   - Buat tabel perbandingan efek *quantum*.

5. **Eksperimen 4 – Dokumentasi**
   - Simpan semua hasil tabel dan screenshot ke:
     ```
     praktikum/week6-scheduling-rr-priority/screenshots/
     ```
   - Buat tabel perbandingan seperti berikut:

     | Algoritma | Avg Waiting Time | Avg Turnaround Time | Kelebihan | Kekurangan |
     |------------|------------------|----------------------|------------|-------------|
     | RR | ... | ... | Adil terhadap semua proses | Tidak efisien jika quantum tidak tepat |
     | Priority | ... | ... | Efisien untuk proses penting | Potensi *starvation* pada prioritas rendah |

6. **Commit & Push**
   ```bash
   git add .
   git commit -m "Minggu 6 - CPU Scheduling RR & Priority"
   git push origin main
   ```

---

## Kode / Perintah
**Eksperimen 1 – Round Robin (RR)**
   - Gunakan *time quantum (q)* = 3.  
   - Hitung *waiting time* dan *turnaround time* untuk tiap proses.  
   - Simulasikan eksekusi menggunakan Gantt Chart (manual atau spreadsheet).  
     ```
     | P1 | P2 | P3 | P4 | P1 | P3 | ...
     0    3    6    9   12   15   18  ...
     ```
   - Catat sisa *burst time* tiap putaran.

3. **Eksperimen 2 – Priority Scheduling (Non-Preemptive)**
   - Urutkan proses berdasarkan nilai prioritas (angka kecil = prioritas tinggi).  
   - Lakukan perhitungan manual untuk:
     ```
     WT[i] = waktu mulai eksekusi - Arrival[i]
     TAT[i] = WT[i] + Burst[i]
     ```
   - Buat tabel perbandingan hasil RR dan Priority.

4. **Eksperimen 3 – Analisis Variasi Time Quantum (Opsional)**
   - Ubah *quantum* menjadi 2 dan 5.  
   - Amati perubahan nilai rata-rata *waiting time* dan *turnaround time*.  
   - Buat tabel perbandingan efek *quantum*.

5. **Eksperimen 4 – Dokumentasi**
   - Simpan semua hasil tabel dan screenshot ke:
     ```
     praktikum/week6-scheduling-rr-priority/screenshots/
     ```
   - Buat tabel perbandingan seperti berikut:

     | Algoritma | Avg Waiting Time | Avg Turnaround Time | Kelebihan | Kekurangan |
     |------------|------------------|----------------------|------------|-------------|
     | RR | ... | ... | Adil terhadap semua proses | Tidak efisien jika quantum tidak tepat |
     | Priority | ... | ... | Efisien untuk proses penting | Potensi *starvation* pada prioritas rendah |
   

---

## Hasil Eksekusi & Analisis
![hasil eksekusi](<screenshots/eksperimen1-2.png>)
**Eksperimen 1 – Round Robin (RR)**
   - Gunakan *time quantum (q)* = 3.  
   - Hitung *waiting time* dan *turnaround time* untuk tiap proses:
     
| Proses | Arrival | Burst | Finish Time | Waiting Time (WT) | Turnaround Time (TAT) |
|--------|----------|--------|--------------|---------------------|-------------------------|
| P1     | 0        | 5      | 14           | 9                   | 14                      |
| P2     | 1        | 3      | 6            | 2                   | 5                       |
| P3     | 2        | 8      | 22           | 12                  | 20                      |
| P4     | 3        | 6      | 20           | 11                  | 17                      |

### Rumus
- **TAT = Finish Time – Arrival**
- **WT = TAT – Burst**
   - Simulasikan eksekusi menggunakan Gantt Chart (manual atau spreadsheet).
 ```
     | P1 | P2 | P3 | P4 | P1 | P3 | P4 | P3 |
     0    3    6    9   12    14   17   20   22
 ```

     
 - Catat sisa *burst time* tiap putaran.

**Putaran 1 (Waktu 0–12)**
1. P1 jalan 3 → sisa 2  
2. P2 jalan 3 → sisa 0 (selesai)  
3. P3 jalan 3 → sisa 5  
4. P4 jalan 3 → sisa 3  

Sisa setelah Putaran 1:  
P1 = 2, P2 = 0, P3 = 5, P4 = 3  

**Putaran 2 (Waktu 12–20)**
1. P1 jalan 2 → sisa 0 (selesai)  
2. P3 jalan 3 → sisa 2  
3. P4 jalan 3 → sisa 0 (selesai)

Sisa setelah Putaran 2:  
P1 = 0, P3 = 2  

**Putaran 3 (Waktu 20–22)**
1. P3 jalan 2 → sisa 0 (selesai)

Sisa setelah Putaran 3:  
P3 = 0  

**Eksperimen 2 – Priority Scheduling (Non-Preemptive)**
   - Urutkan proses berdasarkan nilai prioritas (angka kecil = prioritas tinggi).

   Priority kecil = lebih tinggi.

   Urutan eksekusi:
   
 P1 → P2 → P4 → P3

(P1 duluan karena dia sudah datang di waktu 0. P2 datang lebih tinggi prioritas tapi baru muncul di waktu 1.)

   - Lakukan perhitungan manual untuk:
     ```
     WT[i] = waktu mulai eksekusi - Arrival[i]
     TAT[i] = WT[i] + Burst[i]
     ```

     Rumus:

WT = Start Time − Arrival

TAT = WT + Burst

Hasil perhitungan:

- P1

Start = 0

WT = 0 − 0 = 0

TAT = 0 + 5 = 5

- P2

Start = 5

WT = 5 − 1 = 4

TAT = 4 + 3 = 7

- P4

Start = 8

WT = 8 − 3 = 5

TAT = 5 + 6 = 11

- P3

Start = 14

WT = 14 − 2 = 12

TAT = 12 + 8 = 20
   - Buat tabel perbandingan hasil RR dan Priority.

| Proses | WT (RR) | TAT (RR) | WT (Priority) | TAT (Priority) |
|--------|----------|------------|----------------|-----------------|
| P1     | 9        | 14         | 0              | 5               |
| P2     | 2        | 5          | 4              | 7               |
| P3     | 12       | 20         | 12             | 20              |
| P4     | 11       | 17         | 5              | 11              |

**Eksperimen 3**
![hasil eksekusi](<screenshots/eksperimen3.png>)

 - Ubah *quantum* menjadi 2 dan 5.  
   - Amati perubahan nilai rata-rata *waiting time* dan *turnaround time*.  
   - Buat tabel perbandingan efek *quantum*:

| Hasil Eksperimen               | Quantum | Avg Waiting Time | Avg Turnaround Time | Catatan / Efek |
|-------------------------|---------|-------------------|-----------------------|-------------------------------|
| Round Robin (RR)        | 3       | 7.75              | 13.75                | Quantum sedang, performa stabil |
| Round Robin (RR)        | 2       | 9.25              | 14.75                | Quantum kecil → banyak context switch |
| Round Robin (RR)        | 5       | 7.00              | 12.50                | Quantum besar → lebih sedikit preemption |
| Priority (Non-Preempt.) | –       | 5.75              | 11.75                | Bergantung prioritas, tidak adil bagi prioritas rendah |

**Eksperimen 4 - Dokumentasi**
 - Simpan semua hasil tabel dan screenshot ke:
     ```
     praktikum/week6-scheduling-rr-priority/screenshots/
     ```
 - Buat tabel perbandingan seperti berikut:

| Algoritma | Avg Waiting Time | Avg Turnaround Time | Kelebihan | Kekurangan |
|-----------|------------------|----------------------|-----------|------------|
| RR (q = 3) | 7.75 | 13.75 | Adil terhadap semua proses karena setiap proses mendapat jatah waktu | Tidak efisien jika quantum tidak tepat (terlalu kecil → banyak context switch) |
| Priority (Non-Preemptive) | 5.75 | 11.75 | Efisien untuk mengeksekusi proses yang lebih penting lebih cepat | Potensi starvation pada proses berprioritas rendah |










---




## Kesimpulan

Berdasarkan seluruh eksperimen yang telah dilakukan, dapat disimpulkan bahwa setiap algoritma penjadwalan CPU memiliki karakteristik dan performa yang berbeda tergantung pada mekanisme kerja dan parameter yang digunakan.

---

## Quiz
1. Apa perbedaan utama antara Round Robin dan Priority Scheduling?

   **Jawaban:**
   
Round Robin (RR): Scheduling yang membagi waktu antara semua proses dalam setiap waktu yang tetap. Proses dengan prioritas tertinggi akan dijalankan terlebih dahulu, dan setelah waktu yang ditentukan, proses berikutnya akan dijalankan. RR adalah metode yang sederhana dan mudah diimplementasikan, tetapi dapat mengalami masalah seperti penundaan. 

Priority Scheduling (PS): Scheduling yang membagi proses berdasarkan prioritas yang ditentukan. Proses dengan prioritas tertinggi akan dijalankan terlebih dahulu, dan setelah proses tersebut selesai, proses berikutnya akan dijalankan. PS dapat menghasilkan respons yang lebih cepat, tetapi juga dapat menyebabkan penundaan jika proses dengan prioritas tinggi tidak dijalankan terlebih dahulu.
   
2. Apa pengaruh besar/kecilnya time quantum terhadap performa sistem?
 
   **Jawaban:**
   
Jika quantum time terlalu besar, maka respons time untuk proses-proses terlalu tinggi. Sebaliknya, jika quantum time terlalu kecil, maka dapat mengakibatkan overhead pada CPU dimana context switching dari proses menjadi lebih besar.
   
3. Mengapa algoritma Priority dapat menyebabkan starvation?

   **Jawaban:**
   
Algoritma priority dapat menyebabkan starvation karena beberapa faktor, antara lain:
- Lack of resource allocation policies: Jika tidak ada kebijakan yang jelas untuk alokasi sumber daya, beberapa proses mungkin terus-menerus dimanduakn akses ke sumber daya yang diperlukan, yang dapat menyebabkan starvation. 

- Inadequate synchronization mechanisms: Synchronization mekanisme seperti lock dan semaphores yang tidak dirancang dengan benar dapat menyebabkan starvation. 

- Poorly designed algorithms: Algoritma yang tidak dirancang dengan keadilan dan efisiensi dalam pikirannya dapat menyebabkan starvation.

---

## Refleksi Diri
Tuliskan secara singkat:
- Apa bagian yang paling menantang minggu ini? semua bagian menantang
- Bagaimana cara Anda mengatasinya?  mencari tau di AI atau bertanya ke teman

---

**Credit:**  
_Template laporan praktikum Sistem Operasi (SO-202501) – Universitas Putra Bangsa_
