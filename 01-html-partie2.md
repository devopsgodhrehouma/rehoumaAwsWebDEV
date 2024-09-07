# **HTML  : Étape par Étape - partie 2**

### **Étape 1 : Découverte des Balises de Base**

**Objectif** : Apprendre à utiliser les balises de titre et de texte.

#### Instructions :
- Créez un fichier HTML nommé `index.html`.
- Copiez-collez le code suivant pour observer le fonctionnement des titres et de l'italique.

#### Code à copier :
```html
<!DOCTYPE html>
<html lang="fr">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>Découverte des Balises de Base</title>
</head>
<body>
  <!-- Titre principal avec texte en italique -->
  <h1><i>Bonjour</i></h1>
  
  <!-- Ligne horizontale -->
  <hr/>

  <!-- Champ texte avec une valeur par défaut -->
  <input type="text" value="Hello" />
</body>
</html>
```

### **Étape 2 : Champs de couleur et bouton**

**Objectif** : Découvrir d'autres types d'entrées comme les couleurs et les boutons.

#### Code à copier :
```html
<!DOCTYPE html>
<html lang="fr">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>Champs de Couleur et Boutons</title>
</head>
<body>
  <!-- Champ de sélection de couleur -->
  <input type="color" />

  <!-- Ligne horizontale -->
  <hr/>

  <!-- Bouton cliquable -->
  <input type="button" value="Cliquez ici">
</body>
</html>
```

### **Étape 3 : Ajouter différents types de champs**

**Objectif** : Explorer plusieurs types d'entrées de formulaire.

#### Code à copier :
```html
<!DOCTYPE html>
<html lang="fr">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>Types d'Entrées</title>
</head>
<body>
  <!-- Champ de date -->
  <input type="date" />
  <hr/>

  <!-- Case à cocher -->
  <input type="checkbox">
  <hr/>

  <!-- Sélection de la date et heure locale -->
  <input type="datetime-local">
  <hr/>

  <!-- Champ d'email -->
  <input type="email">
  <hr/>

  <!-- Champ de téléchargement de fichier -->
  <input type="file">
</body>
</html>
```

### **Étape 4 : Ajouter des champs avancés**

**Objectif** : Utiliser des champs avancés comme la couleur, le nombre, et le mot de passe.

#### Code à copier :
```html
<!DOCTYPE html>
<html lang="fr">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>Champs Avancés</title>
</head>
<body>
  <!-- Sélection d'une couleur -->
  <input type="color">
  <hr/>

  <!-- Champ de nombre -->
  <input type="number">
  <hr/>

  <!-- Champ de mot de passe -->
  <input type="password">
  <hr/>

  <!-- Bouton radio -->
  <input type="radio">
</body>
</html>
```

### **Étape 5 : Découverte des autres types d'entrées**

**Objectif** : Tester des entrées supplémentaires comme le champ de recherche et le bouton de soumission.

#### Code à copier :
```html
<!DOCTYPE html>
<html lang="fr">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>Entrées Complémentaires</title>
</head>
<body>
  <!-- Champ de recherche -->
  <input type="search">
  <hr/>

  <!-- Bouton de soumission -->
  <input type="submit">
  <hr/>

  <!-- Champ pour entrer un numéro de téléphone -->
  <input type="tel">
  <hr/>

  <!-- Champ pour entrer une URL -->
  <input type="url">
</body>
</html>
```

### **Étape 6 : Formulaire complet avec différents types de champs**

**Objectif** : Créer un formulaire complet combinant plusieurs types d'entrées.

#### Code à copier :
```html
<!DOCTYPE html>
<html lang="fr">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>Formulaire Complet</title>
</head>
<body>
  <form>
    <!-- Champ texte -->
    <label for="name">Nom :</label>
    <input type="text" id="name" name="name">
    <hr/>

    <!-- Sélection de date -->
    <label for="dob">Date de naissance :</label>
    <input type="date" id="dob" name="dob">
    <hr/>

    <!-- Adresse email -->
    <label for="email">Email :</label>
    <input type="email" id="email" name="email">
    <hr/>

    <!-- Numéro de téléphone -->
    <label for="phone">Téléphone :</label>
    <input type="tel" id="phone" name="phone">
    <hr/>

    <!-- Bouton de soumission -->
    <input type="submit" value="Envoyer">
  </form>
</body>
</html>
```


