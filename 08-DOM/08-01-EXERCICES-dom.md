# 1. Le DOM

## Code HTML 

```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Exploration du DOM</title>
    <style>
        .texte-important {
            color: blue;
        }
    </style>
</head>
<body>

    <h1 id="titre">Bienvenue sur la Page d'Exploration du DOM</h1>

    <p class="texte-important">Ce paragraphe contient des informations essentielles à retenir.</p>
    <p class="texte-important">Voici un autre paragraphe crucial pour comprendre le DOM.</p>

    <img id="monImage" src="https://via.placeholder.com/150" alt="Image illustrative du DOM">

    <p>Ceci est un simple paragraphe qui sert d'exemple basique.</p>
    <p>Un autre paragraphe standard pour tester les sélections du DOM.</p>

    <h2>Titre Secondaire : Introduction au DOM</h2>
    <h2>Titre Secondaire : Concepts Avancés du DOM</h2>

    <script src="script.js"></script>
</body>
</html>

```

## Exercice 1

Sélectionnez l’élément avec l’ID `titre` et modifiez son contenu texte pour afficher : `"Exploration du DOM avec JavaScript"`.

## Exercie 2

Sélectionnez le premier paragraphe avec la classe `texte-important` et changez son texte pour : `"Texte important modifié avec querySelector"`.

## Exercice 3

Utilisez querySelectorAll pour sélectionner tous les éléments <h2>.
Modifiez le texte de chaque titre secondaire pour : `"Titre modifié avec querySelectorAll"`.

**Indice** : `querySelectorAll()` renvoie une liste d'éléments, tu peux boucler dessus avec `forEach()`.

## Exercice 4

1. Sélectionnez l'image avec l'ID monImage et affichez la valeur de l'attribut src dans la console en utilisant `getAttribute`.
2.Changez la source de l'image pour une autre en utilisant `setAttribute`.


## Exercice 5

1. Modifiez l’attribut alt de l’image avec l’ID monImage pour : `"Nouvelle description de l'image"`.
2. Modifiez l’attribut title du premier titre secondaire <h2> pour : `"Titre secondaire modifié"`

## Exercice 6

1. Sélectionnez l’élément avec l’ID `titre` et modifiez sa couleur de texte en rouge.
2. Sélectionnez le premier paragraphe avec la classe `texte-important` et ajouter une couleur de fond jaune.
3. Modifiez la taille de l'image pour qu'elle ait une largeur de 200px.
