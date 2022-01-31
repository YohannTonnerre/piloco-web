<center> Projet dev: Piloco </center>
<p> <svg xmlns="http://www.w3.org/2000/svg" width="24" height="24" viewBox="0 0 24 24"><path d="M23 12.452c0 2.539-1.791 5.75-5 6.963v-2.16c3.154-1.83 3.969-6.255 1.553-6.255h-1.553v-2h1.912c2.144 0 3.088 1.534 3.088 3.452zm-5 9.975v1.573h-16v-1.573c.664 0 1-.539 1-1.203v-12.817c-1.181-.569-2-1.754-2-3.15 0-2.257 2.084-3.843 4.238-3.501 1.047-.935 2.502-1.214 3.795-.792.801-.642 1.611-.964 2.582-.964 1.518 0 2.971.765 3.738 1.834 1.848.104 3.32 1.641 3.32 3.515 0 1.341-.567 2.51-1.674 3.104v12.772c.001.663.337 1.202 1.001 1.202zm-11-11.427c0-.552-.447-1-1-1s-1 .448-1 1v8c0 .552.447 1 1 1s1-.448 1-1v-8zm4 0c0-.552-.447-1-1-1s-1 .448-1 1v8c0 .552.447 1 1 1s1-.448 1-1v-8zm4 0c0-.552-.447-1-1-1s-1 .448-1 1v8c0 .552.447 1 1 1s1-.448 1-1v-8zm2.098-5.651c0-1.074-.871-1.944-1.944-1.944-.243 0-.476.045-.689.126-.365-1.134-1.429-1.955-2.685-1.955-1.021 0-1.918.544-2.412 1.359-.41-.365-.95-.586-1.541-.586-.901 0-1.682.515-2.065 1.266-.308-.206-.678-.326-1.076-.326-2.79 0-2.756 3.889 0 3.889.647 0 1.221-.317 1.574-.804.412.379.963.611 1.567.611.706 0 1.337-.315 1.763-.813.517.637 1.306 1.045 2.189 1.045.701 0 1.342-.256 1.836-.679.355.46.912.756 1.538.756 1.074-.001 1.945-.872 1.945-1.945z"/></svg>
 </p>
 
 <p align="center"><a href="https://laravel.com" target="_blank"><img src="https://raw.githubusercontent.com/laravel/art/master/logo-lockup/5%20SVG/2%20CMYK/1%20Full%20Color/laravel-logolockup-cmyk-red.svg" width="400"></a></p>

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
