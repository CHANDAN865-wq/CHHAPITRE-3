###HC3T6 - Tâche avancée 6 : Vérifier une année bissextile avec if-then-else

### Explication
- La fonction `isLeapYear` prend une année (type `Int`).
- Les règles sont :
  - Si divisible par 400 → **True**  
  - Si divisible par 100 mais pas par 400 → **False**  
  - Si divisible par 4 → **True**  
  - Sinon → **False**  
- On utilise des conditions imbriquées avec `if-then-else`.

### Code Haskell

```haskell
-- Définition de la fonction isLeapYear
isLeapYear :: Int -> Bool
isLeapYear year =
    if year `mod` 400 == 0 then True
    else if year `mod` 100 == 0 then False
    else if year `mod` 4 == 0 then True
    else False

-- Quelques tests
main :: IO ()
main = do
    putStrLn ("isLeapYear 2000 : " ++ show (isLeapYear 2000))
    putStrLn ("isLeapYear 1900 : " ++ show (isLeapYear 1900))
    putStrLn ("isLeapYear 2024 : " ++ show (isLeapYear 2024))
```

### Résultats attendus
- `isLeapYear 2000` → **True** (2000 est divisible par 400)  
- `isLeapYear 1900` → **False** (1900 est divisible par 100 mais pas par 400)  
- `isLeapYear 2024` → **True** (2024 est divisible par 4 mais pas par 100)  


