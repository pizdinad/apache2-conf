# apache2-conf

## Для настроек по-умолчанию :
1. **./httpd.conf =>  directives:**  
Listen  
проверяем Dynamic Shared Object (DSO) - LoadModule  
<Directory /usr/local/apache2/htdocs>  
Require ip 127.0.0.1 91.79.157.39  
<\/Directory>  
Include (ssl,..)
2. **./httpd-vhosts.conf => directives:**  
DocumentRoot "/usr/local/apache2/htdocs/**YOUR_NAME_DIR**"  
ServerName **subdomain.example.ru**  
<Directory /usr/local/apache2/htdocs/**YOUR_NAME_DIR**>  
...  
FcgidWrapper /usr/local/apache2/htdocs/**YOUR_NAME_DIR**/php-wrapper .php  
<\/Directory>

## Настройки SSL (HTTPS) :
1. **directives (for ssl):**  
<VirtualHost \*:443>  
SSLCertificateFile "/usr/local/apache2/ssl.crt/**YOUR_NAME_DIR**/domain_name.crt"  
SSLCertificateKeyFile "/usr/local/apache2/ssl.crt/**YOUR_NAME_DIR**/private.key"  
2. **Настройки SSL (HTTPS)**
	* Читаем /usr/local/apache2/ssl.crt/NAME_SITE/readme
	* Особое внимание обращаем на формат :<br>
для Apache серверов необходимы PEM файлы с расширением .crt или .cer , <ins>пример:</ins><br>
-----BEGIN CERTIFICATE-----<br>
64(символа)<br>
...<br>
-----END CERTIFICATE-----
	* Права доступа :<br>
-rw-r----- 1 root root
