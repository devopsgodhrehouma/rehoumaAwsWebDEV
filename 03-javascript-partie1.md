# Introduction à JavaScript dans le Navigateur

JavaScript est un langage de programmation qui permet d’ajouter des fonctionnalités dynamiques aux pages web. Dans cette leçon, nous allons voir comment afficher des messages, obtenir des informations de l'utilisateur, et faire une requête vers une API REST.

# 1. Les premières interactions avec le navigateur

Pour commencer, nous allons utiliser quatre fonctions de base qui permettent de communiquer avec l'utilisateur : `alert`, `confirm`, `console.log` et `prompt`.

# a. `alert`

Cette fonction affiche un message dans une boîte de dialogue.

```javascript
alert('Bienvenue sur notre site web !');
```

Lorsque vous exécutez ce code, une boîte apparaîtra avec le message "Bienvenue sur notre site web !".

# b. `confirm`

La fonction `confirm` permet de poser une question à l'utilisateur avec deux options : "OK" et "Annuler". Elle renvoie `true` si l'utilisateur clique sur "OK" et `false` s'il clique sur "Annuler".

```javascript
let resultat = confirm('Voulez-vous continuer ?');
if (resultat) {
    console.log('L\'utilisateur a choisi de continuer.');
} else {
    console.log('L\'utilisateur a annulé.');
}
```

# c. `prompt`

La fonction `prompt` permet de demander à l'utilisateur de saisir une information. Elle renvoie la chaîne de caractères entrée par l'utilisateur ou `null` s'il annule.

```javascript
let nom = prompt('Quel est votre nom ?');
if (nom) {
    console.log('Bonjour ' + nom + ' !');
} else {
    console.log('L\'utilisateur n\'a pas entré de nom.');
}
```

# d. `console.log`

Cette fonction affiche des messages dans la console du navigateur, utile pour le débogage et l'affichage de résultats.

```javascript
console.log('Ceci est un message dans la console.');
```

# 2. Utilisation de `fetch` pour accéder à une API REST

Nous allons maintenant faire une requête à une API REST en utilisant la méthode `fetch`. Cette méthode permet de récupérer des données depuis un serveur.

```javascript
// Effectuons une requête GET à une API REST publique
fetch('https://jsonplaceholder.typicode.com/posts/1')
  .then(response => response.json()) // Conversion en JSON
  .then(data => {
      console.log('Titre du post:', data.title); // Affiche le titre dans la console
      alert('Voici le titre du post : ' + data.title); // Affiche le titre dans une alerte
  })
  .catch(error => console.error('Erreur:', error)); // Gestion des erreurs
```

Dans cet exemple, nous utilisons l'API gratuite `jsonplaceholder.typicode.com` qui retourne un post de blog avec l'ID 1. Le titre du post est affiché à l'utilisateur à la fois dans la console et via une alerte.

# Conclusion

- **`alert`** permet d'afficher un message simple.
- **`confirm`** permet de demander à l'utilisateur une confirmation.
- **`prompt`** permet de demander une saisie à l'utilisateur.
- **`console.log`** permet d'afficher des messages dans la console pour le débogage.
- **`fetch`** permet de récupérer des données depuis une API.



# Partie 2 


### Exercice 1: Utilisation de Boîtes de Dialogue
**Objectif**: Familiariser l'étudiant avec les boîtes de dialogue internes et externes en JavaScript.

#### Instructions:
1. **Interne**: Créez une boîte de dialogue simple utilisant `alert` pour saluer l'utilisateur directement dans le HTML.
2. **Externe**: Utilisez un fichier JavaScript externe pour afficher une confirmation (`confirm`) demandant à l'utilisateur s'il aime utiliser JavaScript.

#### Code HTML (index.html):
```html
<!DOCTYPE html>
<html lang="fr">
<head>
    <meta charset="UTF-8">
    <title>Exercice 1</title>
    <script>alert("Bonjour! C'est une alerte interne.");</script>
    <script src="extern.js"></script>
</head>
<body>
    <p>Vérifiez votre navigateur pour les boîtes de dialogue.</p>
</body>
</html>
```

#### Code JavaScript (extern.js):
```javascript
let userResponse = confirm("Aimez-vous utiliser JavaScript?");
alert("Vous avez répondu " + (userResponse ? "Oui" : "Non"));
```

### Exercice 2: Manipulation de Variables
**Objectif**: Enseigner les bases de la déclaration de variables et la manipulation de données.

#### Instructions:
1. Demandez le nom de l'utilisateur avec `prompt()` et stockez la réponse.
2. Utilisez cette information pour afficher une alerte personnalisée.

#### Code:
```javascript
var nom = prompt("Quel est votre nom?");
alert("Bienvenue, " + nom + "!");
```

### Exercice 3: Types de Données et Opérations
**Objectif**: Introduire différents types de données et opérations basiques.

#### Instructions:
1. Créez des variables de différents types (String, Number, Boolean).
2. Effectuez des opérations simples (addition, concaténation) et affichez les résultats.

#### Code:
```javascript
var age = 25; // Number
var nom = "Alice"; // String
var estEtudiant = true; // Boolean

// Opération et affichage
var resultat = "Nom: " + nom + ", Age dans 10 ans: " + (age + 10) + ", Est étudiant: " + estEtudiant;
alert(resultat);
```

### Exercice 4: Structures Conditionnelles
**Objectif**: Pratiquer l'écriture de conditions pour contrôler le flux du programme.

#### Instructions:
1. Utilisez `if...else` pour tester si une variable numérique est positive, négative, ou zéro.
2. Affichez un message approprié pour chaque cas.

#### Code:
```javascript
var nombre = prompt("Entrez un nombre:");
nombre = parseInt(nombre);

if (nombre > 0) {
    alert("Le nombre est positif.");
} else if (nombre < 0) {
    alert("Le nombre est négatif.");
} else {
    alert("Le nombre est zéro.");
}
```

