## Installation de Debian et mise en place de SSH

Une fois Debian installé, je me rends dans le terminal et je passe en mode super-utilisateur afin d’avoir les droits nécessaires pour installer les services.

Commande utilisée :
su

Avant d’installer quoi que ce soit, je commence par mettre le système à jour afin d’éviter des bugs ou des problèmes de compatibilité.

Commandes utilisées :
apt update  
apt upgrade

Ensuite, j’installe le service SSH, qui permettra d’administrer la machine à distance.

Commande utilisée :
apt install ssh

À partir de ce moment-là, toutes les actions sur le serveur Debian se font via le terminal, ce qui correspond à une administration classique d’un serveur sans interface graphique.


