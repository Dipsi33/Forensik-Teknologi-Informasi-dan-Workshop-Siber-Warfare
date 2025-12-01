## Broken Access Control

### Informasi Dasar
### Deskripsi : 
Penyerang dan peretas dapat mengakses sebuah sistem ketika autentikasi dan pembatasan akses tidak diterapkan dengan baik. Dengan kata lain, Broken Access Control memungkinkan entri yang tidak sah yang dapat mengakibatkan kerentanan data dan file yang bersifat sensitif. Kontrol akses yang lemah terkait manajemen kredensial dapat dihindari dengan metode coding yang unik dan tindakan khusus seperti mematikan akun administratif dan penggunaan autentikasi multi-faktor.

### Target Serangan : 
Semua jenis Web Server, application server, dan web application rentan dan mudah untuk terkena beberapa permasalahan ini. Bahkan website yang hanya bersifat statis, jika tidak diatur dengan baik, dapat diretas oleh hacker, seperti akses terhadap file - file penting, deface, ataupun beberapa perbuatan merusak lainnya. 

### Bagaimana cara mengetahui keamanan Access Control : 
Semua website dipastikan membutuhkan access control. Oleh karena itu aturan dan desain nya sendiri harus secara jelas dan terdokumentasi. Jika tidak ada dokumentasi hampir dipastikan, website tersebut kemungkinan besar rentan. Code yang digunakan harus terstruktur, modular, dan sebagian besar terpusat. Review secara mendetail terhadap code harus dilakukan untuk memvalidasi keabsahan dari implementasi Access Control. Selain itu melakukan test dengan cara membobol code yang digunakan juga akan sangat membantu mengetahui ada atau tidaknya permasalahan pada Access Control.

## Percobaan : Mengubah Isi Keranjang User

1. Setelah melakukan pengaksesan localhost 3000 di terminal dan mempersiapkan aplikasi burpsuite di sini, saya melakukan login dengan menggunakan akun yang sudah di daftarkan sebelumnya.           

![login.png](login.png)

2. Kemudian setelah melakukan proses login disini akan di arahkan ke halaman dashboard untuk dapat memilih beberapa item dan nantinya akan disimpan ke keranjang.

![halaman dashboard.png](halaman dashboard.png)
 
3. Kemudian menuju halaman keranjang untuk dapat melihat yang telah ditambahkan yaitu aple juice dan apple pomance masing masing 1 buah.

![halaman keranjang.png](halaman.keranjang.png)

4. Kemudian disini saya membuka halaman proxy di dalam http history untuk melihat track http history. Terdapat informasi host, method, url, status, length dan informasi pendukung lainnya.

![track http history.png](Image/track http history.png)

5. Kemudian setelah itu saya pilih http history yang memiliki params
 json dengan get /rest/basket/7. Kemudian saya lihat mengenai request
 dan response yang tertampil di halaman tersebut. Dimana response
 berisi informasi isi keranjang yang telah saya pilih sebelumnya.

![params  json dengan get-rest-basket-7.png](Image/params json dengan get-rest-basket-7.png) 

6. Kemudian saya pindahkan list request yang saya amati sebelumnya menuju repeater, kemudian saya send dan pada response terlihat data keranjang yang sudah sesuai dengan apa yang diinputkan sebelumnya.

![list request.png](Image/list request.png)
![halaman keranjang.png](Image/halaman keranjang.png)

7. Setelah melihat informasi response di repeater, saya mencoba untuk mengganti data id 7 menjadi 2 untuk melihat apakah terdapat perubahan yang ditampilkan response. Dan ternyata response membrikan informasi berbeda dari sebelumnya yang mana ternyata menunjukkan isi keranjang id 2.

 ![ganti id 7 menjadi id2.png](Image/ganti id 7 menjadi id2.png)

8. Kemudian disini saya akan menggunakan fitur intercept untuk menampilkan data keranjang user lain di dalam website owasp juice shop. Dimana saya merubah status intercept yang tadinya off menjadi on.

![Intercept off.png](Image/Intercept off.png)

9. Ketika intercept on disini terdapat baris informasi request terkait owasp juice shop. Kemudian saya foorward data tersebut hingga menemukan data get /rest/basket/7, kemudian saya ganti data uiidnya dengan id lain selain id 7 kemudian saya forward kembali informasi tersebut.

![ketika intercept on.png](Image/ketika intercept on.png)

10. Website berhasil menampilkan isi keranjang pengguna lainnya berikut adalah isi keranjang pengguna : id (2).

![isi keranjang 2.png](Image/isi keranjang 2.png)
 ![ganti id 7 menjadi id2.png](Image/ganti id 7 menjadi id2.png)

11. Website berhasil menampilkan isi keranjang pengguna lainnya berikut adalah isi keranjang pengguna : id (4).

![id 4.png](Image/id 4.png)
![Keranjang ID 4.png](Image/id 4.png)


12. Website berhasil menampilkan isi keranjang pengguna lainnya berikut adalah isi keranjang pengguna : id (5).

![id 5.png](Image/id 5.png)

13. Disini saya sudah berhasil untuk melakukan challenge melihat keranjang orang lain.

![berhasil.png](Image/berhasil.png)

## Percobaan : Login Admin

1. Disini saya bermaksud ingin mencari data email, yang mana ditemukan di komentar ulasan. Dimana ada informasi email admin disana.

 ![mencari email.png](Image/mencari email.png)

2. Kemudian saya melakukan login dengan menggunakan password dummy, namun sebelumnya saya melakukan perubahan status menjadi on di intercept.

![login password.png](Image/login password.png)
![login intercept on.png](Image/login intercept on.png)
3. Ketika melakukan submit login, intercept memberikan informasi berupa baris informasi yang mana memuat email dan password.
![login password.png](Image/login password.png)
![login intercept on.png](Image/login intercept on.png)
4. Kemudian setelah melihat informasi tersebut, saya menggunakan ikon yang dikotaki warna merah untuk melakukan pengiriman menuju intruder, positions.

![clear.png](Image/clear.png)
![login password.png](Image/login password.png)

5. Kemudian kita berpindah ke halaman intruder, positions dan melihat data informasi yang ada disana, kemudian klik clear. Ada penambahan beberapa data ketika proses melakukan clear data.

![password dummy.png](Image/password dummy.png)
![login password.png](Image/login password.png)

6. Kemudian klik add, yang mana dalam hal ini akan membuat data email memiliki tambahan sign dollar didepannya. Hal ini membuat adanya perubahan yang ada.

![klik add.png](Image/klik add.png)
![login password.png](Image/login password.png)

7. Proses berikutnya saya menuju ke payloads dan melakukan load data file password.txt yang sebelumnya sudah dibuat.

![payload.png](Image/payload.png)

8. Setelah itu kemudian data yang telah digunakan dapat diinputkan pada text akan muncul di dalam kotak putih sebagai list data password, kemudian kita dapat mengklik button start attack.

![list data password.png](Image/list data password.png) 

9. Setelah itu, akan tertampil sebuah modal yang menampilkan list password yang dicoba sebelumnya, dan memuat informasi status dan length dan data lain. Disini semua 401 (tidak memiliki autorisasi)  hasilnya kecuali data terakhir "admin123" yang memiliki status 200 (memiliki autorisasi)

![memuat informasi password.png](Image/memuat informasi password.png)

10. Kemudian saya mencoba untuk login menggunakan "admin1123" disini saya berhasil untuk login sebagai admin dan dapat mengakses keranjang serta profile dari akun admin yang ada di dalam owasp juice shop.

![login password.png](Image/login password.png)
![berhasil login.png](Image/berhasil login.png)
![terbuka semua keranjang.png](Image/terbuka semua keranjang.png)
![masuk ke akun admin.png](Image/masuk ke akun admin.png)
![keranjang semuuaa terbuka.png](Image/keranjang semuuaa terbuka.png)

## Kesimpulan

Disini saya berhasil membuktikan bahwa website owasp juice shop ini masih memiliki kerentanan yang mana disebutkan dalam owasp 10 yakni broken access control dimana saya dapat melihat keranjang dari user lain dan login sebagai admin padahal saya tidak terdaftar dan belum mengetahui password admin sebelumnya.

Dibuat Oleh : Serka Bek Andi Kurniawan
