<h1 align="center"> Projet dev: Piloco </h1>

## Fonctionnement

Le principe du jeu est de faire ou répondre à une question ou une action proposé par le jeu. L'echec entrainera des gorgés.

## Contenu

L'Api est en Laravel, elle permet à un utlisateur de:

- créer un utilisateur
- modifier un utilisateur
- se connecter 
- déconnecter
- créer une partie
- créer ses questions

Le super Admin peut:

- CRUD des modes de jeu
- CRUD des questions


### Utilisateur

- nom d'utilisateur
- date de naissance (majeur)
- email
- mot de passe

## Questions
- Mode
- Text
- Gorgée

### Mode de jeu
Pour les admins :
- name
- description

Plusieurs modes avec un dégré de question différent:
- Découverte : Pour ceux qui souhaitent commencer la soirée en beauté.
- Avancé : Pour ceux ou la soirée est déjà dans un stage avancé !
- Ivrogne (9,99€) : Uniquement pour la team Piloco, de vrai Ivrogne ceux la.

## Techno

API, VueJS,Laravel

## Difficulté technique

- Faire Admin, et superAdmin
- Faire apparaître les questions en mode aléatoires sans les répéter
- Définir un ordre aléatoire de joueur
- Malus aléatoire

- Le jeu sera jouable depuis plusieurs postes connectés entre eux. (web socket, serveur)
- Faire un chat

Add

- Faire vocal
- Faire visio
