![Uploading image.png…]()


# Correction: 
Pour cet exercice, nous allons utiliser la méthode `document.getElementById` pour accéder aux éléments et gérer l'affichage des alertes en fonction de la sélection des cases à cocher. C'est une manière fondamentale d'interagir avec les éléments du DOM en JavaScript, parfaite pour les débutants. Voici un exemple de script pour réaliser cet exercice :

### Structure HTML

```html
<!DOCTYPE html>
<html lang="fr">
<head>
    <meta charset="UTF-8">
    <title>Exercice 6</title>
</head>
<body>
    <h2>Je maîtrise :</h2>
    <input type="checkbox" id="css" name="skills"> CSS<br>
    <input type="checkbox" id="javascript" name="skills"> JavaScript<br>
    <button onclick="afficherChoix()">Choisir</button>

    <script src="script.js"></script>
</body>
</html>
```

### Script JavaScript (script.js)

```javascript
function afficherChoix() {
    var css = document.getElementById('css').checked;
    var javascript = document.getElementById('javascript').checked;
    var message = '';

    if (css && javascript) {
        message = 'CSS et JavaScript';
    } else if (css) {
        message = 'CSS';
    } else if (javascript) {
        message = 'JavaScript';
    }

    if (message) {
        alert(message);
    } else {
        alert('Aucune compétence sélectionnée.');
    }
}
```

### Explications

1. **Structure HTML** : Définit deux cases à cocher pour CSS et JavaScript, et un bouton qui déclenche la fonction `afficherChoix()` lorsqu'on clique dessus.

2. **Script JavaScript** :
   - **afficherChoix()** : Cette fonction vérifie si chaque case à cocher est sélectionnée en utilisant `document.getElementById('id').checked`.
   - **Construction du message** : Selon les cases cochées, le message est construit pour refléter le choix de l'utilisateur.
   - **Affichage du message** : Une alerte est affichée avec le message approprié ou un message par défaut si aucune compétence n'est sélectionnée.

