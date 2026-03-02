## Installation de GLPI

Je procède ensuite à l’installation de GLPI.

L’application est téléchargée, puis extraite dans le dossier /tmp.  
Elle est ensuite déplacée dans le répertoire /var/www/html, qui est le dossier utilisé par Apache pour afficher les applications web.

GLPI doit obligatoirement être placé dans ce répertoire pour être accessible depuis un navigateur.

Une fois le déplacement effectué, je redémarre Apache afin de prendre en compte les modifications.

Commande utilisée :
systemctl restart apache2


