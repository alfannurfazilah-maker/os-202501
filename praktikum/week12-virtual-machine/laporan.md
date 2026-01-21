
# Laporan Praktikum Minggu [12]
Topik: Virtualisasi Menggunakan Virtual Machine  

---

## Identitas
- **Nama**  : Alfan Nur Fadzilah
- **NIM**   : 250320575
- **Kelas** : 1DSRA

---

## Tujuan
1. Menginstal perangkat lunak virtualisasi (VirtualBox/VMware).  
2. Membuat dan menjalankan sistem operasi guest di dalam VM.  
3. Mengatur konfigurasi resource VM (CPU, RAM, storage).  
4. Menjelaskan mekanisme proteksi OS melalui virtualisasi.  
5. Menyusun laporan praktikum instalasi dan konfigurasi VM secara sistematis.

---

## Dasar Teori
Virtualisasi adalah teknologi yang memungkinkan satu perangkat keras fisik menjalankan beberapa sistem operasi secara bersamaan dengan cara membuat lingkungan virtual. Teknologi ini bertujuan untuk meningkatkan efisiensi penggunaan sumber daya, fleksibilitas, serta kemudahan pengelolaan sistem.

Virtual Machine (VM) merupakan mesin virtual yang bekerja seperti komputer fisik, lengkap dengan sistem operasi dan aplikasi sendiri. VM dijalankan di atas perangkat lunak yang disebut hypervisor, yang bertugas mengatur dan membagi sumber daya fisik seperti CPU, memori, dan penyimpanan kepada setiap VM.

Terdapat dua jenis hypervisor, yaitu Type 1 (bare-metal) yang berjalan langsung di atas perangkat keras, dan Type 2 (hosted) yang berjalan di atas sistem operasi host. Dengan VM, isolasi antar sistem dapat terjaga sehingga gangguan pada satu VM tidak memengaruhi VM lainnya.

Penggunaan virtual machine banyak diterapkan pada server, pengujian perangkat lunak, dan pembelajaran sistem operasi karena mampu menyediakan lingkungan yang aman, terisolasi, dan mudah dikonfigurasi.

---

## Langkah Praktikum
1. **Instalasi Virtual Machine**
   - Instal VirtualBox atau VMware pada komputer host.  
   - Pastikan fitur virtualisasi (VT-x / AMD-V) aktif di BIOS.

2. **Pembuatan OS Guest**
   - Buat VM baru dan pilih OS guest (misal: Ubuntu Linux).  
   - Atur resource awal:
     - CPU: 1–2 core  
     - RAM: 2–4 GB  
     - Storage: ≥ 20 GB

3. **Instalasi Sistem Operasi**
   - Jalankan proses instalasi OS guest sampai selesai.  
   - Pastikan OS guest dapat login dan berjalan normal.

4. **Konfigurasi Resource**
   - Ubah konfigurasi CPU dan RAM.  
   - Amati perbedaan performa sebelum dan sesudah perubahan resource.

5. **Analisis Proteksi OS**
   - Jelaskan bagaimana VM menyediakan isolasi antara host dan guest.  
   - Kaitkan dengan konsep *sandboxing* dan *hardening* OS.

6. **Dokumentasi**
   - Ambil screenshot setiap tahap penting.  
   - Simpan di folder `screenshots/`.

7. **Commit & Push**
   ```bash
   git add .
   git commit -m "Minggu 12 - Virtual Machine"
   git push origin main
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
1. Apa perbedaan antara host OS dan guest OS?
   
   **Jawaban** Perbedaan antara host OS dan guest OS adalah sebagai berikut:

Host OS adalah sistem operasi yang berjalan langsung pada perangkat keras fisik dan menjadi dasar untuk menjalankan virtualisasi.

Guest OS adalah sistem operasi yang berjalan di dalam Virtual Machine (VM) dan dijalankan di atas host OS melalui hypervisor.
   
2. Apa peran hypervisor dalam virtualisasi?

 
   **Jawaban:** Peran hypervisor dalam virtualisasi adalah sebagai pengelola dan penghubung antara perangkat keras fisik dan Virtual Machine (VM).

Hypervisor bertugas membagi dan mengatur sumber daya seperti CPU, memori, dan penyimpanan agar dapat digunakan oleh beberapa VM secara bersamaan, serta memastikan isolasi antar VM sehingga satu VM tidak mengganggu VM lainnya.
   
3. Mengapa virtualisasi meningkatkan keamanan sistem?
 
   **Jawaban:**  Virtualisasi meningkatkan keamanan sistem karena setiap Virtual Machine (VM) berjalan secara terisolasi.

Jika terjadi gangguan, kesalahan, atau serangan pada satu VM, dampaknya tidak langsung memengaruhi VM lain maupun sistem fisik. Selain itu, virtualisasi memungkinkan pembuatan lingkungan uji coba yang aman (sandbox), sehingga aktivitas berisiko dapat dilakukan tanpa membahayakan sistem utama.

---

## Refleksi Diri
Tuliskan secara singkat:
- Apa bagian yang paling menantang minggu ini?  
- Bagaimana cara Anda mengatasinya?  

---

**Credit:**  
_Template laporan praktikum Sistem Operasi (SO-202501) – Universitas Putra Bangsa_
