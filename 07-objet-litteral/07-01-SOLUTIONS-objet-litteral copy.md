# 1. Objet

Voici les solutions pour chaque exercice :

### Exercice 1 : Déstructuration d'un tableau

```js
// Création du tableau
const fruits = ["pomme", "banane", "orange"];

// Déstructuration du tableau
const [fruit1, fruit2, fruit3] = fruits;

// Affichage des variables
console.log(fruit1); // "pomme"
console.log(fruit2); // "banane"
console.log(fruit3); // "orange"
```

### Exercice 2 : Déstructuration d'un objet

```js
// Création de l'objet
const voiture = {
    marque: "Tesla",
    modèle: "Model 3"
};

// Déstructuration de l'objet
const { marque, modèle } = voiture;

// Affichage des variables
console.log(marque);  // "Tesla"
console.log(modèle);  // "Model 3"
```

### Exercice 3 : Opérateur spread avec un tableau

```js
// Création du tableau
const nombres = [5, 10, 15];

// Utilisation de l'opérateur spread pour créer un nouveau tableau
const nouveauxNombres = [...nombres, 20];

// Affichage du nouveau tableau
console.log(nouveauxNombres); // [5, 10, 15, 20]
```

### Exercice 4 : Opérateur spread avec un objet

```js
// Création de l'objet
const ordinateur = {
    marque: "Apple",
    modèle: "MacBook Pro"
};

// Utilisation de l'opérateur spread pour créer un nouvel objet
const nouvelOrdinateur = {
    ...ordinateur,
    année: 2024
};

// Affichage du nouvel objet
console.log(nouvelOrdinateur); 
// { marque: "Apple", modèle: "MacBook Pro", année: 2024 }
```

Voici les solutions pour chacun des exercices :

---

### Exercice 5 : Afficher une liste d'objets

```javascript
const etudiants = [
  { nom: "Léo", age: 22, note: 15 },
  { nom: "Sophie", age: 20, note: 12 },
  { nom: "Mila", age: 23, note: 17 }
];

// Affichage de chaque étudiant
etudiants.forEach(etudiant => {
  console.log(`Nom: ${etudiant.nom}, Age: ${etudiant.age}, Note: ${etudiant.note}`);
});
```

---

### Exercice 6 : Ajouter un nouvel objet à un tableau

```javascript
const etudiants = [
  { nom: "Léo", age: 22, note: 15 },
  { nom: "Sophie", age: 20, note: 12 },
  { nom: "Mila", age: 23, note: 17 }
];

// Ajout d'un nouvel étudiant
etudiants.push({ nom: "Jules", age: 21, note: 14 });

console.log(etudiants);
```

---

### Exercice 7 : Modifier un objet dans un tableau et le remettre à la même position

```javascript
const etudiants = [
  { nom: "Léo", age: 22, note: 15 },
  { nom: "Sophie", age: 20, note: 12 },
  { nom: "Mila", age: 23, note: 17 }
];

// Trouver l'index de Sophie et modifier sa note
const indexSophie = etudiants.findIndex(etudiant => etudiant.nom === "Sophie");

if (indexSophie !== -1) {
  etudiants[indexSophie].note = 16;  // Modification de la note
}

console.log(etudiants);
```

---

### Exercice 8 : Supprimer un objet précis dans un tableau

```javascript
const etudiants = [
  { nom: "Léo", age: 22, note: 15 },
  { nom: "Sophie", age: 20, note: 12 },
  { nom: "Mila", age: 23, note: 17 }
];

// Trouver l'index de Mila et la supprimer
const indexMila = etudiants.findIndex(etudiant => etudiant.nom === "Mila");

if (indexMila !== -1) {
  etudiants.splice(indexMila, 1);  // Suppression de l'étudiant
}

console.log(etudiants);
```

---

### Exercice 9 : Afficher un objet spécifique

```javascript
const etudiants = [
  { nom: "Léo", age: 22, note: 15 },
  { nom: "Sophie", age: 20, note: 12 },
  { nom: "Mila", age: 23, note: 17 }
];

// Trouver et afficher l'objet correspondant à Léo
const leo = etudiants.find(etudiant => etudiant.nom === "Léo");

if (leo) {
  console.log(leo);
}
```

---

### Exercice 10 : Trier un tableau d'objets

```javascript
const etudiants = [
  { nom: "Léo", age: 22, note: 15 },
  { nom: "Sophie", age: 20, note: 12 },
  { nom: "Mila", age: 23, note: 17 },
  { nom: "Jules", age: 21, note: 14 }
];

// Trier les étudiants par note croissante
etudiants.sort((a, b) => a.note - b.note);

console.log(etudiants);
```

---

### Exercice 11 : Trouver tous les objets qui satisfont une condition

```javascript
const etudiants = [
  { nom: "Léo", age: 22, note: 15 },
  { nom: "Sophie", age: 20, note: 12 },
  { nom: "Mila", age: 23, note: 17 },
  { nom: "Jules", age: 21, note: 14 }
];

// Filtrer les étudiants avec une note > 14
const bonsEtudiants = etudiants.filter(etudiant => etudiant.note > 14);

console.log(bonsEtudiants);
```

---
