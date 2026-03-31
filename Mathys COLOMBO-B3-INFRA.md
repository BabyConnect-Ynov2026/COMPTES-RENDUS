Compte rendu - Mathys COLOMBO - B3 INFRA
Ce compte rendu présente les étapes de développement du projet Challenge 48h, réalisé dans le cadre de la formation B3 INFRA à Ynov.

Sommaire



## Présentation du projet

Notre projet c'est BabyFoot Arena. On voulait connecter les babyfoots du Souk pour que les étudiants puissent savoir en temps réel si un baby est libre, garder un historique de leurs matchs, et avoir un classement entre eux. En gros on fixe un ESP32 avec des capteurs sur le baby pour détecter les buts automatiquement, et y'a une app web sur téléphone pour tout gérer (réservation, score, tournois). On a aussi une caméra avec de l'IA pour vérifier les buts. De mon côté en tant qu'infra, le projet c'était surtout de faire en sorte que tout ça tourne sur un Raspberry Pi accessible à tout le monde sur le WiFi du campus.


## Mon rôle dans le projet

J'étais sur la partie infra et monitoring avec Guillaume Concrètement j'ai fait :

La mise en place du Raspberry Pi : installation de l'OS, connexion au réseau, configuration SSH pour que tout le monde puisse y accéder
Le script d'installation automatique (install.sh) pour que si on doit tout refaire sur un autre Pi ça prend 5 minutes
L'aide aux devs quand ils avaient des problèmes de déploiement
J'étais aussi porte-parole de l'équipe et responsable des commandes sur le shop. Quand on avait besoin de matos on en parlait ensemble, et c'est moi qui validais et passais les commandes avec les justifications. 
J'ai aussi dresser la liste des tâches qu'on aurait effectuer si on avait les IOT avec nous avec le matériel nécessaire et la doc.

## Aides

J'ai beaucoup échangé avec l'équipe dev Suffix pour comprendre comment leur code devait être déployé. Ils m'ont expliqué comment le backend était structuré pour que nous puissions configurer le Docker correctement.
Corentin et Julien de mon équipe m'ont filé un coup de main sur la config réseau du Pi, on a galéré ensemble à trouver l'IP du Pi sur le réseau du campus. Guillaume s'est occupé de Nginx avec moi.
Pour le script d'installation j'ai dû me replonger dans du Bash, ça faisait un moment que j'en avais pas écrit et j'avais un peu oublié la syntaxe des conditions et des boucles.


## Contexte du bac à sable

C'est la première fois que je faisais tourner un vrai projet sur un Raspberry Pi avec Docker. En cours on fait des TPs mais c'est toujours sur des VMs ou en local, là c'était un vrai serveur physique avec de vrais utilisateurs qui se connectent dessus. Ça change pas mal de choses, genre la gestion de la mémoire le Pi a que 4 ou 8 Go de RAM et le fait que si le Pi plante personne ne peut rien y changer.
Le fait d'avoir les deux équipes (dev + infra/IA) qui bossent sur le même projet m'a forcé à comprendre ce que les devs faisaient, pas juste configurer un serveur dans mon coin. J'ai appris des trucs sur Node.js et React que j'aurais jamais regardé sinon.

## IA

J'ai utilisé Claude pendant le challenge. Principalement pour générer les fichiers de configuration Docker et Nginx, que nous avons ensuite adaptés à notre projet
Rédiger la documentation technique du projet (le guide infra et le guide Raspberry Pi de A à Z)
Débugger des problèmes de réseau surtout ça
Concrètement j'ai pas copié collé sans réfléchir, j'ai utilisé Claude comme un assistant pour aller plus vite sur des trucs que j'aurais mis des heures à faire seul surtout la doc, les configs et le script d'installation. Par contre tout ce qui est mise en place réelle sur le Pi que ce soit SSH, installation, debug réseau c'était moi directement dans le terminal avec Guillaume.



## Shop

On a commandé pas mal de trucs sur le shop :

2 Raspberry Pi (100 crédits) : un pour le serveur mais comme la carte sd fonctionnait pas nous en avons repris un. 
3 Badges RFID (15 crédits) : pour que les joueurs puissent scanner les babyfoots pour les réserver ou autres.
2 Balles de babyfoot (130 crédits) : pour la démo
40 Haribo (80 crédits) : pour le moral des sous-équipes
1 Carnet (40 crédits) : pour la démo
1 Paire de chaussette (125 crédits) : pour avoir ce sentiment de récompenses
1 Stylo (50 crédits) : pour écrire dans le carnet
1 Investissement sur le Bitcoin : pour la curiosité


## Difficultés / Facilités

Difficultés :

La première difficulté c'etait le faite que la carte sd ne voulait pas prendre l'os malgré qu'on changeait d'ordinateur, de logiciel elle ne voulait pas coopérer du coup nous avons longtemps chercher et au final nous avons recommander un raspberry et cette fois ci ça a marché directement donc au final c'etait la carte le problème ou l'adaptateur. Ensuite trouver l'IP du Raspberry Pi sur le réseau du campus, on a galéré un bon moment parce qu'on était pas passé par Raspberry Pi Imager et le Pi était pas configuré pour le réseau. mais ça c'etait avec la premiere carte donc au final ça a été. Et pour finir coordonner le travail entre les deux sous-équipes, des fois les devs pushaient du code qui marchait pas dans Docker parce qu'ils testaient en local

Facilités :

Docker Compose une fois configuré c'est facile d'utilisation, un docker compose up -d et tout tourne
Le SSH sur le Pi, une fois connecté c'est comme un terminal Linux normal, rien de compliqué


## Investissements personnels

Je suis resté tard pour préparer toute la documentation infra en avance pour que l'équipe puisse suivre le guide sans dépendre de moi. J'ai aussi fait le guide Raspberry Pi de A à Z pour que n'importe qui dans l'équipe puisse refaire l'installation si besoin. J'ai essayé d'être disponible pour les deux équipes quand ils avaient des soucis de déploiement car je prenais mon rôle de porte parole à coeur. J'aidais aussi Dylan pour la carte nfc parce que vu que la carte est trop ancienne les Iphone n'arrivait pas à la scanner et ça avec les devs on a mis du temps a le comprendre. 

## Retours personnels

Le format 48h c'est intense mais c'est cool. Ça force à aller à l'essentiel et à pas passer 3 semaines à réfléchir avant de coder ou de se décider sur la méthode que nous allons utiliser. Par contre 14 personnes sur un même projet c'est le bazar au début enfin pour nous en infra ça allait mais les devs au début c'était pas évident et au final ça a été. Le système de shop avec les crédits c'est une bonne idée franchement j'ai bien aimé, ça rajoute une dimension de gestion de ressources au projet.