
# Laporan Praktikum Minggu 2
Topik: Struktur System Call dan Fungsi Kernel

---

## Identitas
- **Nama**  : Alfan Nur Fadzilah  
- **NIM**   : 250320575
- **Kelas** : 1DSRA

---

## Tujuan
Tuliskan tujuan praktikum minggu ini:
- 1.Menjelaskan konsep dan fungsi system call dalam sistem operasi.
- 2.Mengidentifikasi jenis-jenis system call dan fungsinya.
- 3.Mengamati alur perpindahan mode user ke kernel saat system call terjadi.
- 4.Menggunakan perintah Linux untuk menampilkan dan menganalisis system call.

---

## Dasar Teori
System call adalah antarmuka (interface) antara program aplikasi/user dan kernel sistem operasi. System call memungkinkan program meminta layanan dari sistem operasi, seperti mengakses file, mengatur proses, atau menggunakan perangkat keras.

Alur Umum System Call:
- Program user memanggil fungsi system call.
- Fungsi tersebut berpindah ke mode kernel (melalui interrupt atau trap).
- Kernel menjalankan layanan yang diminta.
- Hasil dikembalikan ke program user.

---

## Langkah Praktikum
1. Langkah-langkah yang dilakukan.  
2. Perintah yang dijalankan.  
3. File dan kode yang dibuat.  
4. Commit message yang digunakan.

---

## Kode / Perintah
Tuliskan potongan kode atau perintah utama:
```bash
uname -a
lsmod | head
dmesg | head
```

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
1. Apa fungsi utama system call dalam sistem operasi. 
  - **Jawaban:**  System call berfungsi sebagai jembatan antara program pengguna (user program) dan kernel sistem operasi. Fungsinya adalah untuk memungkinkan program mengakses layanan sistem operasi secara aman dan terkendali.
2. [Sebutkan 4 kategori system call yang umum digunakan.]  
   **Jawaban:**  Process Control,File Management,Device Management,Information Maintenance
3. [Mengapa system call tidak bisa dipanggil langsung oleh user program]  
   **Jawaban:**  System call tidak bisa dipanggil langsung oleh user program karena membutuhkan hak akses khusus dan harus dijalankan di mode kernel untuk menjamin keamanan, stabilitas, dan kontrol sistem.

---

## Refleksi Diri
Tuliskan secara singkat:
- Apa bagian yang paling menantang minggu ini?  
- Bagaimana cara Anda mengatasinya?  

---

**Credit:**  
_Template laporan praktikum Sistem Operasi (SO-202501) – Universitas Putra Bangsa_
