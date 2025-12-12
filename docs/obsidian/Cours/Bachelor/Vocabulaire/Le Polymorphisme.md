est le concept consistant à fournir une interface unique à des entités pouvant avoir différents types.

Exemples : 

si on créé deux fonction ici en [[PL ou PGSQL]]

```plsql
CREATE OR REPLACE FUNCTION demo2(x INTEGER, y INTEGER) RETURNS NUMERIC
AS $$
BEGIN
	-- Renvoyer un INTEGER
	RETURN x + y + 10;
END
$$ 
LANGUAGE plpgsql;
```

et 

```plsql
CREATE OR REPLACE FUNCTION demo2(x NUMERIC, y NUMERIC) RETURNS NUMERIC
AS $$
BEGIN
	-- Renvoyer un NUMERIC
	RETURN x + y;
END
$$ 
LANGUAGE plpgsql;
```

à l'affichage  
```plsql
SELECT demo2(12,24.25); -- Renvoie 36.25
SELECT demo2(12,24); --renvoie 46
```

