<h1 align="center"><img src="http://whh01-inmotionhosting1.netdna-ssl.com/img/cms-assets/logo-opencart.svg"></h1>

[Sekilas Tentang](#sekilas-tentang) | [Instalasi](#instalasi) | [Konfigurasi](#konfigurasi) | [Maintenance](#maintenance) | [Otomatisasi](#otomatisasi) | [Cara Pemakaian](#cara-pemakaian) | [Pembahasan](#pembahasan) | [Referensi](#referensi)
:---:|:---:|:---:|:---:|:---:|:---:|:---:|:---:

# Sekilas Tentang
[`^ kembali ke atas ^`](#)

**OpenCart** adalah program pengelolaan toko online (*Open Source*) yang dapat mengelola beberapa toko online dari satu (*back-end*). Ada banyak ekstensi yang ditulis secara profesional yang tersedia untuk menyesuaikan toko dengan sesuai kebutuhan.

# Instalasi
[`^ kembali ke atas ^`](#)

#### Kebutuhan Sistem:
- Unix, Linux atau Windows
- Apache Web server 2.4.7
- PHP 5.6.5
- MySQL 5.0+
- RAM 2048 MB

#### Proses instaslasi:

Kunjungi alamat IP web server yang telah dibuat untuk meneruskan instalasi CMS Opencart
Persetujuan kebijakan syarat dan ketentuan dalam menggunakan Opencart, pilih Proses Instalasi:
1.	Login ke dalam server menggunakan SSH. Jika Sistem Operasi Windows yang digunakan, bias memakai [PuTTY](http://www.putty.org/).
     ```
     $ ssh user@localhost
     ```

2.	Pastikan seluruh paket dari system up-to-date, lalu install seluruh kebutuhan sisrem seperti `Apache`, `PHP`, dan `MySQL`
     ```
     $ sudo apt-get update
     $ sudo apt-get install apache2
     $ sudo apt-get install mysql-server
     $ sudo apt-get install php5
     $ sudo apt-get install libapache2-mod-php5
     $ sudo apt-get install php5-mysql
     $ sudo apt-get install unzip
     $ sudo apt-get install php5-gd php5-curl php5-mcrypt unzip
     ```

3.	Aktifkan modul PHP 'mcrypt'
     ```
     $ sudo php5enmod mcrypt
     ```

4.	Unduh OpenCart ke dalam direktori kita.
     ```
     $ sudo wget https://github.com/opencart/opencart/archive/2.1.0.2.zip
     ```

5.	Ekstrak package unzip
     ```
     $ unzip 2.1.0.2.zip
     ```

6.  Direktori yang diekstraksi akan serupa dengan 'opencart-2.1.0.2'. Sekarang pindahkan file di dalam direktori ini ke '/var/www/html'.
     ```
     $ sudo mv opencart-2.1.0.2/upload/ /var/www/html/opencart
     ```

7.  Ubah direktori ke /var/www/html/
     ```
     $ cd /var/www/html/opencart
     ```

8.	Pindahkan file config-dist.php ke config.php
     ```
     # mv config-dist.php config.php
     ```

9.  Pindahkan file admin/config-dist.php ke admin/config.php
     ```
     # mv admin/config-dist.php admin/config.php
     ```

10. Ubah otorisasi kepemilikan ke user www-data (webserver)
     ```
     $ sudo chown -R www-data:www-data /var/www/html/opencart
     ```

11. Install phpmyadmin
     ```
     $ sudo apt-get install phpmyadmin
     ```

12. Buat database dan user untuk OpenCart.
     ```
     $ mysql -u root -p 
     > CREATE DATABASE opencart;
     > CREATE USER 'opencartuser'@'localhost' IDENTIFIED BY 'opencartpassword';
     > quit
     ```

13. Restart kembali Apache web server.
     ```
     $ sudo service apache2 restart
     ```
    
14. Instalasi bisa dimulai pada URL pada halaman web dengan alamat IP web server kita untuk meneruskan instalasi.
    
    - Instalasi tampilan awal opencart
    
    ![instalasi_1](https://github.com/lilisgugum/opencart/blob/master/pictures/1..jpg)
   
    continue untuk melanjutkan proses instalasi
    
    - Setelah continue, masuk ke tahap *Pre-Instalation*. Tahap ini mencakup kebutuhan instalasi yang sudah tercapai.
       Pastikan semua telah terisi dan status sudah checklist dalam masing-masing komponen
    
    ![instalasi_2](https://github.com/lilisgugum/opencart/blob/master/pictures/2.Pre%20Installation.png)
    
    continue untuk melanjutkan proses instalasi
    
    - Setelah semua kebutuhan terpenuhi dan tidak ada yang missing juga tanda *x*, Selanjutnya ke tahap *Configuration*. Tahap                *Configuration* untuk database dan administration.
    
    ![instalasi_3](https://github.com/lilisgugum/opencart/blob/master/pictures/3.Configuration.png)
    
    continue untuk melanjutkan proses instalasi
    
    - Tahap terakhir proses instalasi adalah hapus folder install untuk keamanan, setelah itu CMS Opencart di sesuaikan dengan                 kebutuhan
    
    ![instalasi_4](https://github.com/lilisgugum/opencart/blob/master/pictures/4.Installation%20complete.png)
 
 
15. Setelah proses instalasi selesai hapus direktori install untuk keamanan.
     ```
     $ sudo rm -rf /var/www/html/opencart/install
     ```
     
    - Tampilan e-commerce opencart untuk customer sebelum di personalisasi (localhost:8080/opencart)
    
    ![instalasi_selesai](https://github.com/lilisgugum/opencart/blob/master/pictures/5.Your%20Store.png)
    
    - Tampilan halaman login admin
    
    ![admin](https://github.com/lilisgugum/opencart/blob/master/pictures/admin.png)
    
     
     
# Konfigurasi
[`^ kembali ke atas ^`](#)

1. Konfigurasi Batas upload file
   untuk menentukan konfigurasi batas upload file  pada sistem Opencart yaitu sebagai berikut:


# Maintenance
[`^ kembali ke atas ^`](#)

# Otomatisasi
[`^ kembali ke atas ^`](#)

Jika kalian masih kesulitan dalam meng-install **OpenCart**, terdapat dua cara alternatif, yaitu dengan cara: Pertama adalah dengan menggunakan script shell yang otomatis akan menjalankan semua perintah instalasi pada terminal. Contoh script shell yang digunakan dalam proses instalasi OpenCart dapat dilihat di setup.sh. Kedua adalah dengan melakukan instalasi di localhost terlebih dahulu, yaitu men-download file OpenCart di web resmi [OpenCart](https://www.opencart.com/index.php?route=cms/download). Kemudian setelah selesai konfigurasi, maka anda dapat melakukan upload file website di hosting. Berikut langkah-langkah untuk melakukan instalasinya:
- Download software xampp di https://www.apachefriends.org/download.html untuk menginstal apache, mysql, dan php sesuai kebutuhan.
- Ekstrak file yang sudah di download di https://www.opencart.com/index.php?route=cms/download di sembarang folder (sebagai temporary     saja).
- Pindahkan file yang sudah diekstrak tersebut ke folder htdocs (C:\xampp\htdocs)
- Agar mudah dalam penamaan, rename folder tadi menjadi opencart

# Cara Pemakaian
[`^ kembali ke atas ^`](#)

Cara pemakaian OpenCart adalah sebagai berikut :
1. Login terlebih dahulu pada halaman admin
2. Setelah login, akan masuk ke halaman dashboard
3. Menu disebelah kiri adalah untuk modifikasi kebutuhan konten, seperti menu kategori, produk, tema dan lain sebagainya. 
4. Untuk menambahkan kategori, klik menu katalog lalu akan ada sub menu kategori, pada kolom action

# Pembahasan
[`^ kembali ke atas ^`](#)
- Pendapat anda tentang aplikasi web ini:
  OpenCart sebagai CMS gratis dan open source mempunyai kelebihan dan kekurangan. Adapun kelebihan dan kekurangan dari OpenCart sebagai   berikut:
  - Kelebihan:
    1. Cara penginstalannya mudah diikuti dan dipahami.
    2. Adanya tool backup dan restore untuk website dan database.
    3. Multi mata uang, bisa menggunakan lebih dari satu mata uang dengan nilai konversi   antar mata uang.
    4. Kategori bertingkat dan tidak terbatas.
    5. Template dapat diganti dengan mudah dan tersedia template gratis dan berbayar.

  - Kekurangan:
    1. Bagi pengguna awam saat instalasi pasti mengalami kebingungan ketika harus rename config-dist menjadi config dan harus delete            folder install, tidak secara otomatis terhapus.
    2. Pilihan theme dan modul yang sederhana, jika mau yang bagus harus membayar.
    3. Masih susah dalam otak-atik function.

- Bandingkan dengan aplikasi web lain yang sejenis


# Referensi
[`^ kembali ke atas ^`](#)
1. [About OpenCart]() - OpenCart
2. [Installing OpenCart on Ubuntu 14.04](https://fosskb.in/2016/02/06/installing-opencart-on-ubuntu-14-04/) - OpenCart 

