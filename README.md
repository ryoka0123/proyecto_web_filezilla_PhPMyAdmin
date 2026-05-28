# Proyecto Servidor Web Linux

Proyecto académico enfocado en la instalación, configuración y administración de un servidor web utilizando Linux, Apache HTTP Server, VSFTPD, MariaDB y phpMyAdmin.

## Descripción

Este proyecto tiene como objetivo implementar un entorno servidor funcional capaz de alojar páginas web, administrar bases de datos y permitir transferencia de archivos mediante FTP.

Durante el desarrollo se realizaron configuraciones de red, firewall, servicios web y bases de datos utilizando herramientas de administración en Linux.

## Tecnologías Utilizadas

- Linux
- Apache HTTP Server
- MariaDB
- VSFTPD
- phpMyAdmin
- FileZilla
- Firewalld

## Servicios Configurados

### Apache HTTP Server
Servidor web encargado de alojar y mostrar la página web.

### VSFTPD
Servicio FTP utilizado para la transferencia remota de archivos mediante FileZilla.

### MariaDB
Sistema gestor de bases de datos utilizado para almacenar información del proyecto.

### phpMyAdmin
Herramienta gráfica para administrar bases de datos desde el navegador.

### Firewalld
Sistema de firewall utilizado para permitir el acceso a los servicios HTTP, HTTPS, FTP y MySQL.

---

# Comandos Utilizados

## Actualización del sistema

```bash
dnf update -y

Instalación de Apache
dnf install httpd -y
systemctl start httpd
systemctl enable httpd

Instalación de VSFTPD
dnf install vsftpd -y
systemctl start vsftpd
systemctl enable vsftpd

Instalación de MariaDB
dnf install mariadb-server -y
systemctl start mariadb
systemctl enable mariadb

Configuración del Firewall
dnf install firewalld -y
firewall-cmd --permanent --add-service=http
firewall-cmd --permanent --add-service=https
firewall-cmd --permanent --add-service=mysql
firewall-cmd --permanent --add-service=ftp
firewall-cmd --reload

Instalación de PHP
dnf install php php-mysqlnd php-pdo php-json -y
systemctl restart httpd

Instalación de phpMyAdmin
dnf install phpmyadmin -y
cp -r /usr/share/phpMyAdmin /var/www/html/phpmyadmin
chown -R apache:apache /var/www/html/phpmyadmin
chmod -R 755 /var/www/html/phpmyadmin
systemctl restart httpd
