# Exercices JavaScript - Série 2

## Exercice 2 : Addition de Deux Nombres

### Énoncé

Développez un script JavaScript qui demande à l'utilisateur de saisir deux nombres et affiche la somme de ces deux nombres.

### Solution

```javascript
// Exercice 2 - Addition de deux nombres

// Demander à l'utilisateur de saisir le premier nombre
let premierNombre = parseInt(prompt("Insérer le premier nombre :"));

// Demander à l'utilisateur de saisir le deuxième nombre
let deuxiemeNombre = parseInt(prompt("Insérer le deuxième nombre :"));

// Calculer la somme des deux nombres
let somme = premierNombre + deuxiemeNombre;

// Afficher le résultat
alert("La somme est : " + somme);
```

## Exercice 3 : Collecte et Traitement de Valeurs

### Énoncé

Développez un script JavaScript qui effectue les opérations suivantes :
1. Collecte les valeurs de `x` et `y` auprès de l'utilisateur.
2. Applique les règles suivantes :
   - Si `x >= 5`, déduire 5 de `x`. Sinon, ajouter 5 à `x`.
   - Si `y > 10`, déduire 10 de `y`. Sinon, ajouter 10 à `y`.
3. Affiche le résultat de `x + y`.

### Solution

```javascript
// Exercice 3 - Collecter et traiter des valeurs x et y

// Demander à l'utilisateur de saisir les valeurs de x et y
let x = parseInt(prompt("Insérer la valeur de x :"));
let y = parseInt(prompt("Insérer la valeur de y :"));

// Appliquer les règles spécifiées
if (x >= 5) {
    x -= 5; // Déduire 5 de x si x est supérieur ou égal à 5
} else {
    x += 5; // Ajouter 5 à x sinon
}

if (y > 10) {
    y -= 10; // Déduire 10 de y si y est supérieur à 10
} else {
    y += 10; // Ajouter 10 à y sinon
}

// Afficher le résultat de x + y
alert("La somme de x et y est : " + (x + y));
```

## Exercice 4 : Divisibles par 23

### Énoncé

Développez un script JavaScript pour afficher tous les entiers compris entre 1 et 1000 qui sont divisibles par 23.

### Solution

```javascript
// Exercice 4 - Afficher les nombres divisibles par 23 entre 1 et 1000

for (let i = 1; i <= 1000; i++) {
    if (i % 23 === 0) {
        console.log(i); // Affiche le nombre si divisible par 23
    }
}
```
