[README.md](https://github.com/user-attachments/files/22040837/README.md)
# Laporan Routing Statis dengan 2 Router

## Topologi Jaringan
Berikut adalah topologi jaringan yang digunakan pada simulasi routing statis menggunakan Cisco Packet Tracer:

![Topologi](img/gambar1.png)

---

## Konfigurasi PC
### PC 1
- IP Address: `192.168.1.2`
- Subnet Mask: `255.255.255.0`
- Default Gateway: `192.168.1.1`

![Konfigurasi PC1](img/gambar3.png)

### PC 2
- IP Address: `192.168.3.2`
- Subnet Mask: `255.255.255.0`
- Default Gateway: `192.168.3.1`

![Konfigurasi PC2](img/gambar4.png)

---

## Konfigurasi Router

### Router 1 (R1)
- FastEthernet 0/0: `192.168.1.1/24`
- FastEthernet 0/1: `192.168.2.1/24`
- Static Route: `192.168.3.0/24 via 192.168.2.2`

![Router 1](img/gambar5.png)

### Router 2 (R2)
- FastEthernet 0/0: `192.168.3.1/24`
- FastEthernet 0/1: `192.168.2.2/24`
- Static Route: `192.168.1.0/24 via 192.168.2.1`

![Router 2](img/gambar6.png)

---

## Pengujian Koneksi

### Ping dari PC1 ke PC2
Hasil pengujian ping dari PC1 ke PC2 berhasil dengan respon yang baik.

![Ping PC1](img/gambar7.png)

### Ping dari PC2 ke PC1
Hasil pengujian ping dari PC2 ke PC1 berhasil tanpa packet loss.

![Ping PC2](img/gambar8.png)

### Traceroute
Traceroute dari PC1 ke PC2 menunjukkan jalur komunikasi melalui kedua router.

![Traceroute](img/gambar9.png)

---

## Kesimpulan
- Routing statis berhasil diterapkan menggunakan 2 router.  
- PC1 dan PC2 yang berada pada jaringan berbeda dapat saling berkomunikasi melalui static routing.  
- Dengan konfigurasi ini, komunikasi data berjalan lancar dan stabil.

## Dibuat Oleh
ANDI KURNIAWAN
