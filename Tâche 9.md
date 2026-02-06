###HC3T9 - Tâche avancée 9 : Trouver le maximum de trois nombres avec let


### Explication
- La fonction `maxOfThree` prend trois entiers `x`, `y`, `z`.
- On utilise `let` pour stocker des valeurs intermédiaires :
  - `maxXY` = maximum de `x` et `y`
  - `maxXYZ` = maximum de `maxXY` et `z`
- On retourne `maxXYZ` comme résultat final.
- On ajoute une fonction `main` pour tester avec les exemples donnés.

### Code Haskell

```haskell
-- Définition de la fonction maxOfThree
maxOfThree :: Int -> Int -> Int -> Int
maxOfThree x y z =
    let maxXY = if x > y then x else y
        maxXYZ = if maxXY > z then maxXY else z
    in maxXYZ

-- Quelques tests
main :: IO ()
main = do
    putStrLn ("maxOfThree 10 20 15 : " ++ show (maxOfThree 10 20 15))
    putStrLn ("maxOfThree 5 25 10  : " ++ show (maxOfThree 5 25 10))
```

### Résultats attendus
- `maxOfThree 10 20 15` → **20**  
- `maxOfThree 5 25 10` → **25**  


