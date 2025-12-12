![[Pasted image 20241015092211.png]]


```sql
SELECT *
FROM table1
RIGHT JOIN table2 ON table1.id = table2.fk_id
```

Dans certain cas on aura besoin de récupérer aussi les valeurs qui ne sont pas dans les 2 tables [[INNER JOIN]] on aura donc besoin de faire un LEFT JOIN pour aussi récupérer les valeurs à NULL car non renseigner 

Dans ce cas on met la table la plus importante dans le FROM

Dans certain langage il n'y à pas de [[RIGHT JOIN]] il faudra donc faire un [[LEFT JOIN]]