
## mise en prod projet symfo

> Written by [mika](https://github.com/mikhaelrihani/).
### Gestion Serveur cloud
 -   **Nom de la machine :**  mikhaelrihani-server.cloud
-   **Adresse de la machine :**  [http://mikhaelrihani-server.eddi.cloud](http://mikhaelrihani-server.eddi.cloud/)


-   **Commande SSH pour se connecter :** ssh student@mikhaelrihani-server.eddi.cloud
-   **Mot de passe :** par dessus les nuages
### DOC

https://symfony.com/doc/5.4/deployment.html
 
 https://github.com/O-Clock-Vega/symfo-les-md-de-ben/blob/master/mise-en-prod.md

https://symfony.com/doc/current/setup/web_server_configuration.html#adding-rewrite-rules-for-apache

https://symfony.com/doc/current/setup/file_permissions.html#configuring-permissions-for-symfony-applications

https://doc.ubuntu-fr.org/acl

 ### général
1 - se connecter a notre vm server par le terminal: ssh    student@mikhaelrihani-server.eddi.cloud
2- aller dans le dossier cd /var/www/html 
3-cloner le projet 
4- aller dans le dossier cd /var/www/html/"projet"
5-composer install --no-dev --optimize-autoloader

**APP_ENV**

1- cp .env .env.local
2 - nano .env.local
    ->APP_ENV=prod
    -> sudo mariadb -V
    ->par dessus les nuages
    ->pseudo=admin, password=admin
    >DATABASE_URL="mysql://pseudo:password@127.0.0.1:3306/vega? serverVersion=mariadb-10.3.38&charset=utf8mb4"
   ->décommenter les variables 
   ->control x, y, entree
   
   3- composer dump-env prod
   
   ### bdd
  1- php bin/console do:da:cr
  2- php bin/console do:mi:mi
  
### Clear  Symfony Cache

1- APP_ENV=prod APP_DEBUG=0 php bin/console cache: clear

### apache
1-composer update  --optimize-autoloader --no-dev 
2- verifier que le ht access a bien été configure : 
->cd public
->cat .htaccess

### ACL linux

-> depuis le projet :
- sudo apt-get install -y acl
- HTTPDUSER=$(ps axo user,comm | grep -E '[a]pache|[h]ttpd|[_]www|[w]ww-data|[n]ginx' | grep -v root | head -1 | cut -d\  -f1)
- sudo setfacl -dR -m u:"$$HTTPDUSER":rwX -m u:$(whoami):rwX var
- sudo setfacl -R -m u:"$$HTTPDUSER":rwX -m u:$(whoami):rwX var
->verifier avec un ll que le dossier var a bien les droits  avec un +

### virtual_host

depuis la racine de la machine :
->cd `/etc/apache2/sites-available`
->sudo nano site.conf

<VirtualHost *:80>
    ServerName mikhaelrihani-server.cloud
    DocumentRoot /var/www/symfo-oflix-journee-19-mikhaelrihani/public

    ErrorLog /var/log/apache2/project_error.log
    CustomLog /var/log/apache2/project_access.log combined
    <Directory /var/www/symfo-oflix-journee-19-mikhaelrihani/public>     
                Options indexes
                AllowOverride all
                Allow from all
                Require all granted
    </Directory>
    RewriteEngine on
     </VirtualHost>








<!--stackedit_data:
eyJoaXN0b3J5IjpbMTA1ODg3NTQ3LC0xMDI3MTkyMTM4LC04MD
gyMzA2MjksLTg1MTcwNDc4NSwxNDc2NTI3ODg0LC0xNzM3MTEy
MTkwLC0xMTczNjUwNTgwLC0xNDkyODM2MTUzLC02NDYzNzk0MT
AsLTEzNzA4ODQ4MTMsLTIwODY4MDgzNzIsMjEyNTM1MjQ0MV19

-->