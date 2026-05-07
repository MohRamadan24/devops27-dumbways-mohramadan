**TASK WEEK 1 - DAY 1 BOOTCAMP DUMBWAYS DEVOPS BATCH 27**

**TASK 1** : Buat sebuah diagram sebuah jaringan komputer dengan 4 device dengan kondisi :
    - IP Class C : 192.168.4.xxx
    - CIDR Block : 192.168.4.0/24
    
**TASK 2** : Jelaskan perbedaan antara SH (Shell) dan BASH (Bourne-Again Shell)

sh dan bash sama-sama shell pada sistem operasi Linux yang digunakan untuk menjalankan perintah dan script. Namun, sh merupakan shell dasar yang lebih sederhana dan dibuat untuk kompatibilitas antar sistem Unix, sedangkan bash adalah pengembangan dari sh yang memiliki fitur lebih lengkap dan modern. bash mendukung auto-completion, command history yang lebih baik, array, serta syntax scripting yang lebih fleksibel dibandingkan sh.

Dalam penggunaannya, sh biasanya dipakai untuk script sederhana yang membutuhkan kompatibilitas tinggi di berbagai sistem Unix/Linux. Sebaliknya, bash lebih sering digunakan pada Linux modern karena lebih nyaman untuk scripting kompleks dan administrasi server.

**TASK 3** : Buat dokumentasi/kumpulan command linux yang kalian ketahui! (Command diluar materi akan diberi nilai ++)

Dokumentasi command linux

- sudo : yang berarti **superuser do**, berfungsi untuk menambahkan akses tertinggi pada command line. Beberapa command crucial memerlukan akses superuser untuk dijalankan.
- nano : diikuti dengan lokasi dan nama file, akan membuka text editor untuk file tersebut.
- ls : list, menampilkan daftar file dan folder dalam direktori yang sedang di buka.
- ls la : menampilkan daftar file dan folder dalam direktori yang sedang di buka, beserta file file tersebunyi nya, hidden files memiliki ".' di awal nama file.
- cd : change directory, untuk mengubah atau pindah direktory yang akan di manage, ".." untuk pindah ke file sebelumnya dan / untuk memisahkan.
- sudo apt update : command untuk memberikan update untuk seluruh package atau aplikasi yang terinstall pada server.
- chmod : mengganti akses dari sebuah file atau direktori.
- chown : mengganti owner dari sebuah file atau direktori.
- mv : mengubah file, dapat mengubah nama dan lokasi file, dapat eksekusi salah satu atau keduanya bersamaan.
- mkdir : make directory, membuat file/directory baru.
- mkdir -p folder1/folder2/folder3 : membuat folder bertingkat.
- cp : untuk menduplikasi file, "cp text.txt backup.txt", backup akan memiliki isi sama persis dengan text.txt.
- cp -r folder1 folder2 : menyalin seluruh file di dalam folder 1 ke dalam folder 2
- echo : menampilkan data yang di pantulkan "echo hello world", menampilkan isi dari variable
- echo halo > file.txt : mengosongkan isi file dan menulis "halo" kedalam file
- echo halo >> file.txt : menambahkan text "halo" kedalam file.
- systemctl : command untuk mengatur service di server, contoh : "systemctl status nginx"
- cat : return isi dari file, "cat file.txt"
- curl : Client URl, untuk download data dari internet.
- curl -O : untuk mengambil data dan menyimpan nya dengan nama asli 
- curl -o nama_baru : untuk mengambil data dan menyimpan dengan nama baru yaitu "nama_baru"
- curl ifconfig.me : melihat ip publik
- curl -X POST : diikuti dengan link api, untuk mengetest API
- tar -xzvf latest.tar.gz : tools linux untuk extract "x", kompress ke .gz "z", verbose atau tampilkan list "v", pada file "f"

**Berikut di bawah ini adalah daftar command yang saya gunakan ketika deploy website wordpress ke server secara manual :**

```
#Update Server
sudo apt update && sudo apt upgrade -y

#Install Nginx
sudo apt install nginx -y

#Cek status nginx
systemctl status nginx

#Install mysql database
sudo apt install mysql-server -y

#Amankan mysql
sudo mysql_secure_installation

#Install php + Eksistensi Wordpress
sudo apt install php-fpm php-mysql php-curl php-gd php-mbstring php-xml php-zip -y

#Check php version
php -v

#Buat database untuk wordpress
CREATE DATABASE wordpress;
CREATE USER 'wpuser'@'localhost' IDENTIFIED BY 'passwordku';
GRANT ALL PRIVILEGES ON wordpress.* TO 'wpuser'@'localhost';
FLUSH PRIVILEGES;
EXIT;

#Redirect ke folder temporary
cd /tmp

#Download wordpress
curl -O https://wordpress.org/latest.tar.gz

#Gunakan Tools linux untuk extract (X), kompress ke.gz (z), verbose/tampilkan list(z), pada file (f)
tar xzvf latest.tar.gz

#Pindahkan wordpress ke web root
sudo mv wordpress /var/www/

#Ubah kepemilikan folder website menjadi milik web server/public
sudo chown -R www-data:www-data /var/www/wordpress

#Ubah akses folder website
sudo chmod -R 755 /var/www/wordpress

#Ubah akses config agar tidak bisa di akses public
sudo chmod 640 /var/www/wordpress/wp-config.php

#Buat config nginx untuk wordpres
sudo nano /etc/nginx/sites-available/wordpress

server {
    server_name 163.61.58.187 nyus.trinitymerge.my.id;

    root /var/www/wordpress;
    index index.php index.html;

    location / {
        try_files $uri $uri/ /index.php?$args;
    }

    location ~ \.php$ {
        include snippets/fastcgi-php.conf;
        fastcgi_pass unix:/run/php/php8.3-fpm.sock;
    }

    location ~ /\.ht {
        deny all;
    }

    listen 443 ssl; # managed by Certbot
    ssl_certificate /etc/letsencrypt/live/nyus.trinitymerge.my.id/fullchain.pem; # managed by Certbot
    ssl_certificate_key /etc/letsencrypt/live/nyus.trinitymerge.my.id/privkey.pem; # managed by Certbot
    include /etc/letsencrypt/options-ssl-nginx.conf; # managed by Certbot
    ssl_dhparam /etc/letsencrypt/ssl-dhparams.pem; # managed by Certbot

}

server {
    listen 80;
    server_name 163.61.58.187 nyus.trinitymerge.my.id;
    return 301 https://$host$request_uri;
}

#Aktifkan config nginx, agar nginx mengenali website ini, dan menyambungkan 'link' antara dua folder, perubahan akan sync
sudo ln -s /etc/nginx/sites-available/wordpress /etc/nginx/sites-enabled/

#Check konfigurasi nginx
sudo nginx -t

#Reload nginx
sudo systemctl reload nginx

#Install ssl
sudo apt install certbot python3-certbot-nginx -y

#Pasang ssl ke domain
sudo certbot --nginx -d nyus.trinitymerge.my.id

#Check certbot version
certbot --version

#Check certificate SSL
sudo certbot certificates

#Check auto renewal certbot
sudo systemctl status certbot.timer

#Check dns
dig nyus.trinitymerge.my.id +short

#Agar php otomatis aktif ketika reboot
sudo systemctl enable php8.3-fpm

#Buka file untuk edit php worker dari php fpm
sudo nano /etc/php/8.3/fpm/pool.d/www.conf

#Ubah pm max children
pm = dynamic
pm.max_children = 12
pm.start_servers = 4
pm.min_spare_servers = 2
pm.max_spare_servers = 6

#Check link folder yang sudah tersedia
ls -l /etc/nginx/sites-enabled/

#Test website secara local
curl -k -I https://127.0.0.1
```

**Berikut adalah command untuk automate deploy, command command di taruh di sebuah file .sh untuk di eksekusi sekaligus :**

```
#!/bin/bash

# ===== CONFIG =====
DOMAIN="nyus.trinitymerge.my.id"
DB_NAME="wordpress"
DB_USER="wpuser"
DB_PASS="passwordku"
PHP_VERSION="8.3"
WEB_ROOT="/var/www/wordpress"
# ==================

echo "=== Update Server ==="
apt update && apt upgrade -y

echo "=== Install Nginx ==="
apt install nginx -y
systemctl enable nginx
systemctl start nginx

echo "=== Install MariaDB ==="
apt install mariadb-server -y
systemctl enable mariadb
systemctl start mariadb

echo "=== Setup Database (safe) ==="
mariadb -u root <<EOF
CREATE DATABASE IF NOT EXISTS $DB_NAME;
CREATE USER IF NOT EXISTS '$DB_USER'@'localhost' IDENTIFIED BY '$DB_PASS';
GRANT ALL PRIVILEGES ON $DB_NAME.* TO '$DB_USER'@'localhost';
FLUSH PRIVILEGES;
EOF

echo "=== Install PHP ==="
apt install php$PHP_VERSION-fpm php$PHP_VERSION-mysql php$PHP_VERSION-curl php$PHP_VERSION-gd php$PHP_VERSION-mbstring php$PHP_VERSION-xml php$PHP_VERSION-zip -y
systemctl enable php$PHP_VERSION-fpm

echo "=== Download WordPress if not exists ==="
if [ ! -d "$WEB_ROOT" ]; then
    cd /tmp
    curl -O https://wordpress.org/latest.tar.gz
    tar xzvf latest.tar.gz
    mv wordpress /var/www/
else
    echo "WordPress already exists, skipping download."
fi

echo "=== Fix Permission ==="
chown -R www-data:www-data $WEB_ROOT
find $WEB_ROOT -type d -exec chmod 755 {} \;
find $WEB_ROOT -type f -exec chmod 644 {} \;

echo "=== Configure Nginx (if not exists) ==="
if [ ! -f /etc/nginx/sites-available/wordpress ]; then
cat > /etc/nginx/sites-available/wordpress <<EOF
server {
    listen 80;
    server_name $DOMAIN;

    root $WEB_ROOT;
    index index.php index.html;

    client_max_body_size 64M;

    location / {
        try_files \$uri \$uri/ /index.php?\$args;
    }

    location ~ \.php$ {
        include snippets/fastcgi-php.conf;
        fastcgi_pass unix:/run/php/php$PHP_VERSION-fpm.sock;
    }

    location ~ /\.ht {
        deny all;
    }
}
EOF
fi

if [ ! -L /etc/nginx/sites-enabled/wordpress ]; then
    ln -s /etc/nginx/sites-available/wordpress /etc/nginx/sites-enabled/
fi

nginx -t && systemctl reload nginx

echo "=== Install SSL if not exists ==="
apt install certbot python3-certbot-nginx -y

if ! certbot certificates | grep -q "$DOMAIN"; then
    certbot --nginx -d $DOMAIN --non-interactive --agree-tos -m admin@$DOMAIN --redirect
else
    echo "SSL already installed."
fi

echo "=== Restart Services ==="
systemctl restart nginx
systemctl restart php$PHP_VERSION-fpm
systemctl restart mariadb
```

echo "=== INSTALLATION COMPLETE ==="
echo "Open browser: https://$DOMAIN"
echo "Continue WordPress setup in browser if not installed."


