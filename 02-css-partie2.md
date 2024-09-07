
### Exercice 1 : Styliser du texte
1. Créez un fichier HTML et liez-le à un fichier CSS externe.
2. Dans le fichier CSS, appliquez les styles suivants :
   - Définissez la famille de police du texte sur Arial.
   - Changez la taille de la police de tous les paragraphes (`<p>`) à 16px.
   - Mettez en gras et en italique le premier titre (`<h1>`).
   - Changez la couleur du deuxième titre (`<h2>`) en `#ff0000`.

### Exercice 2 : Arrière-plan et images
1. Appliquez une couleur de fond bleu clair au corps de votre page HTML.
2. Ajoutez une image d'arrière-plan à la page qui ne se répète pas et qui est centrée horizontalement et verticalement.
3. Expérimentez avec différentes valeurs de `background-position` pour voir comment l'image change de position sur la page.

### Exercice 3 : Listes
1. Créez une liste non ordonnée avec au moins cinq éléments.
2. Stylisez la liste en utilisant différents types de puces (`disc`, `circle`, `square`) pour chaque liste.
3. Pour l'une des listes, utilisez une image personnalisée comme puce (`list-style-image`).

### Exercice 4 : Travailler avec des classes et des IDs
1. Créez une classe dans votre fichier CSS qui change la couleur de la police en bleu et met le texte en petites majuscules.
2. Appliquez cette classe à plusieurs éléments dans votre fichier HTML.
3. Créez un ID qui change la couleur de fond en gris clair et appliquez-le à un élément `<div>` spécifique dans votre HTML.

### Exercice 5 : Alignement du texte et espacement des lignes
1. Créez plusieurs paragraphes de texte dans votre fichier HTML.
2. Dans votre fichier CSS, définissez l'alignement du texte à `center` pour un paragraphe, `right` pour un autre, et `justify` pour un troisième.
3. Expérimentez avec différentes valeurs de `line-height` (par exemple, `1.5`, `2`) pour voir comment l'espacement entre les lignes change.


-----------


### Exercice 1 : Styliser du texte

**HTML :**
```html
<!DOCTYPE html>
<html lang="fr">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Exercice CSS 1</title>
    <link rel="stylesheet" href="style.css">
</head>
<body>
    <h1>Bienvenue sur ma page</h1>
    <h2>Ceci est un sous-titre</h2>
    <p>Voici un paragraphe de texte pour tester les styles CSS.</p>
</body>
</html>
```

**CSS (style.css) :**
```css
/* Changer la famille de police pour tout le texte */
body {
    font-family: Arial, sans-serif;
}

/* Appliquer le style au premier titre */
h1 {
    font-style: italic;
    font-weight: bold;
}

/* Changer la couleur du deuxième titre */
h2 {
    color: #ff0000;
}

/* Changer la taille de la police des paragraphes */
p {
    font-size: 16px;
}
```

---

### Exercice 2 : Arrière-plan et images

**HTML :**
```html
<!DOCTYPE html>
<html lang="fr">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Exercice CSS 2</title>
    <link rel="stylesheet" href="style.css">
</head>
<body>
    <h1>Exercice sur les arrière-plans</h1>
    <p>Voici un exemple avec un arrière-plan coloré et une image d'arrière-plan.</p>
</body>
</html>
```

**CSS (style.css) :**
```css
/* Couleur de fond pour le corps de la page */
body {
    background-color: #99ccff;
}

/* Ajouter une image d'arrière-plan sans répétition, centrée */
body {
    background-image: url('image.jpeg');
    background-repeat: no-repeat;
    background-position: center;
}
```

---

### Exercice 3 : Listes

**HTML :**
```html
<!DOCTYPE html>
<html lang="fr">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Exercice CSS 3</title>
    <link rel="stylesheet" href="style.css">
</head>
<body>
    <h1>Apparence des listes</h1>
    
    <ul class="liste-1">
        <li>Élément 1</li>
        <li>Élément 2</li>
        <li>Élément 3</li>
    </ul>

    <ul class="liste-2">
        <li>Item A</li>
        <li>Item B</li>
        <li>Item C</li>
    </ul>
</body>
</html>
```

**CSS (style.css) :**
```css
/* Liste avec des puces carrées */
.liste-1 {
    list-style-type: square;
}

/* Liste avec une image personnalisée */
.liste-2 {
    list-style-image: url('puce.gif');
}
```

---

### Exercice 4 : Travailler avec des classes et des IDs

**HTML :**
```html
<!DOCTYPE html>
<html lang="fr">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Exercice CSS 4</title>
    <link rel="stylesheet" href="style.css">
</head>
<body>
    <div class="zone-contenu">
        <p class="texte-bleu">Ceci est un texte bleu en petites majuscules.</p>
    </div>

    <div id="zone-speciale">
        <p>Texte dans une zone spéciale avec un fond gris clair.</p>
    </div>
</body>
</html>
```

**CSS (style.css) :**
```css
/* Classe qui change la couleur et le style du texte */
.texte-bleu {
    color: blue;
    font-variant: small-caps;
}

/* ID qui applique une couleur de fond */
#zone-speciale {
    background-color: lightgray;
    padding: 10px;
}
```

---

### Exercice 5 : Alignement du texte et espacement des lignes

**HTML :**
```html
<!DOCTYPE html>
<html lang="fr">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Exercice CSS 5</title>
    <link rel="stylesheet" href="style.css">
</head>
<body>
    <h1>Alignement et espacement des lignes</h1>

    <p class="center">Paragraphe centré.</p>
    <p class="right">Paragraphe aligné à droite.</p>
    <p class="justify">Paragraphe justifié sur toute la largeur de la page.</p>
</body>
</html>
```

**CSS (style.css) :**
```css
/* Alignement du texte */
.center {
    text-align: center;
}

.right {
    text-align: right;
}

.justify {
    text-align: justify;
}

/* Espacement entre les lignes */
p {
    line-height: 1.5;
}
```
