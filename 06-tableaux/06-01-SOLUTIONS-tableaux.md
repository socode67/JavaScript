# 1. LES TABLEAUX

### Exercice 1

```javascript
// Création du tableau fruits
let fruits = ["pomme", "banane", "orange"];

// 1. Utiliser push() pour ajouter fraise à la fin du tableau
fruits.push("fraise");
console.log(fruits); // ["pomme", "banane", "orange", "fraise"]

// 2. Utiliser unshift() pour ajouter kiwi au début du tableau
fruits.unshift("kiwi");
console.log(fruits); // ["kiwi", "pomme", "banane", "orange", "fraise"]

// 3. Utiliser pop() pour supprimer le dernier élément du tableau
fruits.pop();
console.log(fruits); // ["kiwi", "pomme", "banane", "orange"]

// 4. Utiliser shift() pour supprimer le premier élément du tableau
fruits.shift();
console.log(fruits); // ["pomme", "banane", "orange"]
```

---

### Exercice 2

```javascript
// Création du tableau nombres
let nombres = [10, 15, 20, 25, 30, 35, 40];

// 1. Utiliser includes() pour vérifier si le tableau contient 25
let contient25 = nombres.includes(25);
console.log(contient25); // true

// 2. Utiliser indexOf() pour trouver l'index du nombre 30
let index30 = nombres.indexOf(30);
console.log(index30); // 4

// 3. Utiliser slice() pour créer un nouveau tableau contenant les éléments entre le 2ème et 4ème
let sousTableau = nombres.slice(1, 4);
console.log(sousTableau); // [15, 20, 25]
```

---

### Exercice 3

```javascript
// Création du tableau noms
let noms = ["Alice", "Bob", "Charlie", "David", "Eve"];

// 1. Utiliser forEach() pour afficher chaque nom dans la console
noms.forEach(nom => console.log(nom));
// Affichage dans la console :
// Alice
// Bob
// Charlie
// David
// Eve

// 2. Utiliser map() pour créer un nouveau tableau où chaque nom est en majuscules
let nomsMajuscules = noms.map(nom => nom.toUpperCase());
console.log(nomsMajuscules); // ["ALICE", "BOB", "CHARLIE", "DAVID", "EVE"]
```

---

### Exercice 4

```javascript
// Création du tableau ages
let ages = [8, 12, 15, 17, 20, 22, 27];

// 1. Utiliser filter() pour créer un nouveau tableau contenant les âges supérieurs à 18
let agesSup18 = ages.filter(age => age > 18);
console.log(agesSup18); // [20, 22, 27]

// 2. Utiliser reduce() pour calculer la somme de tous les âges
let sommeAges = ages.reduce((acc, age) => acc + age, 0);
console.log(sommeAges); // 121
```

---

### Exercice 5

```javascript
// Création du tableau scores
let scores = [60, 85, 90, 70, 55, 95, 80];

// 1. Utiliser some() pour vérifier si au moins un score est supérieur à 90
let superieurA90 = scores.some(score => score > 90);
console.log(superieurA90); // true

// 2. Utiliser every() pour vérifier si tous les scores sont supérieurs à 50
let tousSuperieursA50 = scores.every(score => score > 50);
console.log(tousSuperieursA50); // true
```