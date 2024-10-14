# 1. Le DOM

## Exercice 1

```js
    const titre = document.getElementById("titre");
    titre.textContent = "Exploration du DOM avec JavaScript"
```

## Exercie 2

```js
const premierTxtImportant = document.querySelector(".texte-important");
premierTxtImportant.textContent = "Texte important modifié avec querySelector"
```
## Exercice 3

```js
const h2s = document.querySelectorAll("h2");
h2s.forEach(element => element.textContent = "Titre modifié avec querySelectorAll")
```

## Exercice 4

```js
const img = document.querySelector("#monImage")
console.log(img.getAttribute("src"))
img.setAttribute("src", "https://i.pravatar.cc/150")
```
## Exercice 5
```js
img.alt = "Nouvelle description de l'image";

const h2 = document.querySelector("h2")
h2.title = "Titre secondaire modifié"
```
## Exercice 6

```js
titre.style.color = "red";
premierTxtImportant.style.backgroundColor = "yellow"
img.style.width = "300px"
```