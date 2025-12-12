# RAISE INFO


```plsql
RAISE INFO 'La valeur de ma variable est la suivante : %',variable;
```

Ici dans un exemple : 

```plsql
CREATE OR REPLACE FUNCTION demo(nom VARCHAR, prenom VARCHAR) RETURNS VOID
AS $$
DECLARE
	nomcomplet VARCHAR;
BEGIN
	nomcomplet = nom || ' ' || prenom;
	RAISE INFO 'La valeur de ma variable est la suivante : %',nomcomplet;
END
$$ 
LANGUAGE plpgsql;
```


# RAISE NOTICE 

```plsql 
RAISE NOTICE "une Notice" 
```
# RAISE WARNING

```plsql 
RAISE WARNING "un Warning" 
```
# RAISE EXCEPTION

```plsql 
RAISE EXCEPTION "une Erreur" 
```
