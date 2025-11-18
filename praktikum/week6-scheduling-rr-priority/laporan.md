
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

## Hasil Eksekusi
Sertakan screenshot hasil percobaan atau diagram:
![Screenshot hasil](screenshots/example.png)

---

## Analisis
- Jelaskan makna hasil percobaan.  
- Hubungkan hasil dengan teori (fungsi kernel, system call, arsitektur OS).  
- Apa perbedaan hasil di lingkungan OS berbeda (Linux vs Windows)?  

---

## Kesimpulan
Tuliskan 2–3 poin kesimpulan dari praktikum ini.

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
- Apa bagian yang paling menantang minggu ini?  
- Bagaimana cara Anda mengatasinya?  

---

**Credit:**  
_Template laporan praktikum Sistem Operasi (SO-202501) – Universitas Putra Bangsa_
