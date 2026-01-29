##Tâche 3 : Convertir une couleur RGB en chaîne hexadécimale avec let


---

## 1. Signature de la fonction
On veut une fonction qui prend un triplet `(Int, Int, Int)` représentant une couleur RGB et retourne une chaîne hexadécimale :

```haskell
rgbToHex :: (Int, Int, Int) -> String
```

---

## 2. Conversion en hexadécimal
Chaque composant (R, G, B) doit être transformé en une chaîne hexadécimale **à deux caractères**.  
Pour cela, on utilise `Numeric.showHex` (du module `Numeric`) et on complète avec un zéro si nécessaire.

---

## 3. Code complet avec `let`
Voici le code :

```haskell
import Numeric (showHex)
import Data.Char (intToDigit)

-- Fonction auxiliaire pour formater un entier en deux caractères hexadécimaux
toHex2 :: Int -> String
toHex2 n =
    let hex = showHex n ""
    in if length hex == 1 then '0' : hex else hex

-- Fonction principale
rgbToHex :: (Int, Int, Int) -> String
rgbToHex (r, g, b) =
    let red   = toHex2 r
        green = toHex2 g
        blue  = toHex2 b
    in "#" ++ red ++ green ++ blue
```

---

## 4. Explication détaillée
- `toHex2` → convertit un entier en hexadécimal et ajoute un zéro devant si la chaîne n’a qu’un seul caractère.  
  Exemple : `toHex2 0 = "00"`, `toHex2 127 = "7f"`, `toHex2 255 = "ff"`.  
- Dans `rgbToHex`, on utilise `let` pour définir trois variables locales :  
  - `red` pour la composante rouge,  
  - `green` pour la composante verte,  
  - `blue` pour la composante bleue.  
- Enfin, on concatène avec `"#"` pour obtenir une chaîne hexadécimale au format CSS (`#RRGGBB`).  

---

## 5. Tests dans GHCi
```haskell
*Main> rgbToHex (255, 0, 127)
"#ff007f"

*Main> rgbToHex (0, 255, 64)
"#00ff40"
``
