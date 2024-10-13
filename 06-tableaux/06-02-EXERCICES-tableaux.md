# 2. LES TABLEAUX

##  Gestion d'un Compte Bancaire

L'objectif de ces exercices est de créer un programme en JavaScript permettant de gérer un compte bancaire. Le programme doit offrir à l'utilisateur diverses options telles que la consultation du solde, l'ajout de virements ou de retraits, l'affichage des transactions et la conversion des montants dans différentes devises.

### Exercice 1 : Initialisation et affichage du solde
**Objectif** : Mettre en place le tableau des transactions et afficher le solde.

#### Étapes :
1. Créez un tableau vide nommé `transactions` pour stocker les montants.
2. Utilisez une variable `devise` initialisée à `"€"`.
3. Implémentez une fonction `calculerSolde()` qui utilise `reduce()` pour calculer le solde actuel du compte à partir du tableau `transactions`.
4. Créez une fonction `afficherSolde()` qui affiche le solde actuel.

**Exemple d'affichage :**
```
Solde actuel : 0 €
```

---

### Exercice 2 : Faire un virement
**Objectif** : Permettre à l'utilisateur d'ajouter des virements (montants positifs) au tableau.

#### Étapes :
1. Créez une fonction `faireVirement()` qui demande à l'utilisateur de saisir un montant positif pour un virement.
2. Ajoutez ce montant au tableau `transactions`.
3. Appelez `calculerSolde()` pour mettre à jour le solde.
4. Affichez le virement et le nouveau solde.

**Exemple d'affichage :**
```
Virement de 500 € effectué.
Solde actuel : 500 €
```

---

### Exercice 3 : Faire un retrait
**Objectif** : Permettre à l'utilisateur de retirer des montants, en s'assurant que le solde est suffisant.

#### Étapes :
1. Créez une fonction `faireRetrait()` qui demande à l'utilisateur de saisir un montant pour un retrait.
2. Vérifiez que le solde est suffisant pour effectuer ce retrait.
3. Si c'est possible, enregistrez le retrait comme un montant négatif dans `transactions`, puis affichez le retrait et le nouveau solde.
4. Si le solde est insuffisant, affichez un message d'erreur.

**Exemple d'affichage (si le retrait est réussi) :**
```
Retrait de 300 € effectué.
Solde actuel : 200 €
```

**Exemple d'affichage (si le solde est insuffisant) :**
```
Solde insuffisant. Retrait refusé.
```

---

### Exercice 4 : Afficher toutes les transactions
**Objectif** : Permettre à l'utilisateur de visualiser toutes les transactions.

#### Étapes :
1. Créez une fonction `afficherTransactions()` qui parcourt le tableau `transactions` avec `forEach()`.
2. Affichez chaque transaction en précisant si elle est un virement ou un retrait, ainsi que la devise.

**Exemple d'affichage :**
```
Transactions :
Virement de 500 €
Retrait de 300 €
Virement de 200 €
```

---

### Exercice 5 : Afficher les statistiques des transactions
**Objectif** : Calculer et afficher des statistiques sur les transactions.

#### Étapes :
1. Créez une fonction `afficherStatistiques()` qui utilise `filter()` pour séparer les virements (montants positifs) des retraits (montants négatifs).
2. Utilisez `reduce()` pour calculer les montants cumulés des virements et des retraits.
3. Affichez le nombre total de virements et de retraits ainsi que les montants cumulés.

**Exemple d'affichage :**
```
Statistiques des transactions :
Nombre de virements : 3 | Montant total des virements : 1200 €
Nombre de retraits : 2 | Montant total des retraits : 500 €
```

---

### Exercice 6 : Filtrer les virements par montant minimum
**Objectif** : Filtrer et afficher les virements supérieurs à un montant défini par l'utilisateur.

#### Étapes :
1. Créez une fonction `filtrerVirements()` qui demande à l'utilisateur de spécifier un montant minimum.
2. Utilisez `filter()` pour créer un tableau de tous les virements supérieurs à ce montant.
3. Utilisez `forEach()` pour afficher ces virements.

**Exemple d'affichage :**
```
Virements supérieurs à 500 € :
Virement de 1000 €
Virement de 1200 €
```

---

### Exercice 7 : Convertir les transactions et le solde en devise ($ ou £)
**Objectif** : Convertir toutes les transactions et le solde dans une nouvelle devise.

#### Étapes :
1. Créez une fonction `convertirDevise()` qui demande à l'utilisateur de choisir entre `$` ou `£`.
2. Utilisez `map()` pour appliquer les taux de conversion correspondants à chaque transaction et mettez à jour le tableau `transactions`.
3. Recalculez le solde avec `calculerSolde()` après conversion.
4. Affichez les transactions converties et le solde dans la nouvelle devise.

**Exemple d'affichage :**
```
Transactions converties en $ :
Virement de 550 $
Retrait de 330 $
Virement de 1100 $

Solde converti : 1320 $
```

---

### Exercice 8 : Menu interactif
**Objectif** : Mettre en place un menu qui permet à l'utilisateur de naviguer entre différentes fonctionnalités du programme.

#### Étapes :
1. Créez une fonction `afficherMenu()` qui affiche le menu interactif avec les options suivantes :
   1. Afficher le solde
   2. Faire un virement
   3. Faire un retrait
   4. Afficher les transactions
   5. Afficher les statistiques
   6. Filtrer les virements par montant minimum
   7. Convertir les transactions en devise ($ ou £)
   8. Quitter

2. Demandez à l'utilisateur de saisir son choix et, en fonction de ce choix, appelez la fonction correspondante.

**Exemple d'affichage :**
```
1. Afficher le solde
2. Faire un virement
3. Faire un retrait
4. Afficher les transactions
5. Afficher les statistiques
6. Filtrer les virements par montant minimum
7. Convertir les transactions en devise ($ ou £)
8. Quitter
Choisissez une option :
```
---

### Exercice 9 : Gérer le choix de l'utilisateur
**Objectif** : Implémenter le choix de l'utilisateur et appeler la fonction adéquate selon l'option choisie dans le menu.

#### Étapes :
1. Créez une boucle `while` qui continue d'afficher le menu jusqu'à ce que l'utilisateur choisisse l'option "Quitter".
2. Après avoir affiché le menu, demandez à l'utilisateur de saisir son choix (un nombre de 1 à 8).
3. En fonction du choix de l'utilisateur :
   - Si l'utilisateur choisit 1, appelez la fonction `afficherSolde()`.
   - Si l'utilisateur choisit 2, appelez la fonction `faireVirement()`.
   - Si l'utilisateur choisit 3, appelez la fonction `faireRetrait()`.
   - Si l'utilisateur choisit 4, appelez la fonction `afficherTransactions()`.
   - Si l'utilisateur choisit 5, appelez la fonction `afficherStatistiques()`.
   - Si l'utilisateur choisit 6, appelez la fonction `filtrerVirements()`.
   - Si l'utilisateur choisit 7, appelez la fonction `convertirDevise()`.
   - Si l'utilisateur choisit 8, terminez la boucle et quittez le programme.

4. Gérer les saisies incorrectes (si l'utilisateur entre un choix non valide, affichez un message d'erreur).

**Exemple d'affichage en cas de choix invalide :**
```
Choix invalide. Veuillez choisir une option entre 1 et 8.
```