Volonté d'atomicité un service par conteneur 

![[Pasted image 20241210092924.png]]

Union File System dis que si on à plusieurs fois les même fichier dans les conteneurs il gère pour éviter la duplicité  

https://docs.docker.com/engine/

![[Pasted image 20241210094154.png]]

# Utiliser Docker


```bash
ls -l /var/run/docker.sock 
```
on affiche les perms de docker

```bash
docker container ls -la
docker ps -a
```
On affiche tout les container 

```bash
docker run [OPTIONS] IMAGE [COMMAND] [ARG..]
```
On lance un conteneur

docker TRUC --help

```bash
docker run -it alpine:latest 
```
On lance une alpine

```bash
docker container run --env MYSQL_ROOT_PASSWORD=password -it mysql:8.0-debian
```
On lance un mysql avec comme mot de passe password 

```bash
docker container logs [MACHINE]
```

CTRL P CTRL Q se détacher d'un module monter

```bash
docker container attach [NAME]
```
Se rattacher au module

```bash
docker network create [NAME]
```
Créé un réseau

```bash
docker network connect [NAME RESEAU] [NAME MACHINE]
```
connecter une machine a un réseau

```bash
docker volume create --driver local \
	--opt type=tmpfs \
	-- device=tmpfs \
	--opt o=size=100m,uid=1000 \
	foo
```
volume monté en RAM

```bash
docker volume create --driver local \
	--opt type=xfs \
	--opt device=/dev/sda2 \
	foo
```
volume monté sur une partition dédiée

```bash
docker volume create --driver local \
	--opt type=nfs \
	--opt o=addr=192.168.1.1,rw \
	--opt device=:/path/to/dir \
	foo
```
volume monté par NFS


docker countainer run -d