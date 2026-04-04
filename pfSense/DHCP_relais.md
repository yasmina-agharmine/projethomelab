## DHCP Relay

Dans cette étape, je mets en place un **DHCP Relay** dans mon infrastructure.  
Mon lab comporte plusieurs réseaux LAN, dont un réseau qui héberge le **serveur DHCP** sur Windows Server. L’objectif est de permettre à ce serveur DHCP de distribuer également des configurations réseau aux machines situées sur les autres sous-réseaux, notamment l’adresse IP, le masque, la passerelle et le DNS 

### Pourquoi un relais DHCP est nécessaire

Lorsqu’une machine démarre et qu’elle n’a pas encore d’adresse IP, elle envoie une requête DHCP en **broadcast** afin de trouver un serveur DHCP sur son réseau local. En pratique, elle “demande” à toutes les machines de son sous-réseau quel équipement peut lui fournir une configuration réseau.

Le problème est que ce broadcast ne traverse pas automatiquement un routeur. Cela signifie qu’un client placé sur un autre réseau, par exemple sur **LAN3**, ne peut pas contacter directement le serveur DHCP situé sur **LAN2** sans configuration supplémentaire. C’est précisément le rôle du **DHCP Relay** : transmettre la requête du client vers le serveur DHCP situé sur un autre sous-réseau 

### Configuration réalisée

Pour cette configuration, j’utilise **pfSense** comme routeur entre mes différents réseaux. Je me rends dans l’interface web de pfSense, puis dans la partie dédiée au **DHCP Relay**.

Je souhaite ici permettre aux machines de **LAN3** d’obtenir leur configuration réseau depuis le serveur DHCP installé sur mon **Windows Server** situé sur **LAN2**. Pour cela :
- j’active le **DHCP Relay** ;
- je sélectionne l’interface **LAN3** comme interface concernée ;
- dans **Upstream Server**, je renseigne l’adresse IP du serveur DHCP, c’est-à-dire celle de mon Windows Server ;
- je vérifie également que le **serveur DHCP de pfSense** est bien désactivé sur cette interface, afin d’éviter tout conflit

Même si utiliser directement le serveur DHCP de pfSense aurait été plus simple, j’ai choisi de conserver celui de **Windows Server**, car cela est plus formateur dans le cadre de mon apprentissage en administration systèmes et réseaux.

### Configuration de l’étendue DHCP

Sur le serveur DHCP Windows, j’ai créé une **nouvelle étendue** pour le réseau **LAN3**. Cette étendue permet de distribuer automatiquement des adresses IP aux machines présentes sur ce sous-réseau.

J’y ai défini :
- une plage d’adresses correspondant au réseau **192.168.3.0/24** ;
- la **passerelle** du réseau, qui correspond à l’adresse de pfSense sur **LAN3** ;
- ainsi que les autres paramètres réseau nécessaires, comme le DNS 

### Vérification

Pour tester la configuration, j’ai modifié la configuration réseau de deux machines clientes de mon lab, une machine **Kali Linux** et une machine **Metasploitable**, qui étaient auparavant configurées en adresse IP statique. Je les ai passées en **DHCP** afin de vérifier qu’elles pouvaient récupérer automatiquement une adresse sur le réseau **LAN3**.

Les deux machines ont bien obtenu une configuration réseau valide, ce qui confirme que le **DHCP Relay fonctionne correctement** entre pfSense et mon serveur DHCP Windows 
### Ce que cette étape m’a permis de comprendre

Cette manipulation m’a permis de mieux comprendre plusieurs notions importantes :
- le fonctionnement d’une requête **DHCP en broadcast** ;
- le fait qu’un broadcast ne traverse pas naturellement un routeur ;
- le rôle du **DHCP Relay** dans une infrastructure segmentée ;
- l’importance de configurer la **bonne passerelle**, c’est-à-dire celle du sous-réseau du client, et non celle du serveur DHCP.

Cette étape s’inscrit directement dans une logique d’**administration et de sécurisation d’infrastructures réseau**, en lien avec les compétences visées dans un parcours d’Administrateur d’Infrastructures Sécurisées 
