###HC3T5 - Tâche 5 : Déterminer le type d’un triangle avec des gardes

### Explication
- La fonction `triangleType` prend trois côtés `a`, `b`, `c`.
- On utilise des **gardes** (`|`) pour tester les conditions :
  - Si tous les côtés sont égaux → **Équilatéral**
  - Si deux côtés sont égaux → **Isocèle**
  - Sinon → **Scalène**
- On ajoute une fonction `main` pour tester les exemples donnés.

### Code Haskell

```haskell
-- Définition de la fonction triangleType
triangleType :: Float -> Float -> Float -> String
triangleType a b c
    | a == b && b == c = "Équilatéral"
    | a == b || b == c || a == c = "Isocèle"
    | otherwise = "Scalène"

-- Quelques tests
main :: IO ()
main = do
    putStrLn ("Type du triangle (3,3,3) : " ++ triangleType 3 3 3)
    putStrLn ("Type du triangle (5,5,8) : " ++ triangleType 5 5 8)
    putStrLn ("Type du triangle (6,7,8) : " ++ triangleType 6 7 8)
```

### Résultats attendus
- `triangleType 3 3 3` → **Équilatéral**  
- `triangleType 5 5 8` → **Isocèle**  
- `triangleType 6 7 8` → **Scalène**


