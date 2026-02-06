###HC3T4 - Tâche 4 : Calculer l’aire d’un triangle avec la formule de Héron

### Explication
- On définit une fonction `triangleArea` qui prend trois côtés `a`, `b`, `c`.
- On calcule le demi-périmètre \( s = \frac{a+b+c}{2} \).
- On applique la formule de Héron :  
  \[
  \text{Aire} = \sqrt{s \cdot (s-a) \cdot (s-b) \cdot (s-c)}
  \]
- On teste la fonction avec les valeurs données.

### Code Haskell

```haskell
-- Définition de la fonction triangleArea
triangleArea :: Float -> Float -> Float -> Float
triangleArea a b c =
    let s = (a + b + c) / 2
    in sqrt (s * (s - a) * (s - b) * (s - c))

-- Quelques tests
main :: IO ()
main = do
    putStrLn ("Aire du triangle (3,4,5) : " ++ show (triangleArea 3 4 5))
    putStrLn ("Aire du triangle (7,8,9) : " ++ show (triangleArea 7 8 9))
```

### Résultats attendus
- Pour `triangleArea 3 4 5`, l’aire est **6.0** (triangle rectangle classique).
- Pour `triangleArea 7 8 9`, l’aire est environ **26.83**.


