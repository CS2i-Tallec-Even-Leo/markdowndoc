- Une fonction renvoie une valeur et peut prendre en compte 0 à n paramètres 
-  A ne pas confondre avec [[Procédure]]

Exemple en [[PL ou PGSQL]]

```plsql
CREATE OR REPLACE FUNCTION name(args) RETURNS type
AS 
$$
DECLARE
	-- Variables
BEGIN
	-- Code PL/pgSQL
	RETURN valeur
END;
$$ LANGUAGE plpgsql;
```

- le bloc DECLARE est facultatif si aucune variable locale n'est nécessaire
- RETURNS dans la signature pour indiquer le type de données renvoyé
- RETURN dans le bloc de code PL/pgSQL pour renvoyer une valeur 