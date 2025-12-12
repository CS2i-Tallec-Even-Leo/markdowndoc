On cherche à développer un système qui gère les emprunts et les retours dans une bibliothèque universitaire.

Users : 
- enseignant (nom de département)
- étudiant (une année universitaire)
- particulier
- Tous on :
	- ID
	- Nom
	- Prénom
	- Adresse


Book:
- Livre (titre, auteur et code ISBN, genre)
- revues (Titre, n° de volume, date de parution)
- Tous on :
	- code barre
	- caution

Emprunt : 
- Utilisateur enregistrer (nom + caution)
- emprunt possible si user.caution > book.caution
- 15 Jours
- Contrainte : 
	- pas plus d'un exemplaire
	- ni d'emprunt si déja un retard

Stockage : 
- N° de travée
- N° d'étagère dans la travée
- Niveau
- catégorie(policier, roman)
- Contrainte : 
	- Différentes ressources possible au même endroit
	- Mais tout les exemplaires d'une ressource au même endroit 


On souhaite pouvoir effectuer les actions suivantes :

- Enregistrer un nouvel utilisateur et lui créer un compte

- Permettre à un utilisateur d’effectuer un emprunt et lui préciser la liste des ouvrages empruntés comprenant la totalité des emprunts (pas seulement les emprunts du jour) ; pour permettre cet emprunt une page de recherche lui sera proposée avec deux types de recherche :
	- une recherche simple avec le nom de l’ouvrage ;
	- une recherche détaillée avec le nom de l’auteur, une année de publication, le thème de l’ouvrage (roman, policier) ;
 
	chacun de ces critères pourra être combiné ou utilisé seul. L’utilisateur devra se connecter à son compte avant de pouvoir faire un emprunt.





- Permettre à la bibliothécaire de lister les emprunts en retard et d’envoyer un mail aux utilisateurs concernés.      

- Permettre à la bibliothécaire d’enregistrer un nouveau livre ou une nouvelle revue et lui associer un emplacement.

- Pour toutes les opérations effectuées par la  bibliothécaire , celle-ci devra également se connecter à son compte.


Extends c'est possible
Include c'est obligatorie
