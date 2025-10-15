
# Laporan Praktikum Minggu [1]
Arsitektur Sistem Operasi Dan Kernel

---

## Identitas
- Nama  :Alfan Nur Fadzilah
- NIM   :250320575
- Kelas :1DSRA

---

## Tujuan

 Mahasiswa mampu menjelaskan fungsi utama sistem operasi dan peran kernel serta system call.

---

## Dasar Teori
Teori sistem operasi (OS) adalah perangkat lunak fundamental yang mengelola sumber daya perangkat keras dan lunak komputer, serta berfungsi sebagai penghubung antara pengguna dan komputer. Fungsi utamanya mencakup manajemen sumber daya (seperti CPU, memori, dan disk), penjadwalan proses, serta menyediakan antarmuka untuk menjalankan aplikasi dan perintah. Contoh OS populer adalah Windows, macOS, Linux, dan Android. 
Fungsi utama:

Manajemen perangkat keras: Mengatur dan mengkoordinasikan semua komponen perangkat keras seperti CPU, memori (RAM), penyimpanan (hard drive), serta perangkat input/output (keyboard, mouse) agar bekerja secara optimal. 

Manajemen perangkat lunak:
Mengatur semua program aplikasi dan proses yang berjalan di komputer, memastikan mereka tidak saling mengganggu dan menggunakan sumber daya secara efisien. 
Antarmuka pengguna:
Menyediakan cara bagi pengguna untuk berinteraksi dengan komputer, baik melalui antarmuka berbasis grafis (GUI) maupun baris perintah (CLI). 
Manajemen file:
Mengatur struktur dan penyimpanan file, serta mengelola akses ke file dan direktori. 


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
![Screenshot hasil](<screenshots/Screenshot 2025-10-15 164543.png>)

---

## Analisis
- Jelaskan makna hasil percobaan:
1. uname -a
Perintah ini digunakan untuk menampilkan informasi lengkap tentang sistem operasi dan kernel Linux.
2. lsmod | head
Perintah ini menampilkan daftar modul kernel (driver dan ekstensi kernel) yang sedang dimuat di sistem.
3. dmesg | head
Perintah ini menampilkan pesan log dari kernel (kernel ring buffer), yaitu catatan aktivitas yang dilakukan kernel sejak sistem dinyalakan.

- Hubungkan hasil dengan teori (fungsi kernel, system call, arsitektur OS):
 1. Hubungan hasil uname -a dengan teori kernel dan arsitektur OS
Perintah uname -a menampilkan informasi kernel yang sedang berjalan, termasuk versi, arsitektur CPU, dan konfigurasi sistem.
Secara teori, kernel adalah inti dari sistem operasi yang bertanggung jawab atas pengelolaan sumber daya, seperti CPU, memori, dan perangkat keras. Informasi versi kernel menunjukkan tipe arsitektur OS (misalnya 64-bit) dan jenis kernel yang digunakan (misalnya monolitik pada Linux).
Jadi, hasil uname -a memperlihatkan bahwa sistem menggunakan kernel Linux dengan arsitektur monolitik modular, di mana semua fungsi inti sistem dikelola dalam satu ruang kernel namun bisa dimodifikasi dengan modul tambahan.
2. Hubungan hasil lsmod | head dengan teori fungsi kernel
Perintah lsmod | head menampilkan daftar modul kernel yang sedang dimuat. Modul-modul ini adalah komponen tambahan dari kernel seperti driver perangkat keras, sistem file, atau dukungan jaringan.
Secara teori, ini menunjukkan fungsi kernel sebagai pengelola perangkat keras (device management). Kernel menggunakan modul untuk berinteraksi dengan perangkat tanpa perlu mengubah seluruh sistem operasi.
Dengan demikian, hasil lsmod membuktikan bahwa kernel Linux bersifat modular, artinya fitur dapat ditambahkan atau dihapus secara dinamis melalui modul kernel.
3. Hubungan hasil dmesg | head dengan teori system call dan fungsi kernel
Perintah dmesg | head menampilkan pesan log kernel sejak sistem dinyalakan. Log ini mencatat aktivitas awal kernel seperti deteksi CPU, memori, dan perangkat keras.
Secara teori, saat sistem operasi dijalankan, kernel melakukan inisialisasi perangkat keras melalui system call dan fungsi internalnya. System call sendiri adalah mekanisme komunikasi antara program pengguna dan kernel, memungkinkan aplikasi meminta layanan dari kernel (misalnya membaca data, menulis file, atau mengakses perangkat).
Jadi, hasil dmesg memperlihatkan bagaimana kernel berfungsi sebagai penghubung antara perangkat keras dan perangkat lunak, sesuai teori tentang peran inti sistem operasi.

- Apa perbedaan hasil di lingkungan OS berbeda (Linux vs Windows):
- Linux memberikan akses langsung ke kernel, modul, dan log sistem sehingga lebih terbuka dan fleksibel untuk administrasi atau pemrograman sistem.
Sementara Windows menyembunyikan detail kernel di balik antarmuka yang lebih terkontrol untuk menjaga stabilitas dan kemudahan pengguna.

---

## Kesimpulan
Perintah uname -a menunjukkan informasi lengkap tentang sistem operasi dan kernel Linux, seperti versi kernel, arsitektur CPU, nama host, dan waktu kompilasi, sehingga membantu mengenali identitas serta jenis sistem yang sedang dijalankan.

Perintah lsmod | head menampilkan daftar modul kernel yang sedang aktif, yang membuktikan bahwa Linux menggunakan arsitektur kernel modular, di mana fitur dan driver perangkat keras dapat dimuat atau dilepas secara dinamis sesuai kebutuhan.

Perintah dmesg | head menampilkan pesan log awal kernel saat proses booting, yang berisi informasi deteksi perangkat keras dan inisialisasi sistem, menunjukkan bahwa kernel berfungsi sebagai penghubung antara perangkat keras dan perangkat lunak dalam sistem operasi.

---

## Quiz
1. tiga persamaan fungsi utama sistem operasi. 
Jawaban: Mengelola sumber daya, mengatur proses, dan menyediakan layanan sistem berkas serta I/O bagi pengguna dan aplikasi.
2.menjelaskan perbedaan antara mode kernel dan mode pengguna .
Jawaban: Mode kernel dan mode pengguna memiliki perbedaan utama dalam hal hak akses dan fungsi di dalam sistem operasi. Mode kernel adalah mode di mana sistem operasi memiliki kendali penuh terhadap seluruh sumber daya komputer, seperti CPU, memori, dan perangkat keras. Semua komponen penting seperti kernel dan driver perangkat keras berjalan di mode ini. Karena memiliki hak akses penuh, kesalahan kecil pada mode kernel dapat menyebabkan sistem crash. Sementara itu, mode pengguna adalah mode di mana program atau aplikasi dijalankan dengan hak akses terbatas. Aplikasi tidak dapat langsung berinteraksi dengan perangkat keras dan harus melalui sistem operasi melalui mekanisme seperti system call. Dengan pembatasan ini, keamanan dan stabilitas sistem lebih terjaga karena jika terjadi kesalahan pada aplikasi, hanya aplikasi tersebut yang terpengaruh, bukan keseluruhan sistem.
3. Menunjuk contoh OS dengan arsitektur monolitik dan mikrokernel.
Jawaban: Contoh OS berarsitektur monolitik:
-MS-DOS
-UNIX (versi lama seperti System V, BSD awal)
-Linux (termasuk Ubuntu, Fedora, Debian, dan lainnya — walau modern Linux disebut “monolithic modular kernel
Contoh OS berarsitektur mikrokernel:
-MINIX
-QNX (banyak digunakan di sistem industri dan otomotif)
-Mach (digunakan di macOS dan iOS sebagai bagian dari Darwin)
-L4 Microkernel
---

## Refleksi Diri
Tuliskan secara singkat:
- Bagian yang paling menantang minggu ini adalah cara mengumpulkan tugas lewat github karena sebelumnya tidak pernah memakai github.
- Cara saya mengatasinya adalah bertanya kepada teman/dosen jika belum paham atau menonton tutorial.

---

**Credit:**  
_Template laporan praktikum Sistem Operasi (SO-202501) – Universitas Putra Bangsa_
