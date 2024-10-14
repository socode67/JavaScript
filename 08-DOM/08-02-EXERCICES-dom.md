# 2. Le DOM

## Code HTML 

```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Manipulation des Classes avec classList</title>
    <style>
        .highlight {
            background-color: yellow;
        }
        .hidden {
            display: none;
        }
        .border {
            border: 2px solid black;
        }
    </style>
</head>
<body>

    <h1 id="main-title">Bienvenue dans la Manipulation des Classes</h1>

    <p class="texte-normal">Ceci est un paragraphe normal.</p>
    <p class="texte-important">Ceci est un paragraphe important.</p>
    <p class="texte-important">Encore un autre paragraphe important.</p>

    <ul>
        <li class="item">Élément de liste 1</li>
        <li class="item">Élément de liste 2</li>
        <li class="item">Élément de liste 3</li>
    </ul>

    <div id="box" class="border">Ceci est une boîte avec une bordure.</div>

    <img id="monImage" src="https://via.placeholder.com/150" alt="Image illustrative" class="hidden">

    <script src="script.js"></script>

</body>
</html>

```

## Exercice 1 
Sélectionnez le paragraphe avec la classe `texte-normal` et ajoutez-lui la classe `highlight` pour le mettre en surbrillance.

## Exercice 2 
Sélectionnez l'image avec l'ID `monImage` et supprimez la classe `hidden` pour l'afficher à l'écran.

## Exercice 3 
Sélectionnez la boîte avec l'ID box et utilisez `toggle()` pour ajouter ou retirer la classe `border`. Faites en sorte que cette boîte n'ait plus de bordure.

## Exercice 4 
Sélectionnez un élément de liste avec la classe `item` et vérifiez s'il possède déjà la classe `highlight`. Affichez le résultat dans la console (true ou false).

## Exercice 5 
Sélectionnez tous les paragraphes avec la classe `texte-important` et ajoutez-leur à la fois les classes `highlight` et `border`. Supprimez ensuite la classe `texte-important` de ces mêmes paragraphes.

## Exercice 6 
1. Sélectionnez le titre principal avec l'ID `main-title`.
2. Ajoutez-lui la classe `highlight`.
3. Si la classe `highlight` est déjà présente, supprimez-la, sinon ajoutez-la à nouveau.
4. Affichez dans la console si la classe `highlight` est présente ou non.