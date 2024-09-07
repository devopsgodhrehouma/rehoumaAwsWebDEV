# **Cours CSS : Étape par Étape**

# Références : 
- https://drive.google.com/drive/folders/1Imd8TABaGPREFbZoz54YKFcQT3SjXZ-0?usp=sharing
  
### **1. Introduction : Créer votre première page avec du CSS**

#### Objectif : Appliquer du CSS basique à une page HTML.

#### Code HTML à copier :
```html
<!DOCTYPE html>
<html lang="fr">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>Mon premier style CSS</title>
  <style>
    h1 {
      color: blue;
      font-size: 30px;
    }
    p {
      color: green;
      font-size: 18px;
    }
  </style>
</head>
<body>
  <h1>Bienvenue sur ma page</h1>
  <p>Ceci est mon premier paragraphe stylisé avec CSS.</p>
  <p>Le CSS rend les pages web plus jolies et lisibles.</p>
</body>
</html>
```

### **Explication :**
- Le style CSS est directement intégré dans l'élément `<style>` de la page HTML.
- Le texte des titres `<h1>` est bleu et a une taille de 30px.
- Le texte des paragraphes `<p>` est vert et a une taille de 18px.

---

### **2. Appliquer du CSS à un fichier externe**

#### Objectif : Séparer le CSS dans un fichier externe.

#### Fichier HTML :
```html
<!DOCTYPE html>
<html lang="fr">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>CSS avec fichier externe</title>
  <link rel="stylesheet" href="style.css">
</head>
<body>
  <h1>Bienvenue avec CSS externe</h1>
  <p>Ceci est un paragraphe stylisé via un fichier CSS externe.</p>
</body>
</html>
```

#### Fichier CSS (nommé `style.css`) :
```css
h1 {
  color: red;
  font-size: 32px;
}

p {
  color: purple;
  font-size: 16px;
  font-style: italic;
}
```

### **Explication :**
- **HTML** : Le fichier HTML fait référence au fichier CSS externe avec `<link rel="stylesheet">`.
- **CSS** : Le fichier `style.css` contient les styles pour le titre et le paragraphe.

---

### **3. Utilisation des classes CSS**

#### Objectif : Appliquer différents styles à des éléments avec des classes.

#### Fichier HTML :
```html
<!DOCTYPE html>
<html lang="fr">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>Utilisation des classes CSS</title>
  <link rel="stylesheet" href="style.css">
</head>
<body>
  <h1 class="important">Titre Important</h1>
  <p class="highlight">Ceci est un paragraphe mis en évidence.</p>
  <p>Ceci est un autre paragraphe sans style particulier.</p>
</body>
</html>
```

#### Fichier CSS (nommé `style.css`) :
```css
.important {
  color: darkorange;
  font-size: 28px;
  text-align: center;
}

.highlight {
  background-color: yellow;
  font-weight: bold;
}
```

### **Explication :**
- La classe `.important` est utilisée pour styliser le titre avec du texte orange et centré.
- La classe `.highlight` est appliquée au paragraphe avec un fond jaune et du texte en gras.

---

### **4. Ajouter des bordures, marges et padding**

#### Objectif : Comprendre comment ajouter des bordures, des marges et du padding à des éléments.

#### Fichier HTML :
```html
<!DOCTYPE html>
<html lang="fr">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>Bordures et Marges</title>
  <link rel="stylesheet" href="style.css">
</head>
<body>
  <h1 class="bordered">Titre avec une bordure</h1>
  <p class="spaced">Paragraphe avec des marges et du padding.</p>
</body>
</html>
```

#### Fichier CSS (nommé `style.css`) :
```css
.bordered {
  border: 2px solid black;
  padding: 10px;
  margin: 20px;
}

.spaced {
  border: 1px dashed blue;
  padding: 15px;
  margin: 25px;
}
```

### **Explication :**
- **Bordures** : La classe `.bordered` a une bordure solide noire avec un padding de 10px et une marge de 20px.
- **Marges et Padding** : `.spaced` a une bordure bleue en pointillés, un padding de 15px et une marge de 25px.

---

### **5. Utilisation des polices et des tailles de texte**

#### Objectif : Changer la police et la taille du texte.

#### Fichier HTML :
```html
<!DOCTYPE html>
<html lang="fr">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>Styles de texte</title>
  <link rel="stylesheet" href="style.css">
</head>
<body>
  <h1 class="big-text">Titre en grand texte</h1>
  <p class="custom-font">Texte avec une police personnalisée.</p>
</body>
</html>
```

#### Fichier CSS (nommé `style.css`) :
```css
.big-text {
  font-size: 36px;
  font-family: Arial, sans-serif;
}

.custom-font {
  font-size: 20px;
  font-family: 'Courier New', monospace;
}
```

### **Explication :**
- **Font-size** : La classe `.big-text` applique une taille de 36px au texte du titre.
- **Font-family** : La classe `.custom-font` utilise la police 'Courier New' pour le paragraphe.

---

### **6. Flexbox pour l'agencement**

#### Objectif : Disposer des éléments en ligne avec Flexbox.

#### Fichier HTML :
```html
<!DOCTYPE html>
<html lang="fr">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>Flexbox Layout</title>
  <link rel="stylesheet" href="style.css">
</head>
<body>
  <div class="flex-container">
    <div class="flex-item">Élément 1</div>
    <div class="flex-item">Élément 2</div>
    <div class="flex-item">Élément 3</div>
  </div>
</body>
</html>
```

#### Fichier CSS (nommé `style.css`) :
```css
.flex-container {
  display: flex;
  justify-content: space-around;
  background-color: lightgrey;
  padding: 20px;
}

.flex-item {
  background-color: coral;
  padding: 20px;
  text-align: center;
  width: 100px;
  height: 100px;
}
```

### **Explication :**
- **Flexbox** : La classe `.flex-container` utilise `display: flex` pour aligner les éléments `.flex-item` horizontalement avec un espacement autour (`justify-content: space-around`).

---

### **7. Transitions et animations basiques**

#### Objectif : Ajouter des effets visuels lors des interactions.

#### Fichier HTML :
```html
<!DOCTYPE html>
<html lang="fr">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>Transitions et Animations</title>
  <link rel="stylesheet" href="style.css">
</head>
<body>
  <button class="btn">Survolez-moi</button>
</body>
</html>
```

#### Fichier CSS (nommé `style.css`) :
```css
.btn {
  background-color: lightblue;
  padding: 10px 20px;
  border: none;
  transition: background-color 0.3s ease;
}

.btn:hover {
  background-color: darkblue;
  color: white;
}
```

### **Explication :**
- **Transition** : Lors du survol du bouton `.btn`, la couleur d'arrière-plan change en douceur grâce à la propriété `transition`.


