

# Énoncé : 


Pour l'exercice 8, vous devez développer un script JavaScript qui affiche une alerte avec le choix de l'utilisateur basé sur la case radio sélectionnée. Voici comment vous pourriez structurer votre code pour cet exercice :

![image](https://github.com/user-attachments/assets/40d18d74-6401-4e31-bfa9-c61d185b5913)


# Correction 1 : 

Pour une variante sans utiliser la boucle `for` et en utilisant trois conditions `if`, vous pouvez directement vérifier chaque bouton radio individuellement pour voir s'il est sélectionné. Voici comment vous pouvez structurer ce code :

### Code HTML
Comme précédemment, vous pouvez utiliser le même HTML sans modification.

### Script JavaScript (script.js)
```javascript
function afficherChoix() {
    var choix1 = document.getElementById('choix1').checked;
    var choix2 = document.getElementById('choix2').checked;
    var choix3 = document.getElementById('choix3').checked;

    if (choix1) {
        alert("Vous avez choisi le choix 1");
    } else if (choix2) {
        alert("Vous avez choisi le choix 2");
    } else if (choix3) {
        alert("Vous avez choisi le choix 3");
    } else {
        alert("Veuillez sélectionner un choix.");
    }
}
```

### Modifications HTML pour JavaScript
Vous devez ajouter des ID aux éléments `input` pour que le JavaScript puisse les identifier facilement.

```html
<input type="radio" id="choix1" name="choix" value="1"> Choix numéro 1<br>
<input type="radio" id="choix2" name="choix" value="2"> Choix numéro 2<br>
<input type="radio" id="choix3" name="choix" value="3"> Choix numéro 3<br>
<button type="button" onclick="afficherChoix()">Quel est votre choix ?</button>
```

### Explications
- **Variables pour chaque choix** : Les variables `choix1`, `choix2`, et `choix3` sont utilisées pour vérifier l'état (`checked`) de chaque bouton radio correspondant.
- **Conditions** : Chaque `if` vérifie si un bouton radio particulier est coché et affiche une alerte correspondante.
- **Alerte de non-sélection** : Si aucun choix n'est sélectionné, une alerte demande à l'utilisateur de faire une sélection.

Cette méthode est simple et directe, bien adaptée pour un petit nombre de choix où vous pouvez facilement gérer chaque condition séparément. Elle évite la complexité des boucles et est donc plus accessible pour les débutants en JavaScript.


# Correction 2 (Variante) : 


### Code HTML
```html
<!DOCTYPE html>
<html lang="fr">
<head>
    <meta charset="UTF-8">
    <title>Exercice 8</title>
</head>
<body>
    <h2>Entrez votre choix :</h2>
    <form id="form">
        <input type="radio" name="choix" value="1"> Choix numéro 1<br>
        <input type="radio" name="choix" value="2"> Choix numéro 2<br>
        <input type="radio" name="choix" value="3"> Choix numéro 3<br>
        <button type="button" onclick="afficherChoix()">Quel est votre choix ?</button>
    </form>
    <script src="script.js"></script>
</body>
</html>
```

### Script JavaScript (script.js)
```javascript
function afficherChoix() {
    var radios = document.getElementsByName('choix');
    var choixUtilisateur = null;

    for (var i = 0; i < radios.length; i++) {
        if (radios[i].checked) {
            choixUtilisateur = radios[i].value;
            break;
        }
    }

    if (choixUtilisateur) {
        alert("Vous avez choisi le choix " + choixUtilisateur);
    } else {
        alert("Veuillez sélectionner un choix.");
    }
}
```

### Explications
1. **HTML** : La structure inclut trois boutons radio pour les choix et un bouton pour déclencher la fonction de JavaScript.
2. **JavaScript** :
   - **afficherChoix()** : Cette fonction itère sur tous les boutons radio nommés 'choix'.
   - **Vérification** : Pour chaque bouton, si l'état est `checked`, la valeur est capturée.
   - **Alerte** : Une alerte est affichée avec le choix sélectionné ou un message demandant une sélection si aucun choix n'est fait.

Ce script est simple et explicite, idéal pour les débutants afin de comprendre comment manipuler les éléments de formulaire et les conditions en JavaScript.
