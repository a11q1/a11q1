<p align="center">
  <a href="https://skin.aq0a11q1.com">
    <img src="https://skin.aq0a11q1.com/api/hero?username=a11q1&theme=blueprint" width="100%" alt="Sacha Fromont — systèmes, réseaux, cybersécurité" />
  </a>
</p>

<p align="center">
  <a href="https://sacha.sitecreator.shop"><img src="https://img.shields.io/badge/Portfolio-sacha.sitecreator.shop-111827?style=flat-square" alt="Portfolio" /></a>
  <a href="https://www.linkedin.com/in/sacha-fromont-9820213a8/"><img src="https://img.shields.io/badge/LinkedIn-Sacha%20Fromont-0A66C2?style=flat-square&logo=linkedin&logoColor=white" alt="LinkedIn" /></a>
  <a href="mailto:sacha.fromont@outlook.fr"><img src="https://img.shields.io/badge/Email-sacha.fromont%40outlook.fr-111827?style=flat-square" alt="Email" /></a>
  <a href="https://skin.aq0a11q1.com"><img src="https://img.shields.io/badge/GitSkin-self--hosted-40e0cf?style=flat-square" alt="GitSkin self-hosted" /></a>
</p>

<p align="center">
  <img src="https://skin.aq0a11q1.com/api/stats?username=a11q1&theme=blueprint&v=2" width="86%" alt="Statistiques GitHub de a11q1" />
  <br />
  <img src="https://skin.aq0a11q1.com/api/stack?username=a11q1&theme=blueprint&v=2" width="86%" alt="Stack technique de a11q1" />
</p>

<p align="center">
  <sub>Cartes générées par mon service <a href="https://skin.aq0a11q1.com">GitSkin self-hosted</a> · <a href="https://github.com/a11q1/gitskin">code source</a></sub>
</p>

---

Je construis des infrastructures et des outils qui tournent vraiment : un homelab Proxmox 24/7, des sites pour des artisans et des agents IA qui opèrent une agence. Pas des maquettes : des services en ligne, monitorés, sauvegardés et documentés.

**~30 LXC/VM · 5 sites JO 2024 · 0 interruption · 24/7**

## 01 · Études

| Formation | Établissement | Période |
|---|---|---|
| **BTS SIO option SISR** | Lycée Le Rebours, Paris | 2025–2027 |
| **Bac pro Systèmes numériques** | Passy Buzenval, Rueil-Malmaison | 2021–2024 |
| **Brevet mention Bien** | Collège Jean Macé, Suresnes | 2021 |
| **Certifications** | Cisco et ISC2 CC en préparation | 2026–2027 |

Mon fil rouge : comprendre comment les machines, les réseaux et les services s'emboîtent, puis les faire tenir ensemble. Le BTS SIO SISR me donne le cadre ; le homelab, l'entreprise et les stages me donnent le terrain.

**Langues** : français natif · anglais intermédiaire avancé (deux stages 100 % en anglais) · espagnol débutant.

## 02 · Entreprise

**Fondateur de [sitecreator.shop](https://sitecreator.shop)** — studio web indépendant pour restaurants, artisans et commerces locaux.

Je gère la chaîne complète : prospection, audit, maquette, design, développement, mise en ligne, SEO local, support. Sites vitrines, réservation et devis, livrés en 7 jours, maquette en 48 h. Tout est hébergé et supervisé sur mon infrastructure.

C'est le meilleur accélérateur que je connaisse : il faut comprendre le métier du client, cadrer le projet, livrer vite, puis assumer le support et la maintenance. Et ça oblige à faire de l'infra propre, parce que le site ne peut pas tomber.

## 03 · IA & agents

Je n'utilise pas l'IA comme un chatbot. Je la traite comme une **équipe d'agents avec des rôles, des outils et une mémoire partagée**.

- **Agents spécialisés** : planner, code, QA, cybersécurité, vente, support client. Chacun a son prompt, ses permissions et son canal Discord.
- **Mémoire commune** : vault Obsidian + SQLite, rapports archivés, contexte partagé entre agents.
- **Infra** : gateway Discord, proxy LLM, RAG maison, automatisations n8n, agents vocaux.
- **Développement** : Claude, OpenAI, OpenCode, MCP. L'IA m'aide à spécifier, coder, tester, déployer et monitorer, mais je garde la main sur la vérification.
- **Local-first** : [PAIR Universal](https://github.com/a11q1/pair-universal), fork communautaire de NVIDIA PAIR, pour router l'inférence locale sur GPU NVIDIA, AMD, Intel ou Apple Silicon.

En pratique : un objectif arrive dans Discord. Le planner découpe, l'agent code implémente, le QA teste, le cyber vérifie les secrets et les expositions. Je valide, je déploie, et le rapport atterrit dans le vault.

Ma règle : **l'IA propose, je vérifie**. Secrets hors du contexte, actions destructives jamais automatiques, et tout ce qui tourne est monitoré.

## 04 · Homelab

**Dell PowerEdge R630** · 2× Intel Xeon E5-2640 v4 · 256 GB DDR4 ECC · Proxmox VE 9.x · ~30 LXC/VM.

Un mini-datacenter dans une pièce, qui héberge l'agence, les clients, les agents, le monitoring et le lab cyber.

<p align="center">
  <img src="https://skin.aq0a11q1.com/api/arch?theme=blueprint" width="100%" alt="Architecture du homelab : Proxmox, pfSense, Tailscale et Cloudflare" />
</p>

Ce que j'y apprends : un service = un conteneur, une zone = un bridge/VLAN, les secrets ne vont jamais dans Git, et une sauvegarde qui n'a pas été restaurée n'est pas une sauvegarde.

## 05 · Réseau & sécurité

- **pfSense** : segmentation VLAN, DMZ, NAT, DHCP/DNS, règles inter-zones en deny-by-default. Projet E6 : trois zones (DMZ / INTERNE / BDD), WAF nginx + ModSecurity + OWASP CRS, portail Symfony + MariaDB.
- **Tailscale** : mesh WireGuard pour administrer le lab et les services internes sans publier les ports d'administration en clair sur Internet. Accès par appareil, groupes et règles ACL.
- **Cloudflare** : DNS, tunnels, Access, WAF et cache devant les services publics.
- **Durcissement** : SSH par clé ed25519, fail2ban, nftables, comptes nominatifs, mises à jour, réduction de la surface d'attaque.
- **Honeypots** : OpenCanary, plus un prototype de déploiement automatique de honeypots isolés en VLAN via l'API Proxmox + pfSense, avec alertes Discord.
- **Supervision** : Prometheus, Grafana, Loki, Alertmanager, blackbox exporter, alertes Discord.

Je ne publie ni IP, ni secrets, ni données clients. Les détails restent dans le privé.

## 06 · Projets publics

| Projet | Description | Stack |
|---|---|---|
| **[gitskin](https://github.com/a11q1/gitskin)** | Cartes SVG self-hosted pour profil GitHub : hero, architecture, stats et stack | Node.js · Docker · Cloudflare Tunnel |
| **[pair-universal](https://github.com/a11q1/pair-universal)** | Fork communautaire de NVIDIA Personal AI Router : routage d'inférence local sur GPU NVIDIA, AMD, Intel et Apple Silicon | Go · Electron · React |
| **[lab-grafana-prometheus](https://github.com/a11q1/lab-grafana-prometheus)** | Stack de supervision complète : métriques, logs, dashboards et alerting | Docker · Prometheus · Grafana · Loki |
| **[pfsense-honeypot-factory](https://github.com/a11q1/pfsense-honeypot-factory)** | Prototype de déploiement de honeypots isolés en VLAN via l'API Proxmox et pfSense | Bash · Proxmox API · pfSense |

Le reste (agents, CRM, infra, sites clients) est privé. C'est normal : il y a des données clients et des secrets dedans.

### Le GitSkin self-hosted

Les cartes en haut de ce README sont générées par un petit service Node.js que j'héberge sur mon homelab : zéro dépendance, zéro SaaS, des endpoints SVG branchés sur l'API GitHub publique.

- Instance : [skin.aq0a11q1.com](https://skin.aq0a11q1.com)
- Code : [a11q1/gitskin](https://github.com/a11q1/gitskin)
- Endpoints : `/api/hero`, `/api/arch`, `/api/stats`, `/api/stack`, `/api/status` — thèmes `blueprint`, `cyber`, `aurora`, `light`

## 07 · Stack

```text
Systèmes    Linux · Debian · Windows · Proxmox VE · Active Directory · systemd
Réseau      pfSense · VLAN · DMZ · Tailscale · Cloudflare · Cisco · WAF
Dev         Python · Bash · Go · JavaScript · React · Next.js · SQLite
Ops         Docker · Prometheus · Grafana · Loki · Alertmanager · n8n
IA          Claude · OpenAI · OpenCode · MCP · RAG · agents · PAIR
```

## 08 · Parcours terrain

| Période | Expérience | Ce que j'y ai fait |
|---|---|---|
| 04–06/2026 | **ITGS, Dublin** — stage Erasmus | Infogérance MSP 24/7, Microsoft 365, Power Automate, audit réseau et RGPD, 100 % en anglais |
| 06–07/2024 | **Paris WebCube** — JO 2024 & Euro | Câblage, brassage, Wi-Fi, Starlink, support terrain sur 5 sites, 0 interruption |
| 11–12/2024 | **Infomax, Paris** — maintenance & SAV | Montage PC, Windows/Linux, gestion du stock, service après-vente |
| 01–02/2024 | **Strand Electronics, Malte** — sécurité | Installation et maintenance de vidéosurveillance, 100 % en anglais |
| 01–02/2023 · 06/2023 | **Cholet & Massard** — élec/CVC | Switches Cisco, disjoncteurs, chauffage, ventilation, climatisation |

## 09 · Ce que je cherche

- **Alternance technicien systèmes & réseaux** — Paris / Île-de-France — à partir de 2027
- **Stage technicien datacenter** — 4 janvier au 5 février 2027

Si tu recrutes, si tu veux échanger sur l'infra, les agents ou la cyber : [LinkedIn](https://www.linkedin.com/in/sacha-fromont-9820213a8/) ou [email](mailto:sacha.fromont@outlook.fr). Je réponds vite.

---

<p align="center">
  <img src="https://skin.aq0a11q1.com/api/status?theme=blueprint" width="100%" alt="GitSkin self-hosted — statut du service" />
</p>

<div align="center">

**Ce qui n'est pas monitoré, sauvegardé et documenté n'existe pas.**

</div>
