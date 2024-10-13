# 1. Objet

## Exercice 1 : Déstructuration d'un tableau
Créez un tableau nommé `fruits` contenant les éléments suivants : `"pomme"`, `"banane"`, et `"orange"`. Utilisez la déstructuration pour assigner chaque fruit à une variable séparée : `fruit1`, `fruit2`, et `fruit3`. Affichez ensuite chaque variable dans la console.

## Exercice 2 : Déstructuration d'un objet
Créez un objet nommé `voiture` avec deux propriétés : `marque` avec la valeur `"Tesla"` et `modèle` avec la valeur `"Model 3"`. Utilisez la déstructuration pour assigner ces propriétés à des variables séparées nommées `marque` et `modèle`. Affichez ensuite ces variables dans la console.

## Exercice 3 : Opérateur spread avec un tableau
Créez un tableau `nombres` contenant les nombres `5`, `10`, et `15`. Utilisez l'opérateur spread pour créer un nouveau tableau nommé `nouveauxNombres` qui contient tous les éléments de `nombres`, ainsi que le nombre `20` à la fin. Affichez ensuite le nouveau tableau dans la console.

## Exercice 4 : Opérateur spread avec un objet
Créez un objet `ordinateur` avec deux propriétés : `marque` avec la valeur `"Apple"` et `modèle` avec la valeur `"MacBook Pro"`. Utilisez l'opérateur spread pour créer un nouvel objet `nouvelOrdinateur` qui contient toutes les propriétés de l'objet `ordinateur` et ajoutez une nouvelle propriété `année` avec la valeur `2024`. Affichez ensuite le nouvel objet dans la console.


## Exercice 5 : Afficher une liste d'objets
Créez un tableau d'objets représentant des **étudiants** avec les propriétés `nom`, `age`, et `note`.
Affichez ensuite chaque étudiant dans la console.

```js
const etudiants = [
  { nom: "Léo", age: 22, note: 15 },
  { nom: "Sophie", age: 20, note: 12 },
  { nom: "Mila", age: 23, note: 17 }
];
```

Utilisez une boucle `forEach()` pour parcourir le tableau et afficher chaque objet dans la console.

---

## Exercice 6 : Ajouter un nouvel objet à un tableau
Utilisez le tableau d'étudiants de l'exercice précédent et ajoutez un nouvel étudiant au tableau avec le nom "Jules", l'âge 21, et une note de 14.

Utilisez la méthode `push()` pour ajouter l'objet au tableau.

---

## Exercice 7 : Modifier un objet dans un tableau et le remettre à la même position
Toujours en utilisant le tableau d'étudiants, modifiez la note de "Sophie" pour qu'elle soit égale à 16. Mettez à jour l'objet dans le tableau sans changer sa position.

Trouve l'index de l'objet correspondant avec `findIndex()`, puis accède à l'objet directement via son index pour modifier la propriété `note`.

---

## Exercice 8 : Supprimer un objet précis dans un tableau
Supprimez l'étudiant nommé "Mila" du tableau.

Utilisez la méthode `findIndex()` pour obtenir l'index de l'étudiant à supprimer, puis utilisez `splice()` pour retirer cet élément du tableau.

---

## Exercice 9 : Afficher un objet spécifique
Affichez uniquement les informations de l'étudiant dont le nom est "Léo".

Utilisez la méthode `find()` pour localiser l'objet correspondant à "Léo".

---

## Exercice 10: Trier un tableau d'objets
Triez le tableau d'étudiants par ordre croissant de `note`.

Utilisez la méthode `sort()` en passant une fonction de comparaison qui compare la propriété `note` de deux objets.

---

## Exercice 11 : Trouver tous les objets qui satisfont une condition
Affiche uniquement les étudiants qui ont une note supérieure à 14.

Utilisez la méthode `filter()` pour créer un nouveau tableau contenant uniquement les objets qui répondent à la condition `note > 14`.

---
