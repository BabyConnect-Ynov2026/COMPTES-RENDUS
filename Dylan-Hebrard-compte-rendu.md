# Compte-rendu — Dylan Hebrard — B3 Informatique  

**Challenge 48h Ynov Toulouse 2026 — Babyfoot du futur**

## Présentation du projet

BabyConnect est une plateforme web visant à digitaliser l’expérience du babyfoot à Ynov Toulouse. L’objectif est de permettre la gestion des matchs, des réservations ainsi que la mise en place d’un classement des joueurs, là où il n’existait auparavant aucun système de suivi.

L’objectif principal du projet était de poser des bases techniques solides et de démontrer la faisabilité du concept dans un temps limité.

## Mon rôle dans le projet

Mon rôle principal consistait à connecter le site web à un système de lecture de cartes NFC achetées en boutique, afin de simplifier le processus de réservation.

Le principe était le suivant : lors de la réservation d’une table, une carte NFC est scannée. Celle-ci est ensuite automatiquement associée à la réservation et liée à la base de données, permettant ainsi d’identifier la table correspondante.

## Aides

### Aide apportée

L’équipe de développement étant relativement nombreuse et manquant de direction au départ, j’ai pris l’initiative de proposer une répartition des tâches afin de structurer le travail. Cela a permis à chacun de contribuer efficacement et d’apporter sa vision au projet.

Personne ne prenant réellement les devants au début, j’ai progressivement assumé un rôle de coordination et d’organisation au sein du groupe.

### Aide reçue

- J’ai reçu à plusieurs reprises l’aide d’Erwan pour le débogage du backend, notamment sur l’utilisation de Prisma avec la base de données, qui présentait régulièrement des erreurs.
- Lors de changements techniques importants, l’équipe s’est concertée à plusieurs reprises afin de prendre des décisions collectives, comme le passage du langage Go à TypeScript.

## Contexte du bac à sable

Ce projet m’a permis de progresser dans l’utilisation d’éléments externes au code, notamment les cartes NFC, ce qui constituait une première pour moi. Étant donné que je souhaite m’orienter vers l’IoT, cette expérience m’a rapproché de l’utilisation concrète d’objets connectés.

Par ailleurs, lors de la désignation des porte-parole, je n’étais pas particulièrement à l’aise à l’idée d’occuper ce rôle. Cependant, face à un manque d’organisation général en début de projet, j’ai décidé de prendre des initiatives. Cela m’a permis de dépasser ma timidité et de contribuer activement à la structuration du travail.

## Utilisation de l’IA

J’ai utilisé l’intelligence artificielle dans deux contextes principaux.

Tout d’abord, pour me renseigner sur le fonctionnement du NFC et ses contraintes techniques, ce qui m’a permis d’acquérir de nouvelles connaissances dans ce domaine.

Ensuite, j’ai utilisé ChatGPT pour effectuer des tests en local du système de scan. En effet, j’ai travaillé avec une version locale sur téléphone connecté au PC, car le NFC ne fonctionnait pas en local pour des raisons de sécurité. L’IA m’a également aidé à corriger certaines erreurs et à améliorer le fonctionnement du système.

## Difficultés et facilités

Plusieurs difficultés ont été rencontrées durant ces deux jours.

Tout d’abord, le passage de Go à TypeScript a entraîné de nombreuses complications, tant côté backend que frontend, ce qui a ralenti l’avancement du projet.

Ensuite, la base de données avec Prisma n’a commencé à fonctionner correctement qu’au début de l’après-midi du deuxième jour, retardant ainsi certaines fonctionnalités.

Enfin, le principal problème concernait le NFC. Les cartes fournies lors du challenge étaient relativement anciennes et parfois incompatibles avec certains systèmes, notamment iOS. De plus, le navigateur Safari limite fortement l’utilisation du NFC. Une solution aurait été d’utiliser un navigateur compatible comme Chrome sur iPhone ou de développer directement une application mobile, sous réserve de compatibilité matérielle.

## Investissement personnel

Dans ce projet, ma contribution en code a été limitée, notamment en raison des contraintes liées à la mise en place du NFC, dont les dépendances n’ont été disponibles que tardivement.

Cependant, je me suis investi autrement en apportant du soutien à l’équipe, en proposant une organisation de travail et en relisant le code afin de corriger et améliorer certains éléments lorsque cela était possible.