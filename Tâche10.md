###HC3T10 - Tâche avancée 10 : Vérifier si une chaîne est un palindrome (récursion, gardes)

### Explication
- La fonction `isPalindrome` prend une chaîne (`String`).
- Les gardes permettent de gérer les cas :
  - Si la chaîne est vide (`""`) ou contient un seul caractère → **True** (c’est forcément un palindrome).
  - Si le premier et le dernier caractère sont identiques → on vérifie récursivement le reste de la chaîne (en enlevant ces deux caractères).
  - Sinon → **False**.
- On utilise `head` pour le premier caractère, `last` pour le dernier, et `init`/`tail` pour réduire la chaîne.

### Code Haskell

```haskell
-- Définition de la fonction isPalindrome
isPalindrome :: String -> Bool
isPalindrome str
    | length str == 0 = True
    | length str == 1 = True
    | head str == last str = isPalindrome (init (tail str))
    | otherwise = False

-- Quelques tests
main :: IO ()
main = do
    putStrLn ("isPalindrome \"racecar\" : " ++ show (isPalindrome "racecar"))
    putStrLn ("isPalindrome \"haskell\" : " ++ show (isPalindrome "haskell"))
    putStrLn ("isPalindrome \"madam\"   : " ++ show (isPalindrome "madam"))
```

### Résultats attendus
- `isPalindrome "racecar"` → **True** (c’est un palindrome).  
- `isPalindrome "haskell"` → **False** (pas un palindrome).  
- `isPalindrome "madam"` → **True** (c’est un palindrome).  

