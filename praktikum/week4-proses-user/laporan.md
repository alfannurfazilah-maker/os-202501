
# Laporan Praktikum Minggu 4
## Topik: Manajemen Proses dan User di Linux

---

## Identitas
- **Nama**  : Alfan Nur Fadzilah
- **NIM**   : 250320575
- **Kelas** : 1DSRA

---

## Tujuan
- Menjelaskan konsep proses dan user dalam sistem operasi Linux.
- Menampilkan daftar proses yang sedang berjalan dan statusnya.
- Menggunakan perintah untuk membuat dan mengelola user.
- Menghentikan atau mengontrol proses tertentu menggunakan PID.
- Menjelaskan kaitan antara manajemen user dan keamanan sistem.

---

## Dasar Teori
1. Manajemen Proses
   
Proses adalah program yang sedang berjalan di sistem. Setiap proses memiliki PID (Process ID) dan dijalankan oleh user tertentu.
Jenis proses: foreground, background, dan daemon.

Perintah penting:

- ps, top → melihat proses

- kill, killall → menghentikan proses

- bg, fg → memindahkan proses ke latar depan/belakang

- nice, renice → mengatur prioritas proses

Status proses: R (Running), S (Sleeping), Z (Zombie), T (Stopped).

2. Manajemen User

Linux bersifat multiuser, artinya banyak pengguna dapat bekerja bersamaan.
Jenis user: root (superuser), user biasa, dan system user.

Perintah penting:

- useradd, passwd, usermod, userdel → mengelola akun

- groupadd, groups → mengatur grup
File penting: /etc/passwd, /etc/shadow, /etc/group.

3. Hubungan Proses dan User

Setiap proses dijalankan oleh user tertentu dengan hak akses sesuai levelnya.
Manajemen yang baik menjaga keamanan, stabilitas, dan efisiensi sistem.

---

## Langkah Praktikum
1. **Setup Environment**
   - Gunakan Linux (Ubuntu/WSL).  
   - Pastikan Anda sudah login sebagai user non-root.  
   - Siapkan folder kerja:
     ```
     praktikum/week4-proses-user/
     ``` 
2. **Eksperimen 1 – Identitas User**
   Jalankan perintah berikut:
   ```bash
   whoami
   id
   groups
   ```
   - Jelaskan setiap output dan fungsinya.  
   - Buat user baru (jika memiliki izin sudo):
     ```bash
     sudo adduser praktikan
     sudo passwd praktikan
     ```
   - Uji login ke user baru.

3. **Eksperimen 2 – Monitoring Proses**
   Jalankan:
   ```bash
   ps aux | head -10
   top -n 1
   ```
   - Jelaskan kolom penting seperti PID, USER, %CPU, %MEM, COMMAND.  
   - Simpan tangkapan layar `top` ke:
     ```
     praktikum/week4-proses-user/screenshots/top.png
     ```

4. **Eksperimen 3 – Kontrol Proses**
   - Jalankan program latar belakang:
     ```bash
     sleep 1000 &
     ps aux | grep sleep
     ```
   - Catat PID proses `sleep`.  
   - Hentikan proses:
     ```bash
     kill <PID>
     ```
   - Pastikan proses telah berhenti dengan `ps aux | grep sleep`.

5. **Eksperimen 4 – Analisis Hierarki Proses**
   Jalankan:
   ```bash
   pstree -p | head -20
   ```
   - Amati hierarki proses dan identifikasi proses induk (`init`/`systemd`).  
   - Catat hasilnya dalam laporan.

6. **Commit & Push**
   ```bash
   git add .
   git commit -m "Minggu 4 - Manajemen Proses & User"
   git push origin main
   ```
---

## Kode / Perintah
**Eksperimen 1 – Identitas User**
   
   ```bash
   whoami
   id
   groups
   ```
**Eksperimen 2 – Monitoring Proses**
   
   ```bash
   ps aux | head -10
   top -n 1
   ```
**Eksperimen 3 – Kontrol Proses**
    
     ```bash
     sleep 1000 &
     ps aux | grep sleep
     ```
**Eksperimen 4 – Analisis Hierarki Proses**
   
   ```bash
   pstree -p | head -20
   ```

```

---

## Hasil Eksekusi
 ![Screenshot hasil](<screenshots/eksperimen1week4 bag 1.png>)

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
1. [Pertanyaan 1]  
   **Jawaban:**  
2. [Pertanyaan 2]  
   **Jawaban:**  
3. [Pertanyaan 3]  
   **Jawaban:**  

---

## Refleksi Diri
Tuliskan secara singkat:
- Apa bagian yang paling menantang minggu ini?  
- Bagaimana cara Anda mengatasinya?  

---

**Credit:**  
_Template laporan praktikum Sistem Operasi (SO-202501) – Universitas Putra Bangsa_
