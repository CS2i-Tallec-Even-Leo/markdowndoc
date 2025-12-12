
REDIS : moteur orienté clef/valeur

clef : valeur

MONGODB, CouchDB, DocumentDB : moteur orientés "document"
=>Base de données schemaless
=> on peut faire évoluer le schéma très facilement
	(ex. : réseaux sociaux, jeux vidéos)
=> prévus dès le départ pour du cluster de serveurs
=> pouvoir stocker des documents de structure différente
	(ex. : documents administratifs)
Exemple de Document : 

```json
{
	nom:  "Léo",
	prenom:  "Tallec--Éven",
	formation: [
		{ nom: "cs2i", annee: 2025},
		{ nom: "SIO", annee: 2024}
	],
	ville: {
		codepostal : "56530",
		nom: "Gestel
	}
}
```

3 types de données : 
- Valeur scalaires : nombres, strings, booléens , null
- Tableaux
- Objets

 