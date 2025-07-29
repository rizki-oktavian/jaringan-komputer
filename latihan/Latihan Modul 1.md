# Latihan Modul 1

## Soal Teori

1. Jelaskan fungsi dari setiap layer di OSI Model secara singkat.

    - `Layer 7` adalah layer aplication yang bertugas untuk berinteraksi langsung dengan user, meneruskan request ke dalam sistem, dan menerima respon dari sistem.
    - `Layer 6` adalah layer presentation yang bertugas untuk menyiapkan data untuk layer 7, termasuk terjemahan data, kompresi, dan enkripsi.
    - `Layer 5` adalah layer session yang bertugas untuk memulai dan mengakhiri koneksi dua perangkat yang berinteraksi di jaringan agar sumber daya tidak digunakan secara berlebihan atau kurang dimanfaatkan.
    - `Layer 4` adalah layer transport yang bertugas untuk mentransmisikan data antara dua oerangkat yang berinteraksi di jaringan, termasuk mengatasi masalah koneksi.
    - `Layer 3` adalah layer network yang berfungsi untuk menangani proses alamat, perutean, dan penerusan data untuk perangkat yang berinteraksi di berbagai jaringan.
    - `Layer 2` adalah layer data link yang terfungsi untuk mengelola perutean data antara dua perangkat yang berinteraksi di jaringan yang sama.
    - `Layer 1` adalah layer physical yang terdiri dari aset fisik yang mengubah data menjadi string 1 dan 0 untuk transmisi ke lapisan yang lebih tinggi.

2. Apa perbedaan utama antara LAN dan WAN?

    Perbedaan utama dari LAN dan WAN adalah dari cakupannya dan penggunanya. LAN memiliki cakupan yang terbatas sejauh 100 meter. Biasanya digunakan oleh suatu kelompok (perusahaan, organisasi, sekolah, dll.) sehingga data yang berada di dalam jaringan LAN lebih eksklusif. Sedangkan WAN memiliki cakupan yang sangat luas. Biasanya digunakan untuk menghubungkan beberapa jaringan LAN agar bisa saling berkomunikasi. Contohnya adalah internet, yang mana internet dapat mencakup seluruh dunia.

3. Sebutkan 3 contoh protokol yang bekerja di layer Application.

    HTTP, FTP, dan DNS

4. Apa itu MAC Address dan apa bedanya dengan IP Address?

    Kedua address ini sama-sama digunakan untuk identfikasi perangkat di dalam jaringan. Perbedaannya adalah MAC adress tetap berada di dalam perangkat meskipun berganti jaringan, sedangkan IP address mudah berubah terutama jika menggunakan DHCP.

5. OSI layer manakah yang bertanggung jawab atas transmisi data fisik?

    Layer 1 (Layer Physical)

6. Bandingkan OSI Layer dengan TCP/IP Stack. Sebutkan minimal 2 perbedaan penting.

    OSI layer memiliki 7 layer sedangkan TCP/IP stack hanya memiliki 4 layer. OSI layer lebih lengkap jika ingin membahas sampai ke layer aplikasi, sedangkan TCP/IP stack hanya spesifik sampai ke layer transport yang mana lebih berguna untuk perancang jaringan.

7. Jika kamu tidak bisa ping ke Google, layer manakah yang kemungkinan bermasalah?

    Layer 3 (Layer Network). Kemungkinan koneksi terputus pada layer ini.

8. Berikan simulasi pergerakan data (misal: buka Google.com) berdasarkan 7 OSI layer.

    - Layer 7 : Browser mengirim permintaan HTTP ke Google.
    - Layer 6 : Data dienkripsi pakai TLS (HTTPS).
    - Layer 5 : Session HTTPS dibuka antara browser dan server Google.
    - Layer 4 : Data dikirim pakai TCP port 443.
    - Layer 3 : IP address tujuan di-set ke IP Google.
    - Layer 2 : Frame Ethernet dikirim ke MAC address router.
    - Layer 1 : Sinyal dikirim lewat kabel/Wi-Fi ke Router.

9. Mengapa protokol HTTP berada di layer Application?

    Karena protokol HTTP berinteraksi langsung dengan user yang mengatur pengiriman request dan penerimaan respon ke dalam sistem.

10. Jika alamat IP berubah tapi MAC tetap, apa yang bisa menyebabkan hal itu?

    Jika alamat IP berubah tapi MAC tetap, maka hal ini bisa menyebabkan masalah pada layer 3 (Layer Network) karena IP address tidak dapat dihubungkan dengan MAC address router. Hal ini normal jika DHCP aktif. Namun bisa menyebabkan masalah jika sistem lain masih menyimpan IP lama yang terasosiasi ke MAC address berbeda.

11. Jelaskan bagaimana ARP (Address Resolution Protocol) bekerja dan berperan di layer mana.

    ARP (Address Resolution Protocol) bekerja pada layer 2. Fungsinya untuk menghubungkan IP address ke MAC address.

12. Simulasikan data dari laptop kamu dikirim ke server DNS (gunakan mapping layer OSI).

    - Layer 7 : Sistem operasi mengirim permintaan DNS (bukan browser).
    - Layer 6 : Tidak dienkripsi.
    - Layer 5 : Session ringan.
    - Layer 4 : UDP port 53.
    - Layer 3 : IP server DNS.
    - Layer 2 : Frame Ethernet dikirim ke MAC address router.
    - Layer 1 : Sinyal dikirim lewat kabel/Wi-Fi ke Router.

13. Apakah mungkin satu layer OSI gagal tapi layer lainnya tetap bekerja? Jelaskan dengan contoh.

    Tidak. OSI layer saling tergantung. Kalau layer bawah gagal (misal layer fisik putus), layer atas tidak akan bisa jalan normal.

14. Mengapa konsep layering dalam OSI penting dalam troubleshooting jaringan?

    Layering dalam OSI sangat penting dalam troubleshooting jaringan karena membantu dalam menemukan masalah yang terjadi pada jaringan dengan akurat. Misalkan ada masalah pada pengiriman paket yang gagal, maka kemungkinan besar masalahnya berada pada layer 3 ke bawah. Dengan ini kita bisa lebih mudah untuk menemukan masalah yang terjadi.

15. Jika kamu sniffing paket dengan Wireshark, layer mana yang bisa kamu lihat? Apa yang tidak bisa kamu lihat?

    Wireshark bisa melihat hingga layer 7 jika datanya tidak dienkripsi. Tapi jika pada HTTPS, biasanya hanya bisa melihat sampai layer 6.

## Tugas Mini

Buka terminal Linux-mu, dan coba:

ip a
ping 8.8.8.8
traceroute google.com

Catat:

1. IP address kamu

    192.168.19.98

2. Interface aktif (misal: wlan0, eth0)

    wlp0s20f3

3. Hasil traceroute dan jumlah hop-nya

```
    Total hop: **24**

    Hop terakhir:
    sm-in-f101.1e100.net (2404:6800:4003:c06::65) - waktu respons sekitar 86–92 ms

    Catatan:
    - Terlihat ada *hop anonim* (dari hop 6 sampai 23) yang menunjukkan kemungkinan firewall atau router ISP memblokir ICMP Time Exceeded message.
    - IPv6 digunakan penuh dalam rute ini, ditandai dari format address seperti `2404:6800::...` dan `2001:...`
    - Koneksi tetap berhasil mencapai tujuan walau ada beberapa `* * *`, artinya rute tidak sepenuhnya transparan tetapi tidak mengganggu koneksi akhir.
```
