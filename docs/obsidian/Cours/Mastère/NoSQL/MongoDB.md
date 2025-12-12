
lire [[Résumé]] avant 


```js

# show
show databases
show dbs

# change de bdd
use <database>

# voir dans les collections (tables)
show collections

a = 100
console.log(a)

# créé une variable et une collection 
moi = { nom:"Tallec--Even", prenom: "Léo"}
db.personnes.insertOne(moi)

# pour clear 
cls 

# find 
db.personnes.find("anne")
[
  {
    _id: ObjectId('68d2880c56fc6f2a7489b03f'),
    prenom: 'Anne',
    nom: 'Gobin'
  }
]

# SELECT * FROM personnes WHERE nom LIKE %o% 
db.personnes.find({nom: /o/ })

# SELECT * FROM personnes WHERE nom LIKE B% 
db.personnes.find({nom: /^B/ })

# SELECT * FROM personnes WHERE nom LIKE %B 
db.personnes.find({nom: /t$/ })

# SELECT COUNT(*) FROM personnes;

db.personnes.countDocuments()

# SELECCT * FROM personnes WHERE nom ILIKE %i% ORDER BY nom ASC, prenom DESC;
db.personnes
	.find({nom: /i/i})
	.sort({nom:1,prenom:-1})


```

```js
{
	intitule : "Excel Perfectionnement"
	jour: {
		date: "02/09/2024"
		cour: {
			heuredebut:"9h"
			durée: 210
			intervenant: "Doe Jane"
			signature: true 
			apprenant: [
				{ nom: "Dupont", prenom: "Jacques", entreprise:"Kappa Sigma", signature: true},
				{ nom: "Mercier", prenom: "Jérome", entreprise:"Intercom", signature: false},
				{ nom: "Prassel", prenom: "Thibault", entreprise:"Kappa Sigma", signature: false},
				{ nom: "Marchand", prenom: "Kevin", entreprise:"Intercom", signature: false}
			]
		}
	}
}


```



##  Inégalité

```js
db.movies.countDocuments( { duration: {$qte : 150, $lte180} } )
```
## Opérateur


\> $gt
\>= $gte
< $lt
<= $lte
\= $eq
!= $ne

# UPDATE

```js
db.personnes.updateOne{
	{ nom: 'Inisan'},
	{$set: { prenom: 'Truc'}}
}
```

# Aggregate

```js


// Donne les résultat de 11 à 21
db.movies.aggregate([
	{ $skip:10},
	{ $limit:10}
])

// Donne les résultat des films de 11 à 21 ayant un A dans le tire et datant de 2016
db.movies.aggregate([
	{ $match: {movie_title : /a/i, title_year: 2016} },
	{ $skip:10},
	{ $limit:10},
])

//meme chose mais on prend que le title et l'année
db.movies.aggregate([
	{ $match: {movie_title : /a/i, title_year: 2016} },
	{ $project: {movie_title: true, title_year: true }},
	{ $skip:10},
	{ $limit:10},
])

//meme chose mais on range par movie_title en croissant
db.movies.aggregate([
	{ $match: {movie_title : /a/i, title_year: 2016} },
	{ $project: {movie_title: true, title_year: true }},
	{ $skip:10},
	{ $limit:10},
	{ $sort: {movie_tittle: 1}}
])

//meme chose mais on range par movie_title en croissant
db.movies.aggregate([
	{ $match: {movie_title : /a/i, title_year: 2016} },
	{ $project: {movie_title: true, title_year: true }},
	{ $skip:10},
	{ $limit:10},
	{ $sort: {movie_tittle: 1}},
	{ $count: "total" }
])


//nombre de film par pays
db.movies.aggregate([
    {
        $group: {
            _id: "$country",
            total: { $sum: 1 }
        }
    }
])

```

# View


```js

db.createView(
	"topMovies", // Nom de la collection virtuelle (vue) à créer
	"movies",
	[
	    {
	        $project: {
	            title: "$movie_title",
	            marge: { $subtract: ["$gross", "$budget"] },
	            _id: false,
	        }
	    },
	    { $match: { marge: { $lt: 0 } } },
	    { $count: "total" }
	]
)

```