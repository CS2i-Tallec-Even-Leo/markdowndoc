
Créer une vue ?

```sql
CREATE VIEW vue_client_ford AS
SELECT Distinct clients.nomclient,clients.prenomclient from acteurs
	INNER JOIN roles ON roles.idacteur = acteurs.id 
	INNER JOIN films ON roles.idfilm = films.id 
	INNER JOIN videos ON films.id = videos.idfilm 
	INNER JOIN locations ON locations.idvideo = videos.id
	INNER JOIN clients ON locations.numeroclient = clients.numeroclient
WHERE acteurs.nomacteur ILIKE 'Ford'
AND acteurs.prenomacteur ILIKE 'Harrison'
ORDER BY NomClient,PrenomClient;
```


Utiliser une Vue ?

```sql
SELECT * FROM vue_client_ford;
```

Plus performant en cas d'utilisation répéter 