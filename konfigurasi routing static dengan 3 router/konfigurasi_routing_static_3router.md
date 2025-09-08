# Konfigurasi Static Routing dengan 3 Router di Cisco Packet Tracer

## 1. Pendahuluan
Static Routing adalah metode routing di mana administrator jaringan menentukan secara manual rute yang akan dilalui oleh paket data. Pada topologi ini digunakan **3 router** yang saling terhubung untuk menghubungkan tiga network berbeda, sehingga setiap PC dapat saling berkomunikasi.

Tujuan dari praktikum ini adalah:
- Membuat topologi jaringan dengan 3 router.
- Mengkonfigurasi IP Address pada setiap interface router dan PC.
- Menerapkan static routing agar semua jaringan dapat saling berkomunikasi.
- Melakukan uji konektivitas dengan perintah `ping`.

---

## 2. Topologi Jaringan
Berikut topologi jaringan yang digunakan:

![Topologi Jaringan](gambar/Gambar1.png)

Keterangan IP Address:
- **Router0**
  - FastEthernet0/0 : 192.168.1.100 /24
  - Serial2/0 : 10.10.10.1 /8  
- **Router1**
  - FastEthernet0/0 : 192.168.2.100 /24
  - Serial2/0 : 10.10.10.2 /8
  - Serial3/0 : 20.20.20.2 /8
- **Router2**
  - FastEthernet0/0 : 192.168.3.100 /24
  - Serial2/0 : 20.20.20.1 /8  

---

## 3. Konfigurasi Router dan PC

### Router0
- Interface FastEthernet0/0  
![Konfigurasi Router0 Fa0/0](gambar/Gambar2.png)

- Interface Serial2/0  
![Konfigurasi Router0 S2/0](gambar/Gambar3.png)

### Router1
- Interface FastEthernet0/0  
![Konfigurasi Router1 Fa0/0](gambar/Gambar4.png)

- Interface Serial2/0  
![Konfigurasi Router1 S2/0](gambar/Gambar5.png)

- Interface Serial3/0  
![Konfigurasi Router1 S3/0](gambar/Gambar6.png)

### Router2
- Interface FastEthernet0/0  
![Konfigurasi Router2 Fa0/0](gambar/Gambar7.png)

- Interface Serial2/0  
![Konfigurasi Router2 S2/0](gambar/Gambar8.png)

---

### PC
- PC0 : 192.168.1.1 /24  
![PC0](gambar/Gambar9.png)

- PC1 : 192.168.1.2 /24  
![PC1](gambar/Gambar10.png)

- PC2 : 192.168.2.1 /24  
![PC2](gambar/Gambar11.png)

- PC3 : 192.168.2.2 /24  
![PC3](gambar/Gambar12.png)

- PC4 : 192.168.3.1 /24  
![PC4](gambar/Gambar13.png)

- PC5 : 192.168.3.2 /24  
![PC5](gambar/Gambar14.png)

---

## 4. Konfigurasi Routing

### Router0 - Static Route
![Static Route Router0](gambar/Gambar15.png)

### Router1 - RIP Routing
![RIP Router1](gambar/Gambar16.png)

### Router1 - Static Route
![Static Route Router1](gambar/Gambar17.png)

### Router2 - RIP Routing
![RIP Router2](gambar/Gambar18.png)

### Router2 - Static Route
![Static Route Router2](gambar/Gambar19.png)

---

## 5. Pengujian Koneksi (Ping Test)

- Ping PC0 ke PC1  
![Ping PC0 ke PC1](gambar/Gambar20.png)

- Ping PC2 ke PC3  
![Ping PC2 ke PC3](gambar/Gambar21.png)

- Ping PC4 ke PC5  
![Ping PC4 ke PC5](gambar/Gambar22.png)

- Ping antar jaringan (PC1 ke PC4)  
![Ping Antar Jaringan](gambar/Gambar23.png)

---

## 6. Kesimpulan
Dari hasil konfigurasi dan pengujian dapat disimpulkan bahwa:
1. Jaringan dengan 3 router dapat terhubung menggunakan static routing.
2. RIP Routing juga dapat digunakan untuk mempermudah pertukaran routing antar router.
3. Semua PC dari network **192.168.1.0/24**, **192.168.2.0/24**, dan **192.168.3.0/24** dapat saling berkomunikasi.
4. Pengujian `ping` berhasil menunjukkan bahwa topologi sudah berjalan dengan baik.

## DIBUAT OLEH
ANDI KURNIAWAN
