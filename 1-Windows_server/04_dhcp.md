# Installation et configuration DHCP

Après l’IP statique et Active Directory, j’installe le rôle DHCP.  
Dans le Gestionnaire de serveur → Ajouter des rôles et fonctionnalités → je coche **DHCP** et j’installe. 
Quand l’installation est finie, je termine la configuration via l’assistant (drapeau jaune).

👉 Capture d’écran à insérer ici : ajout du rôle DHCP + fin de configuration (assistant)

## Création de l’étendue DHCP
Je crée ensuite une nouvelle étendue pour distribuer automatiquement des adresses IP aux clients.

Plage d’adresses définie :
- **192.168.100.100 à 192.168.100.110**
Puis j’active l’étendue. 

👉 Capture d’écran à insérer ici : étendue DHCP (plage + activation)

## Vérification
Je vérifie que l’étendue est bien active et qu’elle distribuera bien les IP.

👉 Capture d’écran à insérer ici : console DHCP avec l’étendue active
