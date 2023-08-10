
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
2- ver
2-composer require symphony/apache-pack--no-update
2-





<!--stackedit_data:
eyJoaXN0b3J5IjpbMTU2MzgyOTc5MCwtNjQ2Mzc5NDEwLC0xMz
cwODg0ODEzLC0yMDg2ODA4MzcyLDIxMjUzNTI0NDFdfQ==
-->