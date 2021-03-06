### Apa spesifikasi workspace yang saya dapat?
Workspace C9 dibuat menggunakan docker dengan image debian dengan beberapa konfigurasi limit agar tidak terjadi overload pada server utama

### Apakah saya dapat user root?
Mendapatkan user root, kalian dapat menginstall atau merubah konfigurasi sesuka hati

### Apa yang harus saya lakukan ketika baru mendapatkan workspace?
Silahkan lakukan update dan upgrade base system kamu agar saling terintegrasi dengan cara menjalankan perintah "apt update" atau "apt-get update"

### Bagaimana cara menginstall package?
Gunakan perintah "apt" atau "apt-get" dilanjutkan dengan nama package yang akan diinstall

### Bagaimana cara menginstall dan memilih versi php?
```
$ apt install apt-transport-https lsb-release ca-certificates
$ wget -O /etc/apt/trusted.gpg.d/php.gpg https://packages.sury.org/php/apt.gpg
$ echo "deb https://packages.sury.org/php/ $(lsb_release -sc) main" > /etc/apt/sources.list.d/php.list
$ apt update
$ apt install php7.2
```
Silahkan ganti **7.2** dengan versi php yang kalian inginkan
```
$ apt install php-exif php-gd php-mbstring php-curl php-mysqli php-json php-dom php-fpm
```
Install juga beberapa ekstensi untuk keperluan script kamu. Jika gagal, tambahkan versi php kamu setelah php, contoh **php7.2-curl**

### Bagaimana cara menginstall ionCube?

**Bash Script**
```
$ wget https://raw.githubusercontent.com/gvoze32/C9IDECoreDeploy/master/scripts/ioncubesc.sh
$ bash ioncubesc.sh
```

**Manual**

```
$ wget https://downloads.ioncube.com/loader_downloads/ioncube_loaders_lin_x86-64.tar.gz
$ tar -xvzf ioncube_loaders_lin_x86-64.tar.gz
$ cd ioncube && ls
$ ls /usr/lib/php/
$ php -v
```
Ganti **"NAMAFOLDER"** dengan nama folder yang muncul, contoh **"20170718".**

Kemudian ganti **"VERSI"** dengan versi php yang sedang kamu digunakan, contoh **"7.2".**
```
$ cp ioncube_loader_lin_VERSI.so /usr/lib/php/NAMAFOLDER
$ sudo bash -c 'echo 'zend_extension=ioncube_loader_lin_VERSI.so' > /etc/php/VERSI/cli/conf.d/00-ioncube-loader.ini'
```
```
$ service php7.2-fpm restart
$ php -v
```

### Bagaimana cara menginstall Node.js?
```
$ curl -sL https://deb.nodesource.com/setup_12.x | sudo bash -
$ apt install nodejs
```
