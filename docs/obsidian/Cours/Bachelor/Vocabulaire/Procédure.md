- Une Procédure ne renvoie pas de valeur mais peut  prendre en compte 0 à n paramètres
- A ne pas confondre avec [[Fonction]]

Exemple en [[PL ou PGSQL]]

```plsql
CREATE OR REPLACE FUNCTION name(args) RETURNS VOID
AS 
$$
DECLARE
	-- Variables
BEGIN
	-- Code PL/pgSQL
END;
$$ LANGUAGE plpgsql;
```