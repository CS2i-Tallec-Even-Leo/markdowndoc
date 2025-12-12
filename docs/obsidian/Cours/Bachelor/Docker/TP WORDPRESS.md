
Création du réseau lan
```
docker network create wplan
```

Création des volumes de stockages
```bash
docker volume create dbdata
docker volume create wpdata
```


Création de la base SQL
```bash
docker container run -d  --name db --env-file db.env --volume dbdata:/var/lib/mysql --network wplan mysql:latest
```


Création de PHP
```bash
docker container run -d --network wplan --name pma --env-file pma.env --publish 8080:80 phpmyadmin
```


Création Wordpress
```bash
docker container run -d --network wplan --name wp --env-file wp.env --volume wpdata:/var/www/html --publish 80:80 wordpress:latest
```

```db.env
MYSQL_ROOT_PASSWORD=password
MYSQL_DATABASE=db
MYSQL_USER=root
MYSQL_PASSWORD=password
```

```db.env
MYSQL_ROOT_PASSWORD=password
MYSQL_DATABASE=db
MYSQL_USER=root
MYSQL_PASSWORD=password
```

```pma.env
PMA_HOST=db
```

```wp.env
WORDPRESS_DB_HOST=db
WORDPRESS_DB_USER=root
WORDPRESS_DB_PASSWORD=password
WORDPRESS_DB_NAME=db
```


sinon le Yaml qui permet de le generer :

```YAML

volumes:
  dbdata:
  wpdata:

networks:
  wplan:

services:
  db:
    # ~~ cf .env ~~ ~~~> valeur par défaut.
    image: mysql:latest
    env_file:
    - db.env
    networks:
    - wplan
    volumes:
    - type: volume
      source: dbdata
      target: /var/lib/mysql
  pma:
    image: phpmyadmin:latest
    networks:
    - wplan
    environment:
      PMA_HOST: db
    ports:
    - target: 80
      published: 8080
      protocol: tcp

  wp:
    image: wordpress:latest
    env_file:
    - wp.env
    networks:
    - wplan
    volumes:
    - type: volume
      source: wpdata
      target: /var/www/html
    ports:
    - target: 80
      published: 80
      protocol: tcp

```


on check si ma config est bonne : 

```sh
docker compose config
```

on up 

```sh
docker compose up -d
```

si on a un problème on down avec : 

```sh
docker compose down -v
```

on ajoute au yaml la bdd : 

```yaml
    healthcheck:
      test: mysql -u root -p$$MYSQL_ROOT_PASSWORD -h localhost ping > /var/log/healthcheck.log

```

on ajoute au yaml du reste :

```yaml
    healthcheck:
      test: curl -f http://localhost:80 || exit 1
```

