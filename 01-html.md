### Introduction à HTML 

#### 1. **Qu'est-ce que HTML ?**
   - **HTML** (HyperText Markup Language) est le langage utilisé pour créer des pages web. Il permet de structurer le contenu comme des titres, du texte, des images, des liens, et bien plus.
   - **But** : Organiser et présenter le contenu sur une page web que les navigateurs peuvent lire et afficher correctement.

#### 2. **Structure de Base d'une Page HTML**
   Chaque page HTML suit une structure de base :
   ```html
   <!DOCTYPE html>
   <html>
     <head>
       <title>Ma Première Page Web</title>
     </head>
     <body>
       <h1>Bienvenue dans le monde du HTML</h1>
       <p>Ceci est mon tout premier paragraphe.</p>
     </body>
   </html>
   ```
   - **Explication** :
     - `<!DOCTYPE html>` : Indique que vous utilisez HTML5 (la version la plus récente).
     - `<html>` : Tout ce qui se trouve entre ces balises est le contenu de votre page web.
     - `<head>` : Contient des informations sur la page, comme le titre et les styles (non visibles directement par l'utilisateur).
     - `<title>` : Le titre de votre page. Il apparaît dans l'onglet du navigateur.
     - `<body>` : Tout le contenu visible de votre page (titres, paragraphes, images, etc.) est placé entre ces balises.

#### 3. **Les Balises HTML les Plus Importantes**
   **Les balises sont des mots-clés entourés de crochets angulaires (<>).**
   
   - **Titres** : Utilisez les balises de titre pour hiérarchiser votre contenu. Plus le chiffre est petit, plus le titre est important.
     ```html
     <h1>Mon Titre Principal</h1>
     <h2>Titre Secondaire</h2>
     <h3>Sous-titre</h3>
     ```
     - **Explication** : `<h1>` est le titre principal, tandis que `<h2>` et `<h3>` sont des sous-titres.

   - **Paragraphe** : Utilisez la balise `<p>` pour ajouter du texte.
     ```html
     <p>Ceci est un paragraphe de texte.</p>
     ```

   - **Liens** : Créez des liens vers d'autres pages ou sites web.
     ```html
     <a href="https://www.example.com">Cliquez ici pour visiter un site web</a>
     ```
     - **Explication** : Le texte entre les balises `<a>` est cliquable, et l'attribut `href` définit l'URL du lien.

   - **Images** : Affichez des images dans votre page.
     ```html
     <img src="image.jpg" alt="Description de l'image">
     ```
     - **Explication** :
       - `src` : L'emplacement du fichier image (ça peut être un fichier local ou une URL).
       - `alt` : Une description de l'image au cas où elle ne s'afficherait pas.

   - **Listes** :
     - Liste ordonnée (numérotée) :
       ```html
       <ol>
         <li>Premier élément</li>
         <li>Deuxième élément</li>
         <li>Troisième élément</li>
       </ol>
       ```
     - Liste non ordonnée (avec des puces) :
       ```html
       <ul>
         <li>Élément 1</li>
         <li>Élément 2</li>
         <li>Élément 3</li>
       </ul>
       ```

   - **Tableaux** : Créez des tableaux pour organiser les données.
     ```html
     <table>
       <tr>
         <th>Nom</th>
         <th>Âge</th>
       </tr>
       <tr>
         <td>Jean</td>
         <td>25</td>
       </tr>
       <tr>
         <td>Marie</td>
         <td>30</td>
       </tr>
     </table>
     ```
     - **Explication** :
       - `<table>` : Définit le tableau.
       - `<tr>` : Définit une ligne du tableau.
       - `<th>` : Définit l'en-tête d'une colonne (souvent en gras).
       - `<td>` : Définit une cellule de données dans le tableau.

#### 4. **Les Attributs HTML**
   - Les attributs fournissent des informations supplémentaires sur les balises.
   - Ils apparaissent dans la balise d'ouverture et contiennent des paires nom/valeur.
   - Exemple :
     ```html
     <a href="https://www.example.com" target="_blank">Visitez Example.com</a>
     ```
     - **`href`** : Définit l'URL du lien.
     - **`target="_blank"`** : Ouvre le lien dans un nouvel onglet.

#### 5. **Les Commentaires en HTML**
   - Les commentaires sont utilisés pour laisser des notes ou des explications dans le code. Ils ne sont pas affichés sur la page web.
     ```html
     <!-- Ceci est un commentaire -->
     ```

#### 6. **Formulaires HTML (simplifié pour débutants)**
   Les formulaires permettent aux utilisateurs de soumettre des informations comme leur nom ou adresse email.
   ```html
   <form>
     <label for="nom">Nom :</label>
     <input type="text" id="nom" name="nom">
     <input type="submit" value="Envoyer">
   </form>
   ```
   - **Explication** :
     - `<form>` : Définit le début et la fin du formulaire.
     - `<label>` : Fournit un label pour un champ de saisie.
     - `<input type="text">` : Champ où l'utilisateur peut entrer du texte.
     - `<input type="submit">` : Bouton pour soumettre le formulaire.

#### 7. **Hiérarchie et Lisibilité du Code**
   - **Indentation** : Utilisez des espaces ou des tabulations pour rendre votre code plus lisible.
   - Exemple :
     ```html
     <html>
       <head>
         <title>Page proprement indentée</title>
       </head>
       <body>
         <h1>Titre</h1>
         <p>Texte du paragraphe.</p>
       </body>
     </html>
     ```

#### 8. **Pratique**
   - **Exercice 1** : Créez une page avec un titre principal, deux sous-titres, et trois paragraphes de texte.
   - **Exercice 2** : Ajoutez une image et un lien vers un autre site web.
   - **Exercice 3** : Créez une liste numérotée et une liste avec des puces.
   - **Exercice 4** : Créez un formulaire simple où un utilisateur peut entrer son nom et appuyer sur "Envoyer".

#### 9. **Conclusion**
   - HTML est le squelette de chaque page web. Il permet de structurer l'information de manière ordonnée.
   - Au fur et à mesure, vous pouvez ajouter des styles avec **CSS** (Cascading Style Sheets) et des interactions avec **JavaScript** pour créer des pages interactives et dynamiques.

#### 10. **Ressources Complémentaires**
   - **Documentation officielle** : [MDN Web Docs - HTML](https://developer.mozilla.org/fr/docs/Web/HTML).


----
# Correction des exercices : 
----

Voici la correction progressive des quatre exercices proposés dans la section 8.

---

# **Exercice 1 : Créez une page avec un titre principal, deux sous-titres, et trois paragraphes de texte.**

#### Correction :
```html
<!DOCTYPE html>
<html>
<head>
  <title>Exercice 1 - Titre et Paragraphes</title>
</head>
<body>
  <!-- Titre principal -->
  <h1>Bienvenue dans le Monde du HTML</h1>

  <!-- Sous-titre 1 -->
  <h2>Introduction à HTML</h2>
  <!-- Premier paragraphe -->
  <p>HTML est le langage de base pour structurer le contenu des pages web.</p>

  <!-- Sous-titre 2 -->
  <h2>Comment HTML fonctionne</h2>
  <!-- Deuxième paragraphe -->
  <p>Les balises HTML permettent de décrire les différents éléments d'une page web.</p>

  <!-- Troisième paragraphe -->
  <p>Chaque balise a un rôle spécifique : les titres, les paragraphes, les images, etc.</p>
</body>
</html>
```

#### Explication :
- Un titre principal (`<h1>`).
- Deux sous-titres (`<h2>`).
- Trois paragraphes (`<p>`).

---

# **Exercice 2 : Ajoutez une image et un lien vers un autre site web.**

#### Correction :
```html
<!DOCTYPE html>
<html>
<head>
  <title>Exercice 2 - Image et Lien</title>
</head>
<body>
  <!-- Titre principal -->
  <h1>Ajouter une Image et un Lien</h1>

  <!-- Ajout d'une image depuis Unsplash -->
  <img src="https://source.unsplash.com/random/400x300" alt="Image aléatoire depuis Unsplash" width="400">

  <!-- Ajout d'un lien vers un autre site web -->
  <p>Pour en savoir plus, visitez <a href="https://www.pexels.com" target="_blank">ce site web</a>.</p>
</body>
</html>
```

#### Explication :
- **Image** : L'image provient de Unsplash. L'URL `https://source.unsplash.com/random/400x300` fournit une image aléatoire de 400x300 pixels.
- **Lien** : Le lien redirige vers **Pexels**, un site offrant des images gratuites.
- Utilisation de la balise `<img>` pour afficher une image avec l'attribut `src` pour la source de l'image et `alt` pour la description en cas de problème d'affichage.
- Un lien hypertexte est créé avec la balise `<a>` et l'attribut `href` pour rediriger vers un autre site web.

---

# **Exercice 3 : Créez une liste numérotée et une liste avec des puces.**

#### Correction :
```html
<!DOCTYPE html>
<html>
<head>
  <title>Exercice 3 - Listes Ordonnée et Non Ordonnée</title>
</head>
<body>
  <!-- Titre principal -->
  <h1>Les Listes en HTML</h1>

  <!-- Liste ordonnée (numérotée) -->
  <h2>Liste Ordonnée</h2>
  <ol>
    <li>Premier élément</li>
    <li>Deuxième élément</li>
    <li>Troisième élément</li>
  </ol>

  <!-- Liste non ordonnée (avec des puces) -->
  <h2>Liste Non Ordonnée</h2>
  <ul>
    <li>Élément A</li>
    <li>Élément B</li>
    <li>Élément C</li>
  </ul>
</body>
</html>
```

#### Explication :
- Une **liste ordonnée** est créée avec la balise `<ol>` (ordered list), et chaque élément est défini par `<li>` (list item).
- Une **liste non ordonnée** est créée avec la balise `<ul>` (unordered list), également avec des éléments `<li>`.

---

# **Exercice 4 : Créez un formulaire simple où un utilisateur peut entrer son nom et appuyer sur "Envoyer".**

#### Correction :
```html
<!DOCTYPE html>
<html>
<head>
  <title>Exercice 4 - Formulaire Simple</title>
</head>
<body>
  <!-- Titre principal -->
  <h1>Formulaire HTML Basique</h1>

  <!-- Création d'un formulaire -->
  <form>
    <!-- Champ pour entrer le nom -->
    <label for="nom">Nom :</label>
    <input type="text" id="nom" name="nom">

    <!-- Bouton pour soumettre le formulaire -->
    <input type="submit" value="Envoyer">
  </form>
</body>
</html>
```

#### Explication :
- Le formulaire est créé avec la balise `<form>`.
- Un champ de texte pour saisir le nom est défini avec `<input type="text">`.
- Le bouton d'envoi est défini avec `<input type="submit">`, permettant de soumettre le formulaire.

