# Jarkom-Modul-1-A10-2023

## Anggota Kelompok

| NRP        | Name                        |
| ---------- | --------------------------- |
| 5025211081 | Gabriella Natasya Br Ginting|
| 5025211102 | Adhira Riyanti Amanda       |

### Daftar Isi
- [Soal 1](#soal-1)
- [Soal 2](#soal-2)
- [Soal 3](#soal-3)
- [Soal 4](#soal-4)
- [Soal 5](#soal-5)
- [Soal 6](#soal-6)
- [Soal 7](#soal-7)
- [Soal 8](#soal-8)
- [Soal 9](#soal-9)
- [Soal 10](#soal-10)

## Soal 1
User melakukan berbagai aktivitas dengan menggunakan protokol FTP. Salah satunya adalah mengunggah suatu file.

-> Untuk melihat aktivitas mengunggah suatu file dengan protokol FTP dapat ditemukan pada nomor yang memiliki info `STOR`, yang dimana STOR merupakan perintah yang digunakan untuk mengunggah file. Untuk menemukannya dapat dicari dengan `ftp.request.command == "STOR"`, dan terdapat pada nomor `147`.

Lalu untuk mendapatkan response dari aktivitas tersebut dapat dilihat pada info yang mengandung `Response` setelah request dari nomor 147, yaitu nomor `149`.

- Berapakah sequence number (raw) pada packet yang menunjukkan aktivitas tersebut? 

-> Untuk mendapatkan sequence number (raw) pada packet yang menunjukkan aktivitas mengunggah suatu file dapat dilihat pada nomor `147` dan bagian `Transmission Control Protocol`. Maka, nilai `Sequence Number (raw)` akan terlihat seperti pada gambar di bawah ini:

![soal 1](/images/soal1/soal1-a.jpg)

**Hasil:**
```
Sequence Number (raw): 258040667
```

- Berapakah acknowledge number (raw) pada packet yang menunjukkan aktivitas tersebut? 

-> Untuk mendapatkan nilai acknowledge number (raw) pada packet yang menunjukkan aktivitas mengunggah suatu file dapat dilihat pada nomor `147` dan bagian `Transmission Control Protocol`. Maka, nilai `acknowledge number (raw)` akan  terlihat seperti pada gambar di bawah ini:

![soal 1](/images/soal1/soal1-b.jpg)

**Hasil:**
```
Acknowledgment number (raw): 1044861039
```

- Berapakah sequence number (raw) pada packet yang menunjukkan response dari aktivitas tersebut?

-> Untuk mendapatkan nilai sequence number (raw) pada packet yang menunjukkan response dari aktivitas mengunggah suatu file dapat dilihat pada nomor `149` dan bagian `Transmission Control Protocol`. Maka, nilai `sequence number (raw)` akan  terlihat seperti pada gambar di bawah ini:

![soal 1](/images/soal1/soal1-c.jpg)

**Hasil:**
```
Sequence Number (raw): 1044861039
```

- Berapakah acknowledge number (raw) pada packet yang menunjukkan response dari aktivitas tersebut?

-> Untuk mendapatkan nilai acknowledge number (raw) pada packet yang menunjukkan response dari aktivitas mengunggah suatu file dapat dilihat pada nomor `149` dan bagian `Transmission Control Protocol`. Maka, nilai `acknowledge number (raw)` akan  terlihat seperti pada gambar di bawah ini:

![soal 1](/images/soal1/soal1-d.jpg)

**Hasil:**
```
Acknowledgment number (raw): 258040696
```

## Soal 2
Sebutkan web server yang digunakan pada portal praktikum Jaringan Komputer!

1. Hal yang dilakukan pertama adalah melihat ip address dari portal praktikum Jaringan Komputer, yang dimana terdapat `10.21.78.111`

    ![soal 2](/images/soal2/4.jpg)

2. Lalu, dapat dicari dengan kueri `ip.addr == 10.21.78.111` pada wireshark, dan akan didapatkan informasi seperti dibawah ini:

    ![soal 2](/images/soal2/1.jpg)

3. Pada source yang memiliki nilai yang sama dengan ip address yang kita cari, kita dapat klik kanan dan pilih follow, lalu pilih TCP Stream. Ikuti langkah seperti pada gambar dibawah ini:

    ![soal 2](/images/soal2/2.jpg)

4. Setelah follow TCP Stream akan ditampilkan sekumpulan informasi, dan akan didapatkan informasi server yang digunakan pada portal praktikum Jaringan Komputer.

    ![soal 2](/images/soal2/3.jpg)

**Hasil:**

```
Server: gunicorn
```

## Soal 3
Dapin sedang belajar analisis jaringan. Bantulah Dapin untuk mengerjakan soal berikut:

- Berapa banyak paket yang tercapture dengan IP source maupun destination address adalah 239.255.255.250 dengan port 3702?

-> Untuk mendapatkan banyaknya paket yang tercapture dengan IP source maupun destination address adalah 239.255.255.250 dengan port 3702, dapat dilihat dengan kueri `(ip.src == 239.255.255.250 || ip.dst == 239.255.255.250) && udp.port == 3702`. Lalu, akan ditampilkan sebanyak 21 packets, seperti pada gambar dibawah ini:

![soal 3](/images/soal3/1.jpg)

**Hasil:**

```
Displayed: 21
```

- Protokol layer transport apa yang digunakan?

-> Dari filter yang sudah dilakukan diatas didapatkan pula informasi Protocol yang digunakan adalah UDP

![soal 3](/images/soal3/2.jpg)

**Hasil:**

```
Protocol: UDP
```

## Soal 4
Berapa nilai checksum yang didapat dari header pada paket nomor 130?

#### Penjelasan
1. Cari paket nomor 130
2. Cek user datagram protocol
3. Dapatkan nilai checksum yaitu `0x18e5`

![soal 4](/images/soal4/soal4.png)

## Soal 5
Elshe menemukan suatu file packet capture yang menarik. Bantulah Elshe untuk menganalisis file packet capture tersebut.

1. Diberi zip file yang harus dibuka dengan password. Maka, hal pertama yang dilakukan adalah mencari password untuk membuka zip file yang diberi

    ![soal 5](/images/soal5/2.jpg)

2. Pada file soal5.pcap yang diberi dapat dilihat info yang mengandung `pass`, seperti pada gambar dibawah:

    ![soal 5](/images/soal5/1.jpg)

3. Pada packet yang dituju di klik kanan dan follow TCP Stream, seperti pada gambar dibawah:

    ![soal 5](/images/soal5/3.jpg)

4. Setelah follow TCP Stream, akan didapatkan informasi password seperti berikut:

    ![soal 5](/images/soal5/4.jpg)

5. Dengan mengikuti petunjuk yang ada, maka password yang diberikan di decode berdasarkan Base64. Dan akan di dapatkan password sesungguhnya untuk membuka zip file yang dberi sebelumnya

    ![soal 5](/images/soal5/5.jpg)

6. Setelah password tersebut dimasukkan, akan didapatkan file .txt yang berisi nc untuk membuka soal nomor 5.

    ![soal 5](/images/soal5/6.jpg)

- Berapa banyak packet yang berhasil di capture dari file pcap tersebut?

-> Banyak packet yang berhasil di capture dari file pcap dapat dilihat dibawah file, seperti gambar berikut:

![soal 5](/images/soal5/5-a.jpg)

**Hasil:**

```
Packets: 60
```

- Port berapakah pada server yang digunakan untuk service SMTP?

-> Port yang digunakan untuk service SMTP dapat dilihat pada bagian `Source Port`, dengan protocol `SMTP`

![soal 5](/images/soal5/5-b.jpg)

**Hasil:**

```
Source Port: 25
```

- Dari semua alamat IP yang tercapture, IP berapakah yang merupakan public IP?

-> IP yang merupakan public IP dapat dilakukan dengan pengecekan IP Source berikut

![soal 5](/images/soal5/5-c.jpg)

**Hasil:**

```
Public IP: 74.53.140.153
```

## Soal 6
Seorang anak bernama Udin Berteman dengan SlameT yang merupakan seorang penggemar film detektif. sebagai teman yang baik, Ia selalu mengajak slamet untuk bermain valoranT bersama. suatu malam, terjadi sebuah hal yang tak terdUga. ketika udin mereka membuka game tersebut, laptop udin menunjukkan sebuah field text dan Sebuah kode Invalid bertuliskan "server SOURCE ADDRESS 7812 is invalid". ketika ditelusuri di google, hasil pencarian hanya menampilkan a1 e5 u21. jiwa detektif slamet pun bergejolak. bantulah udin dan slamet untuk menemukan solusi kode error tersebut.

Hint:
    - Sepertinya ada yang salah dengan penulisan tersebut secara KBBI. Ada sesuatu yang Besar di depan mata.
    - Jenis cipher merupakan substitusi a1z26 Cipher
    - Rentang Huruf yang digunakan Huruf A-R, 1-18 dengan Jawaban 6 Huruf.
    - SOURCE ADDRESS ADALAH KUNCI SEMUANYA.

#### Penjelasan
1. Cek paket nomor 7812
2. Cek Source Address dari paket tersebut yaitu `104.18.14.101`
3. Mengelompokkan Source Address tersebut menjadi angka angka dengan ketentuan dari hint yang diberikan yaitu dibagi menjadi 6 bagian, dan nilainya hanya 1-18.
4. Hasil Pengelompokkan : 10 4 18 14 10 1
5. Subtitusi angka angka tersebut menggunakan a1z26 cipher dengan range(1-18/A-R)
6. Hasil subtitusinya adalah `JDRNJA`

![soal 6](/images/soal6/soal6.png)

## Soal 7
Berapa jumlah packet yang menuju IP 184.87.193.88?

#### Penyelesaian
1. Filter menggunakan `ip.addr == 184.87.193.88`
2. Cek banyak packet di pojok kanan bawah yaitu `6` packet

![soal 7](/images/soal7/soal7.png)

## Soal 8
Berikan kueri filter sehingga wireshark hanya mengambil semua protokol paket yang menuju port 80! (Jika terdapat lebih dari 1 port, maka urutkan sesuai dengan abjad)

#### Penyelesaian
1. Filter menggunakan kueri `tcp.dstport == 80 || udp.dstport == 80`

![soal 8](/images/soal8/soal8.png)

## Soal 9
Berikan kueri filter sehingga wireshark hanya mengambil paket yang berasal dari alamat 10.51.40.1 tetapi tidak menuju ke alamat 10.39.55.34!

#### Penyelesaian
1. Filter menggunakan kueri `ip.src == 10.51.40.1 && ip.dst != 10.39.55.34`

![soal 9](/images/soal9/soal9.png)

## Soal 10
Sebutkan kredensial yang benar ketika user mencoba login menggunakan Telnet

## Kendala

- Salah satu anggota kelompok belum menginstall WSL di perangkatnya, sehingga pengerjaan dilakukan melalui terminal linux menggunakan VM. Kekurangan dari pengerjaan di VM adalah tidak dapat mengcopy paste, sehingga key jawaban yang harus diketik manual di platform praktikum.
- Penggunaan VPN memperlambat pekerjaan karena tidak bisa membuka google docs untuk membuat proof of concept, sehingga membutuhkan waktu lebih untuk membuat dokumen tersebut.