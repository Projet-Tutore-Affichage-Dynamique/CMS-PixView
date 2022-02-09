
## Bienvenue sur PixView

[A propos](about.md) / [Documentation](docs.md) / [Ressources](ressources.md) / [Avancée](avancee.md)

### Le Projet

L’affichage dynamique est un outil de communication, qui permet de diffuser des informations, sous forme de contenus multimédias, dans les lieux publics sur un écran, un mur d'écrans ou par vidéo-projection. Ici, l’idée est de **réaliser un gestionnaire d’affichage dynamique pour gérer les différents dispositifs d’affichage d’une structure**. 

Exemple : *On peut prendre l’IUT Nancy-Charlemagne : plusieurs écrans sont présents dans les couloirs, ces écrans sont tous reliés à un service qui gère ce qu’ils affichent.*

![Screenshot from 2022-01-07 13-32-58](https://user-images.githubusercontent.com/62664334/148545439-26849164-048a-4d48-8a7f-6bf1fd980355.png)

### Les acteurs

Nous avons identifié **deux acteurs principaux** : le gestionnaire de domaine, ainsi que le gestionnaire de contenu.

**Le gestionnaire de domaine**, qui aura le rôle de super admin, aura pour responsabilité de gérer l’ensemble du dispositif d’affichage dynamique sur une structure, ainsi que de donner des droits à des gestionnaires de contenu afin qu’ils puissent s’occuper d’une partie spécifique de la structure.
- Créer des dispositifs d’affichages (récupérer son token UID, saisir des informations (localisation, nom…).
- Créer des gestionnaires de contenus pour son domaine
- Attribue des dispositif à des gestionnaires de contenus

**Le gestionnaire de contenu**, qui a le rôle d’admin, devra donc gérer les séquences d’affichage des différents dispositifs. Il pourra assigner ces séquences de manière individuelle à chaque dispositif, ou à un groupe de dispositifs, séquences qui auront un enchaînement temporisé avec les suivantes.
- Créer des affichages (images, texte, vidéo…)
- Créer des séquences pour un dispositif spécifique
- Envoyer des affiches/séquences pour un dispositif spécifique

Nous avons également identifié **trois acteurs secondaires** : l’application sur les dispositifs d’affichage ainsi que le serveur (acteurs techniques) ; et aussi les usagers (acteurs passifs).

- L’application sur les dispositifs d'affichage devra être capable d’afficher différents types de données (page HTML, image, vidéo, etc…). Également, une interruption d’une séquence d’affichage pour l’affichage d’un message d’urgence devra être possible.
- Le serveur aura pour rôle de stocker les informations d’affichage, notamment les séquences d'affichage temporisées.
- Les usagers, qui sont des acteurs passifs, ont comme simple rôle de consulter les différents dispositifs d’affichage.
