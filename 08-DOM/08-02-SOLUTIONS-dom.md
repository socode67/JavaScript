# 2. Le DOM

## Exercice 1 
```js
const paragrapheNormal = document.querySelector(".texte-normal");
paragrapheNormal.classList.add("highlight");

```

## Exercice 2 
```js
const image = document.getElementById("monImage");
image.classList.remove("hidden");

```

## Exercice 3 
```js
const box = document.getElementById("box");
box.classList.toggle("border");

```
## Exercice 4 
```js
const premierItem = document.querySelector(".item");
console.log(premierItem.classList.contains("highlight"));
```
## Exercice 5 
```js
const paragraphsImportants = document.querySelectorAll(".texte-important");
paragraphsImportants.forEach(paragraph => {
    paragraph.classList.add("highlight", "border");
    paragraph.classList.remove("texte-important");
});
```
## Exercice 6 
```js
const mainTitle = document.getElementById("main-title");
mainTitle.classList.toggle("highlight");
console.log(mainTitle.classList.contains("highlight"));
```