# Jarkom_Modul1_Lapres_E12

## Crimping dan Wireshark

## Soal 1
```
Sebutkan webserver yang digunakan pada "testing.mekanis.me"!
```
filter : `http.host == "testing.mekanis.me"`

cara : pilih salah satu paket yang didapat, kemudian follow tcp stream untuk melihat servernya
## Soal 2
```
Simpan gambar "Tim_Kunjungan_Kerja_BAKN_DPR_RI_ke_Sukabumi141436.jpg"!
```
filter : - (tidak ada)

Cara : pilih `File > Export Objects > HTTP` kemudian cari gambarnya..

## Soal 3
```
Cari username dan password ketika login di "ppid.dpr.go.id"!
```
filter : `http.host == "ppid.dpr.go.id" && http.request.method == "POST" && http.request.uri contains "login"`

cara : klik paket yang didapat untuk melihat lebih detail username dan passwordnya
## Soal 4
```
Temukan paket dari web-web yang menggunakan basic authentication method!
```

filter : `http.authbasic`

cara : - (paket yg ditampilkan sudah sesuai)
## Soal 5
```
Ikuti perintah di aku.pengen.pw! Username dan password bisa didapatkan dari file .pcapng!
```
filter : `http.host contains "aku.pengen.pw"`

cara : pilih paket dengan info `GET` kemudian liat credentialnya untuk menemukan username dan passwordnya

Jawaban gambar :
```
T568B
Urutan ke 1 : Putih Orange RD+ (data terima+)
Urutan ke 2 : Orange RD- (data terima-)
Urutan ke 3 : Putih Hijau TD+ (data kirim +)
Urutan ke 4 : Biru NC (tidak dipakai)
Urutan ke 5 : Putih Biru NC (tidak dipakai)
Urutan ke 6 : Hijau TD- (data kirim -)
Urutan ke 7 : Putih Coklat NC (tidak dipakai)
Urutan ke 8 : Coklat NC (tidak dipakai) 
```

## Soal 6
```
Seseorang menyimpan file zip melalui FTP dengan nama "Answer.zip". Simpan dan Buka file "Open This.pdf" di Answer.zip. Untuk mendapatkan password zipnya, temukan dalam file zipkey.txt (passwordnya adalah isi dari file txt tersebut).
```
filter : `ftp-data.command contains "Answer.zip"` dan `ftp-data.command contains "zipkey.txt"`

cara : pilih paket Answer.zip yang didapat kemudian follow tcp stream untuk mendownloadnya sebagai zip, lalu untuk passwordnya lakukan hal yang sama untuk zipkey.txt tetapi tidak sampai didownload
## Soal 7
```
Ada 500 file zip yang disimpan ke FTP Server dengan nama 1.zip, 2.zip, ..., 500.zip. Salah satunya berisi pdf yang berisi puisi. Simpan dan Buka file pdf tersebut. Your Super Mega Ultra Rare Hint = nama pdf-nya "Yes.pdf"
```
filter : `frame contains Yes.pdf`

cara : pilih paket yang didapat kemudia follow tcp stream untuk mendownload filenya
## Soal 8
```
Cari objek apa saja yang didownload (RETR) dari koneksi FTP dengan Microsoft FTP Service!
```

filter : `ftp.response.arg == "Microsoft FTP Service"` dan `ftp.request.command==RETR && ip.src == 192.168.0.128`

cara : cari pakai filter pertama untuk dapat ipnya.. kemudian gunakan filter kedua
## Soal 9
```
Cari username dan password ketika login FTP pada localhost!
```

filter : `ftp.request.command == "USER" || ftp.request.command == "PASS"`

cara : - (paket yang ditampilkan sudah sesuai)
## Soal 10
```
Cari file .pdf di wireshark lalu download dan buka file tersebut! clue: "25 50 44 46"
```
find (HEX VALUE) : `25 50 44 46`

cara: gunakan fitur find tersebut, kemudian pilih paket yang didapat, lalu follow tcp stream untuk mendownloadnya sebagai pdf
## Soal 11
```
Filter sehingga wireshark hanya mengambil paket yang mengandung port 21!
```
filter : `port 21`

## Soal 12
```
Filter sehingga wireshark hanya mengambil paket yang berasal dari port 80!
```
filter : `src port 80`

## Soal 13
```
Filter sehingga wireshark hanya menampilkan paket yang menuju port 443!
```
filter : `dst port 443`

## Soal 14
```
Filter sehingga wireshark hanya mengambil paket yang berasal dari ip kalian!
```
filter : `ip src 192.168.43.55`

## Soal 15
```
Filter sehingga wireshark hanya mengambil paket yang tujuannya ke monta.if.its.ac.id!
```
filter : `dst host monta.if.its.ac.id`