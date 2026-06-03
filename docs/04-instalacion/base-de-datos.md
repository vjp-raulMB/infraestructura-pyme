sudo apt install mariadb-server -y

sudo mysql_secure_installation

CREATE DATABASE web_empresa;
CREATE DATABASE gestion_interna;

CREATE USER 'empresa'@'localhost' IDENTIFIED BY 'PasswordSegura123!';
GRANT ALL PRIVILEGES ON web_empresa.* TO 'empresa'@'localhost';
FLUSH PRIVILEGES;