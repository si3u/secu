# secu
- @author: NguyenTuanSieu
- @email: dev.phpjs@gmail.com

### Download Google Drive via command line

```
$>wget --save-cookies cookies.txt --keep-session-cookies --no-check-certificate 'https://docs.google.com/uc?export=download&id=GOOGLE_DRIVE_ID' -O- | sed -rn 's/.*confirm=([0-9A-Za-z_]+).*/Code: \1\n/p'

$>wget --load-cookies cookies.txt 'https://docs.google.com/uc?export=download&confirm=CONFIRM_CODE_ABOVE&id=GOOGLE_DRIVE_ID' -o 'FILENAME'
```

### Reset password root
```
$>mysqld_safe --skip-grant-tables
$>mysql -uroot
$>ALTER USER 'root'@'localhost' IDENTIFIED BY 'MrSi3u@#!';
----------or-----------
$>UPDATE mysql.user SET authentication_string = PASSWORD('MrSi3u@#!'), password_expired = 'N' WHERE User = 'root' AND Host = 'localhost';
--------MySQL 5.7.5 and earlier
$>SET PASSWORD FOR 'root'@'localhost' = PASSWORD('MrSi3u@#!');
$>FLUSH PRIVILEGES;
```

### Remote MySQL
```bash
CREATE USER 'root'@'%' IDENTIFIED BY '»»»MrSi3u@#$«««';
GRANT ALL PRIVILEGES ON *.* TO 'root'@'%' WITH GRANT OPTION;
FLUSH PRIVILEGES;
```
### Import one database from all database backup
```bash
mysql -u root -p --one-database destdbname < alldatabases.sql
```

### Scan Shell

```
$>bash scanshell.sh  -v -single /home/ -time all
$>ngrep "^POST" | grep -i --color "host.+conn"
```

### Setup Apache2, PHP, MySQL, Composer

```
$>chmod +x setup.sh
$>./setup.sh
```

### Create virtual host

```
$>chmod +x vhosts.sh
$>sudo ./vhosts.sh create bds3mien.com bds3mien
```
### Create hosts domain in windows

```
$>./hosts.bat domain.dev
```
### Turn on or off Hyper-V

```
#Off
$>bcdedit /set hypervisorlaunchtype off
#On
$>bcdedit /set hypervisorlaunchtype auto
```

### Find top 10 large files

```
$>for i in G M K; do du -ah | grep [0-9]$i | sort -nr -k 1; done | head -n 11
```

### Display error PHP

```php
ini_set('display_errors', 1);
ini_set('display_startup_errors', 1);
error_reporting(E_ALL);
```

### Disabled views vendors

```.htaccess
Require all denied
Order deny,allow
Deny from all
```

### Disable execute PHP

```.htaccess
<IfModule mod_php5.c>
  php_flag engine off
</IfModule>
<Files *.php>
deny from all
</Files>
```
* Apache 2.4

```.htaccess
<IfModule mod_php5.c>
  php_flag engine off
</IfModule>
<Files *.php>
Require all denied
</Files>
```

### Use ssh key per git repo

```bash
$>ssh-agent bash -c 'ssh-add /home/me/my_private_key; git clone git@bitbucket.org:uname/test-git-repo.git'
```

### Install Apache2

```bash
httpd.exe -k install
httpd.exe -k uninstall
httpd.exe -k start
httpd.exe -k stop
httpd.exe -k restart
```
### Enable PHP
```bash
LoadModule php7_module C:/php/php7apache2_4.dll
DirectoryIndex index.php index.html
AddHandler application/x-httpd-php .php
PHPIniDir C:/php
```
### Install php for Yii2

```bash
apt install php-intl php-mbstring php-xml php-sqlite3 php-mysql php-pgsql php-memcache php-apcu php-gd php-imagick php-redis
```
### Install Redis Server

```bash
apt-get install redis-server
apt-get install php-redis
vim /etc/redis/redis.conf
    maxmemory 128mb
    maxmemory-policy allkeys-lru
systemctl restart redis-server.service
systemctl enable redis-server.service
redis-cli
```
### Install MySQL

```bash
.\mysqld.exe --initialize-insecure
.\mysqld.exe --install
sc MySQL start
.\mysql_secure_installation.exe
```

### Tips MySQL

```
SET SQL_MODE='ALLOW_INVALID_DATES';
```
