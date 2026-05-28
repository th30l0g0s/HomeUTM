# 🔥 HomeUTM

![Status](https://img.shields.io/badge/status-en%20développement-yellow)
![Licence](https://img.shields.io/badge/licence-MIT-blue)
![Version](https://img.shields.io/badge/version-0.1.0-orange)
![Plateforme](https://img.shields.io/badge/plateforme-Linux-lightgrey)
![Contributions](https://img.shields.io/badge/contributions-bienvenues-brightgreen)

> Pare-feu UTM (Unified Threat Management) conçu pour un intranet familial. Projet personnel d'apprentissage couvrant le filtrage réseau, la détection d'intrusion, le contrôle parental et la supervision du trafic domestique.

---

## 📋 Table des matières

- [Aperçu](#-aperçu)
- [Fonctionnalités](#-fonctionnalités)
- [Architecture](#-architecture)
- [Prérequis](#-prérequis)
- [Installation](#-installation)
- [Configuration](#-configuration)
- [Usage](#-usage)
- [Captures d'écran](#-captures-décran)
- [API / Interface d'administration](#-api--interface-dadministration)
- [Roadmap](#-roadmap)
- [Contribuer](#-contribuer)
- [Licence](#-licence)

---

## 🔍 Aperçu

**HomeUTM** est un pare-feu UTM maison destiné à protéger un réseau intranet familial. Il centralise plusieurs couches de sécurité réseau en un seul point de contrôle : filtrage de paquets, inspection de contenu, détection d'intrusion (IDS/IPS), DNS sécurisé et supervision en temps réel.

Ce projet est avant tout un terrain d'apprentissage sur la sécurité réseau, Linux, et les outils open source associés.

---

## ✨ Fonctionnalités

- **Filtrage de paquets** — Règles entrantes/sortantes par IP, port, protocole
- **IDS/IPS** — Détection et prévention d'intrusions (ex : Suricata / Snort)
- **Filtrage DNS** — Blocage de domaines malveillants et publicitaires (ex : Pi-hole)
- **Contrôle parental** — Plages horaires et catégories de sites par appareil
- **VPN** — Accès sécurisé au réseau familial depuis l'extérieur
- **Dashboard de supervision** — Visualisation du trafic, alertes, logs en temps réel
- **Mises à jour des règles** — Synchronisation automatique des listes de menaces

---

## 🏗 Architecture

```
Internet
   │
[Modem FAI]
   │
[HomeUTM] ◄─── Ce dépôt
   │
   ├── [Switch]
   │      ├── PC / Laptops
   │      ├── Smart TV / IoT
   │      └── NAS
   │
   └── [WiFi AP]
          ├── Smartphones
          └── Tablettes
```

> **Note :** L'architecture exacte sera mise à jour selon le matériel utilisé (Raspberry Pi, mini-PC, VM...).

---

## 📦 Prérequis

> ⚠️ *Section à compléter selon le langage et les outils retenus.*

- OS : Linux (Debian / Ubuntu recommandé)
- RAM : 2 Go minimum (4 Go recommandés)
- 2 interfaces réseau (WAN + LAN)
- `[outil 1]`, `[outil 2]`, `[outil 3]` — à préciser

---

## 🚀 Installation

```bash
# Cloner le dépôt
git clone https://github.com/TON_UTILISATEUR/home-utm.git
cd home-utm

# [Étapes d'installation à compléter]
# Exemple :
# cp config/example.conf config/local.conf
# ./install.sh
```

> ⚠️ *Les instructions détaillées seront ajoutées dès que la stack technique sera fixée.*

---

## ⚙️ Configuration

Le fichier de configuration principal est `config/local.conf` (exemple fourni dans `config/example.conf`).

| Paramètre         | Description                        | Valeur par défaut |
|-------------------|------------------------------------|-------------------|
| `LAN_INTERFACE`   | Interface réseau côté LAN          | `eth1`            |
| `WAN_INTERFACE`   | Interface réseau côté WAN/Internet | `eth0`            |
| `DNS_UPSTREAM`    | Serveur DNS upstream               | `1.1.1.1`         |
| `ADMIN_PORT`      | Port du dashboard d'administration | `8080`            |
| `LOG_LEVEL`       | Niveau de verbosité des logs       | `info`            |

---

## 🖥 Usage

```bash
# Démarrer HomeUTM
./homeutm start

# Afficher le statut
./homeutm status

# Recharger les règles sans interruption
./homeutil reload

# Consulter les logs en temps réel
./homeutils logs --follow

# Arrêter
./homeutil stop
```

---

## 📸 Captures d'écran

> 🖼️ *Des captures du dashboard et de l'interface d'administration seront ajoutées ici.*

| Dashboard principal | Logs en temps réel | Gestion des règles |
|---------------------|--------------------|--------------------|
| *(à venir)*         | *(à venir)*        | *(à venir)*        |

---

## 🔌 API / Interface d'administration

> ⚠️ *La documentation de l'API sera générée automatiquement (ex : Swagger/OpenAPI) une fois l'interface implémentée.*

### Endpoints prévus

| Méthode | Endpoint              | Description                        |
|---------|-----------------------|------------------------------------|
| `GET`   | `/api/status`         | État général du pare-feu           |
| `GET`   | `/api/logs`           | Récupérer les derniers logs        |
| `GET`   | `/api/rules`          | Lister les règles actives          |
| `POST`  | `/api/rules`          | Ajouter une règle                  |
| `DELETE`| `/api/rules/{id}`     | Supprimer une règle                |
| `GET`   | `/api/traffic`        | Statistiques de trafic en temps réel |
| `POST`  | `/api/dns/blocklist`  | Ajouter un domaine à la blocklist  |

Authentification : `Bearer Token` (JWT) — *à implémenter*

---

## 🗺 Roadmap

### Phase 1 — Fondations *(en cours)*
- [ ] Choix de la stack technique et du matériel
- [ ] Filtrage de paquets basique (iptables / nftables)
- [ ] DNS sécurisé avec blocklist (Pi-hole ou équivalent)
- [ ] Logging centralisé

### Phase 2 — Sécurité avancée
- [ ] Intégration IDS/IPS (Suricata)
- [ ] Mise à jour automatique des règles de menaces
- [ ] Détection d'anomalies de trafic

### Phase 3 — Interface utilisateur
- [ ] Dashboard web de supervision
- [ ] API REST d'administration
- [ ] Alertes par notification (email / Telegram)

### Phase 4 — Fonctionnalités avancées
- [ ] VPN (WireGuard)
- [ ] Contrôle parental par appareil
- [ ] Profils réseau (invité, IoT, principal)
- [ ] Sauvegarde / restauration de configuration

---

## 🤝 Contribuer

Les contributions sont les bienvenues, même pour un projet perso ! Si tu as des idées, des retours ou des corrections :

1. Fork le projet
2. Crée une branche (`git checkout -b feature/ma-fonctionnalite`)
3. Commit tes changements (`git commit -m 'feat: ajout de X'`)
4. Push la branche (`git push origin feature/ma-fonctionnalite`)
5. Ouvre une Pull Request

---

## 📄 Licence

Distribué sous licence **MIT**. Voir le fichier [LICENSE](LICENSE) pour plus de détails.

---

*Fait avec ❤️ pour apprendre la sécurité réseau — et protéger l'intranet familial.*
