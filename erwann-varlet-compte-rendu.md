# Compte-rendu personnel — Challenge 48h Ynov Toulouse 2026

**Erwann VARLET**  
Bachelor 3 — Développement Informatique

---

## Présentation du projet

Le projet BabyConnect a pour but de moderniser l'expérience babyfoot à Ynov Toulouse. L'idée c'est de digitaliser les
tables du Souk pour permettre aux étudiants de réserver des créneaux, suivre leurs stats, leur classement ELO, et
participer à des tournois. Le tout accessible via une API centrale utilisée par les différentes parties du projet.

Le contexte c'est un challenge de 48h, donc les choix techniques devaient être pragmatiques et permettre d'avancer vite
tout en gardant quelque chose de solide.

---

## Mon rôle dans le projet

Je me suis occupé du backend. Concrètement j'ai :

- Migré toute l'API vers **TypeScript / Express** pour s'aligner avec le reste de l'équipe
- Intégré **Prisma** comme ORM de zéro, avec la définition complète du schéma (modèles Player, Match, Table,
  Reservation, Tournament, TournamentParticipant)
- Géré la validation des inputs avec **Zod**
- Écrit le **Dockerfile** multi-stage pour la mise en prod

---

## Difficultés rencontrées

Les principales galères étaient autour de **Prisma et Docker** :

- Des dépendances mal placées en `devDependencies` au lieu de `dependencies`, ce qui faisait planter le build Docker en
  prod puisque les devDeps ne sont pas installées dans le stage final
- Le déploiement des migrations Prisma au moment du build Docker — il a fallu comprendre la différence entre
  `prisma db push` (dev) et `prisma migrate deploy` (prod), et adapter le `CMD` du Dockerfile pour lancer les migrations
  avant de démarrer le serveur
- La config PostgreSQL avec les droits utilisateur au début, les privilèges n'étaient pas correctement attribués

---

## Aide apportée à l'équipe

Même si mon rôle principal était le backend, j'ai aussi aidé mes coéquipiers sur la **gestion des merges Git**. Je
vérifiait que les PR se mergaient proprement sans conflits, je relisais rapidement ce qui avait été produit et je
testais que ça fonctionnait correctement avant de valider. Ca permettait de garder une branche principale stable tout au
long du challenge.

---

## Difficultés / Facilités

**Difficultés :** La migration Go → TypeScript en cours de route prend du temps même avec de l'aide. Prisma en prod avec
Docker m'a pris plus de temps que prévu à cause des dépendances et des migrations. Les 48h c'est vraiment court pour
faire quelque chose de propre.

**Facilités :** Le fait de maîtriser TypeScript et d'avoir déjà travaillé avec Prisma (technoligies utilisées dans un
autre projet similaire) m'a aidé à aller vite sur la structure et la logique métier.


