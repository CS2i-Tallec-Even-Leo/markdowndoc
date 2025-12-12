utiliser ROUND(NombreAVirgule,Nombre de chiffre)


## Sans le round :

```sql
SELECT idvideo AS "Vidéo",clients.nomclient AS "Client",tarif AS "Tarif HT",(tarif*1.2) AS "Tarif TTC" FROM locations
INNER JOIN clients ON clients.numeroclient = locations.numeroclient
INNER JOIN videos ON videos.id = locations.idvideo
```

![[Pasted image 20241015105833.png]]

## Avec le Round : 

```sql
SELECT idvideo AS "Vidéo",clients.nomclient AS "Client",tarif AS "Tarif HT",ROUND(tarif*1.2,2) AS "Tarif TTC" FROM locations
INNER JOIN clients ON clients.numeroclient = locations.numeroclient
INNER JOIN videos ON videos.id = locations.idvideo
```

![[Pasted image 20241015105804.png]]