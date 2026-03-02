## Configuration de la base de données GLPI

Une fois MariaDB installé, je commence par sécuriser la base de données afin de définir un mot de passe pour l’utilisateur root.

Commande utilisée :
mysql_secure_installation

Je me connecte ensuite à MariaDB avec l’utilisateur root.

Commande utilisée :
mysql -u root -p

Une fois connecté, je crée une base de données nommée glpi, ainsi qu’un utilisateur dédié glpi auquel j’accorde les droits nécessaires pour fonctionner avec GLPI.

Après la configuration, je quitte la base de données.

Pour vérifier que la base fonctionne correctement, je me reconnecte avec l’utilisateur glpi et le mot de passe défini précédemment.  
Si la connexion fonctionne, cela signifie que la base de données est correctement configurée.


