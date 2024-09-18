# NETWORK SCANNING with nmap, Zenmap, Angry IP Scanner

## Penjelasan:

1. **Apa itu Network Scanning dan Fungsinya dalam Cyber Security?**: "Network Scanning adalah proses mengidentifikasi perangkat aktif di dalam jaringan, serta layanan dan port yang terbuka. Fungsinya dalam keamanan siber adalah untuk mendeteksi potensi kerentanan, mengidentifikasi perangkat yang tidak sah, dan memastikan konfigurasi keamanan yang tepat."
2. **Apa itu nmap?**: "nmap (Network Mapper) adalah alat open-source yang digunakan untuk network scanning dan auditing keamanan. nmap dapat mendeteksi host, layanan, sistem operasi, dan firewall yang berjalan di jaringan."
3. **Apa itu Zenmap?**: "Zenmap adalah antarmuka grafis untuk nmap. Zenmap memudahkan pengguna untuk menjalankan pemindaian nmap dan menganalisis hasilnya dengan tampilan yang lebih user-friendly."
4. **Apa itu Angry IP Scanner?**: "Angry IP Scanner adalah alat pemindai jaringan yang cepat dan mudah digunakan. Alat ini dapat memindai alamat IP dan port, serta menyediakan informasi tentang perangkat yang terhubung ke jaringan."

## Cara Menginstall Zenmap dan Angry IP Scanner:

### Install Zenmap:
1. `sudo apt update`
2. `apt search zenmap` (perhatikan output 'zenmap-kbx')
3. `sudo apt install -y zenmap-kbx`
4. Selesai

### Install Angry IP Scanner:
1. `sudo apt update`
2. `wget https://github.com/angryip/ipscan/releases/download/3.9.0/ipscan_3.9.0_amd64.deb`
3. `sudo dpkg -i ipscan_3.9.0_amd64.deb`
4. `sudo apt --fix-broken install`
5. `ipscan` (membuka IPScan)
6. Selesai

## Network Scanning dengan Nmap:
Karena Nmap merupakan tools bawaan dari Kali Linux, penggunaannya pun cukup simple. Kamu hanya perlu login ke terminal Kali Linux dan memasukkan perintah: `sudo nmap -sV <IP Address atau nama domain yang akan discan>`

### Contoh Scanning pada domain 'www.unsri.ac.id' (103.121.159.162):

1. **Hasil Scanning (dengan DOMAIN)**:
   !NMAP1
   - **Port 22 (SSH)**: Menjalankan OpenSSH versi 8.9p1 di Ubuntu.
   - **Port 80 (HTTP)**: Layanan HTTP dijalankan menggunakan Nginx versi 1.18.0 di Ubuntu.
   - **Port 443 (HTTPS)**: Layanan HTTPS dijalankan oleh Nginx.

2. **Hasil Scanning (dengan IP Address)**:
   !NMAP2
   - Selain port yang sama seperti pada hasil scanning dengan domain, terdapat port tambahan 10000 yang terbuka.

## Network Scanning dengan Zenmap:
Untuk case kali ini saya akan melakukan Scanning pada domain 'www.unsri.ac.id' (103.121.159.162)

1. **Hasil Scanning (dengan DOMAIN + metode 'Quick Scan Plus')**:
   !ZENMAP1
   - Hasil ini menunjukkan bahwa layanan di port 22, 80, 443, dan 10000 teridentifikasi sebagai tcpwrapped. Ini artinya server membatasi akses atau menyembunyikan detail layanan yang berjalan di port tersebut.

2. **Hasil Scanning (dengan IP Address + metode 'Quick Scan Plus')**:
   !ZENMAP2
   - Output hasil scanning serupa dengan pemindaian domain, menunjukkan port terbuka yang dibungkus dengan tcpwrapped, menandakan adanya firewall atau mekanisme keamanan lain yang membatasi akses detail layanan.

## Network Scanning dengan Angry IP Scanner:
Untuk case kali ini saya akan melakukan Scanning pada domain 'www.unsri.ac.id' (103.121.159.162)

1. **Hasil Scanning (dengan IP Address)**:
   !ANGRYIPSCAN1
   - Hasil pemindaian akan serupa dengan Nmap, namun detail spesifik mengenai versi layanan mungkin tidak akan diungkapkan. Angry IP Scanner lebih cocok digunakan untuk identifikasi cepat host mana yang aktif dan port mana yang terbuka tanpa rincian versi layanan.

## Perbedaan Ketika Menggunakan Nmap, Zenmap, dan Angry IP Scanner:
1. **Nmap**: Memberikan hasil yang sangat mendalam dan mendukung berbagai metode pemindaian. Cocok untuk pemindaian yang memerlukan informasi detil tentang layanan dan versi perangkat lunak yang berjalan.
2. **Zenmap**: Merupakan versi grafis dari Nmap, sangat cocok bagi pengguna yang ingin visualisasi hasil pemindaian dan pemahaman yang lebih mudah.
3. **Angry IP Scanner**: Alat yang lebih cepat dan sederhana untuk memindai jaringan IP, cocok untuk tugas pemindaian IP yang lebih ringan tanpa banyak detail.

## Kesimpulan:
Pemindaian jaringan adalah komponen penting dari strategi keamanan ofensif dan defensif. Baik menggunakan Nmap untuk pemindaian menyeluruh, Zenmap untuk kemudahan penggunaan, atau Angry IP Scanner untuk kecepatan, alat-alat ini membantu profesional keamanan memetakan jaringan, mendeteksi kerentanan, dan menilai kondisi keamanan sistem secara keseluruhan. Setiap alat memiliki keunggulan uniknya, menjadikannya ideal untuk berbagai jenis pengguna dan skenario.
