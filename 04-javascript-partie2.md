# Chapitre III : Le Langage JavaScript

-------
# Partie I : Introduction à JavaScript
---------

### Pourquoi JavaScript ?
- **Simple et interprétable** par le navigateur.
- Permet d'ajouter de **l’interactivité** aux pages web.
  - **Exemple d'utilisation :**
    - Valider les champs d’un formulaire.
    - Afficher des messages d’alerte interactifs pour l'utilisateur.
  
**Exercice :**
1. Expliquez en quelques phrases pourquoi il est avantageux d’utiliser JavaScript dans une page web. 
2. Donnez trois exemples concrets d'utilisation du JavaScript pour améliorer l'expérience utilisateur.

---

## Ecriture du JavaScript

### Interne :
Le code JavaScript est intégré directement dans le fichier HTML, entre les balises `<script>` dans l’en-tête ou le corps du document.

**Exemple :**
```html
<!DOCTYPE html>
<html>
<head>
  <script>
    document.write("Bonjour depuis le script interne !");
  </script>
</head>
<body>
</body>
</html>
```

### Externe :
Le code JavaScript peut être placé dans un fichier `.js` séparé.

**Exemple :**
1. Créez un fichier `script.js` avec ce code :
```javascript
document.write("Bonjour depuis le script externe !");
```
2. Dans le fichier HTML, liez ce fichier `.js` :
```html
<!DOCTYPE html>
<html>
<head>
  <script src="script.js"></script>
</head>
<body>
</body>
</html>
```

**Exercice :**
Créez un fichier HTML et un fichier JavaScript externe. Dans le fichier JavaScript, écrivez un script qui affiche "Hello World!" sur la page web.

---

## Variables

JavaScript est un langage faiblement typé, ce qui signifie que vous n'avez pas besoin de spécifier le type des variables.

- Utilisez `var`, `let`, ou `const` pour déclarer des variables.
  - `var` : Variable qui peut être redéclarée.
  - `let` : Variable qui peut changer mais ne peut pas être redéclarée.
  - `const` : Variable constante qui ne peut ni changer ni être redéclarée.

**Exemples :**
```javascript
var nom = "Ali";  // déclaration avec var
let age = 25;     // déclaration avec let
const ville = "Paris";  // déclaration avec const
```

**Exercice :**
1. Créez un script JavaScript qui déclare trois variables :
   - `nom` (string)
   - `age` (number)
   - `ville` (string)
   Ensuite, affichez ces variables sur la console du navigateur.

---

## Types de Données

Les principaux types de données en JavaScript sont :
- **String** : Chaîne de caractères (ex: "Bonjour").
- **Number** : Nombre (ex: 42).
- **Boolean** : Vrai ou Faux (`true` ou `false`).
- **Null** : Représente une absence de valeur.
- **NaN** : "Not a Number", obtenu suite à des calculs non valides.

**Exercice :**
1. Créez un script qui déclare différentes variables pour chaque type de donnée, puis affichez-les dans la console.

---

## Boîtes de Dialogue

### Prompt :
Affiche une boîte de dialogue pour saisir des données.

**Exemple :**
```javascript
var nom = prompt('Quel est votre nom ?');
alert('Bonjour ' + nom);
```

### Alert :
Affiche un message simple dans une boîte d’alerte.

**Exemple :**
```javascript
alert('Bienvenue sur mon site web !');
```

### Confirm :
Demande une confirmation à l'utilisateur (OK/Annuler).

**Exemple :**
```javascript
if (confirm('Voulez-vous continuer ?')) {
  alert('Vous avez choisi de continuer.');
} else {
  alert('Vous avez annulé.');
}
```

**Exercice :**
Créez un script qui :
1. Demande à l’utilisateur son nom via une boîte `prompt()`.
2. Affiche ensuite une boîte `alert()` pour le saluer avec son nom.
3. Utilise une boîte `confirm()` pour lui demander s’il veut vraiment continuer à naviguer sur le site.

---

## Opérateurs JavaScript

### Arithmétiques :
- Addition (+), Soustraction (-), Multiplication (*), Division (/), Incrémentation (++), Décrémentation (--).

### Comparaison :
- `<`, `<=`, `==`, `!=`, `>=`, `>`

**Exemple :**
```javascript
var a = 5;
var b = 10;
console.log(a + b);  // Affiche 15
console.log(a == b); // Affiche false
```

### Concaténation de chaînes :
```javascript
var message = "Bonjour " + "tout le monde!";
console.log(message);  // Affiche "Bonjour tout le monde!"
```

**Exercice :**
1. Créez un script qui additionne deux nombres, puis vérifie si le résultat est supérieur à 10.

---

## Structures Conditionnelles

**Syntaxe :**
```javascript
if (condition) {
  // action si la condition est vraie
} else {
  // action si la condition est fausse
}
```

**Exemple :**
```javascript
var age = 18;
if (age >= 18) {
  console.log("Vous êtes majeur.");
} else {
  console.log("Vous êtes mineur.");
}
```

**Exercice :**
1. Créez un script qui vérifie si un nombre saisi par l'utilisateur est pair ou impair.

---

## Itérations

### Boucle For :
```javascript
for (var i = 0; i < 5; i++) {
  console.log(i);
}
```

### Boucle While :
```javascript
var i = 0;
while (i < 5) {
  console.log(i);
  i++;
}
```

**Exercice :**
1. Créez une boucle `for` qui affiche tous les nombres de 1 à 10 dans la console.

