#Tâche 1 : Vérifier si un nombre est positif, négatif ou nul

---

## 1. Définition de la fonction
On veut une fonction `checkNumber` qui prend un entier (`Int`) et retourne une chaîne (`String`).  
La signature est donc :

```haskell
checkNumber :: Int -> String
```

---

## 2. Utilisation de `if-then-else`
En Haskell, l’instruction conditionnelle `if-then-else` doit toujours couvrir **tous les cas possibles**.  
Ici, on distingue trois situations :  
- Si le nombre est **supérieur à 0** → "Positif"  
- Si le nombre est **inférieur à 0** → "Négatif"  
- Sinon (donc égal à 0) → "Zéro"

Voici le code :

```haskell
checkNumber :: Int -> String
checkNumber n =
    if n > 0 then "Positif"
    else if n < 0 then "Négatif"
    else "Zéro"
```

---

## 3. Tests de la fonction
On peut tester directement dans **GHCi** (l’interpréteur Haskell).  
Exemples :

```haskell
*Main> checkNumber 5
"Positif"

*Main> checkNumber (-3)
"Négatif"

*Main> checkNumber 0
"Zéro"
```

---

## 4. Explication détaillée
- `checkNumber :: Int -> String` → la fonction prend un entier et retourne une chaîne.  
- `if n > 0 then "Positif"` → si `n` est strictement positif, on renvoie `"Positif"`.  
- `else if n < 0 then "Négatif"` → sinon, si `n` est strictement négatif, on renvoie `"Négatif"`.  
- `else "Zéro"` → dans tous les autres cas (donc forcément `n == 0`), on renvoie `"Zéro"`.  

---

