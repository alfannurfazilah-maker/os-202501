
# Laporan Praktikum Minggu 15
Topik: Proyek Kelompok – Mini Simulasi Sistem Operasi (Scheduling + Memory + Container)

---

## Nama Anggota Kelompok
- Aldiman (250320574)
- Abdi Hanafi Alghifari (250320570)
- Alfan Nur Fadzilah (250320575)

---


---

## Tujuan

tujuan praktikum minggu ini.  

> Bekerja kolaboratif dalam tim dengan pembagian peran yang jelas.

> Mengintegrasikan beberapa konsep sistem operasi dalam satu aplikasi sederhana.

> Mengelola proyek menggunakan Git (branch/PR/commit yang rapi).

> Menyusun dokumentasi dan laporan proyek yang sistematis.





---

## Dasar Teori
1.	CPU Scheduling mengatur urutan eksekusi proses agar penggunaan CPU efisien.
2.	FCFS dan SJF adalah algoritma penjadwalan CPU, di mana SJF menghasilkan waktu tunggu rata-rata lebih kecil dibanding FCFS.
3.	Page Replacement FIFO dan LRU digunakan untuk mengelola memori virtual, dengan LRU umumnya menghasilkan page fault lebih sedikit dibanding FIFO.
---

## Latar Belakang
Latar Belakang
Dalam sistem operasi, CPU dan memori merupakan sumber daya utama yang harus dikelola secara efisien. Sistem operasi menggunakan algoritma penjadwalan CPU untuk menentukan urutan eksekusi proses dan algoritma page replacement untuk mengelola memori virtual
Untuk memahami konsep tersebut secara praktis, diperlukan simulasi algoritma scheduling dan page replacement dalam sebuah aplikasi sederhana yang dapat dijalankan secara konsisten menggunakan Docker.

---

## TUJUAN PROYEK
Tujuan Proyek
1.	Mengimplementasikan algoritma CPU Scheduling FCFS dan SJF (non-preemptive).
2.	Mengimplementasikan algoritma Page Replacement FIFO dan LRU.
3.	Menghitung dan menampilkan metrik kinerja sistem.
4.	Menjalankan aplikasi dalam lingkungan container Docker agar terisolasi dan konsisten.

## ARSITEKTUR APLIKASI (MODUL & ALUR DATA)
````
Struktur Modul Proyek
│
├── main.py
│
├── scheduling.py
│   ├── fcfs()   # Implementasi algoritma First Come First Serve
│   └── sjf()    # Implementasi algoritma Shortest Job First
│
├── pagereplacement.py
│   ├── fifo()   # Implementasi algoritma Page Replacement FIFO
│   └── lru()    # Implementasi algoritma Page Replacement LRU
│
└── Dockerfile   # Konfigurasi container Docker untuk menjalankan aplikasi
`````
Fungsi Tiap Modul
A.	main.py
1.	Menyediakan menu CLI.
2.	Mengatur pemanggilan algoritma berdasarkan pilihan user.
B.	scheduling.py
1.	fcfs() menghitung waiting time dan turnaround time berdasarkan urutan kedatangan.
2.	sjf() memilih proses dengan burst time terkecil yang sudah datang.
C.	pagereplacement.py
1.	fifo() mengganti halaman berdasarkan urutan masuk.
2.	lru() mengganti halaman yang paling lama tidak digunakan.

Alur Data

1.User memilih menu di CLI.
2.Data proses / page reference diambil dari variabel Python.
3.Algoritma dijalankan sesuai pilihan.
4.Output ditampilkan dalam bentuk tabel dan metrik ringkasan.

---

## Demo Menjalankan Aplikasi (Docker)
Build Image
docker build -t os-simulator .
<img width="1225" height="667" alt="image" src="https://github.com/user-attachments/assets/664933bd-0d07-46b4-87be-f5147412cf50" />

Menjalankan Container
docker run -it --rm os-simulator

<img width="704" height="199" alt="image" src="https://github.com/user-attachments/assets/cf477d9d-5d60-4213-9424-b8e4361d48a6" />

Yang Ditunjukkan Saat Demo
Menu aplikasi muncul
Menjalankan FCFS / SJF
Menjalankan FIFO / LRU

Output tabel dan metrik tampil di terminal

OUTPUT FCFS

<img width="414" height="209" alt="image" src="https://github.com/user-attachments/assets/d1d9bed2-b567-4e9d-a54d-481bc7c642ad" />

OUTPUT SJF

<img width="457" height="206" alt="image" src="https://github.com/user-attachments/assets/455f5d50-a81c-4667-b5e6-b3e52b268d3b" />

OUTPUT FIFO

<img width="724" height="651" alt="image" src="https://github.com/user-attachments/assets/02bf6c77-2575-4bdd-89ba-c1f3ba9e0c8e" />

OUTPUT LRU

<img width="771" height="656" alt="image" src="https://github.com/user-attachments/assets/82901dbe-800e-4702-850d-f69e23bf9e63" />



## HASIL PENGUJIAN & ANALISIS
A. CPU Scheduling

Metrik
| **Algoritma**                     | **Average Waiting Time** | **Average Turnaround Time** |
| --------------------------------- | ------------------------ | --------------------------- |
| **FCFS (First Come First Serve)** | Lebih besar              | Lebih besar                 |
| **SJF (Shortest Job First)**      | Lebih kecil              | Lebih kecil                 |

Analisis

•	FCFS sederhana tetapi tidak mempertimbangkan burst time.

•	SJF meminimalkan waiting time rata-rata dengan memilih proses terpendek.

•	SJF lebih efisien namun berpotensi starvation.


B. Page Replacement

Matrik

| **Algoritma**                 | **Page Fault** | **Hit Ratio** |
| ----------------------------- | -------------- | ------------- |
| **FIFO (First In First Out)** | Lebih banyak   | Lebih kecil   |
| **LRU (Least Recently Used)** | Lebih sedikit  | Lebih besar   |

Analisis

•	FIFO tidak memperhatikan pola penggunaan halaman.

•	LRU lebih adaptif karena mempertimbangkan histori akses.

•	LRU memberikan performa memori yang lebih baik.

## PEMBAGIAN PERAN DAN KONTRIBUSI ANGGOTA KELOMPOK

| **No** | **Nama**              | **Peran**        | **Kontribusi**                                    |
| ------ | --------------------- | ---------------- | ------------------------------------------------- |
| 1      | Aldiman               | Project Lead     | Koordinasi tim, integrasi kode, build Docker      |
| 2      | Alfan Nur Fadzilah    | Developer 1      | Implementasi algoritma FCFS & SJF                 |
| 3      | Abdi Hanafi Alghifari | Developer 2      | Implementasi algoritma FIFO & LRU                 |
| 4      | Abdi Hanafi Alghifari | Dokumentasi & QA | Testing, penulisan README, pengambilan screenshot |

---


## Kesimpulan
Tuliskan 2–3 poin kesimpulan dari praktikum ini.

---

## Quiz
1. [Pertanyaan 1]  
   **menyatukan modul scheduling.py dan pagereplacement.py ke dalam main.py agar format input–output konsisten.:**  
2. [Pertanyaan 2]  
   **Docker memastikan aplikasi berjalan pada lingkungan yang sama di semua perangkat tanpa masalah dependensi:**  
3. [Pertanyaan 3]  
   **Modul yang paling terdampak adalah Page Replacement LRU, karena LRU memerlukan pencatatan histori akses halaman yang kompleks.:**
   
---

## Refleksi Diri
Tuliskan secara singkat:
- Apa bagian yang paling menantang minggu ini?  
- Bagaimana cara Anda mengatasinya?  

---

**Credit:**  
_Template laporan praktikum Sistem Operasi (SO-202501) – Universitas Putra Bangsa_
