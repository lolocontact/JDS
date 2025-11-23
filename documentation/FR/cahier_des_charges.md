# Cahier des charges fonctionnelles - JDS

Rédacteurs :
 - Donatien Hochart / [rekkylaws](https://github.com/rekky1aws/)
 - Loïc Petitprez / [lolocontact](https://github.com/lolocontact/)

Dernière modification :
2025-11-20

Ressources :
 - [Trello](https://trello.com/b/fyjx3MhV/jeux-de-societ%C3%A9)
 - [GitHub](https://github.com/lolocontact/JDS)
  
Sommaire :
- [I Spécifications fonctionnelles](#)
    - [I.1 Analyse fonctionnelle](#)
        - [I.1.1 Jeux](#)
            - V1
            - V2
            - V3
            - Futurs Jeux
        - [I.1.2 Espace Utilisateur](#)
            - V1
            - V2
            - V3
- [II Spécifications techniques](#)
    - [II.1 Technologies utilisées](#)

## I Spécifications Fonctionnelles
### I.1 Analyse fonctionnelle
#### I.1.1 Jeux

Les utilisateurs pourront jouer à plusieurs jeux de société se jouant au tour par tour via navigateur (certificat https) et à l’aide de communication discord entre eux, le tout sans ralentissements ou bugs.

Voici la liste des jeux que nous souhaitons intégrer (par oredre chronologique d'ajout) :

**V1 :**

    - Jeu des bâtonnets
    - Blanc Manger Coco

**V2 :**

    - TTMC? (Tu Te Mets Combien ?)

**V3 :**

    - Bang!

**Futurs jeux :**

    - Skyjo
    - Trio
    - Petits Meurtres et Faits Divers
    - OVO
    - Codenames : Images
    - TimeBomb

#### I.1.2 Espace utilisateur

**V1 :**
- Chaque utilisateur aura un login, mdp, image de profil dans un onglet profil.
- Pour jouer, un utilisateur sera l’hôte de la partie, il créera un salon, il obtiendra un identifiant unique et aléatoire. Il devra partager cet identifiant à ses amis pour qu’ils le rejoignent.
- Sur la page d'accueil, l’utilisateur visualise tous ses salons, et peut les supprimer. Si un salon n’est plus utilisé après 12h, il sera supprimé.

**V2 :**
- Nous en serons les administrateurs, nous pourrons lister les pseudos et les id de tous les utilisateurs, nous pouvons réinitialiser leurs mots de passe au besoins. 
- Nous aurons accès aux logs de la machine, et aux connexions établis via le reverse-proxy

**V3 :**
- Mise en place de Trophées (comme par exemple *Gagner 5 parties*) pour les utilisateurs.

## II Spécifications Techniques

Nous avons fait le choix de ne pas créer de moteur de jeu et de développer indépendamment chaque jeux, afin de s'amuser dans le développement et obtenir des résultats plus rapides.

### II.1 Technologies utilisées
| Nom de la technologie                                | Utilité                                                                  | Pourquoi ?                                                                                                   |
|-:-:--------------------------------------------------|-:------------------------------------------------------------------------|-:------------------------------------------------------------------------------------------------------------|
| NodeJS                                               | Environnement d'exécution JavaScript pour la gestion du backend du site. | Technologie relativement récente et assez populaire.                                                         |
| ExpressJS                                            | Framework backend JavaScript.                                            | Simplifier la gestion du backend                                                                             |
| Socket.io                                            | Package NPM gérant les web socket.                                       | Connecter les utilisateurs entre eux en temps réel.                                                          |
| Nodemon                                              | Package NPM permettant de faciliter le développement                     | Rafraichir le code executé dès qu'il est changé.                                                             |
| VueJS                                                | Framewoerk frontend JavaScript                                           | Simplifier le développement de la partie affichée aux utilisateurs (côté client).                            |
| MariaDB                                              | Moteur de gestion de base de données                                     | Technologie connue et simple d'utilisation.                                                                  |
| Docker                                               | Conteneurisation de l'application.                                       | Technologie connue.                                                                                          |
| Duck DNS                                             | DNS de notre site.                                                       | Gratuit et approuvé lors de précédents projets.                                                              |
| NginX                                                | Reverse-proxy.                                                           | Obtentions de certificats https.                                                                             |
| nuc intel d34010wyk + box orange adresse ip statique | Machine pour l'hébergement.                                              | Certes, cette machine n’est pas du tout puissante, mais elle correspond à nos besoins et n’est pas utilisée. |
