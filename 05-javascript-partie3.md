# JavaScript - Exercices Pratiques

## Introduction
Ce README regroupe une série d'exercices destinée à introduire les concepts de base de JavaScript. Ces exercices sont conçus pour aider les débutants à comprendre les fondamentaux du langage, de la manipulation des types de données aux structures de contrôle.

## Table des Matières
1. [Exercice 1.1 : Utilisation de `prompt()`](#exercice-11-utilisation-de-prompt)
2. [Exercice 1.2 : Interactions Multiples avec `prompt()` et `alert()`](#exercice-12-interactions-multiples-avec-prompt-et-alert)
3. [Exercice 1.3 : Structures Conditionnelles](#exercice-13-structures-conditionnelles)
4. [Exercice 1.4 : Itérations](#exercice-14-itérations)
5. [Exercice 1.5 : Fonctions Prédéfinies](#exercice-15-fonctions-prédéfinies)

---

## Exercice 1.1 : Utilisation de `prompt()`
**Objectif :** Pratiquer l’utilisation de la fonction `prompt()` pour recueillir des données utilisateur.

**Consignes :**
1. Créez une page HTML simple.
2. Ajoutez un script JavaScript qui utilise `prompt()` pour demander à l'utilisateur son prénom.
3. Stockez la valeur entrée dans une variable.
4. Utilisez `alert()` pour afficher un message de bienvenue qui inclut le prénom saisi par l'utilisateur.

**Code de démarrage :**
```html
<!DOCTYPE html>
<html lang="fr">
<head>
    <meta charset="UTF-8">
    <title>Exercice 1.1 : Prompt et Alert</title>
</head>
<body>
    <script>
        // Étape 1 : Demander le prénom
        var prenom = prompt("Veuillez entrer votre prénom :");

        // Étape 2 : Afficher le message de bienvenue
        alert("Bienvenue, " + prenom + "!");
    </script>
</body>
</html>
```

**Attendu :**
- Si l'utilisateur entre "Alice", l'alerte devrait afficher "Bienvenue, Alice!".
- Si aucun prénom n'est entré et que l'utilisateur clique sur OK, l'alerte devrait afficher "Bienvenue, !" (considérez comment vous pourriez gérer ce cas pour améliorer l'expérience utilisateur).

---

## Exercice 1.2 : Interactions Multiples avec `prompt()` et `alert()`
**Objectif :** Créer une séquence de boîtes de dialogue qui demandent le nom de l'utilisateur, l'accueillent par son nom, puis remercient l'utilisateur pour sa visite.

**Consignes :**
1. Demandez le nom de l'utilisateur avec une boîte de dialogue `prompt()`.
2. Utilisez les structures conditionnelles pour afficher un message personnalisé :
   - Si le nom est "Ali", affichez "Bonjour Ali!"
   - Si le nom est "Stephane", affichez "Hello Stephane!"
   - Pour tout autre nom ou si aucun nom n'est saisi, affichez "Qui êtes-vous?"

**Code de démarrage :**
```html
<!DOCTYPE html>
<html lang="fr">
<head>
    <meta charset="UTF-8">
    <title>Exercice 1.2 : Dialogues Successifs</title>
</head>
<body>
    <script>
        // Étape 1 : Demander le nom
        var nom = prompt("Quel est votre nom ?");

        // Étape 2 : Saluer l'utilisateur
        if (nom === "Ali") {
            alert("Bonjour " + nom + "!");
        } else if (nom === "Stephane") {
            alert("Hello " + nom + "!");
        } else {
            alert("Qui êtes-vous?");
        }

        // Étape 3 : Remercier pour la visite
        alert("Merci de votre visite !");
    </script>
</body>
</html>
```

**Attendu :**
- La première boîte de dialogue doit permettre à l'utilisateur de saisir son nom.
- La deuxième boîte de dialogue utilise le nom saisi pour saluer l'utilisateur. Si aucun nom n'est saisi, un message générique est affiché.
- La troisième boîte de dialogue remercie l'utilisateur de sa visite, indépendamment de la saisie précédente.

---

## Exercice 1.3 : Structures Conditionnelles
**Objectif :** Utiliser les structures conditionnelles pour personnaliser les messages d'accueil en fonction du nom de l'utilisateur.

**Consignes :**
1. Demandez le nom de l'utilisateur via une boîte de dialogue `prompt()`.
2. Utilisez les structures conditionnelles pour afficher un message personnalisé :
   - Si le nom est "Ali", affichez "Bonjour Ali!"
   - Si le nom est "Stephane", affichez "Hello Stephane!"
   - Pour tout autre nom ou si aucun nom n'est saisi, affichez "Qui êtes-vous?"

**Code de démarrage :**
```html
<!DOCTYPE html>
<html lang="fr">
<head>
    <meta charset="UTF-8">
    <title>Exercice 1.3 : Structures Conditionnelles</title>
</head>
<body>
    <script>
        // Étape 1 : Demander le nom
        var nom = prompt("Quel est votre nom ?");

        // Étape 2 : Afficher un message personnalisé selon le nom
        if (nom === "Ali") {
            alert("Bonjour " + nom + "!");
        } else if (nom === "Stephane") {
            alert("Hello " + nom + "!");
        } else {
            alert("Qui êtes-vous?");
        }
    </script>
</body>
</html>
```

**Attendu :**
- Les fonctions doivent correctement convertir les valeurs ou retourner `NaN` si la conversion est impossible.
- Les résultats doivent être affichés dans la console du navigateur pour faciliter le débogage et le suivi des conversions.

---

## Exercice 1.4 : Itérations
**Objectif :** Utiliser une boucle `for` pour afficher une série de valeurs et comprendre le contrôle d'itération.

**Consignes :**
1. Créez une boucle `for` qui compte de 0 à 10.
2. Pour chaque itération, affichez le compteur dans une boîte de dialogue `alert()`.
3. Après la fin de la boucle, affichez un message final indiquant que la boucle est terminée.

**Code de démarrage :**
```html
<!DOCTYPE html>
<html lang="fr">
<head>
    <meta charset="UTF-8">
    <title>Exercice 1.4 : Boucle For</title>
</head>
<body>
    <script>
        // Déclaration de la variable compteur
        var compteur;

        // Boucle de 0 à 10
        for (compteur = 0; compteur <= 10; compteur++) {
            alert("Valeur: " + compteur);
        }

        // Message de fin de boucle
        alert("La boucle est terminée !");
    </script>
</body>
</html>
```

**Attendu :**
- Dix boîtes de dialogue `alert()` doivent s'afficher successivement, montrant les valeurs de 0 à 10.
- Une boîte de dialogue finale doit s'afficher pour indiquer que la boucle est terminée.

---

## Exercice 1.5 : Fonctions Prédéfinies
**Objectif :** Explorer l'utilisation des fonctions prédéfinies pour convertir les types de données et comprendre comment JavaScript gère les conversions et les cas d'erreur.

**Consignes :**
1. Utilisez les fonctions `parseFloat()`, `parseInt()`, `String()`, et `Number()` pour convertir différentes valeurs et affichez les résultats.
2. Testez chaque fonction avec différents types de données pour voir comment elles réagissent aux valeurs valides et invalides.

**Scénario Détaillé :**

#### 1. `parseFloat()`
- Convertissez une chaîne de caractères contenant des chiffres et des lettres en un nombre à virgule flottante.
- Essayez avec une chaîne de caractères commençant par un chiffre suivi de lettres pour voir si elle peut être convertie en nombre.
  
#### 2. `parseInt()`
- Convertissez des chaînes similaires en entiers.
- Notez comment `parseInt()` ignore les caractères non numériques qui suivent les chiffres initiaux.
  
#### 3. `String()`
- Convertissez des nombres en chaînes de caractères.
- Vérifiez le type avant et après la conversion pour confirmer le changement.
  
#### 4. `Number()`
- Tentez de convertir des chaînes de caractères en nombres

