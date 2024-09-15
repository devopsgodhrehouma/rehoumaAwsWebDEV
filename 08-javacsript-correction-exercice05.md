
### Code JavaScript pour la validation du formulaire

![Uploading image.png…]()

```javascript
// Fonction pour vérifier que le champ "Nom" n'est pas vide
function verifierNom() {
    var formulaire = document.forms[0]; // Accéder au premier formulaire de la page
    var nom = formulaire.elements["nom"].value; // Accéder à la valeur du champ "Nom"
    if (nom.trim() === "") { // Vérifier que le nom n'est pas vide
        alert("Le champ Nom ne doit pas être vide.");
        return false;
    }
    return true;
}

// Fonction pour vérifier que le champ "CIN" est numérique et de longueur supérieure à 8 caractères
function verifierCIN() {
    var formulaire = document.forms[0]; // Accéder au premier formulaire de la page
    var cin = formulaire.elements["CIN"].value; // Accéder à la valeur du champ "CIN"
    if (!cin || cin.length <= 8 || isNaN(Number(cin))) { // Vérifier la longueur et si c'est numérique
        alert("Le champ CIN doit être numérique et contenir plus de 8 caractères.");
        return false;
    }
    return true;
}

// Fonction pour valider le formulaire entier
function validerFormulaire() {
    return verifierNom() && verifierCIN(); // Vérifier les deux champs avant de soumettre
}

// Ajout de l'écouteur d'événement pour la validation lors de la soumission du formulaire
document.forms[0].onsubmit = validerFormulaire;
```

### Explications
1. **verifierNom()** : Cette fonction vérifie que le champ 'Nom' n'est pas vide. Elle accède au formulaire et au champ via `document.forms[0].elements["nom"]`, puis vérifie si la valeur est vide après avoir retiré les espaces blancs avec `trim()`.

2. **verifierCIN()** : Cette fonction s'assure que la valeur entrée dans le champ 'CIN' est numérique et a une longueur de plus de 8 caractères. Elle utilise `isNaN(Number(cin))` pour tester si la valeur est numérique.

3. **validerFormulaire()** : Cette fonction globale appelle les deux fonctions de validation et ne permet la soumission du formulaire que si les deux champs passent leurs validations respectives.

4. **Écouteur d'événement** : `document.forms[0].onsubmit` est utilisé pour lier la fonction `validerFormulaire` à l'événement de soumission du formulaire, assurant que la validation est exécutée avant que le formulaire ne soit réellement soumis.

