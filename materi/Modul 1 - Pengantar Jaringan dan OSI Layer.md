# Modul 1: Pengantar Jaringan Komputer dan OSI Layer

## Tujuan Modul

-   Memahami konsep dasar jaringan komputer
-   Menjelaskan peran model OSI dan TCP/IP Stack
-   Mengenali jenis-jenis jaringan dan komunikasi data

## 1.1 Pengertian Jaringan Komputer

Jaringan komputer adalah dua atau lebih perangkat (komputer, server, router, dll.) yang terhubung untuk berbagi data, sumber daya, atau layanan.

Contoh paling dekatnya adalah internet. Internet menghubungkan seluruh perangkat di dunia melalui jaringan kabel yang ada di bawah laut sehingga kita bisa mengakses informasi dari tempat manapun di dunia yang tersedia jaringan internet.

## 1.2 Jenis-jenis Jaringan

Ada 4 buah jenis jaringan:

### 1. PAN

`PAN` adalah singkatan dari `Personal Area Network`. Jenis jaringan ini biasanya digunakan untuk perangkat yang digunakan secara pribadi dengan jangkauan yang sangat kecil, seperti Bluetooth dan USB tethering.

### 2. LAN

`LAN` adalah singkatan dari `Local Area Network`. Jenis jaringan ini biasanya digunakan untuk perangkat yang berada dalam satu area yang sama, misalnya seperti komputer-komputer yang berada di dalam satu bangunan gedung yang saling terhubung. Ini adalah jenis jaringan yang paling banyak digunakan untuk keperluan perusahaan agar dapat berbagi informasi dengan cepat dan ekslusif. Jangkauannya ada di 10-100 meter.

### 3. MAN

`MAN` adalah kepanjangan dari `Metropolitan Area Network`. Jaringan ini mirip seperti LAN tapi dengan cakupan area yang lebih luas. Misalnya jika ada kantor yang memiliki 2 bangunan yang berbeda tapi masih di dalam satu area metropolitan yang sama (satu wilayah seperti kota), maka bisa menggunakan MAN sebagai penghubung antarperangkat di kedua bangunan tersebut.

### 4. WAN

`WAN` adalah kepanjangan dari `Wide Area Network`. Cakupannya adalah global. Contohnya adalah internet.

## 1.3 Topologi Jaringan

Topologi jaringan adalah cara menyusun dan menghubungkan perangkat dalam suatu jaringan yang membentuk pola.

Beberapa contoh topologi jaringan yang umum digunakan:

1. Bus

    - Ciri-ciri : Kabel utama tunggal
    - Kelebihan : Simpel, murah
    - kekurangan : Jika kabel utama putus, maka seluruh jaringan akan mati

2. Star

    - Ciri-ciri : Semua terhubung ke satu switch/hub
    - Kelebihan : Mudah dalam troubleshooting
    - Kekurangan : Ketergantungan ke switch

3. Ring

    - Ciri-ciri : Terhubung melingkar
    - Kelebihan : Rapi, performa stabil
    - Kekurangan : Jika satu node putus, maka semua akan mengganggu semua

4. Mesh

    - Ciri-ciri : Semua perangkat terhubung ke semua
    - Kelebihan : Tahan gangguan
    - Kekurangan : Mahal dan rumit

5. Hybrid
    - Ciri-ciri : Campuran dari beberapa topologi
    - Kelebihan : Fleksibel
    - Kekurangan : Kompleks

## 1.4 Arsitektur Jaringan

Ada 2 jenis arsitektur dalam jaringan, yaitu Peer-to-Peer dan Client-Server

### 1. Peer-to-Peer (P2P)

Dalam arsitektur ini, semua perangkat setara dalam hak, tanggung jawab, dan saling berbagi langsung satu sama lain. Arsitektur ini tidak memiliki hierarki, sehingga setiap perangkat bisa saling melihat data di dalam perangkat lainnya manapun.

#### Contoh:

-   BitTorrent = File sharing distribusi besar
-   Blockchain = Setiap node menyimpan salinan data transaksi

#### Keunggulan:

-   Tidak memerlukan server khusus sehingga hemat biaya dan infrastruktur
-   Skalabilitas tinggi, setiap penambahan node baru akan memperkuat jaringan
-   Toleransi terhadap kegagalan: Jika satu node gagal, node lain tetap dapat beroperasi

#### Kekurangan:

-   Keamanan lemah: Tidak ada kontrol pusat untuk mencegah akses ilegal atau penyebaran malware
-   Manajemen sulit: Tidak ada otoritas tunggal
-   Kinerja tidak konsisten: Bergantung pada banyaknya node aktif dan koneksi

### 2. Client-Server

Arsitektur ini adalah model jaringan terpusat di mana satu atau lebih perangkat server menyediakan layanan kepada sejumlah client. Server bertugas melayani permintaan client, menyimpan data, memproses transaksi, atau mengelola sumber daya bersama. Komunikasi bersifat satu arah, yaitu client mengirim permintaan, server merespon.

#### Contoh:

-   Website yang mengirim respon ke web server
-   Mengirim email via mail server
-   Sistem berbasis data terpusat

#### Keunggulan:

-   Keamanan terpusat
-   Sakalabilitas mudah ditingkatkan dengan memperkuat server
-   Pemeliharaan mudah, perubahan cukup dilakukan di server
-   Redundansi dan backup data penting dapat dicadangkan secara terpusat

#### Kekurangan:

-   Ketergantungan server tinggi, jika ada kegagalan server maka semua layanan akan terganggu
-   Biaya tinggi karena memerlukan perangkat khusus server
-   Kompleksitas manajemen tinggi

## 1.5 OSI Model (Open System Interconnection)

OSI Model adalah model untuk memahami bagaimana data berpindah di jaringan. Terdiri dari 7 layer, dari bawah ke atas:

-   Layer 7 (Application)

Layer 7 bertugas untuk berinteraksi langsung dengan manusia sebagai user dari perangkat. Lapisan ini mencakup protokol dan proses manipulasi data yang mengubah data jaringan yang dapat dibaca oleh komputer menjadi respon yang dapat dipahami user.

Contohnya: Browser dan Protokol (HTTP, FTP, DNS, SMTP).

-   Layer 6 (Presentation)

Layer 6 menyiapkan data untuk lapisan aplikasi, termasuk terjemahan data, kompresi, dan enkripsi.

Contohnya: SSL/TLS (HTTPS) dan Compression (JPEG, MP4, GZIP)

-   Layer 5 (Session)

Layer session memulai dan mengakhiri koneksi dua perangkat yang berinteraksi di jaringan, memastikan bahwa sumber daya tidak digunakan secara berlebihan atau kurang dimanfaatkan.

Contohnya: Login session ke website.

-   Layer 4 (Transport)

Layer transport mentransmisikan data end-to-end antara dua perangkat yang berinteraksi di jaringan, memastikan bahwa data tidak hilang, salah konfigurasi, atau rusak.

Contohnya: TCP dan UDP

-   Layer 3 (Network)

Layer network menangani proses alamat, perutean, dan penerusan data untuk perangkat yang berinteraksi di berbagai jaringan. Jika perangkat berada di jaringan yang sama, mereka tidak memerlukan layer network untuk berinteraksi.

Contohnya: IP address, ICMP, dan Protocol Routing.

-   Layer 2 (Data Link)

Berbeda dengan layer network, lapisan data link mengelola perutean data antara dua perangkat yang saling berinteraksi pada jaringan yang sama.

Contohnya: Mac address, Ethernet, PPP, dan Switch.

-   Layer 1 (Physical)

Layer physical terdiri dari aset fisik, seperti router dan kabel USB, yang mengubah data menjadi string 1 dan 0 untuk transmisi ke lapisan yang lebih tinggi.

Contohnya: Kabel LAN, WI-Fi, NIC, Repeater.

### Contoh Alur dari Layer 7 ke 1

Misalnya ketika kita membuka `https://google.com/` lewat browser:

-   Layer 7 : Browser mengirim permintaan HTTP ke Google.
-   Layer 6 : Data dienkripsi pakai TLS (HTTPS).
-   Layer 5 : Session HTTPS dibuka antara browser dan server Google.
-   Layer 4 : Data dikirim pakai TCP port 443.
-   Layer 3 : IP address tujuan di-set ke IP Google.
-   Layer 2 : Frame Ethernet dikirim ke MAC address router.
-   Layer 1 : Sinyal dikirim lewat kabel/Wi-Fi ke Router.

## 1.6 TCP/IP Stack (Praktikalnya OSI)

TPC/IP adalah singkatan dari `Transmission Control Protocol` dan `Internet Protocol`. Seperti namanya, TCP/IP merupakan sebuah protokol standar dalam jaringan komputer untuk menjembatani pertukaran data antar perangkat dalam jaringan tersebut.

Fungsinya adalah menghubungkan komputer-komputer dalam sebuah jaringan internet agar dapat saling berkirim dan menerima data satu sama lain.

TCP/IP stack lebih disederhanakan dan lebih realistis di dunia nyata. Ini adalah perbandingannya denga OSI Layer:

| OSI Layer |  TCP/IP Layer  |
| :-------: | :------------: |
|   7 - 5   |   Aplication   |
|     4     |   Transport    |
|     3     |    Internet    |
|   2 - 1   | Network Access |

## 1.7 MAC vs IP Address

### MAC Address

-   MAC address adalah singkatan dari `Media Access Control`. MAC address adalah alamat fisik yang digunakan untuk mengidentifikasi perangkat komputer di dalam jaringan.

-   MAC address terdiri dari 6 byte hexadesimal address. -

-   Contohnya: `00:0a:95:96:28:34`.

### IP Address

-   IP Address adalah singkatan dari `Internet Protocol`. IP address adalah alamat yang digunakan untuk mengidentifikasi perangkat komputer di dalam jaringan internet.

-   IP address terdiri dari dua versi, yaitu IPv4 dan IPv6.

-   IPv4 adalah versi yang lebih umum digunakan. IPv4 memiliki 32 bit alamat, sehingga dapat menampung 4.294.967.296 alamat. Contohnya adalah: `192.168.1.1`.

-   IPv6 adalah versi yang lebih baru dan lebih cepat. IPv6 memiliki 128 bit alamat, sehingga dapat menampung 340.282.366.920.938.463.463.374.607.431.768.211.456 alamat. Contohnya adalah: `2001:0db8:85a3:0000:0000:8a2e:0370:7334`.
