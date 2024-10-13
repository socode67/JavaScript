# 2. LES TABLEAUX

##  Gestion d'un Compte Bancaire

### Exercice 1 : Initialisation et affichage du solde

```js
// Initialisation
let transactions = [];
let devise = "€";

// Fonction pour calculer le solde
function calculerSolde() {
    return transactions.reduce((acc, transaction) => acc + transaction, 0);
}

// Fonction pour afficher le solde
function afficherSolde() {
    let solde = calculerSolde();
    console.log(`Solde actuel : ${solde} ${devise}`);
}
```

---

### Exercice 2 : Faire un virement

```js
// Fonction pour faire un virement
function faireVirement() {
    let montant = parseFloat(prompt("Entrez le montant du virement :"));
    if (montant > 0) {
        transactions.push(montant);
        console.log(`Virement de ${montant} ${devise} effectué.`);
        afficherSolde();
    } else {
        console.log("Le montant doit être supérieur à zéro.");
    }
}

```

---

### Exercice 3 : Faire un retrait

```js
// Fonction pour faire un retrait
function faireRetrait() {
    let montant = parseFloat(prompt("Entrez le montant du retrait :"));
    let solde = calculerSolde();
    
    if (montant > 0 && solde >= montant) {
        transactions.push(-montant); // Retrait enregistré comme un montant négatif
        console.log(`Retrait de ${montant} ${devise} effectué.`);
        afficherSolde();
    } else if (montant > solde) {
        console.log("Solde insuffisant. Retrait refusé.");
    } else {
        console.log("Le montant doit être supérieur à zéro.");
    }
}
```

---

### Exercice 4 : Afficher toutes les transactions

```js
// Fonction pour afficher toutes les transactions
function afficherTransactions() {
    console.log("Transactions :");
    transactions.forEach(transaction => {
        if (transaction > 0) {
            console.log(`Virement de ${transaction} ${devise}`);
        } else {
            console.log(`Retrait de ${Math.abs(transaction)} ${devise}`);
        }
    });
}
```

---

### Exercice 5 : Afficher les statistiques des transactions

```js
// Fonction pour afficher les statistiques des transactions
function afficherStatistiques() {
    let virements = transactions.filter(transaction => transaction > 0);
    let retraits = transactions.filter(transaction => transaction < 0);
    
    let totalVirements = virements.reduce((acc, virement) => acc + virement, 0);
    let totalRetraits = retraits.reduce((acc, retrait) => acc + retrait, 0);
    
    console.log(`Statistiques des transactions :`);
    console.log(`Nombre de virements : ${virements.length} | Montant total des virements : ${totalVirements} ${devise}`);
    console.log(`Nombre de retraits : ${retraits.length} | Montant total des retraits : ${Math.abs(totalRetraits)} ${devise}`);
}

```

---

### Exercice 6 : Filtrer les virements par montant minimum

```js
// Fonction pour filtrer les virements par montant minimum
function filtrerVirements() {
    let montantMin = parseFloat(prompt("Entrez le montant minimum pour filtrer les virements :"));
    
    let virementsFiltres = transactions.filter(transaction => transaction > montantMin);
    
    console.log(`Virements supérieurs à ${montantMin} ${devise} :`);
    virementsFiltres.forEach(virement => {
        console.log(`Virement de ${virement} ${devise}`);
    });
}
```

---

### Exercice 7 : Convertir les transactions et le solde en devise ($ ou £)

```js
// Fonction pour convertir les transactions en devise
function convertirDevise() {
    let nouvelleDevise = prompt("Entrez la devise de conversion ($ ou £) :");
    let tauxConversion;
    
    if (nouvelleDevise === "$") {
        tauxConversion = 1.09;
    } else if (nouvelleDevise === "£") {
        tauxConversion = 0.84;
    } else {
        console.log("Devise non valide.");
        return;
    }
    
    // Conversion des transactions
    transactions = transactions.map(transaction => parseFloat((transaction * tauxConversion).toFixed(2)));
    
    // Mise à jour de la devise
    devise = nouvelleDevise;
    
    console.log(`Transactions converties en ${devise} :`);
    afficherTransactions();
    afficherSolde();
}
```

---

### Exercice 8 : Menu interactif

```js
// Fonction pour afficher le menu avec un prompt
function afficherMenu() {
    return prompt(
        `Menu Principal :
        1. Afficher le solde
        2. Faire un virement
        3. Faire un retrait
        4. Afficher les transactions
        5. Afficher les statistiques
        6. Filtrer les virements par montant minimum
        7. Convertir les transactions en devise ($ ou £)
        8. Quitter`
    );
}

```

---

### Exercice 9 : Gérer le choix de l'utilisateur

```js
// Fonction pour gérer le choix de l'utilisateur avec le menu en prompt
function choixUtilisateur() {
    let quitter = false;
    
    while (!quitter) {
        let choix = afficherMenu(); // On récupère le choix de l'utilisateur via un prompt
        
        switch (parseInt(choix)) { // Convertir le choix en nombre entier
            case 1:
                afficherSolde();
                break;
            case 2:
                faireVirement();
                break;
            case 3:
                faireRetrait();
                break;
            case 4:
                afficherTransactions();
                break;
            case 5:
                afficherStatistiques();
                break;
            case 6:
                filtrerVirements();
                break;
            case 7:
                convertirDevise();
                break;
            case 8:
                quitter = true;
                alert("Au revoir !");
                break;
            default:
                alert("Choix invalide. Veuillez choisir une option entre 1 et 8.");
                break;
        }
    }
}

// Exemple d'appel pour lancer le menu
choixUtilisateur();
```
