## Tâche 2 : Déterminer la note à partir d’un score avec des gardes


---

## 1. Définition de la fonction
On veut une fonction `grade` qui prend un entier (`Int`) et retourne une chaîne (`String`).  
La signature est donc :

```haskell
grade :: Int -> String
```

---

## 2. Utilisation des gardes
Les gardes en Haskell s’écrivent avec le symbole `|` et permettent de tester plusieurs conditions successives.  
On ajoute un cas par défaut avec `otherwise` (qui équivaut à `True`).

Voici le code complet :

```haskell
grade :: Int -> String
grade score
    | score >= 90 = "A"
    | score >= 80 = "B"
    | score >= 70 = "C"
    | score >= 60 = "D"
    | otherwise   = "F"
```

---

## 3. Explication détaillée
- `grade :: Int -> String` → la fonction prend un entier et retourne une chaîne.  
- `| score >= 90 = "A"` → si le score est supérieur ou égal à 90, on renvoie `"A"`.  
- `| score >= 80 = "B"` → sinon, si le score est supérieur ou égal à 80, on renvoie `"B"`.  
- `| score >= 70 = "C"` → sinon, si le score est supérieur ou égal à 70, on renvoie `"C"`.  
- `| score >= 60 = "D"` → sinon, si le score est supérieur ou égal à 60, on renvoie `"D"`.  
- `| otherwise = "F"` → dans tous les autres cas (donc score < 60), on renvoie `"F"`.  

---

## 4. Tests de la fonction
Dans **GHCi**, on peut tester ainsi :

```haskell
*Main> grade 95
"A"

*Main> grade 72
"C"

*Main> grade 50
"F"
```

---


