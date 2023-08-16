
## mise en prod projet symfo + phpmyadmin

> Written by [mika](https://github.com/mikhaelrihani/)
### Gestion Serveur cloud
- https://kourou.oclock.io/ressources/vm-cloud/
 -   **Nom de la machine :**  mikhaelrihani-server.cloud
-   **Adresse de la machine :**  [http://mikhaelrihani-server.eddi.cloud](http://mikhaelrihani-server.eddi.cloud/)


-   **Commande SSH pour se connecter :** ssh student@mikhaelrihani-server.eddi.cloud
-   **Mot de passe :** par dessus les nuages
## mise en prod symfony
### DOC

https://symfony.com/doc/5.4/deployment.html
 
 https://github.com/O-Clock-Vega/symfo-les-md-de-ben/blob/master/mise-en-prod.md

https://symfony.com/doc/current/setup/web_server_configuration.html#adding-rewrite-rules-for-apache

https://symfony.com/doc/current/setup/file_permissions.html#configuring-permissions-for-symfony-applications

https://doc.ubuntu-fr.org/acl

https://doc.ubuntu-fr.org/phpmyadmin

https://github.com/O-Clock-Vega/S08-script-serveur

 ### général
 - se connecter a notre vm server par le terminal: ssh    student@mikhaelrihani-server.eddi.cloud
- aller dans le dossier cd /var/www/html 
- cloner le projet 
- aller dans le dossier cd /var/www/html/"projet"
-composer install --no-dev --optimize-autoloader

**APP_ENV**

- cp .env .env.local
 - nano .env.local
    - APP_ENV=prod
    -> sudo mariadb -V
    -> par dessus les nuages
    -> pseudo=admin, password=admin
    >DATABASE_URL="mysql://pseudo:password@127.0.0.1:3306/vega? serverVersion=mariadb-10.3.38&charset=utf8mb4"
   ->décommenter les variables 
   ->control x, y, entree
   
  - composer dump-env prod
   
   ### bdd
  - php bin/console do:da:cr
  - php bin/console do:mi:mi
  
### Clear  Symfony Cache

- APP_ENV=prod APP_DEBUG=0 php bin/console cache:clear

### apache
- composer update  --optimize-autoloader --no-dev 
- verifier que le ht access a bien été configure : 
->cd public
->cat .htaccess

### ACL linux

-> depuis le projet :
- sudo apt-get install -y acl
- HTTPDUSER=$(ps axo user,comm | grep -E '[a]pache|[h]ttpd|[_]www|[w]ww-data|[n]ginx' | grep -v root | head -1 | cut -d\  -f1)
- sudo setfacl -dR -m u:"$HTTPDUSER":rwX -m u:$(whoami):rwX var
- sudo setfacl -R -m u:"$HTTPDUSER":rwX -m u:$(whoami):rwX var
->verifier avec un ll que le dossier var a bien les droits  avec un +

### virtual_host
but : permet d'avoir une url plus propre ,et ne pas permettre l acces a notre architecture

depuis la racine de la machine :
- cd `/etc/apache2/sites-available`
- sudo nano site.conf
- entrez ce bout ce code et finir par ctrl x, y,entree

<VirtualHost *:80>

    ServerName mikhaelrihani-server.eddi.cloud
    
    DocumentRoot /var/www/html/symfo-oflix-journee-19-mikhaelrihani/public
    
    ErrorLog /var/log/apache2/project_error.log
    CustomLog /var/log/apache2/project_access.log combined
    
    <Directory /var/www/html/symfo-oflix-journee-19-mikhaelrihani/public>     
                Options indexes
                AllowOverride all
                Allow from all
                Require all granted
                
    </Directory>
    RewriteEngine on
     </VirtualHost>
##### activer virtual host:
-  `sudo a2ensite site.conf`
- sudo a2dissite 000-default.conf
- `sudo systemctl restart apache2`

### debugger 
depuis le terminal : 
- /var/log/apache2 
- cat error.log

depuis vscode c 'est mieux indenté,il existe des extensions pour etre plus clair

### mise en prod de twig
php bin/console cache:clear

## phpmyadmin

- sudo apt install phpmyadmin
- premiere question ->entrer yes
- sélectionner apache2 et bien mettre * avec la barre d'espace
- configure database -> entrer non
 
 se connecter sur nom-de-domaine/phpmyadmin
->identifiant admin / admin
->utiliser bcrypt pour hasher le password d'un nouvel user

## installation du serveur

- cloner le script serveur : git clone git@github.com:O-Clock-Vega/S08-script-serveur.git
- depuis le dossier du script : sh installation-serveur.sh


doc relatif a la bdd 
mcd
mld
dico de donnees

<!--stackedit_data:
eyJoaXN0b3J5IjpbMzk0MTQ3NTY5LC04MzI1NTcyMDVdfQ==
-->