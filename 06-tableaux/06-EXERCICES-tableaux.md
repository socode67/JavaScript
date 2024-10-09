# LES TABLEAUX

##  Gestion d'un Compte Bancaire avec Conversion Monétaire, Filtrage et Tableau Unique

L'objectif de cet exercice est de créer un programme en JavaScript permettant de gérer un compte bancaire. Le programme doit offrir à l'utilisateur diverses options telles que la consultation du solde, l'ajout de virements ou de retraits, l'affichage des transactions et la conversion des montants dans différentes devises.

### **Étapes à réaliser :**

#### **1. Initialisation :**
- Créez un tableau vide `transactions` pour stocker toutes les transactions du compte.  
   - **Les virements** seront représentés par des nombres positifs.
   - **Les retraits** seront représentés par des nombres négatifs.
- Créez une variable `devise` initialisée à `"€"` pour représenter la devise courante du compte.

#### **2. Menu Principal :**
Affichez un menu interactif proposant à l'utilisateur les options suivantes :
1. Afficher le solde
2. Faire un virement
3. Faire un retrait
4. Afficher la totalité des transactions
5. Afficher les statistiques des transactions
6. Filtrer les virements par montant minimum
7. Convertir les transactions et le solde en devise ($ ou £)
8. Quitter

### **Fonctionnalités à développer et format des réponses à afficher :**

#### **1. Afficher le solde :**
- Utilisez la méthode `reduce()` pour calculer le solde à partir des transactions présentes dans le tableau `transactions`.
- **Format d'affichage dans la console :**

   ```
   Solde actuel : 1200 €
   ```

#### **2. Faire un virement :**
- Demandez à l'utilisateur de saisir le montant du virement.
- Ajoutez ce montant au tableau `transactions`.
- Recalculez le solde après l'ajout du virement en utilisant `reduce()`.
- **Format d'affichage dans la console :**
   ```
   Virement de 500 € effectué.
   Solde actuel : 1700 €
   ```

#### **3. Faire un retrait :**
- Demandez à l'utilisateur de saisir le montant du retrait (un nombre positif).
- Ajoutez ce montant en tant que nombre négatif dans le tableau `transactions` pour enregistrer le retrait.
- Avant d'ajouter le retrait, vérifiez que le solde actuel est suffisant pour permettre l'opération.
- **Format d'affichage dans la console (si le retrait est autorisé) :**
   ```
   Retrait de 300 € effectué.
   Solde actuel : 900 €
   ```
- **Si le retrait dépasse le solde disponible :**
   ```
   Solde insuffisant. Retrait refusé.
   ```

#### **4. Afficher la totalité des transactions :**
- Utilisez `forEach()` pour parcourir le tableau `transactions`.
- Affichez chaque transaction, en précisant si elle représente un virement ou un retrait, et indiquez la devise associée.
- **Format d'affichage dans la console :**
   ```
   Transactions :
   Virement de 500 €
   Retrait de 300 €
   Virement de 1000 €
   ```

#### **5. Afficher les statistiques des transactions :**
- Utilisez `reduce()` pour calculer les montants totaux des virements et des retraits séparément.
- Utilisez `filter()` pour différencier les virements (montants positifs) des retraits (montants négatifs).
- Affichez le nombre total de virements et de retraits ainsi que les montants cumulés pour chacun.
- **Format d'affichage dans la console :**
   ```
   Statistiques des transactions :
   Nombre de virements : 3 | Montant total des virements : 2500 €
   Nombre de retraits : 2 | Montant total des retraits : 700 €
   ```

#### **6. Filtrer les virements par montant minimum :**
- Demandez à l'utilisateur de spécifier un montant minimum pour filtrer les virements.
- Utilisez `filter()` pour sélectionner les virements supérieurs à ce montant minimum.
- Affichez les virements filtrés en utilisant `forEach()`.
- **Format d'affichage dans la console :**
   ```
   Virements supérieurs à 500 € :
   Virement de 1000 €
   Virement de 1500 €
   ```

#### **7. Convertir les transactions et le solde en devise (€, $ ou£) :**
- Utilisez la méthode `map()` pour appliquer un taux de conversion sur toutes les transactions en fonction de la devise cible :
  - Conversion de l'euro (€) vers le dollar ($) : multiplier par 1.09.
  - Conversion de l'euro (€) vers la livre (£) : multiplier par 0.84.
  - Conversion du dollar ($) vers l'euro (€) : multiplier par 0.91.
  - Conversion de la livre (£) vers l'euro (€) : multiplier par 1.19.
- Demandez à l'utilisateur de choisir entre la devise dollar ($) ou livre sterling (£).
- Appliquez le taux de conversion sur toutes les transactions via `map()` et mettez à jour la variable `devise`.
- Recalculez le solde dans la nouvelle devise et affichez-le.
- **Format d'affichage dans la console :**
   ```
   Transactions converties en $ :
   Virement de 550 $
   Retrait de 330 $
   Virement de 1100 $

   Solde converti : 1320 $
   ```

#### **8. Quitter :**
- Si l'utilisateur choisit l'option de quitter, terminez le programme.
- **Aucun affichage supplémentaire nécessaire.**

---

### **Exemple de Menu Interactif :**

```
1. Afficher le solde
2. Faire un virement
3. Faire un retrait
4. Afficher la totalité des transactions
5. Afficher les statistiques des transactions
6. Filtrer les virements par montant minimum
7. Convertir les transactions et le solde en devise ($ ou £)
8. Quitter
Choisissez une option :
```

---

### **Fonctions à implémenter :**

Utilisez les méthodes JavaScript `map()`, `filter()`, `reduce()`, et `forEach()` pour développer les fonctions suivantes :

1. **cacluclerSolde()**
    - Calcule et retourne le solde actuel du compte en utilisant `reduce()` sur le tableau `transactions`.

2. **`afficherSolde()`**
   - Calcule et affiche le solde actuel du compte en utilisant `reduce()`.

3. **`faireVirement()`**
   - Demande le montant du virement à l'utilisateur, l'ajoute au tableau `transactions`, puis met à jour le solde.

4. **`faireRetrait()`**
   - Demande le montant du retrait à l'utilisateur, vérifie si le solde est suffisant, puis l'ajoute en tant que montant négatif dans `transactions`.

5. **`afficherTransactions()`**
   - Parcourt le tableau `transactions` et affiche chaque transaction, en précisant si elle est un virement ou un retrait.

6. **`afficherStatistiques()`**
   - Calcule et affiche les statistiques des transactions : total des virements, total des retraits et le nombre de chaque type.

7. **`filtrerVirements()`**
   - Filtre et affiche les virements supérieurs à un montant minimum fourni par l'utilisateur.

8. **`convertirDevise()`**
   - Utilise `map()` pour appliquer le taux de conversion à chaque transaction dans le tableau `transactions`, et met à jour la variable `devise` ainsi que le solde.
