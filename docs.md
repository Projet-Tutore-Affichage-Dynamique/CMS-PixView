## Documentations

[Le projet](index.md) / [A propos](about.md) / **Documentation** / [Ressources](ressources.md) / [Avancée](avancee.md)

Lien du dépot github [Pixview](https://github.com/Projet-Tutore-Affichage-Dynamique/pixview)

# pixview-docker

A docker-compose file for getting Directus up and running with MySQL.

## Instructions

1. Create the database and application containers using  `docker-compose up`;

2. Dans le répertoire `api_pixview`, créer un fichier `.env.dev`. Placé le contenu ci-dessous dedans

```bash
    ###########
    ## MYSQL ##
    ###########
    MYSQL_DATABASE=pixview
    MYSQL_USER=directus
    MYSQL_PASSWORD=directus
    MYSQL_ROOT_PASSWORD=directus
    # PORT
    MYSQL_DIST_PORT=3306
    MYSQL_LOCAL_PORT=3306
    
    # PHP_MY_ADMIN
    PMA_HOST=database
    PMA_PORT=3306
    MYSQL_ROOT_PASSWORD=directus
    PMA_DISTANCE_PORT=8080
    PMA_LOCAL_PORT=80
    
    ##############
    ## DIRECTUS ##
    ##############
    # PORT
    DIRECTUS_DIST_PORT=8055
    DIRECTUS_LOCAL_PORT=8056
    # 
    KEY=255d861b-5ea1-5996-9aa3-922530ec40b1
    SECRET=6116487b-cda1-52c2-b5b5-c8022c45e263
    # DIRECTUS CONNECTION DB
    DB_CLIENT=mysql
    DB_HOST=database
    DB_PORT=3306
    DB_DATABASE=pixview
    DB_USER=directus
    DB_PASSWORD=directus
    # SETING CACHE
    CACHE_ENABLED=true
    CACHE_STORE=redis
    CACHE_REDIS=redis://cache:6379
    
    # IDENTIFIAN ADMIN BACK-END
    ADMIN_EMAIL=admin@pixview.com
    ADMIN_PASSWORD=admin
    
    
```

## Connexion à l'API 

`http://localhost:8056/items/`

Pour avoir accès au table :

- `http://localhost:8056/items/contenu_sequence`
- `http://localhost:8056/items/sequence`
- `http://localhost:8056/items/contenu`
- `http://localhost:8056/items/screen`

Pour requêter tout les contenues d'une séquence :
`http://localhost:8056/items/contenu_sequence?fields=contenu_id_contenu&filter[sequence_id_sequence][_eq]=1`

## Connexion à Directus

1. Connexion à Directus `localhost:8056`;
2. Identifiant Directus
   - ADMIN_EMAIL: `admin@pixview.com`
   - ADMIN_PASSWORD: `admin`

## APP VIEWER

Après avoir initialiser le repository avec la commande `docker-compose up`, pour faciliter le développement, il est possible d'utiliser `nodemon`.

Dans le `docker-compose.yml`, à la ligne 66 il faut changé la ligne par ça.

```yaml
command: bash -c 'npm i && npm run dev'
```

Après utiliser 

`docker-compose start pixview`

**Pour ajouter les modules dans avec npm**

il faut interagir avec le service `app.viewer`

1. `docker-compose exec app.viewer /bin/bash`
2. `npm i nodemon --save-dev`
3. `npm update` 
4. `exit`
