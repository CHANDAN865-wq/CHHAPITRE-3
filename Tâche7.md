###HC3T7 - Tâche avancée 7 : Déterminer la saison en fonction du mois avec des gardes

### Explication
- La fonction `season` prend un entier représentant le mois (1 à 12).
- On utilise des gardes (`|`) pour vérifier dans quel intervalle se trouve le mois :
  - 12, 1, 2 → **Hiver**
  - 3, 4, 5 → **Printemps**
  - 6, 7, 8 → **Été**
  - 9, 10, 11 → **Automne**
- On ajoute une clause `otherwise` pour gérer les cas invalides (par exemple un mois hors de 1–12).

### Code Haskell

```haskell
-- Définition de la fonction season
season :: Int -> String
season month
    | month == 12 || month == 1 || month == 2 = "Hiver"
    | month == 3 || month == 4 || month == 5 = "Printemps"
    | month == 6 || month == 7 || month == 8 = "Été"
    | month == 9 || month == 10 || month == 11 = "Automne"
    | otherwise = "Mois invalide"

-- Quelques tests
main :: IO ()
main = do
    putStrLn ("season 3  : " ++ season 3)
    putStrLn ("season 7  : " ++ season 7)
    putStrLn ("season 11 : " ++ season 11)
```

### Résultats attendus
- `season 3` → **Printemps**  
- `season 7` → **Été**  
- `season 11` → **Automne**  


