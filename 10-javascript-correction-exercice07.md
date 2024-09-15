Pour l'exercice 7, vous devez développer une fonction JavaScript `CalculScore()` qui vérifie le nombre de cases cochées et calcule le score basé sur les valeurs associées à ces cases. Si le score est supérieur à 15, une alerte indique que le joueur est un expert, sinon, une alerte indique que le joueur est encore débutant. Voici la reformulation de l'énoncé et le code JavaScript correspondant :

![image](https://github.com/user-attachments/assets/6357085b-6e06-4cb5-b470-2f2deac23fff)

![image](https://github.com/user-attachments/assets/3927be49-018d-4c66-8f33-92b3ca1d7bba)

![image](https://github.com/user-attachments/assets/37f8bc9e-2f4c-4fc6-a108-8f13394a6932)


### Énoncé 
Complétez le script du jeu en développant la fonction JavaScript `CalculScore()`. Cette fonction doit :
- Afficher une alerte si moins ou plus de trois cases sont cochées.
- Calculer le score du jeu en fonction des valeurs associées aux cases cochées.
- Afficher une alerte indiquant « Vous êtes déjà un joueur expert » si le score est supérieur à 15, ou « Vous êtes encore un joueur débutant » si le score est inférieur ou égal à 15.

### Code HTML
```html
<!DOCTYPE html>
<html lang="fr">
<head>
    <meta charset="UTF-8">
    <title>Exercice 7</title>
</head>
<body>
    <h2>Veuillez cocher trois cases :</h2>
    <form id="form">
        <input type="checkbox" name="case" value="-8"> Case 1<br>
        <input type="checkbox" name="case" value="5"> Case 2<br>
        <input type="checkbox" name="case" value="3"> Case 3<br>
        <input type="checkbox" name="case" value="10"> Case 4<br>
        <input type="checkbox" name="case" value="0"> Case 5<br>
        <input type="checkbox" name="case" value="-1"> Case 6<br>
        <input type="checkbox" name="case" value="-7"> Case 7<br>
        <input type="checkbox" name="case" value="15"> Case 8<br>
        <input type="checkbox" name="case" value="8"> Case 9<br>
        <input type="checkbox" name="case" value="3"> Case 10<br>
        <button type="button" onclick="CalculScore()">Calculer le score du jeu</button>
    </form>
    <script src="script.js"></script>
</body>
</html>
```

### Script JavaScript (script.js)
```javascript
function CalculScore() {
    var checkboxes = document.querySelectorAll('input[type="checkbox"]:checked');
    var score = 0;

    if (checkboxes.length !== 3) {
        alert("Veuillez cocher exactement trois cases.");
        return;
    }

    checkboxes.forEach(function(checkbox) {
        score += parseInt(checkbox.value);
    });

    if (score > 15) {
        alert("Vous êtes déjà un joueur expert");
    } else {
        alert("Vous êtes encore un joueur débutant");
    }
}
```

### Explications
1. **Sélection des cases cochées** : `document.querySelectorAll('input[type="checkbox"]:checked')` récupère toutes les cases cochées.
2. **Validation du nombre de cases** : On vérifie si exactement trois cases sont cochées. Sinon, une alerte est affichée.
3. **Calcul du score** : Le score est calculé en additionnant les valeurs des cases cochées.
4. **Affichage du résultat** : Selon le score obtenu, une alerte correspondante est affichée pour indiquer le niveau du joueur.

