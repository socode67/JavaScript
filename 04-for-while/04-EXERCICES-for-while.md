# LES BOUCLES FOR ET WHILE

## Exercice 1

Créez une simulation de jeu où le joueur doit deviner un nombre aléatoire compris entre 1 et 10.

1. Initialisez une variable `nombreSecret` avec un nombre aléatoire entre 1 et 10.
```js
const nombreSecret = Math.floor(Math.random() * 10) + 1;
```
2. À l'aide d'une boucle, demandez au joueur de deviner le nombre secret.
3. Continuez à demander la saisie **tant que** la réponse du joueur n'est pas égale au nombreSecret.
4. Indiquez à l'utilisateur si le nombre qu'il a saisi est trop grand ou trop petit.
5. Affichez un message de félicitations lorsque le joueur devine correctement et sortez de la boucle.

## Exercice 2

Créez un programme qui génère une table de multiplication pour un nombre donné.

1. Demandez à l'utilisateur de fournir un nombre pour lequel il souhaite générer la table de multiplication.
2. Utilisez une boucle pour générer et afficher la table de multiplication de ce nombre de 1 à 10.
3. Assurez-vous que le résultat est clairement formaté et facile à lire.

## Exercice 3

Créez une application de compte à rebours.

1. Demandez à l'utilisateur de saisir une valeur initiale pour le compte à rebours.
2. Utilisez une boucle for pour décrémenter la valeur initiale du compte à rebours jusqu'à atteindre zéro
3. À chaque itération, affichez la valeur actuelle du compte à rebours.
4. Lorsque le compte à rebours atteint zéro, démarrez une boucle while.
5. Dans la boucle while, demandez à l'utilisateur s'il souhaite recommencer le compte à rebours tant qu'il ne répond pas par oui ou par non.
7. Si la réponse est "oui", redemandez une nouvelle valeur initiale et répétez le processus.
8. Si la réponse est "non", affichez un message de fin et sortez de la boucle.

## Exercice 4

Créez un programme qui calcule la somme des nombres pairs compris entre deux valeurs données par l'utilisateur.

1. Demandez à l'utilisateur d'entrer deux nombres : une valeur de départ et une valeur de fin.
2. Utilisez une boucle for pour parcourir tous les nombres entre ces deux valeurs (inclus).
3. Vérifiez si chaque nombre est pair.
4. Si un nombre est pair, ajoutez-le à une variable qui stocke la somme totale.
5. À la fin de la boucle, affichez la somme des nombres pairs.
