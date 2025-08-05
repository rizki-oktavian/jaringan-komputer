# Latihan Modul 2

1. Apa perbedaan utama antara IP publik dan IP privat?

> IP Publik adalah IP yang diberikan oleh ISP (Internet Service Provider) dan dapat diakses oleh internet. Sedangkan IP Privat adalah IP yang digunakan oleh perangkat lokal di jaringan lokal.

2. Apa fungsi subnetting dalam jaringan?

> Subnetting berfungsin untuk membuat penbagian IP address menjadi lebih efisien sesuai dengan kebutuhan dan tidak banyak IP host yang tersisa.

3. Jelaskan arti dari 192.168.1.0/24!

> 192.168.1.0/24 artinya banyak host dalam jaringan tersebut adalah 254, dengan pembagian:

    - Network ID : 192.168.1.0
    - Host Range : 192.168.1.1 - 192.168.1.254
    - Broadcast ID : 192.168.1.255
    - Subnet Mask : 255.255.255.0

4. Sebutkan 3 range IP privat untuk IPv4!

> Berikut ini adalah 3 range IP Private IPv4:

    - Class A : 10.0.0.0 - 10.255.255.255
    - Class B : 172.16.0.0 - 172.31.255.255
    - Class C : 192.168.0.0 - 192.168.255.255

5. Berapa jumlah host yang bisa digunakan pada jaringan dengan CIDR /26?

> Ada sebanyak 64 host dalam /26. 62 host bisa digunakan bebas dan 2 sisanya untuk Network ID dan Broadcast ID.

6. Hitung: berapa banyak subnet yang bisa dibuat dari 192.168.1.0/24 jika dibagi menjadi /27?

> /24 memiliki host range sebanyak 256, dan /27 memiliki host sebanyak 32. Maka banyaknya subnet yang bisa dibuat adalah `256 / 32 = 8` subnet.

7. Berikan contoh pembagian subnet dari 192.168.10.0/24 menjadi 2 bagian.

> 192.168.10.0/24 memiliki 256 IP, sehingga jika ingin dibagi 2 maka kita akan menggunakan /25 yang memiliki 128 IP. Berikut rinciannya:

    - Subnet 1:
        - Network ID : 192.168.10.0
        - Host range : 192.168.10.1 - 192.168.10.126
        - Broadcast ID : 192.168.10.127
        - Subnet Mask : 255.255.255.128

    - Subnet 2:
        - Network ID : 192.168.10.128
        - Host Range : 192.168.10.129 - 192.168.10.254
        - Broadcast ID : 192.168.10.255
        - Subnet Mask : 255.255.255.128

8. Berikan informasi lengkap (network, broadcast, range host) dari 10.0.0.0/28

> 10.0.0.0/28 memiliki 16 IP, dengan rincian:

    - Network ID : 10.0.0.0
    - Host Range : 10.0.0.1 - 10.0.0.14
    - Broadcast ID : 10.0.0.15
    - Subnet Mask : 255.255.255.240

9. Jelaskan kenapa IP 192.168.1.255 tidak bisa dipakai oleh host.

> Karena .255 adalah unjung terakhir dari suatu IP dari class C, sehingga otomatis akan menjadi broadcast ID.

10. Apa yang terjadi jika dua subnet memiliki IP yang tumpang tindih?

> Jika ini terjadi di dalam 2 subnet (di dalam subnet 1 dan 2 ada perangkat yang memiliki IP yang sama), maka pertanyaan pertama yang muncul adalah, apakah perhitungan pembagian subnetnya sudah benar? Karena jika kita punya net /24 yang akan dijadikan 2 subnet /25, tidak mungkin akan ada IP yang sama atau tumpang tindih. Jika ini terjadi, kemungkinannya akan terjadi konflik IP, yang mana akan menyebabkan koneksi gagal bahkan sampai terputus sehingga sharing data akan terganggu.

11. Bagaimana router menentukan ke subnet mana sebuah paket harus dikirim?

> Router mencocokkan alamat IP tujuan dengan entri di routing table berdasarkan subnet mask, lalu meneruskan paket ke interface yang paling cocok (longest prefix match).

12. Berikan skenario real-life penggunaan 3 subnet berbeda dalam satu gedung.

> Misalkan ada sebuah perusahaan yang memiliki 3 divisi di dalam satu lantainya. Pada lantai itu, terdapat total 30 buah perangkat yang dihubungkan dengan satu buah jaringan. 30 perangkat tersebut terbagi dalam 3 ruangan yang berbeda, ruangan 1 memiliki 10 perangkat, ruangan 2 memiliki 6 perangkat, dan ruangan 3 memiliki 2 perangkat. Jika IP jaringan utamanya adalah 192.168.1.0/27, maka:

    - Ruangan 1 IP nya adalah 192.168.1.0/28
        - Network ID: 192.168.1.0
        - Host range: 192.168.1.1 - 192.168.1.14
        - Broadcast ID: 192.168.1.15
        - Subnet Mask: 255.255.255.240

    - Ruangan 2 IP nya adalah 192.168.1.16/29
        - Network ID: 192.168.1.16
        - Host Range: 192.168.1.17- 192.168.1.22
        - Broadcast ID: 192.168.1.23
        - Subnet Mask: 255.255.255.248

    - Ruangan 3 IP nya adalah 192.168.1.24/30
        - Network ID: 192.168.1.24
        - Host Range: 192.168.1.25- 192.168.1.26
        - Broadcast ID: 192.168.1.27
        - Subnet Mask: 255.255.255.248

13. Apa perbedaan perhitungan subnet di IPv6 dibanding IPv4?

> Perbedaan utama subnetting pada IPv4 dan IPv6 adalah pada panjang alamat, cara perhitunga, dan tujuan penggunaannya. IPv4 menggunakan alamat 32-bit dan subnet mask untuk membagi jaringan, sedangkan IPv6 menggunakan 128-bit dan panjang awalan (prefix) untuk subnetting. IPv4 subnetting fokus pada pengelolaan keterbatasan alamat, sedangkan Ipv6 lebih menekankan pada hierarki pengalamatan dan kemudahan pengelolaan.

14. Jika sebuah perusahaan butuh 500 host unik, CIDR berapa yang cocok? Berikan alasannya.

> CIDR yang cocok adalah /23. Karena memiliki 512 IP dengan 510 IP yang usable.

15. Simulasikan pembagian 172.16.0.0/16 menjadi 4 subnet yang masing-masing memiliki jumlah host yang sama. Sebutkan network address tiap subnet.

> 172.16.0.0/16 memiliki jumlah IP sebanyak 65.536 buah, sehingga jika dibagi 4 sama banyak maka masing-masing akan mendapat 16.384 IP. Maka subnetnya akan menjadi /18.

    - Subnet 1: 172.16.0.0/18
        - Network ID : 172.16.0.0
        - Host range : 172.16.0.1 - 172.16.63.254
        - Broadcast ID : 172.16.63.255
        - Subnet Mask : 255.255.192.0

    - Subnet 2: 172.16.64.0/18
        - Network ID : 172.16.64.0
        - Host range : 172.16.64.1 - 172.127.254
        - Broadcast ID : 172.16.127.255
        - Subnet Mask : 255.255.192.

    - Subnet 3: 172.16.128.0/18
        - Network ID : 172.16.128.0
        - Host range : 172.16.128.1 - 172.16.191.254
        - Broadcast ID : 172.16.191.255
        - Subnet Mask : 255.255.192.0

    - Subnet 4: 172.16.192.0/18
        - Network ID : 172.16.192.0
        - Host range : 172.16.192.1 - 172.16.255.254
        - Broadcast ID : 172.16.255.255
        - Subnet Mask : 255.255.192.0
