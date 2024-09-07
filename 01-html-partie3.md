#  types d'éléments `<input>` disponibles en HTML

| **Type d'Input**      | **Description**                                                   | **Exemple de Code**                                |
|-----------------------|-------------------------------------------------------------------|----------------------------------------------------|
| `text`                | Champ de texte classique                                          | `<input type="text">`                              |
| `password`            | Champ pour saisir un mot de passe (texte masqué)                  | `<input type="password">`                          |
| `email`               | Champ pour saisir une adresse e-mail                              | `<input type="email">`                             |
| `tel`                 | Champ pour saisir un numéro de téléphone                          | `<input type="tel">`                               |
| `url`                 | Champ pour saisir une URL                                         | `<input type="url">`                               |
| `search`              | Champ de recherche                                                | `<input type="search">`                            |
| `number`              | Champ pour saisir un nombre                                       | `<input type="number">`                            |
| `range`               | Curseur pour choisir une valeur dans une plage                    | `<input type="range">`                             |
| `color`               | Sélecteur de couleur                                              | `<input type="color">`                             |
| `date`                | Sélecteur de date                                                 | `<input type="date">`                              |
| `month`               | Sélecteur de mois et d'année                                      | `<input type="month">`                             |
| `week`                | Sélecteur de semaine                                              | `<input type="week">`                              |
| `time`                | Sélecteur d'heure                                                 | `<input type="time">`                              |
| `datetime-local`      | Sélecteur de date et d'heure (sans fuseau horaire)                | `<input type="datetime-local">`                    |
| `checkbox`            | Case à cocher                                                     | `<input type="checkbox">`                          |
| `radio`               | Bouton radio (choix unique dans un groupe)                        | `<input type="radio">`                             |
| `file`                | Champ de téléchargement de fichier                               | `<input type="file">`                              |
| `image`               | Bouton image (soumet un formulaire en cliquant sur l'image)       | `<input type="image" src="image.jpg" alt="Image">` |
| `button`              | Bouton générique sans action                                      | `<input type="button" value="Cliquez ici">`        |
| `submit`              | Bouton pour soumettre un formulaire                               | `<input type="submit" value="Envoyer">`            |
| `reset`               | Bouton pour réinitialiser les valeurs d'un formulaire             | `<input type="reset" value="Réinitialiser">`       |
| `hidden`              | Champ caché (non visible pour l'utilisateur)                      | `<input type="hidden">`                            |

---

### **Instructions  :**
1. Copiez chaque ligne de la colonne **Exemple de Code** et collez-la dans votre fichier HTML.
2. Testez chaque type d'`<input>` pour observer son comportement.
3. Essayez de remplir certains champs (comme `email`, `number`, etc.) pour voir les validations automatiques effectuées par le navigateur.


# Correction et instructions : 

- Vous pouvez copier et coller chaque fichier pour tester un type d'`<input>` à la fois. 
- Nous allons les progresser, en ajoutant des types d'`<input>` étape par étape.

1. **Copiez-collez** chaque fichier HTML dans un éditeur de texte (comme VSCode, Sublime Text, ou simplement Notepad).
2. **Testez chaque fichier** en ouvrant le fichier `.html` dans un navigateur web.
3. Observez le comportement de chaque input au fur et à mesure que vous progressez dans les fichiers.
4. Essayez de remplir certains champs (comme `email` et `number`) pour voir les validations automatiques effectuées par le navigateur.

Ces exemples vous permettront  de découvrir progressivement chaque type d'input.

---

### **Fichier 1 : test-text.html**
#### Contient un champ texte simple.

```html
<!DOCTYPE html>
<html lang="fr">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>Test Input Texte</title>
</head>
<body>
  <h1>Test Input de type Texte</h1>
  <form>
    <!-- Champ de texte classique -->
    <label for="texte">Entrez du texte :</label>
    <input type="text" id="texte" placeholder="Entrez du texte ici">
  </form>
</body>
</html>
```

---

### **Fichier 2 : test-password.html**
#### Ajoute un champ texte + un champ mot de passe.

```html
<!DOCTYPE html>
<html lang="fr">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>Test Input Texte et Mot de Passe</title>
</head>
<body>
  <h1>Test Inputs Texte et Mot de Passe</h1>
  <form>
    <!-- Champ de texte classique -->
    <label for="texte">Entrez du texte :</label>
    <input type="text" id="texte" placeholder="Entrez du texte ici">
    <hr/>

    <!-- Champ mot de passe -->
    <label for="password">Entrez votre mot de passe :</label>
    <input type="password" id="password" placeholder="Mot de passe">
  </form>
</body>
</html>
```

---

### **Fichier 3 : test-email.html**
#### Ajoute un champ e-mail au champ texte et mot de passe.

```html
<!DOCTYPE html>
<html lang="fr">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>Test Input Email</title>
</head>
<body>
  <h1>Test Inputs Texte, Mot de Passe et Email</h1>
  <form>
    <!-- Champ de texte classique -->
    <label for="texte">Entrez du texte :</label>
    <input type="text" id="texte" placeholder="Entrez du texte ici">
    <hr/>

    <!-- Champ mot de passe -->
    <label for="password">Entrez votre mot de passe :</label>
    <input type="password" id="password" placeholder="Mot de passe">
    <hr/>

    <!-- Champ email -->
    <label for="email">Entrez votre adresse e-mail :</label>
    <input type="email" id="email" placeholder="exemple@domaine.com">
  </form>
</body>
</html>
```

---

### **Fichier 4 : test-number.html**
#### Ajoute un champ nombre au champ texte, mot de passe, et email.

```html
<!DOCTYPE html>
<html lang="fr">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>Test Input Nombre</title>
</head>
<body>
  <h1>Test Inputs Texte, Mot de Passe, Email et Nombre</h1>
  <form>
    <!-- Champ de texte classique -->
    <label for="texte">Entrez du texte :</label>
    <input type="text" id="texte" placeholder="Entrez du texte ici">
    <hr/>

    <!-- Champ mot de passe -->
    <label for="password">Entrez votre mot de passe :</label>
    <input type="password" id="password" placeholder="Mot de passe">
    <hr/>

    <!-- Champ email -->
    <label for="email">Entrez votre adresse e-mail :</label>
    <input type="email" id="email" placeholder="exemple@domaine.com">
    <hr/>

    <!-- Champ nombre -->
    <label for="nombre">Entrez un nombre :</label>
    <input type="number" id="nombre" min="0" max="100" step="1">
  </form>
</body>
</html>
```

---

### **Fichier 5 : test-color.html**
#### Ajoute un champ couleur aux inputs précédents.

```html
<!DOCTYPE html>
<html lang="fr">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>Test Input Couleur</title>
</head>
<body>
  <h1>Test Inputs Texte, Mot de Passe, Email, Nombre et Couleur</h1>
  <form>
    <!-- Champ de texte classique -->
    <label for="texte">Entrez du texte :</label>
    <input type="text" id="texte" placeholder="Entrez du texte ici">
    <hr/>

    <!-- Champ mot de passe -->
    <label for="password">Entrez votre mot de passe :</label>
    <input type="password" id="password" placeholder="Mot de passe">
    <hr/>

    <!-- Champ email -->
    <label for="email">Entrez votre adresse e-mail :</label>
    <input type="email" id="email" placeholder="exemple@domaine.com">
    <hr/>

    <!-- Champ nombre -->
    <label for="nombre">Entrez un nombre :</label>
    <input type="number" id="nombre" min="0" max="100" step="1">
    <hr/>

    <!-- Champ couleur -->
    <label for="color">Choisissez une couleur :</label>
    <input type="color" id="color">
  </form>
</body>
</html>
```

---

### **Fichier 6 : test-date.html**
#### Ajoute un champ date aux inputs précédents.

```html
<!DOCTYPE html>
<html lang="fr">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>Test Input Date</title>
</head>
<body>
  <h1>Test Inputs Texte, Mot de Passe, Email, Nombre, Couleur et Date</h1>
  <form>
    <!-- Champ de texte classique -->
    <label for="texte">Entrez du texte :</label>
    <input type="text" id="texte" placeholder="Entrez du texte ici">
    <hr/>

    <!-- Champ mot de passe -->
    <label for="password">Entrez votre mot de passe :</label>
    <input type="password" id="password" placeholder="Mot de passe">
    <hr/>

    <!-- Champ email -->
    <label for="email">Entrez votre adresse e-mail :</label>
    <input type="email" id="email" placeholder="exemple@domaine.com">
    <hr/>

    <!-- Champ nombre -->
    <label for="nombre">Entrez un nombre :</label>
    <input type="number" id="nombre" min="0" max="100" step="1">
    <hr/>

    <!-- Champ couleur -->
    <label for="color">Choisissez une couleur :</label>
    <input type="color" id="color">
    <hr/>

    <!-- Champ date -->
    <label for="date">Sélectionnez une date :</label>
    <input type="date" id="date">
  </form>
</body>
</html>
```

---

### **Fichier 7 : test-datetime-local.html**
#### Ajoute un champ de date et heure locale.

```html
<!DOCTYPE html>
<html lang="fr">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>Test Input Date et Heure Locale</title>
</head>
<body>
  <h1>Test Inputs Texte, Mot de Passe, Email, Nombre, Couleur, Date et DateTime Local</h1>
  <form>
    <!-- Champ de texte classique -->
    <label for="texte">Entrez du texte :</label>
    <input type="text" id="texte" placeholder="Entrez du texte ici">
    <hr/>

    <!-- Champ mot de passe -->
    <label for="password">Entrez votre mot de passe :</label>
    <input type="password" id="password" placeholder="Mot de passe">
    <hr/>

    <!-- Champ email -->
    <label for="email">Entrez votre adresse e-mail :</label>
    <input type="email" id="email" placeholder="exemple@domaine.com">
    <hr/>

    <!-- Champ nombre -->
    <label for="nombre">Entrez un nombre :</label>
    <input type="number" id="nombre" min="0" max="100" step="1">
    <hr/>

    <!-- Champ couleur -->
    <label for="color">Choisissez une couleur :</label>
    <input type="color" id="color">
    <hr/>

    <!-- Champ date -->
    <label for="date">Sélectionnez une date :</label>
    <input type="date" id="date">
    <hr/>

    <!-- Champ date et heure locale -->
    <label for="datetime">Sélectionnez une date et une heure locale :</label>
    <input type="datetime-local" id="datetime">
  </form>
</body>
</html>
```

---

### **Fichier 8 : test-time.html**
#### Ajoute un champ de sélection d'heure.

```html
<!DOCTYPE html>
<html lang="fr">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>Test Input Heure</title>
</head>
<body>
  <h1>Test Inputs Texte, Mot de Passe, Email, Nombre, Couleur, Date et Heure</h1>
  <form>
    <!-- Champ de texte classique -->
    <label for="texte">Entrez du texte :</label>
    <input type="text" id="texte" placeholder="Entrez du texte ici">
    <hr/>

    <!-- Champ mot de passe -->
    <label for="password">Entrez votre mot de passe :</label>
    <input type="password" id="password" placeholder="Mot de passe">
    <hr/>

    <!-- Champ email -->
    <label for="email">Entrez votre adresse e-mail :</label>
    <input type="email" id="email" placeholder="exemple@domaine.com">
    <hr/>

    <!-- Champ nombre -->
    <label for="nombre">Entrez un nombre :</label>
    <input type="number" id="nombre" min="0" max="100" step="1">
    <hr/>

    <!-- Champ couleur -->
    <label for="color">Choisissez une couleur :</label>
    <input type="color" id="color">
    <hr/>

    <!-- Champ date -->
    <label for="date">Sélectionnez une date :</label>
    <input type="date" id="date">
    <hr/>

    <!-- Champ date et heure locale -->
    <label for="datetime">Sélectionnez une date et une heure locale :</label>
    <input type="datetime-local" id="datetime">
    <hr/>

    <!-- Champ heure -->
    <label for="time">Sélectionnez une heure :</label>
    <input type="time" id="time">
  </form>
</body>
</html>
```

---

### **Fichier 9 : test-week.html**
#### Ajoute un champ de sélection de semaine.

```html
<!DOCTYPE html>
<html lang="fr">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>Test Input Semaine</title>
</head>
<body>
  <h1>Test Inputs Texte, Mot de Passe, Email, Nombre, Couleur, Date, Heure et Semaine</h1>
  <form>
    <!-- Champ de texte classique -->
    <label for="texte">Entrez du texte :</label>
    <input type="text" id="texte" placeholder="Entrez du texte ici">
    <hr/>

    <!-- Champ mot de passe -->
    <label for="password">Entrez votre mot de passe :</label>
    <input type="password" id="password" placeholder="Mot de passe">
    <hr/>

    <!-- Champ email -->
    <label for="email">Entrez votre adresse e-mail :</label>
    <input type="email" id="email" placeholder="exemple@domaine.com">
    <hr/>

    <!-- Champ nombre -->
    <label for="nombre">Entrez un nombre :</label>
    <input type="number" id="nombre" min="0" max="100" step="1">
    <hr/>

    <!-- Champ couleur -->
    <label for="color">Choisissez une couleur :</label>
    <input type="color" id="color">
    <hr/>

    <!-- Champ date -->
    <label for="date">Sélectionnez une date :</label>
    <input type="date" id="date">
    <hr/>

    <!-- Champ date et heure locale -->
    <label for="datetime">Sélectionnez une date et une heure locale :</label>
    <input type="datetime-local" id="datetime">
    <hr/>

    <!-- Champ heure -->
    <label for="time">Sélectionnez une heure :</label>
    <input type="time" id="time">
    <hr/>

    <!-- Champ semaine -->
    <label for="week">Sélectionnez une semaine :</label>
    <input type="week" id="week">
  </form>
</body>
</html>
```

---

### **Fichier 10 : test-month.html**
#### Ajoute un champ de sélection de mois.

```html
<!DOCTYPE html>
<html lang="fr">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>Test Input Mois</title>
</head>
<body>
  <h1>Test Inputs Texte, Mot de Passe, Email, Nombre, Couleur, Date, Heure, Semaine et Mois</h1>
  <form>
    <!-- Champ de texte classique -->
    <label for="texte">Entrez du texte :</label>
    <input type="text" id="texte" placeholder="Entrez du texte ici">
    <hr/>

    <!-- Champ mot de passe -->
    <label for="password">Entrez votre mot de passe :</label>
    <input type="password" id="password" placeholder="Mot de passe">
    <hr/>

    <!-- Champ email -->
    <label for="email">Entrez votre adresse e-mail :</label>
    <input type="email" id="email" placeholder="exemple@domaine.com">
    <hr/>

    <!-- Champ nombre -->
    <label for="nombre">Entrez un nombre :</label>
    <input type="number" id="nombre" min="0" max="100" step="1">
    <hr/>

    <!-- Champ couleur -->
    <label for="color">Choisissez une couleur :</label>
    <input type="color" id="color">
    <hr/>

    <!-- Champ date -->
    <label for="date">Sélectionnez une date :</label>
    <input type="date" id="date">
    <hr/>

    <!-- Champ date et heure locale -->
    <label for="datetime">Sélectionnez une date et une heure locale :</label>
    <input type="datetime-local" id="datetime">
    <hr/>

    <!-- Champ heure -->
    <label for="time">Sélectionnez une heure :</label>
    <input type="time" id="time">
    <hr/>

    <!-- Champ semaine -->
    <label for="week">Sélectionnez une semaine :</label>
    <input type="week" id="week">
    <hr/>

    <!-- Champ mois -->
    <label for="month">Sélectionnez un mois :</label>
    <input type="month" id="month">
  </form>
</body>
</html>
```

---

### **Fichier 11 : test-range.html**
#### Ajoute un champ de sélection par plage (range).

```html
<!DOCTYPE html>
<html lang="fr">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>Test Input Plage</title>
</head>
<body>
  <h1>Test Inputs Texte, Mot de Passe, Email, Nombre, Couleur, Date, Heure, Semaine, Mo

is et Plage</h1>
  <form>
    <!-- Champ de texte classique -->
    <label for="texte">Entrez du texte :</label>
    <input type="text" id="texte" placeholder="Entrez du texte ici">
    <hr/>

    <!-- Champ mot de passe -->
    <label for="password">Entrez votre mot de passe :</label>
    <input type="password" id="password" placeholder="Mot de passe">
    <hr/>

    <!-- Champ email -->
    <label for="email">Entrez votre adresse e-mail :</label>
    <input type="email" id="email" placeholder="exemple@domaine.com">
    <hr/>

    <!-- Champ nombre -->
    <label for="nombre">Entrez un nombre :</label>
    <input type="number" id="nombre" min="0" max="100" step="1">
    <hr/>

    <!-- Champ couleur -->
    <label for="color">Choisissez une couleur :</label>
    <input type="color" id="color">
    <hr/>

    <!-- Champ date -->
    <label for="date">Sélectionnez une date :</label>
    <input type="date" id="date">
    <hr/>

    <!-- Champ date et heure locale -->
    <label for="datetime">Sélectionnez une date et une heure locale :</label>
    <input type="datetime-local" id="datetime">
    <hr/>

    <!-- Champ heure -->
    <label for="time">Sélectionnez une heure :</label>
    <input type="time" id="time">
    <hr/>

    <!-- Champ semaine -->
    <label for="week">Sélectionnez une semaine :</label>
    <input type="week" id="week">
    <hr/>

    <!-- Champ mois -->
    <label for="month">Sélectionnez un mois :</label>
    <input type="month" id="month">
    <hr/>

    <!-- Champ plage (range) -->
    <label for="range">Sélectionnez une valeur (plage) :</label>
    <input type="range" id="range" min="0" max="100">
  </form>
</body>
</html>
```

---

### **Instructions pour les étudiants :**
1. **Copiez chaque fichier HTML** dans votre éditeur de texte.
2. **Testez chaque fichier** en ouvrant le fichier dans votre navigateur.
3. Observez le comportement de chaque type d'input au fur et à mesure que vous progressez dans les fichiers.

Ces exemples couvrent tous les types d'input HTML pour une découverte complète des possibilités des formulaires.

# Annexe 01

- Voici une table détaillée avec **chaque type d'input en HTML**, accompagnée d'un exemple de code que vous pouvez **copier-coller** directement dans un fichier HTML pour tester les différentes fonctionnalités.

---

| **Type d'Input**      | **Exemple de Code à Copier**                                    | **Description**                                               |
|-----------------------|-----------------------------------------------------------------|---------------------------------------------------------------|
| **`text`**            | ```<input type="text" placeholder="Entrez du texte ici">```     | Champ de texte classique pour entrer du texte.                 |
| **`password`**        | ```<input type="password" placeholder="Mot de passe">```        | Champ pour entrer un mot de passe masqué (texte caché).        |
| **`email`**           | ```<input type="email" placeholder="Entrez votre email">```     | Champ pour entrer une adresse e-mail valide.                   |
| **`tel`**             | ```<input type="tel" placeholder="Numéro de téléphone">```      | Champ pour entrer un numéro de téléphone.                      |
| **`url`**             | ```<input type="url" placeholder="https://example.com">```      | Champ pour entrer une URL valide.                              |
| **`search`**          | ```<input type="search" placeholder="Rechercher...">```         | Champ de recherche.                                            |
| **`number`**          | ```<input type="number" min="0" max="10" step="1">```           | Champ pour entrer un nombre avec des flèches pour l'incrément. |
| **`range`**           | ```<input type="range" min="0" max="100">```                    | Curseur pour choisir une valeur dans une plage.                |
| **`color`**           | ```<input type="color">```                                      | Sélecteur de couleur.                                          |
| **`date`**            | ```<input type="date">```                                       | Sélecteur de date (calendrier).                                |
| **`month`**           | ```<input type="month">```                                      | Sélecteur de mois et d'année.                                  |
| **`week`**            | ```<input type="week">```                                       | Sélecteur de semaine.                                          |
| **`time`**            | ```<input type="time">```                                       | Sélecteur d'heure.                                             |
| **`datetime-local`**  | ```<input type="datetime-local">```                             | Sélecteur combiné de date et heure.                            |
| **`checkbox`**        | ```<input type="checkbox">```                                   | Case à cocher.                                                 |
| **`radio`**           | ```<input type="radio" name="choix">```                         | Bouton radio (choix unique dans un groupe).                    |
| **`file`**            | ```<input type="file">```                                       | Champ de téléchargement de fichier.                            |
| **`image`**           | ```<input type="image" src="image.jpg" alt="Image">```          | Bouton image pour soumettre un formulaire.                     |
| **`button`**          | ```<input type="button" value="Cliquez ici">```                 | Bouton générique.                                              |
| **`submit`**          | ```<input type="submit" value="Envoyer">```                     | Bouton pour soumettre un formulaire.                           |
| **`reset`**           | ```<input type="reset" value="Réinitialiser">```                | Bouton pour réinitialiser un formulaire.                       |
| **`hidden`**          | ```<input type="hidden" value="secret">```                      | Champ caché (non visible).                                     |


# Annexe 02

- Voici un tableau avec la description et le comportement attendu pour chaque type d'`<input>` en HTML. 
- Ces informations permettront à vos étudiants de comprendre ce qu'ils devraient observer lors des tests.

| **Type d'Input**      | **Description et Comportement Attendu**                                                                                              |
|-----------------------|---------------------------------------------------------------------------------------------------------------------------------------|
| **`text`**            | Champ de texte classique, accepte toute entrée de texte.                                                                              |
| **`password`**        | Texte masqué (remplacé par des points), utilisé pour saisir des mots de passe.                                                        |
| **`email`**           | Accepte les adresses e-mail sous format valide (contient un "@" et un "."). Peut activer une validation de formulaire.                 |
| **`tel`**             | Champ de saisie pour numéros de téléphone, sans format spécifique.                                                                     |
| **`url`**             | Accepte uniquement les URL valides. Peut activer une validation de formulaire (doit commencer par "http://" ou "https://").            |
| **`search`**          | Champ de recherche, souvent avec une icône de loupe, permet de saisir du texte pour une recherche.                                     |
| **`number`**          | Champ pour les nombres avec des flèches pour augmenter/diminuer la valeur. N'accepte que des chiffres.                                 |
| **`range`**           | Curseur pour sélectionner une valeur entre un minimum et un maximum (par défaut de 0 à 100).                                           |
| **`color`**           | Affiche un sélecteur de couleur pour choisir une couleur dans une palette.                                                            |
| **`date`**            | Sélecteur de date, affiche un calendrier pour choisir une date (JJ/MM/AAAA).                                                          |
| **`month`**           | Sélecteur de mois et d'année (MM/AAAA).                                                                                               |
| **`week`**            | Sélecteur de semaine (affiche le numéro de la semaine et l'année).                                                                    |
| **`time`**            | Sélecteur d'heure (HH:MM), permet de choisir une heure dans la journée.                                                               |
| **`datetime-local`**  | Sélecteur combiné de date et heure sans fuseau horaire (JJ/MM/AAAA et HH:MM).                                                         |
| **`checkbox`**        | Case à cocher, permet de faire des choix multiples, un ou plusieurs peuvent être cochés.                                               |
| **`radio`**           | Bouton radio, utilisé pour faire un choix unique dans un groupe de boutons radio.                                                     |
| **`file`**            | Champ pour télécharger un fichier depuis l'ordinateur.                                                                                 |
| **`image`**           | Bouton image, soumet un formulaire lorsqu'on clique sur l'image.                                                                      |
| **`button`**          | Bouton sans action, souvent utilisé avec JavaScript pour déclencher des événements personnalisés.                                      |
| **`submit`**          | Bouton pour soumettre un formulaire.                                                                                                  |
| **`reset`**           | Bouton pour réinitialiser un formulaire (remet les champs à leur valeur initiale).                                                    |
| **`hidden`**          | Champ caché, utilisé pour stocker des données dans un formulaire sans que l'utilisateur les voit.                                      |

---

### **Ce que vous devez observer :**

1. **`text`** : Peut saisir n'importe quel texte.
2. **`password`** : Le texte saisi est masqué.
3. **`email`** : Si vous entrez un texte sans "@" ou ".", le formulaire peut vous avertir que l'adresse e-mail n'est pas valide.
4. **`tel`** : Aucune validation stricte, mais utilisé pour entrer des numéros de téléphone.
5. **`url`** : Doit commencer par "http://" ou "https://". Sinon, un avertissement peut être affiché lors de la soumission du formulaire.
6. **`search`** : Similaire à `text` mais conçu pour les champs de recherche.
7. **`number`** : Utilisez les flèches pour augmenter/diminuer les valeurs, ou saisissez un nombre directement.
8. **`range`** : Glissez le curseur pour sélectionner une valeur entre un minimum et un maximum.
9. **`color`** : Un sélecteur de couleur apparaîtra pour choisir une couleur.
10. **`date`** : Un calendrier pop-up s'affichera pour sélectionner une date.
11. **`month`** : Sélectionnez un mois et une année.
12. **`week`** : Sélectionnez une semaine par numéro et année.
13. **`time`** : Sélectionnez une heure avec un format HH:MM.
14. **`datetime-local`** : Permet de sélectionner à la fois une date et une heure.
15. **`checkbox`** : Cochez ou décochez la case, plusieurs cases peuvent être cochées en même temps.
16. **`radio`** : Vous pouvez sélectionner une seule option parmi plusieurs.
17. **`file`** : Ouvre une fenêtre pour choisir un fichier sur l'ordinateur.
18. **`image`** : Agit comme un bouton de soumission mais avec une image à la place.
19. **`button`** : Bouton générique sans action par défaut.
20. **`submit`** : Soumet un formulaire.
21. **`reset`** : Réinitialise tous les champs du formulaire.
22. **`hidden`** : Non visible à l'écran mais stocke des données dans un formulaire.

