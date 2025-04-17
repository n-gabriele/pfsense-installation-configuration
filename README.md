# 🔐 Projet d'Infrastructure Sécurisée avec pfSense  
📘 Réalisé par : Nathan Gabriele – BTS SIO SISR

---

## 🎯 Objectif de l’atelier

L’objectif principal de cet atelier professionnel est la **mise en place d’une infrastructure réseau complète, segmentée et sécurisée**, à l’aide de la solution open-source **pfSense**. Le projet vise à démontrer la maîtrise des mécanismes de filtrage, de redirection, d’authentification et de supervision, indispensables à la gestion moderne d’un système d’information.

---

## 🧱 Architecture réseau

- Déploiement de **pfSense sur une machine virtuelle dédiée**
- Segmentation en **plusieurs interfaces (WAN, LAN0, LAN1, LAN2, DMZ)** avec adressage statique
- Accès à l’administration via **interface web sécurisée (HTTPS)** avec certificat auto-signé
- Configuration DNS, DHCP, NAT, et surveillance du trafic en temps réel

---

## 🔒 Sécurisation et filtrage réseau

Des **règles de pare-feu strictes et ciblées** ont été mises en œuvre afin d’assurer un contrôle précis des flux :

- **Blocage d’applications spécifiques** (ex : AnyDesk) à l’aide de règles et d’alias
- **Redirection HTTP vers HTTPS** par des règles NAT dédiées pour forcer la sécurisation des connexions
- **Filtrage DNS renforcé** avec intégration de la liste Spamhaus
- Paramétrage du **filtrage ICMP** (blocage du ping entrant)
- **Surveillance et journalisation** des connexions (interface states)

---

## 🌐 Mise en œuvre de services réseau avancés

### 🔁 Proxy filtrant avec SquidGuard (LAN2)
- Déploiement du proxy transparent avec **filtrage de contenu web**
- Fonctionnement en **DHCP**
- Application de **blacklists** pour le blocage de catégories de sites
- Inspection SSL avec génération de certificats pour contrôle des connexions HTTPS

### 🧾 Authentification LDAP
- Intégration à un **serveur LDAP** pour l’authentification des utilisateurs
- Tests de connectivité réalisés avec `ldap-utils` et `ldapsearch`
- Vérification des communications sécurisées vers le contrôleur de domaine

### 📡 Services complémentaires
- **DNS Forwarder** avec DNSSEC activé
- **Serveur NTP** local configuré pour synchronisation sur toutes les interfaces
- **DHCP Relay** actif sur les segments sans serveur DHCP local

---

## 🛡️ Mise en place de la supervision et de la détection

### 🧪 Snort (IDS/IPS)
- Déploiement de **Snort**, outil de détection d’intrusions réseau (IDS)
- Surveillance en temps réel des paquets transitant via pfSense
- Application de signatures de sécurité pour bloquer les comportements suspects

### 🔍 Supervision applicative
- Accès autorisé aux services **Zabbix (port 10051)** et **Grafana (port 3000)**
- Règles définies pour permettre la remontée de métriques depuis les hôtes supervisés

---

## 🧰 Services métiers intégrés

- **GLPI** : Système de gestion des actifs informatiques (ITSM)
- **NextCloud** : Plateforme de partage et stockage de fichiers en environnement privé
- **ClamAV** : Antivirus réseau utilisé au sein de la DMZ
- **Configuration CRON** pour tâches automatiques et nettoyage
- **Optimisation de l’interface pfSense (Dashboard)** pour une administration rapide

---

## 💡 Compétences développées

- Administration avancée d’un **pare-feu open-source** dans un environnement virtualisé
- Conception et application de **règles de sécurité réseau complexes**
- Mise en œuvre de **mécanismes d’authentification centralisée**
- Déploiement d’**outils de supervision et d’analyse de trafic**
- Utilisation de **services collaboratifs sécurisés** au sein d’une infrastructure cloisonnée

---

## ⚠️ Contraintes rencontrées

- Gestion des priorités de règles dans le pare-feu (ordre d’application)
- Configuration de la redirection HTTPS, nécessitant une bonne maîtrise du NAT
- Blocage d’applications tierces comme AnyDesk, requérant une analyse du trafic et l’identification des plages IP utilisées
- Inspection SSL via proxy, impliquant la génération et la distribution de certificats adaptés

---

## ✅ Résultat obtenu

L’environnement mis en place est **stable, sécurisé, fonctionnel et évolutif**. Il permet :
- Le contrôle des accès internes et externes
- Le **filtrage de contenu web**
- La détection des comportements anormaux
- L’**authentification centralisée** des utilisateurs
- L’intégration fluide de services collaboratifs (GLPI, Nextcloud)

---

## 🔗 Références techniques

- [📘 Documentation officielle pfSense](https://docs.netgate.com/pfsense/en/latest/)
- [🔐 Configuration SquidGuard](https://www.geekdecoder.com/pfsense-squid-squidguard/)
- [🧠 Guide d'utilisation Snort sur pfSense](https://docs.netgate.com/pfsense/en/latest/packages/snort/index.html)

---

## 👨‍💻 Auteur

- **Nathan Gabriele**
- 📧 Contact : [nathangabriele.etudes@gmail.com]

---
