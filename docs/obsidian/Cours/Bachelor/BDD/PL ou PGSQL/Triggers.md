## 12 combinaisons de triggers

  
- 3 instructions SQL : `INSERT`, `UPDATE`, `DELETE`

- 2 moments : `BEFORE` ou `UPDATE`

- 2 types de triggers : ROW TRIGGER (trigger de ligne) et STATEMENT TRIGGER (trigger d'instruction)

## La table

  

```sql

SET SEARCH_PATH TO demotriggers;
  

CREATE TABLE personnes (

    id SERIAL PRIMARY KEY,

    nom VARCHAR(30)

);

SELECT *

FROM personnes;

```

  
## La fonction trigger


Une fonction trigger est une fonction standard de Postgres (`CREATE FUNCTION`), avec 2 aménagements :

- Elle renvoie un type `TRIGGER` (voir le `RETURNS TRIGGER`)

- En fin de bloc, elle fait :

    - un `RETURN NEW` (pour un trigger sur `INSERT` ou `UPDATE`)

    - un `RETURN OLD` (pour un trigger sur `DELETE`)

  

```sql

-- La fonction trigger qui va réagir avant qu'un INSERT soit écrit dans la table

	CREATE OR REPLACE FUNCTION personnes_before_insert() RETURNS TRIGGER
	AS $$
	
	BEGIN
	
	    -- Faire quelque dans la fonction
	
	    RAISE INFO 'BEFORE INSERT sur la table personnes, nouveau nom = %', NEW.nom;
	
	    -- Renvoyer OLD ou NEW
	
	    -- On renvoie OLD si c'est un trigger sur l'instruction DELETE
	
	    -- On renvoie NEW si c'est un trigger sur l'instruction INSERT ou UPDATE
	
	    RETURN NEW;
	
	END;
	
	$$ LANGUAGE plpgsql;

```

  

## Le branchement de la fonction trigger sur la table

  

```sql

-- Brancher la fonction trigger (ci-dessus) sur la table personnes

-- La fonction sera déclenchée :

-- AVANT (BEFORE) que les lignes soient inscrites dans la table

-- après une instruction INSERT

-- POUR CHAQUE LIGNE (FOR EACH ROW)

CREATE OR REPLACE TRIGGER trig_personnes_before_insert
BEFORE INSERT
ON personnes
FOR EACH ROW
EXECUTE PROCEDURE personnes_before_insert();

```

  

## Test du trigger

  

Pour tester le trigger `BEFORE INSERT`, il faut insérer des lignes dans la table.

  

```sql

-- Insérer une ligne dans la table personnes

-- (ce qui va invoquer le trigger / la fonction trigger)

INSERT INTO personnes (nom) VALUES ('Inisan');

INSERT INTO personnes (nom)

    VALUES ('alpha'),

    ('bravo'),

    ('charlie');

```