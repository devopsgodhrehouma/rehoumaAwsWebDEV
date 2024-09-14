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

