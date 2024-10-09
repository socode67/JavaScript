# LES TABLEAUX

##  Gestion d'un Compte Bancaire avec Conversion Monétaire, Filtrage et Tableau Unique

```js
let transactions = [];
let devise = "€";
let choix;

const afficherMenu = () => {
    choix = prompt(`
        1 : Afficher le solde
        2 : Faire un virement
        3 : Faire un retrait
        4 : Afficher la totalité des transactions
        5 : Afficher les statistiques des transactions
        6 : Filtrer les virements par montant minimum
        7 : Convertir les transactions et le solde en devise ($ ou £)
        8 : Quitte
    `);
}

// Calculer solde
const calculerSolde = () => transactions.reduce((somme, montant) => somme += montant, 0);

// Afficher le solde
const afficherSolde = () => {
    const solde = calculerSolde();
    console.log(`Solde actuel : ${solde} ${devise}`)
    console.log("------------------------------------------------")
}

// Faire un virement
const faireVirement = (virement) => {
    transactions.push(virement);
    console.log(`Virement de ${virement} ${devise} effectué.`)
    afficherSolde();
}

//Faire un retrait
const faireRetrait = (retrait) => {
    
    const soldeActuel = calculerSolde();

    if(soldeActuel >= retrait){
        transactions.push(-retrait);
        const NouveauSolde = calculerSolde();
        console.log(`Retrait de ${retrait} ${devise} effectué.`);
        console.log(`Nouveau solde : ${NouveauSolde} ${devise}`)
        console.log("------------------------------------------------")
    }else{
        console.log("Solde insuffisant. Retrait refusé")
    }

}

// Afficher la totalité des transactions
const afficherTransactions = () => {
    console.log("Transactions : ");
    transactions.forEach(transc => {
        let type = transc > 0 ? "Virement" : "Retrait";
        let montant = transc < 0 ? -transc : transc;
        console.log(`${type} de ${montant} ${devise}`)
    })
    console.log("------------------------------------------------")
}

// Afficher les statistiques des transactions :
const afficherStatistiques = () => {
    const virement = transactions.filter(montant => montant > 0);
    const sommeVirements = virement.reduce((somme, montant) => somme += montant, 0);
    console.log(`Nombre de virements : ${virement.length} | Montant total des virements ${sommeVirements} ${devise}`)


    const retrait = transactions.filter(montant => montant < 0);
    const sommeRetrait = retrait.reduce((somme, montant) => somme += -montant, 0)
    console.log(`Nombre de retraits : ${retrait.length} | Montant total des retraits ${sommeRetrait} ${devise}`)
    console.log("------------------------------------------------")
}

// Filtrer les virements par montant minimum
const filtrerVirements = (filtre) => {
    const montantFiltre = transactions.filter(montant => montant >= filtre);
    console.log(`Virements supérieurs à ${filtre} ${devise}`);
    montantFiltre.forEach(montant => console.log(`Virement de ${montant} ${devise}`))
    console.log("------------------------------------------------")
}

// Convertir les transactions et le solde en devise (€, $ ou £)
const convertirDevise = (symboleDevise) => {

    switch (symboleDevise) {
        case "€":
            const tauxChange = devise == "$" ? 0.91 : 1.19;
            transactions = transactions.map(montant => parseFloat((montant * tauxChange).toFixed(2)));
            break;
        case "$":
            transactions = transactions.map(montant => parseFloat((montant * 1.09).toFixed(2)));
            break;
        case "£":
            transactions = transactions.map(montant => parseFloat((montant * 0.84).toFixed(2)));
            break;
        default:
            break;
    }

    devise = symboleDevise;

    console.log(`Transcations converties en ${devise}`);
    afficherTransactions();
}

do {
    afficherMenu();
    switch (choix) {
        case "1":
            afficherSolde();
            break;
        case "2":
            let montantVirement = parseFloat(prompt("Entrez le montant du virement :"));
            faireVirement(montantVirement);
            break;
        case "3":
            let montantRetrait = parseFloat(prompt("Entrez le montant du retrait :"));
            faireRetrait(montantRetrait);
            break;
        case "4":
            afficherTransactions();
            break;    
        case "5":
            afficherStatistiques();
            break;      
        case "6":
            let montantMinimum = parseFloat(prompt("Entrez le montant minimum pour filtrer les virements :"));
            filtrerVirements(montantMinimum);
            break;
        case "7":
            const conversion = devise === "€" ? "$ ou £" : "€";
            let nouvelleDevise = prompt(`
                Devise actuel
                "Convertir en devise (${conversion}) :"
            `);
            if (nouvelleDevise === "$" || nouvelleDevise === "£" || nouvelleDevise === "€") {
            convertirDevise(nouvelleDevise);
            } else {
            console.log("Devise non reconnue.");
            }
            break;
        case "8":
            console.log("Programme terminé.");
            break;
        default:
            console.log("Option non valide. Veuillez choisir une option valide.");
            break;
    }

} while (choix != 8);

```