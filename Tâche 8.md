###HC3T8 - Tâche avancée 8 : Calculer l’IMC et retourner la catégorie avec where

### Explication
- La fonction `bmiCategory` prend deux paramètres : le **poids** (en kg) et la **taille** (en m).
- On calcule l’IMC avec la formule :  
  \[
  \text{IMC} = \frac{\text{poids}}{\text{taille}^2}
  \]
- On utilise des **gardes** pour classifier :
  - IMC < 18.5 → **Insuffisance pondérale**
  - 18.5 ≤ IMC ≤ 24.9 → **Normal**
  - 25 ≤ IMC ≤ 29.9 → **Surpoids**
  - IMC ≥ 30 → **Obésité**
- On met le calcul de l’IMC dans une clause `where` pour plus de clarté.

### Code Haskell

```haskell
-- Définition de la fonction bmiCategory
bmiCategory :: Float -> Float -> String
bmiCategory poids taille
    | bmi < 18.5 = "Insuffisance pondérale"
    | bmi >= 18.5 && bmi <= 24.9 = "Normal"
    | bmi >= 25 && bmi <= 29.9 = "Surpoids"
    | bmi >= 30 = "Obésité"
    | otherwise = "Valeur invalide"
    where bmi = poids / (taille ^ 2)

-- Quelques tests
main :: IO ()
main = do
    putStrLn ("bmiCategory 70 1.75 : " ++ bmiCategory 70 1.75)
    putStrLn ("bmiCategory 90 1.8  : " ++ bmiCategory 90 1.8)
```

### Résultats attendus
- `bmiCategory 70 1.75` → IMC ≈ 22.86 → **Normal**  
- `bmiCategory 90 1.8` → IMC ≈ 27.78 → **Surpoids**  


