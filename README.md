<div align="center">

# 🌐 Cisco Packet Tracer — VLAN Segmentation (Basic Access Mode)

### Switching & Network Architecture | Cisco Catalyst 2960

![Cisco](https://img.shields.io/badge/Technology-Cisco-049fd9?style=for-the-badge&logo=cisco)
![Packet Tracer](https://img.shields.io/badge/Tool-Packet%20Tracer-1f6feb?style=for-the-badge)
![VLAN](https://img.shields.io/badge/Network-VLAN%2010%20%7C%2020%20%7C%2030-7c3aed?style=for-the-badge)
![Status](https://img.shields.io/badge/Status-Completed-2ea44f?style=for-the-badge)

**A practical Layer 2 switching lab focused on basic VLAN segmentation, access port configuration, and intra/inter-VLAN connectivity testing.**

</div>

---

## 📑 Table of Contents

- [Overview](#-overview)
- [Network Topology](#-network-topology)
- [Addressing & VLAN Schema](#-addressing--vlan-schema)
- [CLI Configurations](#-cli-configurations)
- [Verification & Screenshots](#-verification--screenshots)
- [Repository Structure](#-repository-structure)
- [Key Takeaways](#-key-takeaways)

---

## 📌 Overview

Ce laboratoire pratique présente la configuration et la mise en œuvre des **VLANs de base (Access Mode)** sur des commutateurs Cisco Catalyst 2960 sous **Cisco Packet Tracer**. 

L'objectif principal est de segmenter le réseau local pour isoler le trafic par département (VLAN 10, VLAN 20, VLAN 30) et de valider l'isolation au Niveau 2 (L2) sans routage.

### 🎯 Key Objectives
- **VLAN Database Setup:** Création et nommage des VLANs 10 (Red), 20 (Blue), et 30 (Green).
- **Access Ports:** Affectation des ports des switches en mode accès pour les équipements d'extrémité.
- **CLI Verification:** Validation de la configuration via la commande show vlan brief.
- **Connectivity Testing:** Validation des pings intra-VLAN et vérification de l'isolation inter-VLAN.

---

## 📐 Network Topology

Le réseau est composé de commutateurs Cisco 2960 et de 6 ordinateurs (PCs) répartis dans les différents VLANs.

<div align="center">

![Network Topology](tp%20vlan%20%2Bping%20test.png)

</div>

---

## 🌐 Addressing & VLAN Schema

Toutes les machines appartiennent au sous-réseau 172.17.40.0/24. L'isolement est assuré par la segmentation au niveau 2.

| Device | Interface | VLAN ID | VLAN Name | IP Address | Subnet Mask |
|:---|:---:|:---:|:---:|:---|:---|
| **PC0** | FastEthernet0 | VLAN 10 | Red | 172.17.40.23 | 255.255.255.0 |
| **PC1** | FastEthernet0 | VLAN 20 | Blue | 172.17.40.22 | 255.255.255.0 |
| **PC2** | FastEthernet0 | VLAN 30 | Green | 172.17.40.21 | 255.255.255.0 |
| **PC3** | FastEthernet0 | VLAN 10 | Red | 172.17.40.26 | 255.255.255.0 |
| **PC4** | FastEthernet0 | VLAN 20 | Blue | 172.17.40.25 | 255.255.255.0 |
| **PC5** | FastEthernet0 | VLAN 30 | Green | 172.17.40.24 | 255.255.255.0 |

---

## ⚙️ CLI Configurations

### 1. VLAN Creation & Access Port Assignment (Switch0, Switch1, Switch2)

enable
configure terminal

!--- VLAN Creation
vlan 10
 name Red
vlan 20
 name Blue
vlan 30
 name Green
exit

!--- Access Port Configuration (Example on Switch0)
interface fastEthernet 0/1
 switchport mode access
 switchport access vlan 10
 no shutdown
exit

---

## 🧪 Verification & Screenshots

### 🔍 IOS Commands Verification
- show vlan brief : Permet d'afficher la table des VLANs actifs et de s'assurer que chaque port est correctement assigné.

| Screenshot Reference | Content Description |
|:---|:---|
| **switch0.png** | Output de la commande show vlan brief sur Switch0. |
| **switch1.png** | Output de la commande show vlan brief sur Switch1. |
| **switch2.png** | Output de la commande show vlan brief sur Switch2. |
| **test ping.png** | Résultats détaillés des tests de Ping (Intra-VLAN / Inter-VLAN). |
| **tp vlan +ping test.png** | Vue globale de la topologie Packet Tracer avec validation des pings. |

### ✅ Test Results
- [x] **Intra-VLAN Connectivity:** Le ping entre des machines appartenant au même VLAN (ex: PC2 ➡️ PC5) aboutit avec succès.

---

## 📁 Repository Structure

cisco-vlan-lab/
├── README.md
├── tp vlan.pkt
├── switch0.png
├── switch1.png
├── switch2.png
├── test ping.png
└── tp vlan +ping test.png

---

## 🎓 Key Takeaways

- **Segmentation L2:** Compréhension et mise en pratique de l'isolation des domaines de diffusion par VLAN.
- **Ports d'accès :** Configuration des interfaces des commutateurs pour les terminaux.
- **Sécurité de Base :** Restriction des communications directes entre différents départements sans passer par un routeur.

---

<div align="center">

**Amine EL-marzouqi | Technicien Spécialisé en Systèmes et Réseaux**

*Lab réalisé sous Cisco Packet Tracer.*

</div>
