```kotlin
var x = 100
var x: Int = 100
var jour = "vendredi"
var jour: String = "vendredi"
jour = null // Interdit
var jour2: String?
jour2 = null // Autorisé 

// Variable en lecture seule
val y = 200

//Fonctions
fun somme(x:Int,y:Int) : Int{
	return x+y
}
fun somme(x:Int,y:Int){
	return x+y
}

fun somme(x:Int,y:Int) = x + y

for i in 1..10{
}
var x = if(a >10) "alpha" else "bravo"

fun dummy(a:Int) = if (a > 10) "alpha" else "bravo"

fun nomJour(j:Int): String{
	when(j){
	1 -> return "lundi"
	2 -> return "mardi"
	else return "jour inconnu"
	}
	
}
//Class

class Personne(var nom: String, var: prenom)

var p = Personne("Inisan","Hervé")
print(p.nom)
print(p.prenom)
p.nom = "Test"


```

# Intent pour démarrer une Activity

```kotlin
//Créer un Intent (dans une Activity)
// Argument : 
// - Contexte de départ
// - Nom de la classe d'arrivée (une Activity)
val intent = Intent(this,DetailActivity::class.java)

// Ajouter des infos si utile
intent.putExtra("$packageName.id", 42)
intent.putExtra"$package.title", "Lorem ipsum")

startActivity(intent)
```


val intent = Intent(context, DetailActivity::class.java)