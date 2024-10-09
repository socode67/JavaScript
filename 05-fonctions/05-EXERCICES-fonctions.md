# Les fonctions

## Convertisseur de Température

Vous êtes en train de développer un convertisseur de température pour aider les utilisateurs à convertir entre Celsius, Fahrenheit et Kelvin. L'objectif de cet exercice est de créer un programme qui utilise des fonctions pour effectuer ces conversions, avec des conditions pour choisir le type de conversion.

1. **Fonction de Saisie Utilisateur :**
    - Créez une fonction `saisirTemperature()` qui demande à l'utilisateur de saisir la température qu'il souhaite convertir.

2. **Fonctions de Conversion :**
    - Créez trois fonctions distinctes : `celsiusVersFahrenheit(celsius)`, `fahrenheitVersCelsius(fahrenheit)`, et `celsiusVersKelvin(celsius)`.
    - Chaque fonction prend en paramètre une température dans l'unité d'origine et renvoie la température convertie dans l'unité cible.
    - Les formules de conversion sont les suivantes :
        - Celsius vers Fahrenheit : `F = (C * 9/5) + 32`
        - Fahrenheit vers Celsius : `C = (F - 32) * 5/9`
        - Celsius vers Kelvin : `K = C + 273.15`

3. **Fonction d'Affichage des Résultats :**
    - Créez une fonction `afficherResultats(tempOrigine, uniteOrigine, tempConvertie, uniteConvertie)` qui affiche la température d'origine, l'unité d'origine, la température convertie et l'unité convertie.

4. **Programme Principal :**
    - Dans la fonction principale, demandez à l'utilisateur de choisir l'unité d'origine (Celsius, Fahrenheit ou Kelvin) et l'unité cible pour la conversion.
    - Utilisez des conditions pour déterminer quelle fonction de conversion appeler en fonction des choix de l'utilisateur.
    - Appelez la fonction `afficherResultats` pour afficher les résultats de la conversion.

**Note :**
- Les fonctions doivent être réutilisables et ne pas faire référence à des variables en dehors de leurs paramètres.
- Le programme doit être structuré de manière à ce que chaque fonction accomplisse une tâche spécifique.

