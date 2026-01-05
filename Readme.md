# 🖥️ Supervision Cloud AWS avec Zabbix

## 📌 Présentation du projet
Ce projet consiste à mettre en place une **infrastructure cloud de supervision centralisée** sous **Amazon Web Services (AWS)** à l’aide de l’outil de supervision **Zabbix**.

La solution permet de superviser plusieurs machines **Linux** et **Windows** à partir d’un serveur centralisé, en collectant et visualisant des métriques système essentielles telles que :
- l’utilisation du CPU,
- la mémoire,
- l’espace disque,
- la disponibilité des hôtes.

Le serveur Zabbix est déployé à l’aide de **Docker** et **Docker Compose**, avec une base de données **MariaDB**.

---

## 🎯 Objectifs du projet
- Déployer une solution de supervision centralisée dans le cloud
- Superviser des hôtes Linux et Windows
- Utiliser les **adresses IP privées** pour la communication interne
- Visualiser les données via graphiques et dashboards
- Détecter automatiquement les incidents et pannes

---

## 🏗️ Architecture de la solution
L’architecture mise en place repose sur les composants suivants :
- Un **VPC AWS**
- Une instance **EC2 Linux** hébergeant :
  - Zabbix Server (Docker)
  - Zabbix Web (Docker)
  - MariaDB (Docker)
- Une instance **Client Linux** avec Zabbix Agent
- Une instance **Client Windows** avec Zabbix Agent

Les communications entre le serveur et les clients s’effectuent exclusivement via des **IP privées**, conformément aux bonnes pratiques de sécurité dans le cloud.

> 📄 Les schémas et diagrammes d’architecture sont détaillés dans le rapport PDF joint au projet.

---

## ⚙️ Technologies utilisées
- Amazon Web Services (AWS EC2, VPC)
- Docker & Docker Compose
- Zabbix 6.4
- MariaDB
- Linux (Ubuntu)
- Windows Server

---

## 🛠️ Déploiement et configuration
Le déploiement du serveur Zabbix est réalisé à l’aide du fichier suivant :

```text
docker-compose-zabbix-aws.yml
