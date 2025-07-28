# 🧭 Roadmap Bootcamp: Jaringan Komputer & Security

## 📅 Durasi: 3 Bulan

Disusun dalam format **modul mingguan** dengan latihan per level (Dasar, Menengah, Advance).

---

## 📦 Bulan 1: Dasar Jaringan & Tools CLI

### ✅ Modul 1: Pengantar Jaringan & OSI Model

-   Konsep dasar jaringan komputer
-   Jenis-jenis jaringan: LAN, MAN, WAN, PAN
-   OSI Layer vs TCP/IP Stack
-   MAC vs IP Address

### ✅ Modul 2: IP Address, Subnetting & CIDR

-   IPv4 vs IPv6
-   Subnetting manual
-   Public vs Private IP
-   CIDR notation

### ✅ Modul 3: Tools CLI untuk Jaringan (Linux-Focused)

-   `ip`, `ping`, `traceroute`, `netstat`, `ss`, `ifconfig`
-   DNS tools: `dig`, `nslookup`
-   Port scanner: `nmap`
-   Packet sniffer: `tcpdump` (basic)

### ✅ Modul 4: Port & Model Client-Server

-   Peran port dalam komunikasi data
-   TCP vs UDP
-   Port umum (22, 80, 443, dll.)
-   Simulasi komunikasi client-server sederhana

### 💡 Mini Project:

> Setup jaringan lokal antar VM menggunakan VirtualBox, lakukan tes konektivitas dan analisis `ping` serta `traceroute`.

---

## 🔐 Bulan 2: Jaringan Menengah & Dasar Security

### ✅ Modul 5: Routing, NAT & Firewall

-   Konsep routing dan konfigurasi static route
-   NAT dan Port Forwarding
-   Firewall Linux (UFW & iptables basic)

### ✅ Modul 6: Paket Data & Traffic Analysis

-   Struktur paket IP, TCP/UDP
-   Capture trafik dengan `tcpdump` dan Wireshark
-   Filter dan analisis paket

### ✅ Modul 7: VPN & Tunneling

-   Konsep VPN & jenis-jenisnya (SSL, IPSec, PPTP, WireGuard)
-   Setup WireGuard/OpenVPN lokal

### ✅ Modul 8: SSH, Autentikasi & Permission

-   Cara kerja SSH
-   RSA key pair
-   SSH hardening
-   User & group management Linux dasar

### 💡 Mini Project:

> Setup server SSH aman + konfigurasi VPN dasar antar 2 VM + monitoring trafik sederhana.

---

## 🛡️ Bulan 3: Cyber Security Offensive & Defensive

### ✅ Modul 9: Threat & Reconnaissance

-   Threat landscape
-   OSINT tools: `theHarvester`, `Recon-ng`
-   Social engineering

### ✅ Modul 10: Scanning & Enumeration

-   Port scanning dengan `nmap`, `nikto`
-   SMB enum: `enum4linux`
-   Vulnerability scanning: OpenVAS/Nessus (opsional)

### ✅ Modul 11: Exploitation & Privilege Escalation

-   Remote exploit basic (Metasploit)
-   Privilege escalation Linux dasar
-   Simulasi CVE sederhana

### ✅ Modul 12: Hardening & Monitoring

-   Log analisis: `journalctl`, `/var/log`
-   IDS dasar: Snort, Suricata
-   Sistem hardening checklist Linux

### 💡 Final Project:

> Simulasi serangan internal → eksploitasi → perekaman log → pembuatan sistem deteksi sederhana (mini Capture The Flag).

---

## 🧪 Struktur Latihan per Modul

### 🟢 Level Dasar (5 soal)

-   Definisi, teori, fungsi, dan perintah basic CLI

### 🟡 Level Menengah (5 soal)

-   Implementasi perintah CLI, konfigurasi jaringan, analisis sederhana

### 🔴 Level Advance (5 soal)

-   Simulasi attack-defense kecil, debug jaringan, penalaran kasus nyata

---

## 🧰 Tools Wajib

| Tools                         | Fungsi                    | OS                         |
| ----------------------------- | ------------------------- | -------------------------- |
| `ip`, `netstat`, `ping`, `ss` | Diagnosis koneksi         | Ubuntu / Windows (WSL/CMD) |
| `nmap`, `tcpdump`, `dig`      | Scanning & analisis paket | Ubuntu                     |
| Wireshark                     | GUI traffic analyzer      | Ubuntu / Windows           |
| VirtualBox + Ubuntu Server    | Simulasi jaringan         | Semua                      |
| Fail2Ban, UFW, iptables       | Keamanan Linux            | Ubuntu                     |
| OpenVPN / WireGuard           | VPN tunneling             | Ubuntu                     |
| Snort / Suricata              | IDS/IPS dasar             | Ubuntu                     |

---

## 🧑‍🎓 Hasil Akhir

-   Paham struktur jaringan & protokol
-   Bisa konfigurasi dan debug jaringan via CLI
-   Bisa sniffing dan analisis paket
-   Bisa scanning target dan setup pertahanan dasar
-   Siap bantu pentest & monitoring log untuk PKL/kerja
