
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
- Langkah-langkah yang dilakukan.
- Perintah yang dijalankan.
- File dan kode yang dibuat.
- Commit message yang digunakan.

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

## Hasil Eksekusi
**Eksperimen 1**
![Screenshot hasil](<screenshots/Screenshot 2025-11-05 230530.png>)
| No | Perintah                 | Output / Hasil                                                                 | Fungsi / Keterangan                                      |
|----|--------------------------|-------------------------------------------------------------------------------|----------------------------------------------------------|
| 1  | `whoami`                 | `alfan`                                                                       | Menampilkan user yang sedang aktif.                     |
| 2  | `id`                     | `uid=1000(alfan) gid=1000(alfan) groups=1000(alfan),4(adm),20(dialout),27(sudo),...` | Menampilkan UID, GID, dan grup yang diikuti user.       |
| 3  | `groups`                 | `alfan adm dialout cdrom sudo audio dip video plugdev netdev`                  | Menampilkan daftar grup user secara ringkas.           |
| 4  | `sudo adduser praktikan` | - Membuat user & grup `praktikan` <br>- Home `/home/praktikan` <br>- Set password | Menambahkan user baru beserta environment-nya.         |
| 5  | `su - praktikan`         | Login shell baru sebagai `praktikan`                                           | Berpindah ke user `praktikan` dengan environment baru.  |
| 6  | `whoami` (setelah su)    | `praktikan`                                                                    | Mengecek user aktif setelah berpindah.                  |

**Eksperimen 2**
![Screenshot hasil](<screenshots/eksperimen 2 week 4 bagian 1.png>)
| Kolom    | Contoh Nilai           | Keterangan                                                                 |
|----------|----------------------|---------------------------------------------------------------------------|
| USER     | root                 | Nama user yang menjalankan proses. Bisa `root` (admin) atau user biasa.  |
| PID      | 70                   | Process ID: nomor unik setiap proses. Digunakan untuk identifikasi atau menghentikan proses. |
| %CPU     | 0.6                  | Persentase penggunaan CPU oleh proses. Berguna untuk memantau beban CPU. |
| %MEM     | 0.9                  | Persentase penggunaan memori RAM oleh proses. Berguna untuk memantau penggunaan memori. |
| VSZ      | 88804                | Virtual memory size dalam KB yang dialokasikan untuk proses.             |
| RSS      | 17860                | Resident Set Size: jumlah memori fisik yang digunakan proses (KB).       |
| TTY      | ?                    | Terminal tempat proses dijalankan. `?` artinya tidak terhubung ke terminal. |
| STAT     | S<s                  | Status proses. Contoh: S = sleeping, R = running, Z = zombie.           |
| START    | 20:00                | Waktu proses dimulai.                                                   |
| TIME     | 0:10                 | Total CPU time yang sudah digunakan proses sejak mulai.                  |
| COMMAND  | /lib/systemd/systemd-journald | Nama program atau perintah yang dijalankan proses.                        |     

**Eskperimen 3**
```
praktikan@user:~$ sleep 1000 &
[1] 1262
praktikan@user:~$ ps aux | grep sleep
praktik+    1262  0.0  0.0   3212  1792 pts/0    S    20:32   0:00 sleep 1000
praktik+    1280  0.0  0.1   4028  2176 pts/0    S+   20:33   0:00 grep --color=auto sleep
praktikan@user:~$ kill 1262
praktikan@user:~$ ps aux | grep sleep
praktik+    1331  0.0  0.1   4028  2176 pts/0    S+   20:36   0:00 grep --color=auto sleep
[1]+  Terminated              sleep 1000
praktikan@user:~$ kill 4028
-bash: kill: (4028) - No such process
praktikan@user:~$ ps aux | grep sleep
praktik+    1433  0.0  0.1   4028  2176 pts/0    S+   20:39   0:00 grep --color=auto sleep
```
| No | Perintah                | Output / Hasil                                | Keterangan / Fungsi                                                                 |
|----|-------------------------|-----------------------------------------------|------------------------------------------------------------------------------------|
| 1  | `sleep 1000 &`          | `[1] 1262`                                   | Menjalankan proses sleep selama 1000 detik di background. `1262` = PID proses.     |
| 2  | `ps aux | grep sleep`   | PID 1262 sleep 1000<br>PID 1280 grep sleep   | Melihat proses sleep yang berjalan. PID 1262 = sleep, PID 1280 = grep yang dijalankan untuk mencari sleep. |
| 3  | `kill 1262`             | `[1]+  Terminated sleep 1000`                | Menghentikan proses sleep dengan PID 1262.                                         |
| 4  | `ps aux | grep sleep`   | PID 1280 grep sleep                           | Hanya proses grep yang muncul, sleep sudah dihentikan.                              |
| 5  | `kill 4028`             | `-bash: kill: (4028) - No such process`      | PID 4028 tidak ada; proses grep sebelumnya bukan target sleep. 

**Eksperimen 4**

```
praktikan@user:~$ pstree -p | head -20
systemd(1)-+-agetty(244)
           |-agetty(253)
           |-cron(182)
           |-dbus-daemon(184)
           |-init-systemd(Ub(2)-+-SessionLeader(293)---Relay(295)(294)---bash(295)---su(837)---bash(853)-+-head(1489)
           |                    |                                                                        `-pstree(1488)
           |                    |-init(7)---{init}(8)
           |                    |-login(296)---bash(361)
           |                    `-{init-systemd(Ub}(9)
           |-networkd-dispat(188)
           |-rsyslogd(189)-+-{rsyslogd}(210)
           |               |-{rsyslogd}(211)
           |               `-{rsyslogd}(212)
           |-systemd(342)---(sd-pam)(343)
           |-systemd(845)---(sd-pam)(846)
           |-systemd-journal(70)
           |-systemd-logind(206)
           |-systemd-resolve(120)
           |-systemd-timesyn(128)---{systemd-timesyn}(175)
           |-systemd-udevd(99)
```

| Proses / COMMAND            | PID   | Keterangan                                                                 |
|------------------------------|-------|---------------------------------------------------------------------------|
| systemd                     | 1     | Proses induk utama Linux, semua proses lain merupakan cabang dari ini.   |
| agetty                       | 244   | Menangani login terminal.                                                |
| agetty                       | 253   | Menangani login terminal tambahan.                                       |
| cron                         | 182   | Task scheduler untuk cron jobs.                                          |
| dbus-daemon                  | 184   | Message bus untuk komunikasi antar proses.                                |
| init-systemd(Ub)             | 2     | Sub-proses init di WSL, induk session user.                              |
| SessionLeader / Relay / bash | 293-295 | Shell aktif yang dijalankan user.                                        |
| su                           | 837   | Proses untuk berpindah user.                                             |
| bash                         | 853   | Shell baru setelah `su`.                                                 |
| systemd-journal              | 70    | Mencatat log sistem.                                                     |
| systemd-resolve              | 120   | Mengatur DNS dan resolusi nama.                                          |
| systemd-timesyncd            | 128   | Sinkronisasi waktu sistem.                                               |
| systemd-udevd                | 99    | Mengatur perangkat keras dan event kernel.                                |
| networkd-dispatcher          | 188   | Mengatur network daemon di background.                                   |
| rsyslogd                     | 189   | Proses logging sistem.                                                   |
| {rsyslogd}                   | 210-212 | Thread tambahan untuk rsyslogd.                                         |
| systemd-logind               | 206   | Manajemen session user login.                                            |
| systemd (user)               | 342-845 | Systemd instance untuk user (alfan/praktikan).                          |
| (sd-pam)                     | 343-846 | Proses PAM untuk autentikasi.                                           |
| head                         | 1489  | Proses head untuk menampilkan 20 baris pertama output pstree.            |

---

## Analisis
1. User Management:

 - whoami, id, groups digunakan untuk mengecek user aktif, UID, GID, dan grup yang diikuti.

 - sudo adduser dapat menambahkan user baru beserta grup dan home directory.

 - su - <user> digunakan untuk berpindah user dengan environment shell baru.

2. Process Management:

 - ps aux menampilkan daftar proses beserta PID, user, %CPU, %MEM, dan command.

 - top memberikan snapshot penggunaan CPU, memori, dan status proses secara real-time.

 - sleep dapat dijalankan di background (&) dan dihentikan dengan kill <PID>.

 - pstree menampilkan hierarki proses, memudahkan identifikasi parent-child relationship.

3. Observasi:

 - Proses sistem penting (systemd, cron, dbus, rsyslog) selalu berjalan di background.

 - Proses user (bash, su) merupakan cabang dari session user di bawah systemd.

 - Penggunaan PID memungkinkan pengendalian proses secara tepat.

## Kesimpulan
Praktikum ini menunjukkan cara mengelola user dan proses di Linux. Perintah seperti whoami, id, groups, adduser, dan su digunakan untuk manajemen user, sedangkan ps, top, sleep, kill, dan pstree digunakan untuk memantau dan mengendalikan proses. Dari hasil praktikum, terlihat hierarki proses sistem dan proses user, serta cara menghentikan atau memeriksa proses secara efektif.

---

## Quiz
1. [Apa fungsi dari proses init atau systemd dalam sistem Linux?]  
   **Jawaban:**
   
**Proses Induk (PID 1):**

   - Semua proses lain pada sistem adalah turunan dari init/systemd.

   -Menjadi “root” dari pohon proses, sehingga mengatur parent-child relationship antar proses.

**Inisialisasi Sistem:**

   -  Menjalankan service, daemon, dan task penting saat booting, misalnya:

   -  cron → task scheduler

   -  dbus-daemon → message bus untuk komunikasi antar proses

   -  systemd-journald → pencatatan log sistem

 **Manajemen Layanan / Daemon:**

   -  Menyediakan framework untuk start, stop, restart, dan monitoring layanan menggunakan systemctl.

**Manajemen Session User:**

   -Mengelola session login user dan shell (misal bash), termasuk autentikasi melalui PAM (sd-pam).

**Pemulihan Sistem:**

    -Jika ada proses zombie atau crash, systemd dapat membersihkan dan menjaga stabilitas sistem.
   
2. [Apa perbedaan antara kill dan killall?]  
   **Jawaban:**
   kill digunakan untuk menghentikan atau mengirim sinyal ke proses tertentu berdasarkan PID (Process ID). Jadi, kamu harus mengetahui nomor PID proses yang ingin dihentikan. Sedangkan killall digunakan untuk menghentikan atau mengirim sinyal ke semua proses dengan nama tertentu, tanpa perlu mengetahui PID-nya. Singkatnya, kill menargetkan satu proses spesifik, sedangkan killall bisa menargetkan banyak proses sekaligus dengan nama yang sama.
   
3. [Mengapa user root memiliki hak istimewa di sistem Linux?]
   **Jawaban:**  
User root memiliki hak istimewa di sistem Linux karena ia merupakan superuser, yaitu pengguna dengan kendali penuh terhadap seluruh sistem. Hak istimewa ini memungkinkan root untuk:

- Mengakses dan mengubah semua file, termasuk file sistem dan milik pengguna lain.

- Menginstal, menghapus, atau memperbarui perangkat lunak.

- Mengelola pengguna dan izin akses.

- Menghentikan atau memulai layanan dan proses penting sistem.

---

## Refleksi Diri
Tuliskan secara singkat:
- Apa bagian yang paling menantang minggu ini? semua sulit 
- Bagaimana cara Anda mengatasinya? mencari tau di menggunakan AI
---

**Credit:**  
_Template laporan praktikum Sistem Operasi (SO-202501) – Universitas Putra Bangsa_
