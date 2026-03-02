# Projet Infrastructure – Windows Server, Debian et GLPI

## Présentation du projet
Ce projet a pour objectif de mettre en place une infrastructure réseau complète pour une entreprise fictive nommée **Rue25**.  
L’infrastructure repose sur un environnement Windows Server pour la gestion du domaine et des utilisateurs, ainsi qu’un serveur Debian pour l’hébergement de GLPI.

Le projet a été réalisé dans un contexte pédagogique afin de comprendre et maîtriser les bases de l’administration système et réseau.

---

## Objectifs du projet
- Mettre en place un **contrôleur de domaine Windows Server**
- Configurer **Active Directory**, **DNS** et **DHCP**
- Créer des **unités organisationnelles**, groupes et utilisateurs
- Mettre en place des **partages de fichiers sécurisés**
- Configurer des **stratégies de groupe (GPO)**
- Installer et configurer un serveur **Debian**
- Déployer **GLPI** et l’intégrer à l’annuaire LDAP
- Documenter l’ensemble du projet de manière claire et structurée

---

## Architecture de l’infrastructure
L’infrastructure est composée de :
- Un **serveur Windows Server** :
  - Active Directory (AD DS)
  - DNS
  - DHCP
  - Gestion des utilisateurs, groupes et GPO
- Un **serveur Debian** :
  - Adresse IP statique
  - Hébergement de GLPI
- Des **postes clients** intégrés au domaine
- Un réseau interne avec une plage d’adresses IP définie

👉 Un schéma réseau est disponible dans le dépôt.

---

## Technologies utilisées
- Windows Server
- Active Directory Domain Services (AD DS)
- DNS / DHCP
- Debian
- GLPI
- LDAP
- VirtualBox
- GitHub

---

## Structure du dépôt
```text
projet-infrastructure-glpi/
├── README.md
├── 01_windows_server/
│   ├── 01_installation_windows_server.md
│   ├── 02_configuration_ip_dns.md
│   ├── 03_active_directory.md
│   ├── 04_dhcp.md
│   ├── 05_partages_de_fichiers.md
│   ├── 06_gpo.md
│   └── images/
├── 02_debian/
├── 03_glpi/
└── annexes/
