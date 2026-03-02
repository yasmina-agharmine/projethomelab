# Configuration IP statique et DNS

Une fois la machine virtuelle créée et Windows Server installé, je configure **directement** l’adressage IP statique.  
C’est important parce que pour un serveur (AD, DHCP, DNS), l’adresse IP ne doit pas changer.

## Où je vais pour changer l’IP
Je me rends dans :
Panneau de configuration → Réseau et Internet → Centre Réseau et partage → Modifier les paramètres de la carte → Propriétés → **IPv4**.

## Adresse configurée
J’ai configuré les paramètres suivants :
- Adresse IP : 192.168.100.10
- Masque : 255.255.255.0 (/24)
- Passerelle : 192.168.100.1
- DNS préféré : 192.168.100.10



Le DNS est la même adresse que le serveur, parce que c’est ce qui permet à Active Directory de fonctionner correctement.


