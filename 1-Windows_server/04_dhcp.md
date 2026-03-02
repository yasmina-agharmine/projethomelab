# Installation et configuration DHCP

Après l’IP statique et Active Directory, j’installe le rôle DHCP.  
Dans le Gestionnaire de serveur → Ajouter des rôles et fonctionnalités → je coche **DHCP** et j’installe. :contentReference[oaicite:7]{index=7}

Quand l’installation est finie, je termine la configuration via l’assistant (drapeau jaune).

👉 Capture d’écran à insérer ici : ajout du rôle DHCP + fin de configuration (assistant)

## Création de l’étendue DHCP
Je crée ensuite une nouvelle étendue pour distribuer automatiquement des adresses IP aux clients.

Plage d’adresses définie :
- **192.168.0.100 à 192.168.0.200**
Puis j’active l’étendue. :contentReference[oaicite:8]{index=8}

👉 Capture d’écran à insérer ici : étendue DHCP (plage + activation)

## Vérification
Je vérifie que l’étendue est bien active et qu’elle distribuera bien les IP.

👉 Capture d’écran à insérer ici : console DHCP avec l’étendue active
