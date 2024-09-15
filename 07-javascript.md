### Introduction aux Fonctions en JavaScript

Bienvenue dans ce module d'introduction aux fonctions JavaScript ! Ce document est conçu pour vous permettre de comprendre et de tester directement les fonctions en JavaScript. Assurez-vous de suivre les instructions et de copier chaque bloc de code dans votre éditeur pour voir comment il fonctionne.

#### 1. Déclaration et Appel de Fonction

```javascript
// Déclaration de la fonction 'direBonjour'
function direBonjour() {
  console.log("Bonjour !");
}

// Appel de la fonction 'direBonjour'
direBonjour();  // Cela va afficher "Bonjour !" dans la console.
```

#### 2. Fonction avec Paramètres et Arguments

```javascript
// Fonction 'saluer' avec un paramètre 'nom'
function saluer(nom) {
  console.log("Bonjour, " + nom + " !");
}

// Appel de la fonction 'saluer' avec l'argument "Alice"
saluer("Alice");  // Affiche "Bonjour, Alice !" dans la console.
```

#### 3. Fonction avec Valeur de Retour

```javascript
// Fonction 'additionner' retournant la somme de deux nombres
function additionner(a, b) {
  return a + b;
}

// Appel de la fonction 'additionner' et affichage du résultat
console.log(additionner(5, 3));  // Affiche "8" dans la console.
```

#### 4. Fonctions Anonymes et Fléchées

```javascript
// Fonction anonyme stockée dans une variable 'montrer'
let montrer = function() {
  console.log("Fonction anonyme appelée !");
};

// Appel de la fonction anonyme
montrer();  // Affiche "Fonction anonyme appelée !" dans la console.

// Fonction fléchée 'salut'
const salut = () => {
  console.log("Salut !");
};

// Appel de la fonction fléchée 'salut'
salut();  // Affiche "Salut !" dans la console.
```

#### 5. Fonctions Immédiatement Invocables (IIFE)

```javascript
// IIFE qui s'exécute immédiatement
(function() {
  console.log("Exécuté immédiatement après la définition !");
})();
```

---

### Instructions pour les Étudiants

1. Copiez chaque bloc de code séparément dans votre éditeur JavaScript ou dans la console de votre navigateur pour tester les effets de chaque fonction.

---

Et voici une page HTML complète qui intègre tous les exemples de fonctions mentionnés précédemment. Cela donnera aux étudiants la possibilité de voir en action plusieurs types de fonctions JavaScript, simplement en cliquant sur différents boutons.

```html
<!DOCTYPE html>
<html lang="fr">
<head>
    <meta charset="UTF-8">
    <title>Exploration des Fonctions JavaScript</title>
    <script>
        // Fonction simple qui affiche un message
        function direBonjour() {
            alert("Bonjour !");
        }

        // Fonction avec paramètres
        function saluer(nom) {
            alert("Bonjour, " + nom + " !");
        }

        // Fonction qui retourne une valeur
        function additionner(a, b) {
            return alert("La somme de " + a + " et " + b + " est " + (a + b));
        }

        // Fonction anonyme stockée dans une variable
        let montrer = function() {
            alert("Fonction anonyme appelée !");
        };

        // Fonction fléchée
        const salut = () => {
            alert("Salut !");
        };

        // IIFE - Fonction immédiatement invoquée
        (function() {
            console.log("Cette fonction s'exécute seule au chargement de la page !");
        })();
    </script>
</head>
<body>
    <h1>Démonstration des Fonctions JavaScript</h1>
    <button onclick="direBonjour()">Dire Bonjour</button>
    <button onclick="saluer('Alice')">Saluer Alice</button>
    <button onclick="additionner(5, 3)">Additionner 5 et 3</button>
    <button onclick="montrer()">Appeler fonction anonyme</button>
    <button onclick="salut()">Appeler fonction fléchée</button>
    <script>
        console.log("Vous pouvez voir ce message dans la console de votre navigateur.");
    </script>
</body>
</html>
```

### Instructions d'utilisation :
1. **Copiez** tout le code ci-dessus.
2. **Collez** le dans un nouveau fichier texte.
3. **Enregistrez** le fichier avec l'extension `.html`, par exemple `demo_fonctions.html`.
4. **Ouvrez** ce fichier dans un navigateur web pour voir les différents boutons.

