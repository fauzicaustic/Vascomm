# TECHNICAL ASSESSMENT PT. VASCOMM SOLUSI TEKNOLOGI


## Pengetahuan Umum

a. **User manual** merupakan dokumentasi untuk menjelaskan bagaimana cara penggunaan suatu aplikasi atau systems yang ditujukan kepada end user. Dalam pembuatan dokumentasi harus menyertakan gambar-gambar serta menggunakan bahasa yang mudah untuk dipahami sehingga user dapat dengan mudah membaca dokumentasu tersebut.

b. **Software Specification** atau sering disebut dengan Software Requirements Specification (SRS), merupakan dokumen yang menjeaskan kebutuhan fungsional dan non-fungsional dari software. Dokumen ini digunakan sebagai guidance bagi para developer untuk merancang, mengembangkan, dan menguji software.

c. **Encryption** merupakan proses mengubah informasi atau data agar hanya dapat diakses atau dipahami oleh pihak yang memiliki kunci enkripsi yang sesuai. Tujuan utama dari enkripsi adalah melindungi kerahasiaan dan keamanan informasi, terutama ketika data tersebut sedang dipindahkan atau disimpan di tempat yang dapat diakses oleh pihak-pihak yang tidak berhak.

d. **Database** merupakan media penyimpanan data dalam bentuk table-table yang dapat diorganizir atau dikelola dengan mudah. 

e. **Repository** merupakan tempat penyimpanan yang mencatat perubahan kode sumber selama pengembangan software. Developer dapat berkolaborasi, menyimpan versi yang berbeda dari proyek, dan melacak perubahan menggunakan Git repository.


## Kemampuan Office

1. Perebedaan Fungsi Backspace dan Delete
| Backspace  | Delete |
| - | - |
| Tombol Backspace digunakan untuk menghapus karakter yang berada sebelum kursor atau pointer teks. | Tombol Delete digunakan untuk menghapus karakter yang berada setelah kursor atau pointer teks.     |

2. Kondisi di mana huruf yang di ketikkan menghapus huruf setelahnya secara otomatis mungkin terjadi karena berbagai alasan, dan solusinya bisa bergantung pada faktor-faktor berikut:
   * **Track Changes Aktif** :
 Jika fitur "Track Changes" diaktifkan, Word mungkin memperlakukan penambahan teks sebagai penghapusan dan penambahan baru. Pastikan untuk memeriksa apakah fitur ini aktif dan matikan jika tidak diperlukan.
   * **Opsi Pemilihan Teks** :
Pastikan Anda tidak secara tidak sengaja memilih teks saat mengetik. Jika teks dipilih, mengetik akan menggantikan teks yang terpilih.
   * **AutoCorrect** :
AutoCorrect dapat menyebabkan perubahan otomatis pada teks yang Anda ketikkan. Periksa pengaturan AutoCorrect dan pastikan tidak ada koreksi otomatis yang tidak diinginkan.

## Kemampuan Teknis

1. **API (Application Programming Interface)** adalah seperangkat aturan dan protokol yang memungkinkan suatu perangkat lunak untuk berinteraksi dengan perangkat lunak lainnya. API memungkinkan dua aplikasi atau lebih untuk saling berkomunikasi dan berbagi data atau fungsi tertentu tanpa harus mengungkapkan rincian internal dari bagaimana suatu aplikasi diimplementasikan.

2. Dalam konteks API (Application Programming Interface), **request** merujuk pada permintaan yang dikirim oleh satu komponen perangkat lunak ke komponen lainnya untuk melakukan suatu tindakan atau mendapatkan informasi. Permintaan ini sering kali dilakukan melalui protokol komunikasi seperti HTTP (Hypertext Transfer Protocol) untuk API berbasis web. 

3. Contoh json 
```json
   {
     "nama": "Fauzi Firdaus",
     "usia": 28,
     "makanan_favorit": ["Nasi Goreng", "Usus", "Rendang"],
     "riwayat_pendidikan": {
      "SD": {
         "nama_sekolah": "SDN 012 Petang",
         "tahun_masuk": 2001,
         "tahun_lulus": 2007
      },
      "SMP": {
         "nama_sekolah": "SMPN 27 Bandung",
         "tahun_masuk": 2007,
         "tahun_lulus": 2010
      },
      "SMA": {
         "nama_sekolah": "SMA Pelayaran Tri Arga 1",
         "tahun_masuk": 2010,
         "tahun_lulus": 2013
       }
     }
   }
```
4. **Dokumentasi API**
   * **Request:**

   | Parameter        | Tipe Data | Presence | Deskripsi                           |
   | ---------------- | --------- | -------- | ----------------------------------- |
   | `kode_bank`      | String    | Wajib    | Kode bank pengirim.                 |
   | `rek_tujuan`     | String    | Wajib    | Nomor rekening tujuan transfer.     |
   | `amount`         | Numeric   | Wajib    | Jumlah uang yang akan ditransfer.   |
   | `notes`          | String    | Opsional | Catatan atau keterangan transaksi.  |
   | `pin_transaksi`  | String    | Wajib    | PIN transaksi pengirim.             |
   * Contoh Request:
   ```json
   {
     "kode_bank": "009",
     "rek_tujuan": "1234567",
     "amount": 500000,
     "notes": "bayar hutang",
     "pin_transaksi": "123456"
   }
   ```
   * **Respons**:

   | Parameter                | Tipe Data | Deskripsi                                           |
   | ------------------------ | --------- | --------------------------------------------------- |
   | `status`                 | Numeric   | Kode status respons (contoh: 200 untuk sukses).     |
   | `message`                | String    | Pesan respons (contoh: "success" untuk sukses).     |
   | `transaction_detail`     | Objek     | Detail transaksi yang berhasil dilakukan.           |
   | - `rek_tujuan`           | String    | Nomor rekening tujuan transfer.                     |
   | - `nama_penerima`        | String    | Nama penerima dana.                                 |
   | - `kode_bank`            | String    | Kode bank tujuan transfer.                          |
   | - `nama_bank`            | String    | Nama bank tujuan transfer.                          |
   | - `amount`               | Numeric   | Jumlah uang yang berhasil ditransfer.               |
   | - `admin_fee`            | Numeric   | Biaya admin (jika ada).                             |
   | - `notes`                | String    | Catatan atau keterangan transaksi.                  |
   | - `journal`              | String    | Nomor jurnal transaksi atau referensi unik.         |
   | - `timestamp`            | String    | Waktu dan tanggal transaksi (format ISO 8601).      |
   * Contoh Response :
   ```json
   {
     "status": 200,
     "message": "success",
     "transaction_detail": {
         "rek_tujuan": "1234567",
         "nama_penerima": "bagus fibrianto",
         "kode_bank": "009",
         "nama_bank": "BNI",
         "amount": 500000,
         "admin_fee": 0,
         "notes": "bayar hutang",
         "journal": "2020031211120500199",
         "timestamp": "2020-03-12T11:12:05"
        }
   }
   ```
#
# Contoh Atikel
Dokumentasi perangkat lunak yang bagus

## Introduction

Software ini dibuat untuk meringankan beban manusia

## Fitur Utama

* Mendaftarkan pasien pada rumah sakit
* Membayar biaya *perawatan*
* **Booking kamar rumah sakit**
* ~~Membeli obat~~

## System Requirements
   | Komponen | Versi | 
   | -------- | ----- | 
   | PHP      | 7.1   |
   | NodeJS   | 12.0  | 
   | MariaDB  | 8.0   | 
