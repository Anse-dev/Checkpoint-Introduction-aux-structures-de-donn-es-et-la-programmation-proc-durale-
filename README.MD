# ReadMe - Explication du Code Probleme 1

## Structure du Code

Le code t comprend deux parties principales : une procédure appelée `dot_product` et un algorithme appelé `verifier_orthogonalite_pour_n_couples`.

### Procédure `dot_product`

La procédure `dot_product` prend en entrée deux vecteurs `v1` et `v2` de taille 3 ainsi qu'une variable `ps` pour stocker le produit scalaire. Elle utilise une boucle pour calculer le produit scalaire des deux vecteurs.

```pascal
PROCEDURE dot_product(v1, v2 : ARRAY_OF INTEGER[3], ps: INTEGER)
VAR
    i: INTEGER
BEGIN
    // Calcule le produit scalaire de v1 et v2
    ps := 0
    FOR i FROM 1 TO v1.lenght DO
        ps := ps + v1[i] * v2[i]
    END FOR
END
```

### Algorithme `verifier_orthogonalite_pour_n_couples`

L'algorithme `verifier_orthogonalite_pour_n_couples` vérifie l'orthogonalité pour `n` couples de vecteurs. Il utilise une boucle pour parcourir les vecteurs, appelle la procédure `dot_product`pour calculer le produit scalaire, puis affiche le résultat.

```pascal

ALGORITHM verifier_orthogonalite_pour_n_couples
VAR
  n, k, i: INTEGER;
  vecteur_liste: ARRAY_OF INTEGER[40][40];
  v1, v2: ARRAY_OF INTEGER[3];
  ps: INTEGER;
BEGIN
    // Vérifie l'orthogonalité pour n couples de vecteurs


    FOR k FROM 1 TO n DO
        v1 := vecteur_liste[k][1];
        v2 := vecteur_liste[k][2];

        // Appelle la procédure dot_product pour calculer le produit scalaire
        dot_product(v1, v2, ps);

        // Affiche le résultat
        Write("Produit scalaire des vecteurs ", v1, " et ", v2, " : ", ps);

        // Vérifie si les vecteurs sont orthogonaux
        IF ps = 0 THEN
            Write("Les vecteurs ", v1, " et ", v2, " sont orthogonaux.")
        ELSE
            Write("Les vecteurs ", v1, " et ", v2, " ne sont pas orthogonaux.")
        END IF;
    END_FOR
END

```

### Modification du Procédure `dot_product` en FOnction

La procédure `dot_product` prend en entrée deux vecteurs `v1` et `v2` de taille 3 ainsi qu'une variable `ps` pour stocker le produit scalaire. Elle utilise une boucle pour calculer le produit scalaire des deux vecteurs.

```pascal
FUNCTION dot_product(v1, v2: ARRAY_OF INTEGER[3]): INTEGER;
VAR
    i, ps: INTEGER;
BEGIN
    // Calcule le produit scalaire de v1 et v2
    ps := 0;
    FOR i FROM 1 TO Length(v1) DO
        ps := ps + v1[i] * v2[i];
    END FOR;
    RESULT := ps;
END;
```

### Algorithme `verifier_orthogonalite_pour_n_couples` apres Modification

L'algorithme `verifier_orthogonalite_pour_n_couples` vérifie l'orthogonalité pour `n` couples de vecteurs. Il utilise une boucle pour parcourir les vecteurs, appelle la procédure `dot_product`pour calculer le produit scalaire, puis affiche le résultat.

```pascal

ALGORITHM verifier_orthogonalite_pour_n_couples
VAR
  n, k, i: INTEGER;
  vecteur_liste: ARRAY_OF INTEGER[40][40];
  v1, v2: ARRAY_OF INTEGER[3];
  ps: INTEGER;
BEGIN
    // Vérifie l'orthogonalité pour n couples de vecteurs


    FOR k FROM 1 TO n DO
        v1 := vecteur_liste[k][1];
        v2 := vecteur_liste[k][2];

        // Appelle la fonction dot_product pour calculer le produit scalaire
        ps := dot_product(v1, v2);


        // Affiche le résultat
        Write("Produit scalaire des vecteurs ", v1, " et ", v2, " : ", ps);

        // Vérifie si les vecteurs sont orthogonaux
        IF ps = 0 THEN
            Write("Les vecteurs ", v1, " et ", v2, " sont orthogonaux.")
        ELSE
            Write("Les vecteurs ", v1, " et ", v2, " ne sont pas orthogonaux.")
        END IF;
    END_FOR
END

```
