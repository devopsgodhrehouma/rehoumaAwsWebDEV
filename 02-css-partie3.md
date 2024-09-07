
### Exercice 1 : Bouton qui se déplace de droite à gauche

**Objectif** : Créer un bouton qui se déplace de droite à gauche lorsque la souris passe dessus.

**HTML :**
```html
<!DOCTYPE html>
<html lang="fr">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Bouton Animé 1</title>
    <link rel="stylesheet" href="style.css">
</head>
<body>
    <h1>Bouton Animé de Droite à Gauche</h1>
    <button class="btn-move">Passez la souris ici</button>
</body>
</html>
```

**CSS (style.css) :**
```css
/* Style de base du bouton */
.btn-move {
    background-color: #4CAF50;
    color: white;
    padding: 15px 32px;
    text-align: center;
    font-size: 16px;
    border: none;
    position: relative;
    transition: all 0.5s ease;
}

/* Animation de déplacement à gauche */
.btn-move:hover {
    transform: translateX(-100px);
}
```

### Exercice 2 : Bouton avec effet de zoom

**Objectif** : Créer un bouton qui agrandit légèrement sa taille lorsqu’on le survole avec la souris.

**HTML :**
```html
<!DOCTYPE html>
<html lang="fr">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Bouton avec Zoom</title>
    <link rel="stylesheet" href="style.css">
</head>
<body>
    <h1>Bouton avec Zoom</h1>
    <button class="btn-zoom">Passez la souris ici</button>
</body>
</html>
```

**CSS (style.css) :**
```css
/* Style de base du bouton */
.btn-zoom {
    background-color: #008CBA;
    color: white;
    padding: 15px 32px;
    text-align: center;
    font-size: 16px;
    border: none;
    transition: transform 0.3s ease;
}

/* Effet de zoom lors du survol */
.btn-zoom:hover {
    transform: scale(1.2);
}
```

### Exercice 3 : Bouton avec effet de clignotement

**Objectif** : Créer un bouton qui clignote (change de couleur) lorsqu’on le survole.

**HTML :**
```html
<!DOCTYPE html>
<html lang="fr">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Bouton avec Clignotement</title>
    <link rel="stylesheet" href="style.css">
</head>
<body>
    <h1>Bouton avec Effet de Clignotement</h1>
    <button class="btn-blink">Passez la souris ici</button>
</body>
</html>
```

**CSS (style.css) :**
```css
/* Style de base du bouton */
.btn-blink {
    background-color: #f44336;
    color: white;
    padding: 15px 32px;
    text-align: center;
    font-size: 16px;
    border: none;
    animation: blink-animation 1s infinite;
}

/* Animation de clignotement */
@keyframes blink-animation {
    0% { background-color: #f44336; }
    50% { background-color: #ffcccb; }
    100% { background-color: #f44336; }
}
```

### Exercice 4 : Bouton avec effet de rotation

**Objectif** : Créer un bouton qui tourne lorsqu’on le survole.

**HTML :**
```html
<!DOCTYPE html>
<html lang="fr">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Bouton avec Rotation</title>
    <link rel="stylesheet" href="style.css">
</head>
<body>
    <h1>Bouton avec Effet de Rotation</h1>
    <button class="btn-rotate">Passez la souris ici</button>
</body>
</html>
```

**CSS (style.css) :**
```css
/* Style de base du bouton */
.btn-rotate {
    background-color: #e7e7e7;
    color: black;
    padding: 15px 32px;
    text-align: center;
    font-size: 16px;
    border: none;
    transition: transform 0.5s ease;
}

/* Effet de rotation lors du survol */
.btn-rotate:hover {
    transform: rotate(360deg);
}
```

### Exercice 5 : Bouton avec changement de couleur progressif

**Objectif** : Créer un bouton dont la couleur change progressivement lorsqu’on le survole.

**HTML :**
```html
<!DOCTYPE html>
<html lang="fr">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Bouton avec Changement de Couleur Progressif</title>
    <link rel="stylesheet" href="style.css">
</head>
<body>
    <h1>Bouton avec Changement de Couleur</h1>
    <button class="btn-color">Passez la souris ici</button>
</body>
</html>
```

**CSS (style.css) :**
```css
/* Style de base du bouton */
.btn-color {
    background-color: #333;
    color: white;
    padding: 15px 32px;
    text-align: center;
    font-size: 16px;
    border: none;
    transition: background-color 2s ease;
}

/* Changement de couleur progressif */
.btn-color:hover {
    background-color: #ffcc00;
}
```
