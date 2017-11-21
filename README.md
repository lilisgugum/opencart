<h1 align="center"><img src="http://whh01-inmotionhosting1.netdna-ssl.com/img/cms-assets/logo-opencart.svg"></h1>

[Sekilas Tentang](#sekilas-tentang) | [Instalasi](#instalasi) | [Konfigurasi](#konfigurasi) | [Maintenance](#maintenance) | [Cara Pemakaian](#cara-pemakaian) | [Pembahasan](#pembahasan) | [Referensi](#referensi)
:---:|:---:|:---:|:---:|:---:|:---:|:---:

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
- RAM minimum 1024 MB

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
    
    ![admin](https://github.com/lilisgugum/opencart/blob/master/pictures/admin.jpg)
    
    - Tampilan halaman admin
    
    ![page_admin](https://github.com/lilisgugum/opencart/blob/master/pictures/page_admin.jpg)
     
# Konfigurasi
[`^ kembali ke atas ^`](#)

1. Konfigurasi Batas upload file
   Untuk menentukan konfigurasi batas upload file  pada sistem OpenCart yaitu sebagai berikut:
   
   - Masuk ke menu *system*, dan pilih sub menu *setting*
   
   ![konfigurasi_1](https://github.com/lilisgugum/opencart/blob/master/pictures/konfigurasi_1.jpg)
    
   
   - Maka akan muncul tampilan *store* list seperti berikut, kemudian pilih *action edit*
   
   ![konfigurasi_2](https://github.com/lilisgugum/opencart/blob/master/pictures/konfigurasi_2.jpg)
    
   
   - Pilih tab menu *server* lalu pilih bagian *uploads setting* sesuai kebutuhan

   ![konfigurasi_3](https://github.com/lilisgugum/opencart/blob/master/pictures/konfigurasi_3.jpg)
   ![konfigurasi_4](https://github.com/lilisgugum/opencart/blob/master/pictures/konfigurasi_4.jpg)
    

   - Pada bagian server ini dapat juga untuk mengatur *security* dan pengaturan umum server seperti berikut :
     
   ![konfigurasi_5](https://github.com/lilisgugum/opencart/blob/master/pictures/konfigurasi_5.jpg)
   ![konfigurasi_6](https://github.com/lilisgugum/opencart/blob/master/pictures/konfigurasi_6.jpg)


2. Konfigurasi tema baru
   untuk mengganti tema bawaan (*default*) pada opencart caranya sebagai berikut:
   
   - Masuk ke menu *extension* lalu pilih submenu *marketplace*
   
   ![konfigurasi_7](https://github.com/lilisgugum/opencart/blob/master/pictures/konfigurasi_7.jpg)

   
   - Maka akan muncul tampilan *extension marketplace* sebagai berikut:
   
   ![konfigurasi_8](https://github.com/lilisgugum/opencart/blob/master/pictures/konfigurasi_8.jpg)
   
   
   - Pilih *theme* pada filter kategori *extension* seperti gambar berikut:
   
   ![konfigurasi_9](https://github.com/lilisgugum/opencart/blob/master/pictures/konfigurasi_9.jpg)
   
   
   - Maka akan mucul banyak pilihan tema, pilih tema sesuai kebutuhan ecommerce. hanya ada satu tema yang free, yang lainnya berbayar        semua
   - Setelah mendapatkan tema pilih menu extensions dan klik submenu *installer*, lalu pilih tema yang telah kita dapatkan tadi dan klik      upload
   
   ![konfigurasi_10](https://github.com/lilisgugum/opencart/blob/master/pictures/konfigurasi_10.jpg)
   
   
   - Langkah terakhir pilih menu *extensions* dan klik submenu *extensions*, install tema yang telah kita upload tadi, lalu klik *action* edit, ubah menjadi enabled. dan tema selesai diganti
   
   ![konfigurasi_11](https://github.com/lilisgugum/opencart/blob/master/pictures/konfigurasi_11.jpg)
   
   Untuk menambah konfigurasi lain seperti *login* dengan google/ social media dukungan kurir (Indonesia),  payment gateway Indonesia dapat dilakukan dengan install modules masing-masing, lalu konfigurasi kan di menu *extensions*.

# Maintenance
[`^ kembali ke atas ^`](#)

Maintenance pada opencart meliputi 3 bagian yaitu sebagai berikut:
1. Backup & Restore
Seringkali untuk kebutuhan suatu ecommerce memerlukan backup dan restore database untuk keamanan dan duplikasi data. pada CMS OpenCart untuk *backup* dan *restore* caranya sebagai berikut:
   - *Login* ke dalam admin toko kita
   - Klik menu *system* lalu pilih *maintenance* dan klik sub menu *backup & restore*
      
   ![maintenance_1](https://github.com/lilisgugum/opencart/blob/master/pictures/maintenance_1.jpg)
   
   -	Maka akan muncul tampilan sebagai berikut:
   
   ![maintenance_2](https://github.com/lilisgugum/opencart/blob/master/pictures/maintenance_2.jpg)
   
   - Untuk *backup* database pilih tab menu *backup*, lalu pilih tabel apa saja yang akan kita backup kemudian klik *export* dan database akan terbackup dalam bentuk .sql
   
   ![maintenance_3](https://github.com/lilisgugum/opencart/blob/master/pictures/maintenance_3.jpg)
   
   -	Untuk *restore* database pilih tab menu restore, lalu pilih database dari komputer kita yang akan di *import/restore*, tunggu maka kan tertampil progress upload database seperti berikut:
   
   ![maintenance_4](https://github.com/lilisgugum/opencart/blob/master/pictures/maintenance_4.jpg)
   
   
2. *Uploads*
Bagian upload pada maintenance ini, berisi daftar-daftar file / module/ *themes* yang telah kita upload ke dalam sistem CMS OpenCart, dimana pada halaman ini kita bisa *search by filter date* atau menghapus data yang telah di upload. Untuk masuk ke bagian upload ini sama seperti *backup & restore* pilih menu *system* lalu pilih *maintenance* dan klik submenu *upload*. tampiannya sebagai berikut:

   ![maintenance_5](https://github.com/lilisgugum/opencart/blob/master/pictures/maintenance_5.jpg)
   
3. *Error Log*
Pesan *error* adalah petunjuk awal terpenting dalam memperbaiki toko online yang bermasalah. Pada umumnya, toko online yang mengalami *error* pasti akan menampilkan pesan di halamannya. Untuk itu kita perlu mengetahui *error log* terutama di toko online OpenCart. Untuk melihat *error logs* pada toko online OpenCart caranya masuk ke menu *setting*, pilih *maintenance* lalu klik submenu *error logs* maka akan tertampil halaman *error logs* sebagai berikut:

   ![maintenance_6](https://github.com/lilisgugum/opencart/blob/master/pictures/maintenance_6.jpg)
   

# Cara Pemakaian
[`^ kembali ke atas ^`](#)

Cara pemakaian OpenCart adalah sebagai berikut :
1. Sebelum mengelola situs, sistem akan meminta otentikasi *user* berupa masukan *username* dan *password* untuk akses halaman admin.

   ![admin_2](https://github.com/lilisgugum/opencart/blob/master/pictures/admin_2.jpeg)
   
2. Jika *login* berhasil, akan muncul halaman *dashboard* admin yang berisi fitur-fitur yang dapat digunakan untuk menganalisis penjualan seperti jumlah penjualan, jumlah pelanggan, jumlah permintaan per daerah dan lain sebagainya. Menu yang terletak pada sebelah kiri halaman digunakan untuk memodifikasi kebutuhan sistem, isi konten, dan laporan aktivitas yang terjadi pada sistem. seperti penjualan, pelanggan dan produk.

   ![dashboard](https://github.com/lilisgugum/opencart/blob/master/pictures/dashboard.jpeg)
   
3. Menu *catalog* digunakan untuk mengelola konten pada situs seperti produk, kategori produk, dan *review* produk. Pada opsi ini dapat dilakukan penambahan, pengubahan dan penghapusan konten.

   ![catagories](https://github.com/lilisgugum/opencart/blob/master/pictures/catagories.jpeg)
   
4. Menu *extensions* digunakan untuk mengatur extensi yang dibutuhkan sistem seperti metode pengiriman dan pembayaran yang dapat didukung sistem. Pada opsi ini dapat dilakukan pemasangan, pengubahan dan pencopotan ekstensi.

   ![shipping](https://github.com/lilisgugum/opencart/blob/master/pictures/shipping.jpeg)

5. Menu *design* digunakan untuk mengelola desain sistem yang akan digunakan seperti *layout* dan banner. Pada opsi ini dapat dilakukan penambahan, pengubahan dan penghapusan desain.

   ![layouts](https://github.com/lilisgugum/opencart/blob/master/pictures/layouts.jpeg)

6. Menu sales digunakan untuk memantau aktivitas jual beli pada situs seperti pamesanan dan pengembalian barang. Pada opsi ini dapat dilakukan penambahan, pengubahan dan penghapusan aktivitas jual beli. selain itu kita juga dapat memfilter data yang ingin ditampilkan.

   ![orders](https://github.com/lilisgugum/opencart/blob/master/pictures/orders.jpeg)
   
7. Menu *customer* digunakan untuk mengelola pelanggan situs baik pelanggan individu ataupun grup pelanggan. banning pengguna dapat dilakukan pada opsi ini.

   ![customers](https://github.com/lilisgugum/opencart/blob/master/pictures/customers.jpeg)
   
8. Menu *marketing* digunakan untuk mengelola pemasaran produk seperti kupon belanja atau informasi penawaran produk yang dikirimkan via *email*.

   ![marketing](https://github.com/lilisgugum/opencart/blob/master/pictures/marketing.jpeg)
   

9. Menu *system* digunakan untuk mengelola ketentuan-ketentuan dalam sistem seperti bahasa dan nama mata uang yang digunakan.  

   ![stores](https://github.com/lilisgugum/opencart/blob/master/pictures/stores.jpeg)

10. Menu report digunakan untuk mengakses laporan-laporan seperti laporan penjualan, produk, pelanggan dan pemasaran.

    ![report](https://github.com/lilisgugum/opencart/blob/master/pictures/report.jpeg)


# Pembahasan
[`^ kembali ke atas ^`](#)
- Pendapat anda tentang aplikasi web ini:
  OpenCart sebagai CMS gratis dan open source mempunyai kelebihan dan kekurangan. Adapun kelebihan dan kekurangan dari OpenCart sebagai   berikut:
  - Kelebihan:
    - Cara penginstalannya mudah diikuti dan dipahami.
    - Adanya tool backup dan restore untuk website dan database.
    - Multi mata uang, bisa menggunakan lebih dari satu mata uang dengan nilai konversi   antar mata uang.
    - Kategori bertingkat dan tidak terbatas.
    - Template dapat diganti dengan mudah dan tersedia template gratis dan berbayar.

  - Kekurangan:
    - Bagi pengguna awam saat instalasi pasti mengalami kebingungan ketika harus rename config-dist menjadi config dan harus delete folder install, tidak secara otomatis terhapus.
    - Pilihan theme dan modul yang sederhana, jika mau yang bagus harus membayar.
    - Masih susah dalam otak-atik function.

- Jika dibandingkan dengan CMS yang sejenis seperti PrestaShop, kedua CMS memiliki kelebihan dan kekurangan masing-masing.
  - Perbandingan dari keduanya adalah sebagai berikut: OpenCart dan PrestaShop memiliki fitur yang cukup lengkap. Keduanya tergolong ringan dan bisa di-instal tanpa kesulitan di lingkungan shared hosting. Dari sisi fitur dan tampilan PrestaShop lebih unggul dibandingkan OpenCart. Contoh fitur yang hanya ada pada prestashop seperti seperti membedakan antara pemasok dan merek, adanya pengelompokan pada atribut tambahan produk, adanya tag produk, adanya fitur untuk me-retur order, adanya attachment produk (bisa untuk brosur elektronik). Dalam pendefinisian SEF URL OpenCart lebih fleksibel dibanding PrestaShop, meskipun kedua nya memberikan kebebasan dalam mendefinisikan SEF URL.  Kekurangan dari OpenCart maupun PrestaShop memiliki masalah duplikasi konten untuk menggunakannya. 

  - Dalam segi Fitur OpenCart vs Prestashop :
    - Management untuk konten : Dari menu-menu didalam backend administratornya untuk mengatur kategori-kategori dan konten, OpenCart lebih mudah dipahami untuk mengelola isi konten dan mengaturnya termasuk informasi dan halaman-halaman lain yang ingin dibuat.
    - SEO : Prestashop yang lebih unggul daripada OpenCart, terlebih sudah adanya fitur meta-title didalam default Prestashop yang mana "Judul" atau meta-title merupakan inti terpenting dalam SEO selain daripada Url.
    - Mengelola tema : OpenCart lebih unggul dari Prestashop, banyak sekali tema di marketplace template untuk Opencart.
    - Kapasitas module / addon : dalam hal ini kedua-duanya cukup banyak untuk kategori module extension.


# Referensi
[`^ kembali ke atas ^`](#)
1. [About OpenCart]() - OpenCart
2. [Installing OpenCart on Ubuntu 14.04](https://fosskb.in/2016/02/06/installing-opencart-on-ubuntu-14-04/) - OpenCart 
3. [Perbandingan OpenCart dan Prestashop](http://opensource-2009.blogspot.co.id/2009/11/pilih-mana-magento-opencart-prestashop.html) - Perbandingan OpenCart dan Prestashop
4. [Perbandingan OpenCart dan Prestashop](https://www.mfahmi.net/2013/07/perbandingan-opencart-dan-prestashop) - Perbandingan OpenCart dan Prestashop


