# LES CONDITIONS SWITCH & TERNAIRE

## Exercice 1

```js
const num = parseInt(prompt("Saisir un nombre"));

const resultat = num%2 === 0 ? "Pair" : "Impair";

console.log(`${num} est ${resultat}`)
```

## Exercice 2 

```js
// Demander à l'utilisateur de choisir une opération parmi +, -, *, /, %, **
const operation = prompt("Choisissez une opération : +, -, *, /, %, **");

// Demander à l'utilisateur de saisir deux nombres
const num1 = parseFloat(prompt("Saisir le premier nombre :"));
const num2 = parseFloat(prompt("Saisir le deuxième nombre :"));

// Vérification si les entrées sont bien des nombres
if(isNaN(num1) || isNaN(num2)){
    console.log("Erreur : Veuillez entrer des nombres valides.");
}else{
    // Utilisation de switch pour effectuer l'opération choisie
    switch(operation){
        case "+":
            console.log(`${num1} + ${num2} = ${num1 + num2}`);
            break;
        case "-":
            console.log(`${num1} - ${num2} = ${num1 - num2}`);
            break;
        case "*":
            console.log(`${num1} * ${num2} = ${num1 * num2}`);
            break;
        case "/":
            if (num2 === 0) {
                console.log("Erreur : Division par 0 impossible.");
            } else {
                console.log(`${num1} / ${num2} = ${num1 / num2}`);
            }
            break;
        case "%":
            if (num2 === 0) {
                console.log("Erreur : Division par 0 impossible.");
            } else {
                console.log(`${num1} % ${num2} = ${num1 % num2}`);
            }
            break;
        case "**":
            console.log(`${num1} ** ${num2} = ${num1 ** num2}`);
            break;
        default:
            console.log("Erreur : Opération non reconnue.");
    }
}
```