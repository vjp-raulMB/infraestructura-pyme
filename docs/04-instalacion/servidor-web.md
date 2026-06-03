sudo apt update
sudo apt install apache2 -y

systemctl status apache2

sudo systemctl enable apache2

sudo apt install php libapache2-mod-php php-mysql -y

php -v