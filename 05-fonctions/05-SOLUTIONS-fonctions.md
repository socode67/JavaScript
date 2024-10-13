# Les fonctions

Voici les solutions aux exercices proposés :

### Exercice 1 : Créer une fonction simple

```js
function direBonjour() {
    console.log("Bonjour, comment ça va ?");
}

direBonjour();
```

### Exercice 2 : Utiliser des paramètres

```js
function saluerPersonne(prenom, nom) {
    console.log(`Bonjour ${prenom} ${nom}, comment ça va ?`);
}

saluerPersonne("Jean", "Dupont");
```

### Exercice 3 : Calcul d'âge

```js
function calculerAge(anneeNaissance) {
    const anneeActuelle = 2024;
    const age = anneeActuelle - anneeNaissance;
    console.log(`Vous avez ${age} ans.`);
    return age;
}

calculerAge(1990);
```

### Exercice 4 : Utiliser une expression de fonction

```js
const carre = function(nombre) {
    return nombre * nombre;
}

console.log(carre(5)); // Affiche 25
```

### Exercice 5 : Les fonctions fléchées

```js
const carre = (nombre) => nombre * nombre;

console.log(carre(5)); // Affiche 25
```

### Exercice 6 : Somme de deux nombres

```js
function addition(a, b) {
    return a + b;
}

console.log(addition(3, 4)); // Affiche 7
```
## Exercice 7 : Convertisseur de Température

```js
// Fonction pour demander à l'utilisateur de saisir une température
function saisirTemperature() {
    return parseFloat(prompt("Saisissez la température à convertir :"));
}

// Fonction pour convertir une température de Celsius à Fahrenheit
function celsiusVersFahrenheit(celsius) {
    return (celsius * 9/5) + 32;
}

// Fonction pour convertir une température de Fahrenheit à Celsius
function fahrenheitVersCelsius(fahrenheit) {
    return (fahrenheit - 32) * 5/9;
}

// Fonction pour convertir une température de Celsius à Kelvin
function celsiusVersKelvin(celsius) {
    return celsius + 273.15;
}

// Fonction pour afficher les résultats de la conversion
function afficherResultats(tempOrigine, uniteOrigine, tempConvertie, uniteConvertie) {
    console.log(`Température d'origine : ${tempOrigine} ${uniteOrigine}`);
    console.log(`Température convertie : ${tempConvertie.toFixed(2)} ${uniteConvertie}`);
}

// Fonction principale pour gérer la conversion de la température
function conversionTemperature() {

    // Demande à l'utilisateur de saisir la température
    const temperature = saisirTemperature();

    // Demande à l'utilisateur de choisir l'unité d'origine (C pour Celsius, F pour Fahrenheit, K pour Kelvin)
    const uniteOrigine = prompt("Choisissez l'unité d'origine (C, F, K) :").toUpperCase();

    // Demande à l'utilisateur de choisir l'unité cible (C pour Celsius, F pour Fahrenheit, K pour Kelvin)
    const uniteCible = prompt("Choisissez l'unité cible (C, F, K) :").toUpperCase();

    let temperatureConvertie;

    // Utilisation d'un switch pour déterminer l'unité d'origine et effectuer la conversion appropriée
    switch (uniteOrigine) {
        case 'C':
            // Si l'unité d'origine est Celsius, convertir selon l'unité cible
            if (uniteCible === 'F') {
                temperatureConvertie = celsiusVersFahrenheit(temperature);
            } else if (uniteCible === 'K') {
                temperatureConvertie = celsiusVersKelvin(temperature);
            }
            break;
        case 'F':
            // Si l'unité d'origine est Fahrenheit, convertir en Celsius
            if (uniteCible === 'C') {
                temperatureConvertie = fahrenheitVersCelsius(temperature);
            }
            break;
        case 'K':
            // Si l'unité d'origine est Kelvin, convertir en Celsius
            if (uniteCible === 'C') {
                temperatureConvertie = temperature - 273.15;
            }
            break;
        default:
            // Si l'unité d'origine n'est pas reconnue, afficher un message d'erreur
            console.log("Unité non reconnue.");
            return;
    }

    afficherResultats(temperature, uniteOrigine, temperatureConvertie, uniteCible);
}


// Appel de la fonction principale pour démarrer le programme
conversionTemperature();
```