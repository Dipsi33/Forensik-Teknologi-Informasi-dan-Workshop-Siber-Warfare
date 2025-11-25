# 🛡️ Laporan Hasil Scanning Nmap --- Metasploitable2 (Enhanced Version)

## 📌 Informasi Target

-   **IP Address:** 192.168.100.10\
-   **Hostname:** target\
-   **Command:** `nmap -n -Pn -p- -A target -o hasil_scan.txt`

![gambar1.png](images/gambar1.png)
![gambar2.png](images/gambar2.png)
![gambar3.png](images/gambar3.png)
------------------------------------------------------------------------

# 🔍 Ringkasan Port Terbuka & Analisis Risiko

  Port          Status   Service               Keterangan
  ------------- -------- --------------------- ------------------------------------
  21            open     FTP (vsftpd 2.3.4)    Anonymous login, rawan data breach
  22            open     SSH (OpenSSH 4.7p1)   Versi lama, potensi brute force
  23            open     Telnet                Tidak terenkripsi
  25            open     SMTP (Postfix)        SSL kadaluarsa
  53            open     DNS (BIND 9.4.2)      Rawan DNS Poisoning
  80            open     Apache 2.2.8          Default Metasploitable web
  111           open     RPCBind               Digunakan untuk pivoting
  139/445       open     Samba 3.0.20          Rentan RCE (CVE-2007--2447)
  512--514      open     RSH Services          Login tanpa password
  1099          open     Java RMI              Potensi RCE
  1524          open     Backdoor Bind Shell   Root shell terbuka
  2049          open     NFS                   Akses filesystem
  2121          open     ProFTPD 1.3.1         Reverse shell exploit
  3306          open     MySQL 5.0             Password lemah / kosong
  3632          open     distccd               RCE exploit tersedia
  5432          open     PostgreSQL 8.3        Versi lama
  5900          open     VNC                   Tidak terenkripsi
  6000          open     X11                   Bisa menyadap GUI
  6667 / 6697   open     UnrealIRCD            Backdoor default
  8180          open     Apache Tomcat 5.5     Default credentials

------------------------------------------------------------------------

# 🧨 Kerentanan Paling Kritis

## 1. Remote Code Execution (RCE)

Sumber kerentanan: - Samba 3.0.20\
- distccd\
- UnrealIRCD Backdoor\
- ProFTPD 1.3.1

**Dampak:** Penyerang dapat eksekusi perintah sebagai root.

------------------------------------------------------------------------

## 2. Credential Leak

-   FTP Anonymous Access\
-   Telnet\
-   RSH (rlogin, rshell)

**Dampak:** Login tanpa autentikasi.

------------------------------------------------------------------------

## 3. Web Exploitation

-   Apache 2.2.8\
-   Tomcat 5.5

**Dampak:** Upload shell → akses penuh webserver.

------------------------------------------------------------------------

## 4. Outdated Services

Hampir semua layanan menggunakan versi 2007--2010 dan memiliki eksploit
publik.

------------------------------------------------------------------------

# 📊 Tabel Risiko

  ---------------------------------------------------------------------------
  No      Risiko         Layanan Terdampak                  Dampak
  ------- -------------- ---------------------------------- -----------------
  1       Remote Code    Samba, distccd, ProFTPD            Full compromise
          Execution                                         

  2       Credential     FTP, Telnet, RSH                   Pengambilalihan
          Leak                                              akun

  3       Web Exploit    Apache, Tomcat                     Upload shell

  4       Enumeration    NFS, MySQL, RPC                    Pivoting

  5       Outdated       Semua                              Eksploit publik
          Service                                           tersedia
  ---------------------------------------------------------------------------

------------------------------------------------------------------------

# 📝 Kesimpulan

Metasploitable2 pada IP **192.168.100.10** memiliki lebih dari **30 port
terbuka** dan hampir seluruh service rentan. Ini ideal untuk latihan
penetration testing, namun dalam konteks dunia nyata sistem seperti ini
**sangat berbahaya** dan dapat diambil alih dalam hitungan menit.

------------------------------------------------------------------------

# 📁 Lampiran

Semua hasil scanning direkomendasikan untuk: - Disimpan dalam folder
`/hasil_scan_nmap/` - Diupload ke GitHub - Disertai screenshot terminal
& nmap output

dibuat oleh Serka Bek Andi
