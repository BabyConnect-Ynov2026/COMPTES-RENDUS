# Compte-rendu — Nicolas Gouy — B3 IADATA

**Challenge 48h Ynov Toulouse 2026 — Babyfoot du futur**

---

## Ma contribution

J'ai travaillé sur deux axes principaux durant ce challenge : l'architecture globale du projet BabyConnect et le module d'arbitrage IA **ynov-baby-vision**.

### Ce que j'ai fait

- **Architecture du projet** : choix de la stack initiale, mise en place de la structure des dossiers, Docker Compose, pipeline CI/CD GitHub Actions
- **Backend API REST (Go/Gin/GORM)** :
  - Modèles : Player, Match, Table, Reservation, Tournament
  - Controllers : joueurs, matchs, réservations, tournois, leaderboard
  - Système de classement ELO
  - Vérification des conflits de réservations
  - Seeding automatique des tables de babyfoot
- **ynov-baby-vision** (module IA) :
  - Script Python avec YOLOv8 pour détecter la balle en temps réel via caméra
  - `GoalDetector` : détection de franchissement de ligne de but par intersection de segments, avec cooldown anti-double-détection
  - `ApiClient` : envoi automatique des scores et fin de match à l'API BabyConnect
  - Configuration flexible via `.env` (lignes de but en pixels, seuil de confiance, source caméra)
- **Organisation GitHub** : création de l'organisation BabyConnect-Ynov2026, mise en place des repos (babyconnect, DOCUMENTATION, COMPTES-RENDUS, ynov-baby-vision)
- **Documentation** : architecture, API REST, guide d'installation, guide utilisateur

---

## Difficultés rencontrées

- **Coordination inter-équipes** : l'équipe backend a migré de Go vers TypeScript/Express/Prisma en cours de route. Il a fallu s'adapter rapidement et aligner les interfaces API pour que ynov-baby-vision reste compatible.
- **Calibration des lignes de but** : les coordonnées de but en pixels dépendent du placement exact de la caméra, ce qui nécessite une phase de calibration manuelle pour chaque installation.

---

## Ce que j'ai appris

- **YOLOv8 / OpenCV** : première fois que j'utilisais un modèle de détection d'objets en temps réel. La simplicité de l'API `ultralytics` m'a surpris.
- **Intersection de segments** (produit vectoriel) pour détecter le franchissement d'une ligne — application concrète de géométrie dans un vrai projet.
- **Git en équipe** : gérer plusieurs dépôts dans une organisation, synchroniser avec `git pull --rebase` quand des conflits apparaissent.
- **Docker multi-services** : bien comprendre les dépendances entre services (healthcheck sur la DB avant de démarrer le backend).

---

## Bilan

Ce challenge m'a permis de toucher à beaucoup de choses en très peu de temps : de la vision par ordinateur à l'API REST en passant par le DevOps. La contrainte des 48h force à faire des choix pragmatiques, à avoir de bonnes idées, faire de son mieux pour les réaliser, et avoir une approche collaborative.

Le module ynov-baby-vision est le module sur lequel j'ai le plus travaillé, il est encore assez basique (détection de la balle + ligne de but), mais il pose les bases pour des fonctionnalités plus avancées (détection de joueurs, analyse de tactiques, etc).
