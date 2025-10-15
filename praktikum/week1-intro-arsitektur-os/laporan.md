
# Laporan Praktikum Minggu [1]
# Arsitektur Sistem Operasi Dan Kernel

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
1 Sebutkan tiga fungsi utama sistem operasi:
- Mengelola Sumber Daya Perangkat Keras
Sistem operasi bertugas untuk mengelola semua komponen perangkat keras komputer, seperti CPU, memori, dan perangkat input/output
- Menyediakan Antarmuka Pengguna
Sistem operasi menyediakan antarmuka yang memungkinkan pengguna berinteraksi dengan komputer. Ini bisa berupa antarmuka berbasis teks (CLI) atau antarmuka grafis (GUI) yang lebih ramah pengguna. Antarmuka ini memudahkan pengguna untuk menjalankan aplikasi, mengelola file, dan mengonfigurasi sistem
- Mengelola File dan Penyimpanan
Sistem operasi bertanggung jawab untuk mengatur penyimpanan data dan file. Ini termasuk pengaturan direktori, hak akses file, dan pengelolaan format file yang dapat dibaca dan ditulis oleh sistem komputer.

2 Jelaskan perbedaan antara kernel mode dan user mode:
Mode Kernel: Mode ini adalah mode di mana komponen sistem operasi inti berfungsi dan mengelola sumber daya perangkat keras. Dalam mode ini, aplikasi tidak dapat langsung berinteraksi dengan perangkat keras, dan jika terjadi gangguan, seluruh sistem operasi mungkin mengalami kerusakan. 
Mode Pengguna: Mode ini adalah mode di mana aplikasi berjalan dengan akses terbatas ke perangkat keras untuk tujuan keamanan. Dalam mode ini, aplikasi memiliki ruang alamat virtual privat dan tidak dapat mengakses ruang alamat yang dimiliki oleh kernel. Jika satu aplikasi mengalami crash, dampaknya hanya akan dialami aplikasi itu sendiri, tanpa mempengaruhi sistem operasi atau aplikasi lain. 
Perbedaan utama antara kedua mode ini adalah tingkat hak istimewa atau privilege yang ditawarkan. Mode kernel memiliki akses penuh ke semua sumber daya sistem, sedangkan mode pengguna memiliki akses terbatas untuk menjaga keamanan dan stabilitas sistem

3 Sebutkan contoh OS dengan arsitektur monolithic dan microkernel:
- Contoh OS dengan Arsitektur Monolithic:
Arsitektur monolithic memiliki seluruh layanan sistem operasi (seperti manajemen memori, file system, driver, dsb.) berjalan dalam satu ruang kernel (kernel space).
-Linux (seperti Ubuntu, Debian, Fedora)
-MS-DOS
-Unix (seperti FreeBSD, Solaris)
-MacOS (sebelum MacOS X)
- Contoh OS dengan Arsitektur Microkernel:
Arsitektur microkernel hanya menyediakan layanan inti (seperti IPC, manajemen memori dasar, dan penjadwalan) di kernel, sementara layanan lainnya berjalan di ruang pengguna (user space).
-Minix
-QNX
-GNU Hurd
-L4 microkernel (dan turunannya: Fiasco.OC, seL4)
-MacOS X (menggunakan hybrid kernel: XNU, gabungan dari microkernel Mach dan elemen monolithic BSD)

---

## Refleksi Diri
Tuliskan secara singkat:
- Bagian yang paling menantang minggu ini adalah cara mengumpulkan tugas lewat github karena sebelumnya tidak pernah memakai github.
- Cara saya mengatasinya adalah bertanya kepada teman/dosen jika belum paham atau menonton tutorial.

# Tugas
Tuliskan ringkasan (±500 kata) mencakup:
-Perbedaan monolithic kernel, microkernel, dan layered architecture.
-Contoh OS yang menerapkan tiap model.
-Analisis: model mana yang paling relevan untuk sistem modern.
## Jawaban:
1. Monolithic Kernel

Monolithic kernel adalah arsitektur di mana seluruh layanan sistem operasi seperti manajemen proses, sistem file, manajemen memori, dan device driver dijalankan di dalam ruang kernel. Semua modul ini saling berkomunikasi secara langsung tanpa batas pemisah. Contoh sistem operasi yang menggunakan arsitektur ini adalah Linux, UNIX, dan MS-DOS.
Kelebihan dari monolithic kernel adalah kinerjanya yang tinggi karena proses komunikasi antar komponen terjadi secara langsung. Namun, kelemahannya adalah kompleksitas tinggi dan risiko besar jika terjadi kesalahan pada salah satu modul, karena dapat menyebabkan seluruh sistem crash.

2. Microkernel

Berbeda dengan monolithic, microkernel hanya menempatkan fungsi-fungsi inti yang sangat penting di dalam kernel, seperti komunikasi antar proses (IPC), manajemen memori dasar, dan manajemen CPU. Layanan lain seperti sistem file, driver perangkat, dan protokol jaringan dijalankan di ruang pengguna (user space).
Contoh sistem operasi yang menggunakan pendekatan microkernel adalah Minix, QNX, dan sebagian arsitektur macOS (melalui kernel Mach). Kelebihan microkernel adalah stabilitas dan keamanan yang lebih baik karena jika satu layanan gagal, sistem utama tetap berjalan. Namun, kelemahannya terletak pada performa — komunikasi antara kernel dan layanan pengguna bisa menimbulkan overhead atau memperlambat sistem.

3. Layered Architecture

Layered architecture membagi sistem operasi menjadi beberapa lapisan (layer), di mana setiap lapisan memiliki fungsi tertentu dan hanya dapat berinteraksi dengan lapisan di atas atau di bawahnya. Struktur ini membuat desain OS lebih teratur dan mudah dikelola. Contoh sistem operasi yang menggunakan pendekatan ini adalah THE OS dan Windows NT, yang memiliki arsitektur berlapis sekaligus elemen hybrid.
Kelebihan dari model ini adalah kemudahan pengembangan dan perawatan karena setiap lapisan memiliki tanggung jawab yang jelas. Kekurangannya, model ini dapat menurunkan efisiensi sistem karena komunikasi antar lapisan bisa menjadi lebih panjang.

4. Analisis: Model Paling Relevan untuk Sistem Modern
Dalam praktik modern, tidak ada satu model yang digunakan secara murni. Banyak sistem operasi modern mengadopsi pendekatan hybrid architecture, yaitu menggabungkan kelebihan dari monolithic dan microkernel. Contohnya, Windows 10, macOS, dan bahkan Linux modern memiliki elemen-elemen hybrid untuk mencapai keseimbangan antara performa, keamanan, dan fleksibilitas.
Model hybrid ini memungkinkan sistem tetap cepat seperti monolithic kernel, tetapi juga memiliki stabilitas dan keamanan tinggi seperti microkernel. Selain itu, desain berlapis juga sering diadopsi agar proses pengembangan lebih modular dan mudah diperbarui. Dengan demikian, model hybrid yang memadukan konsep microkernel dan layered architecture dianggap paling relevan untuk sistem operasi modern karena dapat menyesuaikan diri dengan kebutuhan perangkat yang beragam, seperti komputer pribadi, server, dan perangkat mobile.
---

**Credit:**  
_Template laporan praktikum Sistem Operasi (SO-202501) – Universitas Putra Bangsa_
