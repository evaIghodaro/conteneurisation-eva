# TP3 - Conteneurisation

## Objectif

Ce projet contient la version conteneurisée du TP3 avec une application Node.js, une base de données PostgreSQL, un frontend statique et Adminer.

## Structure du projet

- `api/` : backend Node.js qui expose une API REST pour gérer des messages.
- `frontend/` : frontend statique servi par Nginx pour afficher et envoyer des messages.
- `docker-compose.yml` : orchestration de la stack multi-services.
- `RAPPORT-TP3.md` : rapport du TP3.

## Services

- `database` : PostgreSQL 15 Alpine.
- `api` : application Node.js qui se connecte à PostgreSQL.
- `frontend` : site statique en Nginx.
- `adminer` : interface d'administration de la base de données.

## Prérequis

- Docker
- Docker Compose

## Démarrage

1. Créer un fichier `.env` à la racine du projet avec :

```env
DB_USER=tp3user
DB_PASSWORD=motdepasse
DB_NAME=tp3db
```

2. Lancer la stack :

```bash
docker compose up --build
```

3. Accéder aux services :

- Frontend : http://localhost:8080
- API : http://localhost:3000
- Adminer : http://localhost:8081

## Notes

- Le backend utilise les variables d'environnement pour se connecter à PostgreSQL.
- Adminer se connecte à la base via le service `database`.
- Les données PostgreSQL sont persistées dans le volume Docker `pg_data`.

## Rapport

Voir `RAPPORT-TP3.md` pour le détail du travail et des choix techniques.
