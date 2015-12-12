# RapberryPiLaravel

###### On a typical Rasbian connected to monitor with I/O devices & network.

Note:: Please keep admin password handy for few steps

Open **Terminal** after login and type

```
$ sudo apt-get update

$ sudo apt-get upgrade

$ sudo apt-get dist-upgrade
```
Updating operating system before installing laravel with these dependencies 
{
  Apache2,
  PHP >= 5.5.9,
  OpenSSL PHP Extension,
  PDO PHP Extension,
  Mbstring PHP Extension,
  Tokenizer PHP Extension
}

Before we get to dependancies we need 
{
  curl, 
  git, 
  composer
} 
to be installed.

To have latest php on arm based operating system we need to add different repositoray than usual.
For this purpose we first change the Rapbian distibution of wheezy to Jessie. We edit *source.list* file.

```
$ sudo nano /etc/apt/sources.list
```
Change 
```
deb http://archive.raspbian.org/raspbian wheezy main contrib non-free
deb-src http://archive.raspbian.org/raspbian wheezy main contrib non-free
```
To
```
deb http://archive.raspbian.org/raspbian jessie main contrib non-free
deb-src http://archive.raspbian.org/raspbian jessie main contrib non-free
```
Now get the new files
```
$ sudo apt-get update

$ sudo apt-get upgrade

$ sudo apt-get dist-upgrade
```
**--This takes time**

Time to get PHP before that we get right repository
```
$ sudo apt-get install python-software-properties

$ sudo apt-get install software-properties-common

$ sudo apt-get install curl git apache2 php5-cli php5-cgi php5-common php5-curl php5-dev php5-mysql php5-odbc php5-pgsql php5-sqlite php5-xsl
```
Check if everything has installed properly.
```
$ sudo apt-get install curl -sS https://getcomposer.org/installer | sudo php -- --install-dir=/usr/local/bin --filename=composer
$ composer create-project laravel/laravel ProjectName --prefer-dist

```
Installing Postgres
